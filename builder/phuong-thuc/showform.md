---
description: >-
  Dùng để hiển thị màn hình form, thêm màn hình form vào stack (sau màn hình
  hiện tại)
---

# showForm

**Return type:** void

**Arguments:** (controller, params)

* **controller:** required, string , tên controller của form, tương ứng với tên file trong thư mục form
* **params:** optional, json object, các giá trị mà màn hình form nhận được

**Example:**

```javascript
p.showForm("dmvt")
p.showForm("dmkh",{action:"NEW", memvars:{}, title:"Thêm mới khách hàng"})
```
