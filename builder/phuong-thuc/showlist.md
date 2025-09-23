---
description: >-
  Dùng để hiển thị màn hình list, thêm màn hình list vào stack (sau màn hình
  hiện tại)
---

# showList

**Return type:** void

**Arguments:** (controller, params)

* **controller**: required, string, tên controller của màn hình list (tương ứng với tên file.xml trong thư mục List)
* params: optional, json object, các giá trị mà list cần

**Example:**

```javascript
p.showList("abc"),
p.showList("abc", {title:"Danh mục abc"}), 
p.showList("abc",  {title:"Danh mục abc", memvars:{ma_kh:"XYZ"}})
```
