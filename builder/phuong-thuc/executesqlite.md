# executeSQLite

Version ≥ 2.0.0. Thực thi câu lệnh SQL không trả về dữ liệu (INSERT, UPDATE, DELETE, CREATE, DROP).

### Cú pháp <a href="#c-c3-ba-ph-c3-a1p" id="c-c3-ba-ph-c3-a1p"></a>

```javascript
const rowsAffected = await builder.executeSQLite(query);
```

### Tham số <a href="#tham-s-e1-bb-91" id="tham-s-e1-bb-91"></a>

* query: Câu lệnh SQL cần thực thi

### Trả về <a href="#tr-e1-ba-a3-v-e1-bb-81" id="tr-e1-ba-a3-v-e1-bb-81"></a>

* Số nguyên >= 0: số dòng bị ảnh hưởng (thành công)
* -1: lỗi xảy ra

### Ví dụ <a href="#v-c3-a-d-d-e1-bb-a5" id="v-c3-a-d-d-e1-bb-a5"></a>

```javascript
// UPDATE
await builder.executeSQLite(`UPDATE users SET age = 31 WHERE id = 1`);

// DELETE
await builder.executeSQLite(`DELETE FROM users WHERE age > 50`);

// INSERT
await builder.executeSQLite(`INSERT INTO users (id, name, age) VALUES (3, 'Charlie', 35)`);

// CREATE INDEX
await builder.executeSQLite(`CREATE INDEX idx_users_age ON users(age)`);
```
