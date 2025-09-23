# DataTable

Là class chứa thông tin dữ liệu của màn hình

Cách gọi: p.options.data (để lấy DataTable chính của màn hình (ví dụ màn hình form chứa list, thì sẽ có rất nhiều dataTable, nhưng p.options.data chỉ lấy dataTable của Form)). Hoặc [**p.options.dataSet.get(tableIndex)**](dataset.md#phuong-thuc)

Định nghĩa class

## Thuộc tính&#x20;

* obj: kiểu object, thể hiện dữ liệu chính của dataTable
* name: kiểu string, tên dataTable

## Phương thức

**addRow(row, index)**

* Return type: void
* row: kiểu obj, required, giá trị một dòng của dataTable, ví dụ {ma\_kh:"abc", ten\_kh:"Vu Duy"}
* index: number, optional, thêm dòng này vào vị trí thứ index của dataTable, nếu như không truyền index vào thì hàm này sẽ thêm vào cuối của dataTable

**append(rows, index)**

* Return type: void
* rows: kiểu \[obj], required, giá trị nhiều dòng, ví dụ \[{ma\_kh:"abc", ten\_kh:"Vu Duy"},{ma\_kh:"xyz", ten\_kh:"Vu Duy 2"}]
* index: vị trí append, nếu không truyền thì sẽ append vào cuối của dataTable

**clone() Hàm được dùng để tạo một dataTable mới**

* Return type: dataTable

**copyRow(nthRow, index)**

Hàm được dùng để copy dòng thứ nthRow vào vị trí index của dataTable, nếu không truyền index thì hàm sẽ copy dòng thứ nthRow vào vị trí cuối của dataTable

* Return type: void
* nthRow: vị trí cần copy
* index: vị trí đích để paste dòng thứ nthRow

**count()**

Hàm dược dùng để đếm số dòng hiện tại của dataTable

**existsRow(field, value)**

Hàm được dùng để kiểm tra xem trong dataTable có dòng nào có field bằng với value hay không

* Return type: boolean
* field: kiểu string hoặc \[string] (required), là tên cột cần kiểm tra
* value: kiểu any  hoặc \[any] (required), là giá trị cần kiểm tra

**findRow(field, val)**

Hàm được dùng để trả ra danh sách các dòng có field và val trùng với tham số truyền vào

* Return type: \[số thứ tự dòng]
* field và val: tương tự hàm existsRow

**isEmpty()**

Hàm được dùng để kiểm tra xem dataTable này có rỗng hay không. Định nghĩa rỗng là nếu dataTable có 0 dòng, hoặc 1 dòng mà tất cả thuộc tính đều có giá trị null thì hàm trả về true

* Return type: Boolean

Ví dụ: \[] => true, \[{}] => true, \[{a:null.b:null}] => true Lưu ý: \[{a:undefined}] sẽ trả về false

**removeRow({nthRow, field, val})**

Hàm được dùng để xóa dòng thứ nthRow hoặc các dòng có field và val&#x20;

* Return type: void
* nthRow: kiểu số hoặc \[Số]
* field và val  tương tự hàm existsRow

**updateLine()**

Hàm được dùng để đánh dấu lại line trong dataTable, thường được sử dụng với list ở trong form

* Return type: void

**updateMappingData(r1, dt2, r2)**

**val(nthRow, columnName, newValue)**

Hàm được dùng để lấy giá trị hoặc gán giá trị tại dòng thứ nthRow, với columnName&#x20;

* Return type: any, Giá trị cột vừa được thêm mới
* nthRow: number, required, dòng cần thêm giá trị
* columnName: string, required, tên cột (field)
* newValue: any optional, nếu truyền thì dataTable sẽ gán giá trị newValue vào, ngược lại thì sẽ lấy giá trị&#x20;
