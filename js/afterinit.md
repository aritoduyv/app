# afterInit

## 1. Giới thiệu

afterInit là hàm sẽ được gọi sau khi màn hình được xây xong. Được sử dụng trong tình huống dev muốn thay đổi gì đó sau khi đã có builder và data

## 2. Định nghĩa hàm

**Return type:** void

**Arguments:** (p, initType)

* **p:** required, Builder, là builder của màn hình
* **initType:** required, string, là trạng thái sau khi xây dựng xong init, có các loại initType sau:
  * **ACTIVE:** Là trạng thái sau khi back về từ màn hình sau
  * **FILTER:** Là trạng thái sau khi lọc filter từ màn hình lọc hoặc lọc nhanh
  * **INIT:** Là trạng thái mới mở màn hình lên
  * **RELOAD:** Là trạng thái sau khi reload màn hình
  * **SEARCH:** Là trạng thái sau khi search trên header
