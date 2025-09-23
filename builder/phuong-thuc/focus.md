---
description: >-
  Hàm được dùng để làm nổi bật (highlight) field trên form, sử dụng tại phiên
  bản 1.1.8 trở đi
---

# focus

**p.focus.set(field, status): dùng để làm nổi bật field**

* **Return type**: void
* **field:** required, string hoặc \[string], là danh sách field cần làm nổi bật
* **status:** required, boolean, nếu là true thì thì làm nổi bật, ngược lại là không làm nổi bật

**p.focus.clear():** **dùng để xóa toàn bộ highlight hiện có.**

* **Return type:** void

**Example:**

```javascript
//Tô màu field ma_vt
p.focus.set("ma_vt", true);
//Tô màu nhiều field
p.focus.set(["ten_kh", "ma_kh"],true);
//Không tô màu ma_vt nữa
p.focus.set("ma_vt", false);
//Không tô màu bất kỳ field nào
p.focus.clear()
```
