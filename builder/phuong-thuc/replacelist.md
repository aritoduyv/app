---
description: >-
  Dùng để hiển thị màn hình list, và thực hiện xóa một số màn hình trước đó trên
  stack
---

# replaceList

**Return type:** void

**Arguments:** (controller, params, numberOfScreen)

* **controller:** required, string, tên controller của màn hình list (tương ứng với tên file.xml trong thư mục List)
* **params:** optional, object, là các tham số mà màn hình list chấp nhận
* **numberOfScreen**: optional, number, mặc định là 1. Nghĩa là số màn hình tính từ màn hình hiện tại sẽ bị xóa trên stack trước khi thêm màn hình list vào sau cùng. giải thích giống replaceForm

Example

```javascript
p.replaceList("abc")// thay thế màn hình hiện tại bằng màn hình abc
p.replaceList("abc", {title:"Danh mục abc"})// thay thế màn hình hiện tại bằng màn hình abc, và set lại title cho nó là "Danh mục abc"
p.replaceList("abc",  {title:"Danh mục abc", memvars:{ma_kh:"XYZ"}}, 2)// Mở màn hình abc, truyền title, memvars và xóa 2 màn hình trên stack (màn hình hiện tại và cha của màn hình hiện tại) 
```
