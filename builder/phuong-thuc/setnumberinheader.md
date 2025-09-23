---
description: Dùng để set số màu đỏ trên button của header
---

# setNumberInHeader

**Return type:** void

**Arguments:** (fieldName, val)

* **fieldName:** required, string hoặc \[string], id của button cần set
* **val:** required, string hoặc number, giá trị cần set

**Example:**&#x20;

```javascript
p.setNumberInHeader('cart', 15);

p.setNumberInHeader(['notify', "ok"], "5");
```
