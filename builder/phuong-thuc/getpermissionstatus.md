---
description: version ≥ 1.3.15. Hàm kiểm tra permission trên thiết bị
---

# getPermissionStatus

**Return type:** Promise \<boolean | undefined> , true nếu có quyền, false nếu không quyền, undefined xảy ra khi gặp lỗi trong quá trình check

**Arguments:** (key)

* **key:** required, string, là khóa, thuộc 1 trong các giá trị "GPS", "NOTIFICATION", "CAMERA"



**Example:**

```javascript
p.getPermissionStatus("GPS").then(val=>{
 
})

p.getPermissionStatus("NOTIFICATION").then(val=>{
 
})

p.getPermissionStatus("CAMERA").then(val=>{
 
})

 
```
