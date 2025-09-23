---
description: Hàm bắt sự kiện quét qrcode trên thiết bị PointMobile
---

# pointMobileScanQRCode

## 1. Giới thiệu

pointMobileScanQRCode là hàm sẽ được gọi khi người dùng quét qr code, chỉ gọi được trên màn hình Form hoặc List

## 2. Định nghĩa hàm

**Return type:** any

**Arguments:** (p, data, fullData)

* **p:** Builder, required, là builder của màn hình
* **data:** string, là kết quả quét được, data=fullData.replace(/\n$/, '')
* **fullData:** string,  là kết quả quét được

## 3. Ví dụ

```javascript
pointMobileScanQRCode = (p, data, fulldata)=>{
//do some thing
}
```
