---
description: >-
  Sử dụng để cập nhật lại data cho list ở màn hình list view hoặc list trong
  form (áp dụng từ 1.1.12)
---

# updateList

**Return type:** void

**Arguments:** (dataTable, listname)

* **dataTable: required** kiểu dataTable, là dataTable cần cập nhật vào list
* **listname:** optional, kiểu string, là tên list cần cập nhật, nếu không truyền (thường là list view) thì sẽ cập nhật vào list đầu tiên

```
p.updateList(newDataTable)//ví dụ cập nhật lại thông tin trên list view với dataTable mới
p.updateList(newDataTable, "detail")
```
