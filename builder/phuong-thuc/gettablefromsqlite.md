---
description: Truy vấn dữ liệu từ SQLite và trả về dưới dạng DataTable.
---

# getTableFromSQLite

Version ≥ 2.0.0

### Cú pháp <a href="#c-c3-ba-ph-c3-a1p" id="c-c3-ba-ph-c3-a1p"></a>

```javascript
const dataTable = await p.getTableFromSQLite(query, tableName);
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* query: Câu lệnh SQL SELECT
* tableName: Tên cho DataTable trả về

### Trả về <a href="#tr-e1-ba-a3-v-e1-bb-81" id="tr-e1-ba-a3-v-e1-bb-81"></a>

* Đối tượng DataTable với:
  * dataTable.name: tên bảng
  * dataTable.obj: mảng kết quả (array of objects)

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

```javascript
// Lấy tất cả users
const allUsers = await p.getTableFromSQLite(
  'SELECT * FROM users ORDER BY id',
  'all_users'
);

// Lấy users với điều kiện
const youngUsers = await p.getTableFromSQLite(
  'SELECT * FROM users WHERE age < 30',
  'young_users'
);

// Join nhiều bảng
const userOrders = await p.getTableFromSQLite(
  `SELECT u.name, o.amount FROM users u JOIN orders o ON u.id = o.user_id`,
  'user_orders'
);
```
