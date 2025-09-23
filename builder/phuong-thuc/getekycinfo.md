---
description: Dùng để check người dùng có data ekyc trên server không? version>= 1.3.17
---

# getEKycInfo

**Return type:** Promise\<null: object>, trong object cho biết số lượng phương thức chứng thực, loại chứng thực và trạng thái của người dùng hiện tại



**Arguments**: ()&#x20;

**Example:**&#x20;

```javascript
p.getEKycInfo({verify_type:"face_image"}).then(result=>{
    console.log(result)
}) 
```
