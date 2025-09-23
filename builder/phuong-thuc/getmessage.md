---
description: >-
  Dùng để lấy message của màn hình, nếu màn hình không có messageId nó sẽ tìm
  trong hệ thống, nếu không tìm thấy nó sẽ trả ra lại messageId
---

# getMessage

**Return type:** Promise (string)

**Arguments:** (messageId)

* **messageId:** required, string, là message id cần tìm, bắt đầu với ký tự đô la "$"

**Example:**

```javascript
let messageId = "$FieldNotBlank"
p.getMessage(messageId).then((message)=>{  
       //Thao tác với message
       alert(message)
}); 
```

Lưu ý, nếu muốn lấy nhanh message trên màn hình, ta còn có cách lấy từ options.

```javascript
let message = p.options.message[messageId];
alert(message)
```
