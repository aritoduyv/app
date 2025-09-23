---
description: >-
  Hàm được dùng để tô màu nền cho item trên list, chỉ sử dụng được tại phiên bản
  1.0.x
---

# setSelection deprecared

Vui lòng sử dụng hàm **currentRow** thay thế&#x20;

**Return type:** void

**Arguments:** ({nthRow, fieldKey}) // Chọn nthRow hoặc fieldKey

* **nthRow:** optional, number, số thứ tự dòng muốn tô màu (khoảng giá trị từ 0)
* **fieldKey:** optional, string, giá trị fieldKey muốn tô màu (lưu ý với list được khởi tạo với tham số modify: true thì giá trị fieldKey = md5(JSON.stringify(item) với item là một phần tử trong dataTable.obj))

Ví dụ:

```javascript
p.setSelection({nthRow:10});
p.setSelection({fieldKey:"ABC"});
```
