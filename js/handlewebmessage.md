---
description: Web gửi message đến cho app để app xử lý thông qua script
---

# handleWebMessage

## 1. Giới thiệu

Khi lập trình viên web có nhu cầu gửi message đến cho app (ví dụ lệnh in, reload,...) thì app sẽ đọc được message này

## 2. Định nghĩa hàm

* **p**: [Builder](../class/builder.md), builder của màn hình
* **message:**  string, data nhận được khi web gọi

{% hint style="warning" %}
Lưu ý: Đối với các message đặc biệt thì hàm handleWebMessage sẽ không nhận được mà các message này được app xử lý.&#x20;

message này kiểu string (JSON.stringify) của payload sau:

JSON.stringify({\
action: "goback"|"replaceForm"|"showForm"|"replaceList"|"showList"|"alert",\
controller: String, (yêu cầu nếu mở form list)\
params:Object (yêu cầu nếu mở form, list), xem thêm trên tài liệu showForm\
alert: {title, message} (yêu cầu khi alert)\
})
{% endhint %}

## 3. Ví dụ

```javascript
handleWebMessage = ({p,message}) => {
    p.alert({message});
}
/* code web client
if (window.ReactNativeWebView && typeof window.ReactNativeWebView.postMessage === 'function') {
    const dataToSend = {
        action: "userLoggedIn",
        userInfo: {
            id: "123",
            name: "Nguyen Van A",
            email: "a@example.com"
        }
    };
    window.ReactNativeWebView.postMessage(JSON.stringify(dataToSend));
} else {
    // Log or handle fallback if not running in your WebView  console.log("Not in React Native WebView or postMessage not available.")
    ;
}*/
```

