---
description: Hàm kiểm tra xem app đã cài sinh trắc học chưa, verson >= 1.2.25
---

# getBioLocalAuthenStatus

**Return type:** Promise (string), kiểu số: "1" là đang sử dụng, "0" là đã tắt, null là chưa từng dùng

**Arguments**: ()

**Example:**&#x20;

```javascript
p.getBioLocalAuthenStatus().then((is_use_bio)=>{
    //do something with is_use_bio
})
```
