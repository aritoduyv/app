---
description: Dùng để tạo biến với kiểu dữ liệu là class Memvars
---

# Memvars

**Return type:** class Memvars

**Arguments:** (data)

* **data**: required, là mảng 1 chiều, định dạng: \[{Name, Value}]

**Example:**

```javascript
let data = [{Name: "ma_vt", Value:"A"}]
let memvars = p.Memvars(data);
// thao tác với memvars
p.showForm("dmvt",{memvars: memvars}) //Lưu ý showForm, showList chấp nhận memvars với kiểu dữ liệu là class memvars hoặc đơn giản là json
```
