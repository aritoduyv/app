---
description: Dùng để đánh dấu readOnly 1 hoặc nhiều trường dữ liệu
---

# setReadOnlyField

**Return type:** void

**Arguments:** (field, status)

* **field:** required, string hoặc \[string], truyền vào tên trường hoặc danh sách trường
* **status**: required, boolean, có readOnly hay không

**Example:**

```javascript
p.setReadOnlyField("ma_vt", false)
p.setReadOnlyField(["ma_vt", "ten_vt"], true)
```
