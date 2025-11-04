---
description: Lưu nhiều bảng (DataSet) vào SQLite cùng lúc.
---

# saveDataSetToSQLite

Version ≥ 2.0.0

### Cú pháp <a href="#c-c3-ba-ph-c3-a1p" id="c-c3-ba-ph-c3-a1p"></a>

```javascript
const result = await p.saveDataSetToSQLite(dataSet);
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* dataSet: Đối tượng DataSet chứa nhiều bảng
  * dataSet.obj: Mảng các DataTable

### Trả về <a href="#tr-e1-ba-a3-v-e1-bb-81" id="tr-e1-ba-a3-v-e1-bb-81"></a>

```javascript
{ ok: true, savedTables: ['users', 'orders'] }
// hoặc
{ ok: false, errors: [ { tableName: 'users', error }, { tableName: 'orders', error } ] }
```

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

```javascript
const users = [ { id: 1, name: 'Alice', age: 30 }, { id: 2, name: 'Bob', age: 25 } ];
const orders = [ { order_id: 101, user_id: 1, amount: 150.5 }, { order_id: 102, user_id: 2, amount: 200.0 } ];

const dataSet = new DataSet({ users, orders });
const result = await p.saveDataSetToSQLite(dataSet);
```
