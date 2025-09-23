---
description: >-
  Hàm được dùng để set giá trị vào asyncStorage. Lưu ý, các giá trị này sẽ bị
  xóa sau khi logout, không nên setStorageValue vào những key mà app đang sử
  dụng như accesstoken, language, url, ...
---

# setStorageValue

Hàm thường được sử dụng chung với hàm getStorageValue

**Return type:** Promise (void)

**Arguments:** (key, value)

* **key**: required, string, là key của giá trị muốn set vào asyncStorage
* **value**: required,  string, là giá trị muốn set vào asyncStorage

**Example:**

```javascript
p.setStorageValue("ma_vt_temp","ABCXYZ")
```
