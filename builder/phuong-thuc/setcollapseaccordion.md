---
description: Dùng để đóng mở accordion
---

# setCollapseAccordion

**Return type:** void

**Arguments:** (fieldName, status)

* **fieldName:** required, string, tên accordion cần tương tác
* **status**: required, boolean, có đóng accordion hay không

**Example**

```javascript
//Đóng accordion detail lại
p.setCollapseAccordion("detail", true)
//Mở accordion detail ra
p.setCollapseAccordion("detail", false)
```
