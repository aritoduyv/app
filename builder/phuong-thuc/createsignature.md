---
description: Hàm được dùng để mở màn hình để người dùng ký tên
---

# createSignature

**Return type**: void

**Argument** : ({callback, deleteFile, recentFileIds, title})&#x20;

* callback: function(fileId), fileId là id ảnh sau khi người dùng ký tên và upload ảnh thành công, nếu không khai thì hàm createSignature sẽ không có tác dụng
* deleteFile(fileId), fileId là id ảnh người dùng ấn giữ và muốn xóa ảnh này, nếu không khai thì việc xóa chỉ xóa trên giao diện
* recentFileIds:\[String], danh sách file id của ảnh thể hiện ảnh được dùng gần đây
* title: String, là tiêu đề của màn hình ký tên

**Example:**

```javascript
p.createSignature({
    callback:(fileId)=>{
        // do something with fileId
    },
    deleteFile: (fileId)=>{
        // ví dụ như xóa fileId này trên database
        p.request({requestCode,...})
    },
    recentFileIds:["abc","xyz"],
    title:"Tiêu đề"
})
```
