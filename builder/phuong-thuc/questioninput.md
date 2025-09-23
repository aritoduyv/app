---
description: >-
  Dùng để hiển thị câu hỏi đến người dùng app, người dùng app chọn 1 trong 2 lựa
  chọn (xác nhận hoặc hủy) và nhập  một văn bản vào ô nhập liệu
---

# questionInput

**Return type:** void

**Arguments:** ({ message,allowBlank,label, func})

* **message:** optional, string, là message cần hỏi người dùng, có thể dùng id để lấy message từ hệ thống
* **allowBlank:** optional, boolean (mặc định là false), là có bắt buộc nhập liệu hay không
* **label:** required, string, là place holder của ô nhập liệu
* **func:** optional, function(v, value), đây là call back sẽ được chạy sau khi người dùng ấn xác nhận (chỉ ấn được khi allowBlank==false hoặc allowBlank=true và đã nhập liệu) hoặc hủy, trong đó v là true hoặc false, value là giá trị đã nhập vào ô nhập liệu
* **type:** optional, enum \["text", "password", "number"], string (mặc định là text)

**Example:**

```javascript
p.questionInput({message:"Nêu lý do hủy đơn hàng", allowBlank:false, label:"Lý do", func:(v, value)=>{
    alert("Người dùng vừa bấm nút "+v);
    console.log("Giá trị đã nhập là:" + value)
}})
```
