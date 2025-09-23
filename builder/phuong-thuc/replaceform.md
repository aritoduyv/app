---
description: >-
  Dùng để hiển thị màn hình form, và thực hiện xóa một số màn hình trước đó trên
  stack, parent của màn hình form được hiển thị là màn hình xuất hiện sau khi ấn
  back trên màn hình form
---

# replaceForm

**Return type:** void

**Arguments:** (controller, params, numberOfScreen)

* **controller:** required, string, tên controller của form&#x20;
* **params:** optional, object,  các thuộc tính mà màn hình form chấp nhận
* **numberOfScreen**: optional, number, mặc định là 1, là số lượng màn hình sẽ xóa tính từ màn hình hiện tại. = 0 có nghĩa là giống showForm, =1 có nghĩa là thay thế màn hình hiện tại bằng màn hình form, =2 thì xóa màn hình hiện tại và cha của nó và thay thế bằng màn hình form, ... =-1 có nghĩa là sau khi mở màn hình form lên, ấn back thì nó sẽ quay về màn hình dashboard

Ví dụ:

```javascript
p.replaceForm("dmvt",{memvars:memvars, action:"NEW"}, 5)
```
