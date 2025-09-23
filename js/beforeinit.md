# beforeInit

## 1. Giới thiệu

Hàm này được chạy trước khi màn hình của app được bắt đầu xây dựng, hàm này sẽ tác động vào struct, dataSet, và option&#x20;

## 2. Định nghĩa hàm

**Return type:** void

**Arguments:** (responseStruct, dataSet, options)

* **responseStruct:** Là struct json app nhận được từ server, nó là bản thiết kế và có thể chỉnh sửa trước khi app bắt đầu xây dựng màn hình
* **dataSet:** là dataSet&#x20;
* **options:** là các options sẽ được gắn vào builder sau khi builder được khởi tạo (xem thêm tại [thuộc tính của builder](../builder/thuoc-tinh.md))

