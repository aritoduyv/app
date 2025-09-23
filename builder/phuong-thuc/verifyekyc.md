---
description: Version>= 1.2.35 Được dùng chứng thực khuôn mặt với avatar của user đang login
---

# verifyEkyc

**Return type:** null

**Arguments:** ({verify\_type, callback, maxImageSize, isUseAI})

* **verify\_type:** required, string, enum \["face\_image", "face\_video", "phone\_number", "id\_cards"], phương thức chứng thực bằng khuôn mặt hay video
* **phone\_number**: String, bắt buộc nếu verify\_type là phone\_number

{% hint style="info" %}
verify\_type phone\_number có từ phiên bản 1.2.36
{% endhint %}

* **maxImageSize**: Number, optional, chiều dài tối đa của ảnh trước khi upload lên server (verify\_type = face\_image), mặc định 500

{% hint style="info" %}
maxImageSize có từ phiên bản 1.3.17, id\_cards có từ phiên bản 1.3.18
{% endhint %}

* &#x20; **callback**: required, function, hàm nhận kết quả verify\_status
  * verify\_status: &#x20;
    * Đối với verify\_type là phone\_number hoặc id card
      * is\_verified: Boolean, số điện thoại tryền lên có trùng với số đang ở trên ekyc hay không?
      * method: String, loại verify đã xác thực, enum \["phone\_number", "id\_card"]
    * Đối với verify\_type là image hoặc video
      * is\_same\_person: Boolean (Ảnh có phải là người đã đăng ký trên server ekyc)
        * true: Là cùng 1 người
        * false: là không phải
        * null: là không chứng thực được (do lỗi server ekyc, lỗi ảnh, video, mạng,...)
      * ratio: Number, tỉ lệ giống, thang đo từ 0 đến 100 (càng lớn có nghĩa là càng giống), null tức là không đo được
      * liveness: Boolean, đây có phải là người thật hay không, nếu server không chắc chắn thì server cũng sẽ trả về false
      * localUri: link ảnh người dùng đã dùng để verifyEkyc

{% hint style="info" %}
liveness, localUri chỉ có tại phiên bản >=1.3.17 và sử dụng **isUseAI** là **true**
{% endhint %}

* **isUseAI:** optional, Boolean, default false, có sử dụng AI trong quá trình chứng thực hay không?, Hiện tại phiên bản 1.3.17 chỉ đang áp dụng cho face\_image



**Example:**

```javascript
p.verifyEkyc({
    verify_type: "face_image", callback: (verify_status) => { 
        alert(JSON.stringify(verify_status))
    }
})

p.verifyEkyc({
    verify_type: "face_video", callback: (verify_status) => { 
        alert(JSON.stringify(verify_status))
    }
})

p.verifyEkyc({
    verify_type: "phone_number", phone_number: "0399446438", callback: (verify_status) => {
        alert(JSON.stringify(verify_status))
    }
})

p.verifyEkyc({
    verify_type: "id_cards", callback: (verify_status) => {
        alert(JSON.stringify(verify_status))
    }
}) 
```
