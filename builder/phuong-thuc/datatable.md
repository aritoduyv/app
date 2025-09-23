---
description: >-
  Hàm dùng để khởi tạo dataTable, builder mở hàm này để dev tương tác với class
  DataTable của app
---

# dataTable

**Return type**: class DataTable

**Arguments**: ({tableName,data})

* tableName: required, type string, là tên của dataTable
* data: required, type \[{}], chứa data là các item

**Example:**

```javascript
let data=[{ma_vt:"ABC", ten_vt:"vat tu ABC"},{ma_vt:"xyz", ten_vt:"vat tu XYZ"},]
let newDt = p.dataTable({tableName:"dmvt", data:data});
```

Có thể thay thế phương thức này bằng cách sử dụng DataTable

```javascript
let data=[{ma_vt:"ABC", ten_vt:"vat tu ABC"},{ma_vt:"xyz", ten_vt:"vat tu XYZ"},]
let newDt = new DataTable("dmvt", data);
```
