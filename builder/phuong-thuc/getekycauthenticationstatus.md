---
description: Dùng để check người dùng có data ekyc trên server không? version>= 1.3.17
---

# getEkycAuthenticationStatus

<mark style="color:red;">**Deprecated từ phiên bản 1.3.17**</mark>

**Return type:** Promise\<string>, "1" là đang sử dụng, "0" là không sử dụng, null là không rõ (lỗi trong quá trình check)

**Arguments**: ({verify\_type})

* **verify\_type:** required, string, enum \["face\_image", "face\_video", "phone\_number"], phương thức chứng thực bằng khuôn mặt hay video

**Example:**&#x20;

```javascript
p.getEkycAuthenticationStatus({verify_type:"face_image"}).then(result=>{
    console.log(result)
})
p.getEkycAuthenticationStatus({verify_type:"face_video"}).then(result=>{
    console.log(result)
})
p.getEkycAuthenticationStatus({verify_type:"phone_number"}).then(result=>{
    console.log(result)
})
```
