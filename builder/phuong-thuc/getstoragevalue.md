---
description: >-
  Dùng để lấy giá trị trong async storage, async storage là dữ liệu được lưu
  trên điện thoại, nó sẽ không bị mất đi sau khi thoát app, kill app
---

# getStorageValue

**Return type:** Promise \<string | null> , null xảy ra khi key invalid

**Arguments:** (key)

* **key:** required, string, là khóa

{% hint style="info" %}
lưu ý từ bản 1.3.16 key phải thuộc một trong các giá trị cho phép sau

* access\_token: access token hiện tại của app (version ≥ 1.3.18)
* application: tên ứng dụng ví dụ hrm.com.arito (version ≥ 1.3.18)
* language: ngôn ngữ của máy, giá trị trả về là "v" hoặc "e"
* logsKey: logs của thiết bị
* message: danh sách message&#x20;
* url\_firebase: url cấu hình từ firebase
* secret\_firebase: secret cấu hình từ firebase
* logo\_firebase: logo từ firebase
* is\_register: Có cho phép đăng ký tài khoản mới?
* is\_forget\_password: Có cho phép đổi password
* latestScreenInfo: Màn hình controller xem gần nhất
* device\_id: id duy nhất của thiết bị (lưu ý giá trị này thay đổi nếu người dùng cài đặt lại app)
* deviceName: tên thiết bị
* brand: Thương hiệu thiết bị
* systemVersion: Phiên bản của thiết bị
* model: model của thiết bị
* platform: tên nền tảng, có giá trị là "android" hoặc "iOS"
* app\_version: phiên bản hiện tại của app cài từ store
* user\_info: Thông tin user\_info
* tabs: Thôn tin các tabs hiện có trên app
* debug\_mode: trạng thái lập trình viên
* notify\_sound: loại âm thanh thông báo
* notify\_time: Thời gian hiện cảnh báo, đơn vị giây
* user\_location: Lấy tọa độ cuối cùng được lưu bởi user
* fcmToken: chuỗi firebase cloud messaging, được dùng để gửi thông báo đến app
* persistent\_key: Key cố định, chỉ bị xóa khi xóa app (có từ bản 1.3.24)
{% endhint %}



**Example:**

```javascript
p.getStorageValue("accesstoken").then(val=>{
// Lấy được giá trị val với khóa là "accesstoken"
    alert(val);
})

p.getStorageValue("device_id").then((device_id)=>{
        alert(device_id)
})

p.getStorageValue("previousUser").then((previousUser)=>{
        alert(previousUser)
})
```

Tìm hiểu thêm tại [https://react-native-async-storage.github.io/async-storage/](https://react-native-async-storage.github.io/async-storage/)

Hàm liên quan setStorageValue (dùng để ghi dữ liệu và async storage)
