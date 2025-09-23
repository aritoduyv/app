---
description: >-
  Được dùng để tạo memvars của form, nhưng memvars này sẽ không có thông tin
  data của list đi kèm (trong tình huống có list nằm trong form)
---

# CreateFormMemvarsWithoutList

**Return type**: class Memvars

**Arguments:** ()

**Example:**

```javascript
let memvarsTemp = p.CreateFormMemvarsWithoutList();
alert(JSON.stringify(memvarsTemp))
```
