---
description: Kiểm tra tình trạng bio trên thiết bị (version >= 1.3.15)
---

# checkDeviceBio

**Return type:** Promise <{supportType, isEnrollData} : {supportType: string, isEnrollData: boolean}>

* supportType: required, string, enum \["finger", "face", "both", "none"], cho biết thiết bị hỗ trợ loại chứng thực nào.
* isEnrollData: required, boolean, cho biết người dùng có đang sử dụng sinh trắc học trên thiết bị của họ không (không phải phạm vi trên app)

**Arguments:** ()

**Example:**

```javascript
p.checkDeviceBio().then(json=>{
    //do something with json
}); 
```
