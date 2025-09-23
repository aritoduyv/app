---
description: >-
  version≥ 1.3.14 . Kiểm tra xem các phương thức sinh trắc học user đang dùng.
  vân tay hay khuôn mặt hay cả 2.
---

# getSupportedBioLocalAuthenTypes

**Return type:** Promise \<string | undefined>, enum : \["face", "finger", "both"], undefined xảy ra khi lỗi hoặc không xác định được

**Arguments:** ()&#x20;

**Example:**

```javascript
p.getSupportedBioLocalAuthenTypes().then(result=>{
 //do something with result
    alert(result);
})  
```
