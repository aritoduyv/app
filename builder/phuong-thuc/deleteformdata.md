---
description: >-
  Hàm được dùng để gọi request code là delete đối với màn hình form. Nó cũng
  được gọi khi button với id là delete được bấm
---

# deleteFormData

**Return type:** void

**Arguments:** (callback)

* callback: optional, đây là function sẽ được thực thi sau khi nhận được data sau khi delete thành công, params của callback là dataSet.

**Example:**

```javascript
p.deleteFormData((dataSet)=>{
    //do somethign with dataSet
})
```
