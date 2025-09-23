---
description: Dùng để ẩn 1 hoặc nhiều buttons trên header
---

# setHiddenButton

**Return type:** void

**Arguments:** (field, status)

* **field:** required, string hoặc \[string], truyền vào tên trường hoặc danh sách button cần ẩn
* **status:**  required, boolean, có ẩn hay không

**Example:**

```javascript
p.setHiddenButton("ok", false)
p.setHiddenButton(["ok", "filter"], true)
```
