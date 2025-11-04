---
description: >-
  Lấy dữ liệu danh mục (directory data) cho màn hình List với hỗ trợ phân trang.
  Phương thức này là một wrapper gọi GetDirDataList trong src/core/utils và tự
  động xử lý chế độ offline.
---

# getDirDataList

Version ≥ 2.0.0

### Chữ ký <a href="#ch-e1-bb-af-k-c3-bd" id="ch-e1-bb-af-k-c3-bd"></a>

```ts
builder.getDirDataList(
  controller: string,
  memvars?: object,
  pageIndex?: number /* mặc định: 1 */
): Promise<Response>
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* `controller` (string) — Tên controller của màn hình List. Ví dụ: `"khsale"`, `"idathang_list"`.
* `memvars` (object, optional) — Tập biến nhớ (tham số) lọc/tìm kiếm gửi lên server. Ví dụ: `{ ma_kh: "KH01", keyword: "Sữa" }`.
* `pageIndex` (number, optional) — Chỉ số trang, bắt đầu từ 1.

### Giá trị trả về <a href="#gi-c3-a1-tr-e1-bb-8b-tr-e1-ba-a3-v-e1-bb-81" id="gi-c3-a1-tr-e1-bb-8b-tr-e1-ba-a3-v-e1-bb-81"></a>

*   `Promise<Response>` với cấu trúc điển hình:

    ```json
    {
      "code": 200,
      "data": {
        "<controller>": [ { /* bản ghi trang hiện tại */ }, { /* ... */ } ]
      },
      "msg": "OK",
      "page": {
        "index": 1,
        "pageSize": 20,
        "total": 135
      }
    }
    ```

    Lưu ý: trường `page` phụ thuộc vào API phía server của bạn.

### Hành vi offline <a href="#h-c3-a0nh-vi-offline" id="h-c3-a0nh-vi-offline"></a>

* Logic offline được xử lý nội bộ trong `GetDirDataList` (utils). Khi không có mạng hoặc ở chế độ offline:
  * Hệ thống sẽ ưu tiên lấy dữ liệu cache/SQLite theo controller, filter, page nếu có.
  * Nếu chưa có cache phù hợp, phương thức trả về “schema-only” để UI vẫn hiển thị khung danh sách (cột/tiêu đề) dù chưa có dữ liệu.
* Khuyến nghị: dùng [cacheOfflineScreen](https://file+.vscode-resource.vscode-cdn.net/c%3A/Users/vuduy/Downloads/ARITO/arito_app_core_2/APP/AERP/docs/sqlite/cacheOfflineScreen.md) để chuẩn bị cấu hình.

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

Tải trang đầu tiên:

```ts
const resp = await builder.getDirDataList('idathang_list', { keyword: 'Sữa' }, 1);
const rows = resp?.data?.idathang_list ?? [];
```

Tải trang kế tiếp (load more):

```ts
let page = 1;
let allRows = [];

async function loadMore() {
  page += 1;
  const resp = await builder.getDirDataList('idathang_list', { keyword: 'Sữa' }, page);
  const rows = resp?.data?.idathang_list ?? [];
  allRows = allRows.concat(rows);
}
```

Fallback khi lỗi mạng:

```ts
try {
  const resp = await builder.getDirDataList('idathang_list', { ma_kh: 'KH01' }, 1);
  const rows = resp?.data?.idathang_list ?? [];
  // render
} catch (e) {
  builder.showOfflineScreen({ title: 'Không thể tải danh sách', controller: 'idathang_list' });
}
```

### Ghi chú & lỗi thường gặp <a href="#ghi-ch-c3-ba-l-e1-bb-97i-th-c6-b0-e1-bb-9dng-g-e1-ba-b7p" id="ghi-ch-c3-ba-l-e1-bb-97i-th-c6-b0-e1-bb-9dng-g-e1-ba-b7p"></a>

* Đảm bảo `pageIndex` ≥ 1; nếu null/undefined sẽ mặc định = 1.
* Bộ lọc `memvars` nên khớp với phía server để phân trang chính xác.
* Khi offline mà chưa cache, dữ liệu có thể rỗng; UI nên hỗ trợ trạng thái “Trống/Offline”.
