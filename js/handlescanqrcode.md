# handleScanQrCode

## 1. Giới thiệu

Khi người dùng quét qrcode từ thiết bị, app sẽ đọc được

## 2. Định nghĩa hàm

* **p**: [Builder](../class/builder.md), builder của màn hình
* **data:**  string, data nhận được khi quét

## 3. Ví dụ

```javascript
handleScanQrCode = ({p, data})=>{
    console.log(data);
	p.alert({title:"data nhận được là", message:data})
}
```
