# cacheOfflineScreen

Version≥ 2.0.0. Cache cấu hình màn hình vào SQLite để sử dụng offline (chỉ cache CONFIG, không cache data).

### Cú pháp <a href="#c-c3-ba-ph-c3-a1p" id="c-c3-ba-ph-c3-a1p"></a>

```javascript
const result = await p.cacheOfflineScreen(controller, folder);
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* controller (bắt buộc): Tên controller (vd: 'zc\_acheckbox', 'idathang')
* folder (tuỳ chọn, mặc định 'Form'): 'Form' | 'List' | 'Lookup'

### Trả về <a href="#tr-e1-ba-a3-v-e1-bb-81" id="tr-e1-ba-a3-v-e1-bb-81"></a>

```javascript
{
  ok: true,
  controller: 'zc_acheckbox',
  folder: 'Form',
  cachedAt: 1698765432000,
  configSize: 15234
}
// hoặc
{ ok: false, controller, folder, error: '...' }
```

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

```javascript
// Cache Form screen
await p.cacheOfflineScreen('zc_acheckbox', 'Form');

// Cache List screen
await p.cacheOfflineScreen('khachhang', 'List');

// Default là Form
await p.cacheOfflineScreen('idathang');
```

### Chi tiết kỹ thuật <a href="#chi-ti-e1-ba-bft-k-e1-bb-b9-thu-e1-ba-adt" id="chi-ti-e1-ba-bft-k-e1-bb-b9-thu-e1-ba-adt"></a>

* Bảng SQLite: `screen_config_cache`
  * controller TEXT
  * folder TEXT
  * payload TEXT (JSON cấu hình serialized)
  * updated\_at INTEGER (timestamp)
  * PRIMARY KEY (controller, folder)
* API: gọi `GetConfig(folder, controller)` để lấy struct
* Lưu trữ: serialize JSON và lưu vào SQLite

#### Đọc lại cached config <a href="#c4-91-e1-bb-8dc-l-e1-ba-a1i-cached-config" id="c4-91-e1-bb-8dc-l-e1-ba-a1i-cached-config"></a>

```javascript
const row = await p.sqliteGetOne(
  'SELECT payload, updated_at FROM screen_config_cache WHERE controller=? AND folder=?',
  ['zc_acheckbox', 'Form']
);

if (row) {
  const config = JSON.parse(row.payload);
}
```
