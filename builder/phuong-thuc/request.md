---
description: Được dùng để gọi request code lên trên server
---

# request

**Return type:** Promise(dataSet)

**Arguments:** ({controller,folder,requestCode,method,memvars,func,time,})

* **controller:** optional, string, mặc định là controller của màn hình hiện tại. Là màn hình sẽ nhận và xử lý request code
* **folder:** optional, string, mặc định là folder của màn hình hiện tại. Gồm các giá trị: "Form", "List" và "Lookup"
* **requestCode:** required, string, là request code
* **method:** optional, string, được dùng để gọi api bất kỳ thay vì mặc định là /DirRequest
* **memvars:** required, json, là biến memvars truyền lên cho server xử lý
* **func:** optional, function(dataSet), dùng để chạy sau khi có dataSet trả về từ request code
* **time:** optional, thời gian tối đa mà 1 request được thực thi (chưa làm)

**Example:**

```javascript
//Gọi request thông thường lên server
p.request({requestCode:"testcode",memvars:{ma_kh:"KH_ABC"}});
// Gọi request lên server và xử lý dataSet nhận được từ server
p.request({requestCode:"testcode",memvars:{ma_kh:"KH_ABC"}, func:(dataSet)=>{
    //do something with dataSet
}});
//Vì hàm này trả về dataSet nên ngoài dùng callback, có thể dùng promise (không xài được async await)
p.request({requestCode:"testcode",memvars:{ma_kh:"KH_ABC"}}).then((dataSet)=>{
    //do something with dataSet
});
//Hàm request này sẽ post tới url {{host}}/Signature thay vì {{host}}/DirRequest
p.request({method:"Signature",memvars:{ma_kh:"KH_ABC"}}).then((dataSet)=>{
    //do something with dataSet
})
```
