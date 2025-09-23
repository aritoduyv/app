# showNotification

**Return type:** void

**Arguments:** ({message, func, image})

* **message:** required, string, là nội dung cần thông báo
* **func:** optional, function(), là hàm được thực thi sau khi người dùng bấm thông báo
* **image:** optional, string, 1 trong 3 giá trị "APPLICATION","LOGS", hoặc "LINK", mặc định là trắng

**Example:**

```javascript
p.showNotification({message:"Mô phỏng bạn nhận được thông báo mới", image:"APPLICATION"})
```
