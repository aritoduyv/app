---
description: Version>= 1.2.25 Được dùng bật/tắt chứng thực sinh trắc học
---

# setBioLocalAuthenStatus

**Return type:** Promise \<result: number>, type number 1/0. 1 là bio đã enable, 0 là bio đã disable

**Arguments:** (is\_use\_bio)

* **is\_use\_bio:** required, string, &#x20;

**Example:**

```javascript
p.setBioLocalAuthenStatus(false).then(result=>{
// do something with result
})

p.setBioLocalAuthenStatus(true).then(result=>{
// do something with result
})
```
