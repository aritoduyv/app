---
description: Dùng để điều hướng về màn hình cứng của app
---

# navigate

Hàm p,navigate được dùng để đi đến màn hình (không phân biệt controller) gần nó nhất trên stack, nếu màn hình đó không tồn tại thì nó sẽ tạo ra màn hình mới. lưu ý, các màn hình bao gồm \[FormScreen, ListScreen, LookupScreen, FilterScreen, Dashboard, approval, delivery, hrm, hwshowroom, idathang, notification, sysmenu, login, changepassword, settingscreen, webscreen]&#x20;

**Return type**: void

&#x20;**Arguments:** (screenNam&#x65;**)**

* **screenName:** required, string, là màn hình cần điều hướng, thuộc một trong các màn hình sau \[FormScreen, ListScreen, LookupScreen, FilterScreen, Dashboard, approval, delivery, hrm, hwshowroom, idathang, notification, sysmenu, login, changepassword, settingscreen, webscreen]&#x20;

**Example:**

```javascript
p.navigate("hrm");
p.navigate("login");
```
