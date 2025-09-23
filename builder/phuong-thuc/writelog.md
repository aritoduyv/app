---
description: Hàm ghi log vào async storage
---

# writeLog

Hàm liên quan: showLogs (được dùng để đọc logs đã ghi)

**Return type:** Promise string, key đã được dùng để lưu vào trong async storage

**Arguments:** (status, log)

* **status:** required, string, trạng thái của log, chấp nhận 1 trong 5 giá trị ("DEBUG","INFO", "WARN", "ERROR", "FATAL"), tương ứng với các nghĩa: debug, thông tin, cảnh báo, lỗi, lỗi chí mạng
* **log:** required, string, number hoặc json, khi lưu app sẽ convert nó thành string.

**Example:**

```javascript
p.writeLog("DEBUG","ABC")
```
