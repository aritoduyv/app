# formAfterSave

## 1. Giới thiệu

Tại màn hình form với action là "NEW", sau khi người dùng bấm nút ok, app sẽ thực hiện gọi request code 'beforesave,insert,aftersave'. Sau khi thực hiện xong, app nhận được dataSet từ server trả về, hàm formAfterSave sẽ thao tác trên dataSet đó.

## 2. Định nghĩa hàm

Arguments: (dataSet, p)

* **dataSet:** Kiểu dataSet, là dataSet trả về từ server trong request code 'beforesave,insert,aftersave'
* **p:** Builder, là builder của màn hình hiện tại
