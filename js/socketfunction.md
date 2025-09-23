# socketFunction

## 1. Giới thiệu

Khi mở app tại một màn hình form, thì app sẽ kết nối đến socket nếu như trên xml khai báo function socketFunction, hàm này sẽ chạy sau afterInit để có thể có biến p (builder). khi web gọi kết nối đến app thì app sẽ chạy hàm socketFunction này

## 2. Định nghĩa hàm

* **p**: [Builder](../class/builder.md), builder của màn hình
* **receiver\_id:** string, socketId của web gọi đến, app có thể dùng để phản hồi tìn nhắn tại [emitSocket](../builder/phuong-thuc/emitsocket.md)
* **webData:** any, optional, dữ liệu mà web đã truyền đến app, ví dụ như web muốn app thực hiện lệnh gì đó hoặc đơn giản không truyền gì

## 3. Ví dụ

```javascript
socketFunction = (p, receiver_id, webData) => {
  alert(JSON.stringify(webData));
  console.log(receiver_id);
  p.emitSocket(receiver_id, "Tôi đã nhận được thông tin lúc " + Date.now());
};

```

Xem thêm hàm emitSocket tại [emitSocket](../builder/phuong-thuc/emitsocket.md)

