# Form

## 1. Giới thiệu

Màn hình form là màn hình nhập liệu

## 2. Luồng

Mở form có 2 cách: [showForm ](../builder/phuong-thuc/showform.md)hoặc [replaceForm](../builder/phuong-thuc/replaceform.md)

params khởi tạo form có thể nhận là:

* **action**: string, optional, mặc định là NEW, ngoài ra có thể khai "EDIT", "VIEW", lưu ý ở trạng thái "VIEW", toàn bộ component lấy mặc định là readOnly
* **controller**: string, required, khi showForm hoặc replaceForm thì nó tự động chuyển cho màn hình Form
* **data**: dataTable, nếu màn hình form nhận được dataTable thì sử dụng dataTable làm data chính mà sẽ không load data từ server
* **memvars**: json hoặc [Memvars](../class/memvars.md), optional, form sử dụng memvars này để load data
* **options**: object, optional, cho form một số options
* **parent**: string, required, khi showForm hoặc replaceForm, nó tự động tạo parent cho màn hình form
* **title** truyền title tới màn hình form, title này sẽ ghi đè lên title trên xml

## 3. Các loại form&#x20;

1. **Form thông thường**
2. **Form chứa  list bên trong**

## 4. Form chứa list bên trong

Cách khai: sử dụng field với viewType là list, sau đó định nghĩa list ở bên trong thẻ grids

```xml
<field name="detail" componentName="AListItemSupport" viewType="List"/>
```

```xml
 <grids>
    <grid id="detail" fieldKey="id,line" readOnly="true" flexDirection="row">
      <form>
        <formGroup width="100%">
          <fields>
            <field/>
          </fields> 
         </formGroup>
      </form>
      <script>
        <query>
          <text>
            <![CDATA[   
-- query data cho list            
           ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids>
```

## 5. Lưu ý
