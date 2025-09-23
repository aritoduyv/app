# formFieldValueChange

## 1. Giới thiệu

Tại màn hình form, hàm formFieldValueChange được gọi khi giá trị của một trường thay đổi

## 2. Định nghĩa hàm

**Return type:** any (void, true tùy dev định nghĩa)

**Arguments** (field, value, p)&#x20;

* **field:** string, là tên trường vừa mới thay đổi data (ví dụ ma\_kh, sdt,...)
* **value:** any (string, number tùy theo loại AComponent), là giá trị mới mà field vừa thay đổi đến
* **p:** Builder, là builder của màn hình hiện tại

