# listFieldValueChange

## 1. Giới thiệu

Tại màn hình list, hàm listFieldValueChange được gọi khi giá trị của một trường thay đổi

## 2. Định nghĩa hàm

**Return type:** any &#x20;

**Arguments** (listname, nthRow, field, value, p)

* **listname:** string, là tên list chứa trường vừa thay đổi giá trị
* **nthRow:** number,  là dòng (phần tử) thứ nthRow,
* **field:** string, là tên trường vừa mới thay đổi data (ví dụ ma\_kh, sdt,...)
* **value:** any (string, number tùy theo loại AComponent), là giá trị mới mà field vừa thay đổi đến
* **p:** Builder, là builder của màn hình hiện tại
