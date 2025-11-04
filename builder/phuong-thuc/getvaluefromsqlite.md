---
description: Lấy một giá trị đơn từ câu truy vấn (cột đầu tiên của dòng đầu tiên).
---

# getValueFromSQLite

Version ≥ 2.0.0

### Cú pháp <a href="#c-c3-ba-ph-c3-a1p" id="c-c3-ba-ph-c3-a1p"></a>

```javascript
const value = await builder.getValueFromSQLite(query);
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* query: Câu lệnh SQL SELECT

### Trả về <a href="#tr-e1-ba-a3-v-e1-bb-81" id="tr-e1-ba-a3-v-e1-bb-81"></a>

* Giá trị của cột đầu tiên trong dòng đầu tiên, hoặc `null` nếu không có kết quả.

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

```javascript
// Đếm số lượng
const totalUsers = await builder.getValueFromSQLite(`SELECT COUNT(*) FROM users`);

// Lấy giá trị MAX
const maxAge = await builder.getValueFromSQLite(`SELECT MAX(age) FROM users`);

// Lấy tên user đầu tiên
const firstName = await builder.getValueFromSQLite(`SELECT name FROM users ORDER BY id LIMIT 1`);

// Tính tổng
const totalAmount = await builder.getValueFromSQLite(`SELECT SUM(amount) FROM orders WHERE user_id = 1`);
```
