---
description: >-
  Dùng để hiển thị câu hỏi đến người dùng app, người dùng app chọn 1 trong 2 lựa
  chọn (xác nhận hoặc hủy)
---

# question

**Return type:** void

**Arguments:** ({message,func})

* **message**: optional, string, là thông báo muốn alert lên cho người dùng, message có thể bắt đầu với $ để dùng message hệ thống.
* **func:** optional, function(v), callback sau khi người dùng ấn nút, v có 2 giá trị là true hoặc false, tương ứng với người dùng chọn nút xác nhận hoặc hủy

**Example:**

```javascript
p.question({message:"Thông báo 1", func:(v)=>{
    if(v){// người dùng ấn nút xác nhận
    
    }else{//Người dùng ấn nút hủy
    
    }
}})
```
