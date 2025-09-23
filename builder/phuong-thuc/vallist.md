# valList

**Return type:** any (dựa theo giá trị của trường)

**Arguments:** (listName, nthRow, fieldName, value)

* **listName:** required, string hoặc number, tên list hoặc số thứ tự list trên dataset cần thao tác
* **nthRow:** required, number, dòng dữ liệu cần thao tác
* **fieldName:** required, string, tên trường cần thao tác
* **value:** any, nếu có giá trị thì app sẽ gán giá trị đó cho trường, ngược lại là  sẽ trả ra giá trị của trường

**Example:**

```javascript
p.valList(0, 10, "ma_kh","ABC")
```
