---
description: Lưu một bảng dữ liệu (DataTable) vào SQLite.
---

# saveTableToSQLite

Version ≥ 2.0.0&#x20;

### Cú pháp <a href="#c-c3-ba-ph-c3-a1p" id="c-c3-ba-ph-c3-a1p"></a>

```javascript
const result = await p.saveTableToSQLite(dataTable);
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* dataTable: Đối tượng DataTable chứa dữ liệu cần lưu
  * dataTable.name: Tên bảng
  * dataTable.obj: Mảng các đối tượng (dữ liệu)

### Trả về <a href="#tr-e1-ba-a3-v-e1-bb-81" id="tr-e1-ba-a3-v-e1-bb-81"></a>

```javascript
{ ok: true, tableName: 'test_users' }
// hoặc
{ ok: false, error: Error }
```

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

```javascript
const users = [
  { id: 1, name: 'Alice', age: 30, score: 95.5 },
  { id: 2, name: 'Bob', age: 25, score: 88.0 },
];

const dataTable = new DataTable('users', users);
const result = await p.saveTableToSQLite(dataTable);
```

### Chi tiết kỹ thuật <a href="#chi-ti-e1-ba-bft-k-e1-bb-b9-thu-e1-ba-adt" id="chi-ti-e1-ba-bft-k-e1-bb-b9-thu-e1-ba-adt"></a>

* Tự động phát hiện kiểu dữ liệu: NUMERIC/TEXT
* Tự động thêm `_row_id INTEGER PRIMARY KEY AUTOINCREMENT`
* Chiến lược: DROP IF EXISTS → CREATE TABLE → INSERT batch
* Null-safe: xử lý giá trị null đúng cách
