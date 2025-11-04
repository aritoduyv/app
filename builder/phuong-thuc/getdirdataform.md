---
description: >-
  Lấy dữ liệu danh mục (directory data) cho màn hình Form. Phương thức này là
  một wrapper gọi GetDirDataForm trong src/core/utils và đã được thiết kế để tự
  động xử lý chế độ offline.
---

# getDirDataForm

Version ≥ 2.0.0

### Chữ ký <a href="#ch-e1-bb-af-k-c3-bd" id="ch-e1-bb-af-k-c3-bd"></a>

```ts
p.getDirDataForm(controller: string, memvars?: object): Promise<Response>
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* `controller` (string) — Tên controller của màn hình Form. Ví dụ: `"idathang"`, `"zc_acheckbox"`.
* `memvars` (object, optional) — Tập biến nhớ (tham số) gửi lên server. Ví dụ: `{ ma_kh: "KH01", tu_ngay: "2025-01-01" }`.

### Giá trị trả về <a href="#gi-c3-a1-tr-e1-bb-8b-tr-e1-ba-a3-v-e1-bb-81" id="gi-c3-a1-tr-e1-bb-8b-tr-e1-ba-a3-v-e1-bb-81"></a>

*   `Promise<Response>` với cấu trúc điển hình:

    ```json
    {
      "code": 200,
      "data": {
        "<controller>": [ { /* bản ghi */ }, { /* ... */ } ]
      },
      "msg": "OK"
    }
    ```

    Trong đó `data[controller]` là mảng các bản ghi của danh mục.

### Hành vi offline <a href="#h-c3-a0nh-vi-offline" id="h-c3-a0nh-vi-offline"></a>

* Logic offline được xử lý bên trong `GetDirDataForm` (utils). Khi thiết bị không có mạng hoặc đang bật chế độ offline:
  * Hệ thống sẽ cố gắng lấy dữ liệu đã cache (SQLite) nếu có.
  * Nếu không có dữ liệu cache phù hợp, phương thức sẽ trả về cấu trúc “schema-only” (khung cột, có thể rỗng phần dữ liệu) để UI vẫn dựng được form và trường.
* Khuyến nghị:
  * Trước khi dùng offline, hãy chạy [cacheOfflineScreen](https://file+.vscode-resource.vscode-cdn.net/c%3A/Users/vuduy/Downloads/ARITO/arito_app_core_2/APP/AERP/docs/sqlite/cacheOfflineScreen.md) cho các màn hình quan trọng.

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

<pre class="language-ts"><code class="lang-ts">// Lấy dữ liệu danh mục cho form Đặt Hàng
const resp = await p.getDirDataForm('idathang', { ma_kh: 'KH01' });
const rows = resp?.data<a data-footnote-ref href="#user-content-fn-1">?</a>.idathang ?? [];

// Sử dụng rows để bind vào các control trong form
</code></pre>

Ví dụ kèm fallback offline rõ ràng:

```ts
let rows = [];
try {
  const resp = await builder.getDirDataForm('idathang', { ma_kh: 'KH01' });
  rows = resp?.data?.idathang ?? [];
} catch (e) {
  // Nếu muốn, mở màn hình offline gợi ý hành động cho người dùng
  builder.showOfflineScreen({ title: 'Không thể tải dữ liệu form', controller: 'idathang' });
}
```

### Ghi chú & lỗi thường gặp <a href="#ghi-ch-c3-ba-l-e1-bb-97i-th-c6-b0-e1-bb-9dng-g-e1-ba-b7p" id="ghi-ch-c3-ba-l-e1-bb-97i-th-c6-b0-e1-bb-9dng-g-e1-ba-b7p"></a>

* Đảm bảo các `memvars` cần thiết đã được truyền (ví dụ mã khách hàng, khoảng thời gian…).
* Nếu `resp.code !== 200`, hãy đọc `resp.msg` để hiển thị thông báo phù hợp.
* Khi offline mà chưa từng cache, dữ liệu có thể rỗng; bạn vẫn nên dựng form dựa trên schema/cấu hình để người dùng nhìn thấy giao diện.

[^1]: 
