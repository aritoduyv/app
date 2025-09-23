---
description: Dùng để hiển thị thông báo đến người dùng app
---

# alert

**Return type:** void

**Arguments**: ({title, message, icon,func})

* message: required, type string, là message id (sử dụng message của hệ thống hoặc màn hình) hoặc là message thông thường. Tại phiên bản ≥  1.3.21 không còn dùng được $message, truyền gì thì alert đó
* icon (deprecated ≥ version 1.3.21): optional, type string, "INFORMATION" hoặc "WARINING", nếu không khai thì không có icon
* func: optional, type function, là callback sau khi người dùng ấn ok

**Example:**

```javascript
p.alert({title:"Thông báo", message:"Thông báo 1", icon:"INFORMATION"})
```

```javascript
p.alert({message:"$message", icon:"WARNING"})
```

```javascript
p.alert({message:"$abc"})
```

```javascript
p.alert({message:"$abc", func:()=>{
    //do something 
}})
```
