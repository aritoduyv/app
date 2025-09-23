---
description: Hàm dùng để alert, có thể gọi function sau khi alert
---

# AAlert

**Return type:** void

**Arguments:** ({message, callback})

* **message:** required, chuỗi cần alert
* **callback:** function được thực hiện khi bấm nút ok

**Example:**

```javascript
AAlert({
    message:"Bạn có đơn từ cần duyệt", 
    callback:()=>{
        p.showForm("idontu")
    }
})

AAlert({
    message:"Bạn không có quyền truy cập" 
})
```
