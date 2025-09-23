# List

## 1. Giới thiệu

List được dùng để hiển thị nhiều item có chung cấu trúc

## 2. Luồng

Màn hình List được mở ra bằng hàm [**showList** ](../builder/phuong-thuc/showlist.md)hoặc [**replaceList**](../builder/phuong-thuc/replacelist.md)

Các tham số màn hình list nhận khi showList và replaceList

* **action:** strin&#x67;**,** optional, mặc định là NEW, lưu ý có thể dùng "EDIT" thì mới chỉnh sửa được thông tin item trên List như [AListItemDatHang ](../alistitem/alistitemdathang.md)
* **allowMultiSelection:** Boolean, optional, mặc định false, có cho phép chọn nhiều hay không, params này hoạt động như sau: click vào item chưa được chọn để chọn và nó chỉ bị mất focus khi bị ấn lại vào item một lần nữa
* **controller**: string, required, tự động sinh ra khi dùng hàm showList hoặc replaceList
* **data:** [DataTable](../class/datatable.md), optional, nếu có thì list sẽ dùng data này làm data chính mà không phải đi lấy từ server
* **memvars:** Memvars hoặc json, optional, mặc định là {}, list sẽ dùng memvars này + pageIndex là 1 để gọi request lên server
* **modify:** boolean, optional, mặc định là false, có cho phép update thông tin trên list hay không
* **options:** object, optional, khởi tạo giá trị cho options của list
* **parent:** [BUILDER](../class/builder.md), optional, tự động sinh ra khi dùng hàm showList hoặc replaceList
* **title:** string, optional, nếu truyền thì list sẽ dùng title này ưu tiên hơn là title từ xml

## 3. Phân loại list

Gồm 2 loại: mapList và flatlist

Đặc điểm của các loại:

* **MapList**: hiển thị danh sách chậm,  xử lý sự kiện nhanh, tốn bộ nhớ (ram) của điện thoại
* **FlatList**: hiển thị danh sách nhanh, xử lý sự kiện chậm, tối ưu bộ nhớ

## 4. Phân loại item

item trong list được chia làm 2 loại: theo mẫu (template [AListItem](../alistitem/)) hoặc Custom

Đặc điểm của các loại:

* **AListItem:** Xử lý sự kiện nhanh, load nhanh, cái gì cũng nhanh, nhưng mẫu này phải có sẵn trên app để sử dụng (phải build)
* **Custom:** Được tạo ra giống như xây form, load sẽ chậm hơn, khó xử lý sự kiện hơn

## 5. Lưu ý

