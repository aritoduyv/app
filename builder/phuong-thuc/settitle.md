---
description: Dùng để set lại giá trị title trên header
---

# setTitle

**Return type:** void

**Arguments:** (title)

* **title:** required,string hoặc object {title}, là tiêu đề, có thể dùng messageid

**Example:**

```javascript
p.setTitle("Tiêu đề mới")
p.setTitle({title:"Tiêu đề mới"})
p.setTitle("$title")
p.setTitle({title:"$title"})
```
