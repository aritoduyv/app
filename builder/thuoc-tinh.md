# Thuộc tính

LUỒNG APP: KHỞI TẠO (showForm, showList,...) -> BEFORE INIT -> CREATE SCREEN -> AFTER INIT&#x20;

Builder chỉ có 1 thuộc tính duy nhât là options, để sử dụng, ta gọi p.options.XXX, trong đó XXX gồm các giá trị sau:

**action:** string, tạo lúc KHỞI TẠO,  mặc định trên form là NEW, trên list là VIEW. Là trạng thái hành động của form (NEW, EDIT, VIEW) hoặc list (EDIT, VIEW). Với action là VIEW thì màn hình đó chỉ xem mà không thể chỉnh sửa nội dung. EDIT thì có thể chỉnh sửa nội dung

**allowMultiSelection:** Boolean, tạo lúc KHỞI TẠO, cho phép chọn nhiều trên list hay không, Thuộc tính này liên quan đến thuộc tính **currentRow** bên dưới

**buttons:** object, tạo lúc CREATE SCREEN, từ thẻ buttons trên xml

**configSet:** [ConfigSet](../class/configset.md), tạo lúc CREATE SCREEN, app dùng để quản lý cấu hình của các màn hình

**controller**: string, tạo lúc KHỞI TẠO, app dùng để load cấu hình và data, và nhiều tính năng khác

**css:** string object (có thể JSON.parse), tạo lúc CREATE SCREEN, được dùng để tạo style&#x20;

**currentRow:** \[Số], tạo lúc CREATE SCREEN, Cho biết index (stt bắt đầu từ 0) các dòng đang được chọn,  các item được set sẽ được tô màu. currentRow là mảng nhiều giá trị khi allowMultiSelection = true

**data:** [**DataTable**](../class/datatable.md)**,** tạo lúc KHỞI TẠO, là data chính của app, nếu là Form chứa nhiều list, thì data chính là data của Form

**dataSet:** [DataSet](../class/dataset.md), tạo lúc KHỞI TẠO, là dataSet của màn hình, quản lý nhiều dataTable

**fieldKey:** string, tạo lúc CREATE SCREEN, là tên trường fieldKey

**filterCallBack:** function, tạo lúc KHỞI TẠO, app dùng để chạy lệnh reload màn hình sau khi filter,&#x20;

**folder:** string, tạo lúc CREATE SCREEN, là thư mục "List" hoặc "Form"

**js:** function, tạo lúc KHỞI TẠO, là các function có trong thẻ js của xml, nó tạo trước beforeInit bởi vì nó sinh ra beforeInit

**host\_url:** string, tạo lúc CREATE SCREEN, là host mà app đang sử dụng

**language:** string, tạo lúc CREATE SCREEN, ngôn ngữ được sử dụng trên app, có 2 giá trị "v" hoặc "e", app dùng để xác định nhanh để dịch ngôn ngữ trên app

**memvars:** object, tạo lúc KHỞI TẠO, là memvars của màn hình **hiện tại** (nếu sau khi reload, filter thì memvars này sẽ thay đổi theo)

**message:** object, tạo lúc CREATE SCREEN, là đối tượng tin nhắn với thuộc tính là messageId

**modify:** string, tạo lúc KHỞI TẠO từ params, sử dụng trên list, cho biết list này có thể cập nhật từ màn hình sau nó hay không

**navigation:** function, tạo lúc KHỞI TẠO, app dùng để điều hướng, lập trình viên cũng có thể dùng để p.options.navigation.navigate, p.options.navigation.goback(),..., nhưng builder cũng có method [navigate](phuong-thuc/navigate.md) và [goback](phuong-thuc/goback.md) riêng

**parent:** Builde&#x72;**,** được tạo lúc KHỞI TẠO, là màn hình cha của màn hình hiện tại, lưu ý nếu sử dụng replaceForm, replaceList, thì màn hình cha là màn hình xuất hiện sau khi ấn back về

**reload:** function, tạo lúc CREATE SCREEN, app dùng để [reload](phuong-thuc/reload.md)

**searchCallback:** function, tạo lúc CREATE SCREEN, app dùng để reload màn hình sau khi search trên header

**signatureToken:** string,  tạo lúc CREATE SCREEN,  phần cuối của jwt token (1 jwt chứa 3 phần cách nhau bởi dấu .), thuộc tính này được app dùng để load những ảnh private

**userGroupId:** string, tạo lúc CREATE SCREEN, group id của user,  app dùng để load những ảnh public







