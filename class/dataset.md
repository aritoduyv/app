# DataSet

Class DataSet được dùng để quản lý các [dataTable](datatable.md)&#x20;

Cách gọi: p.options.dataSet

Định nghĩa hàm:

## Thuộc tính

obj: kiểu \[DataTable], được dùng để chứa nhiều dataTable

## Phương thức

**add(dataTable)**

Được dùng để thêm 1 dataTable vào trong obj của DataSet

* Return type: void
* dataTable: Kiểu DataTable (required)

**get(tableIndex)**

Được dùng để lấy một dataTable từ dataSet

* Return type: void
* tableIndex: required, nếu tableIndex là kiểu số, thì hàm trả về dataTable thứ tableIndex. Nếu tableIndex là kiểu chuỗi, thì hàm trả về dataTable với tên là tableIndex

**val(tableIndex, nthRow, columnName, value)**

Hàm này được dùng để cập nhật giá trị của một cột columnName tại dòng thứ nthRow của dataTable tableIndex với giá trị mới là value

Thông thường thì tại class DataTable đã có hàm val rồi, nên hạn chế sử dụng hàm val của class DataSet.

* Return type: void
* tableIndex: required, nếu tableIndex là kiểu số, thì hàm trả về dataTable thứ tableIndex. Nếu tableIndex là kiểu chuỗi, thì hàm trả về dataTable với tên là tableIndex
* nthRow: required, kiểu số: là dòng thứ nthRow cần được cập nhật (với màn hình Form thì nthRow khai là 0)
* columnName: required, kiểu string, là tên cột cần cập nhật, ví dụ ("ma\_kh")
* value: required, kiểu any, là giá trị mới cần cập nhật
