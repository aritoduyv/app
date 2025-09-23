---
description: Chứng thực với sinh trắc học, phiên bản >= 1.3.14
---

# authenticateWithBiometricAuth

**Return type:  Promise \<boolean | undefined>**&#x20;

App sẽ tiến hành chứng thực sinh trắc học dựa trên thông tin sinh trắc trên thiết bị (ưu tiên khuôn mặt hơn vân tay). App trả về true/false nếu chứng thực thành công/thất bại. App trả về undefined nếu gặp lỗi trong quá trình chứng thực

**Arguments:** ()&#x20;

**Example:**

```javascript
 p.authenticateWithBiometricAuth().then(result=>{
 // do some thing with result
 });
```

