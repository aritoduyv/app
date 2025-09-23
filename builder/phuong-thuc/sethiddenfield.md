---
description: Dùng để ẩn 1 hoặc nhiều trường dữ liệu
---

# setHiddenField

**Return type:** void

**Arguments:** (field, status)

* **field:** required, string hoặc \[string], truyền vào tên trường hoặc danh sách trường cần ẩn
* **status**: required, boolean, có ẩn hay không

**Example:**

```javascript
p.setHiddenField("ma_vt", false)
p.setHiddenField(["ma_vt", "ten_vt"], true)
```
