---
description: >-
  Được dùng để tô màu back ground cho dòng thứ nthRow (nthRow bắt đầu từ 0) trên
  list (set) và Dùng để lấy dòng thứ nthRow được tô màu (get)
---

# currentRow

**Return type**: void

**Arguments:**&#x20;

* get()
* set(params, status):&#x20;
  * params: required,  kiểu số hoặc \[Số], là số thứ tự dòng muốn tô màu hoặc xóa màu
  * status: required, boolean, nếu là true thì là tô màu nền, nếu là false thì là không tô màu nền

**Example:**

```javascript
//Tô màu background dòng thứ 15 
p.currentRow.set(15, true);
//Tô màu background dòng 12, 15, 16
p.currentRow.set([12,15,16], true);
//Lấy danh sách dòng đang được tô màu
let list arrNthRow = p.currentRow.get();
```
