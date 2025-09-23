# AFile

## 1. Giới thiệu

AFile là một thành phần quan trọng được sử dụng để cho phép người dùng chọn và tải lên các tệp tin từ thiết bị của họ. Component này giúp tạo trải nghiệm tương tác và thu thập thông tin từ người dùng trong ứng dụng React Native.

## 2. Khai báo xml&#x20;

Các giá trị cần khai

* **componentName**: "AFile"
* **hidden**: Có ẩn component này hay không, mặc định là không
* **name**: tên field, dùng để xấc nhận trường dữ liệu nhận từ data
* **readOnly**: true hoặc false, nếu là true thì chỉ xem kết quả mà không cho phép chọn file nữa
* **viewInfo**
  * **fileExtension**: đuôi file được phép chọn (mặc định là tất cả), xem thêm tại [https://www.npmjs.com/package/react-native-document-picker](https://www.npmjs.com/package/react-native-document-picker)
  * **maxFileCount**: Số lượng file tối đa có thể chọn, mặc định là 10
  * **maxFileSize**: Kích thước tối đa của mỗi file (đơn vị KB), mặc định là 10240&#x20;
* **width**: độ rộng của field, nên khai là "100%"

## 3. Data&#x20;

AFile nếu không có data thì nó sẽ hiển thị mời gọi người dùng chọn file (nếu action của form khác View && readOnly = false, ngược lại thì sẽ không hiện)

AFile nhận data là: String, danh sách fileId, cách nhau bởi dấu phẩy

Ví dụ: select 'file\_id1,file\_id2,file\_id3' as fileupload

Ngoài ra để hiển thị tên thì cũng phải trả ra tên file = field$name

Ví dụ: select 'filename1ÿfilename2ÿfilename3' as fileupload$name

## 4. Css

AComponent này không css được

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" fieldKey="id" >
  <title v="Hướng dẫn sử dụng" e="" o=""></title>
  <forms>
    <form>
      <formGroup>
        <fields>
          <field name="fileupload1" width="100%" componentName="AFile">
            <text v="Chọn file 1" e="" o=""></text>
            <viewInfo fileGroup="IDT" maxFileSize="10240" maxFileCount="5" fileExtension="pdf"></viewInfo>
          </field>
          
          <field name="fileupload2" width="100%" componentName="AFile">
            <text v="Chọn file 2" e="" o=""></text>
            <viewInfo fileGroup="IDT" maxFileSize="10240" maxFileCount="5"></viewInfo>
          </field>

          <field name="fileupload3" width="100%" componentName="AFile" hidden="true">
            <text v="Chọn file 3" e="" o=""></text>
            <viewInfo fileGroup="IDT" maxFileSize="20480" maxFileCount="15"></viewInfo>
          </field>

          <field name="fileupload4" width="100%" componentName="AFile" readOnly="true">
            <text v="Chọn file 4" e="" o=""></text>
            <viewInfo fileGroup="IDT" maxFileSize="20480" maxFileCount="15"></viewInfo>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select 'file_id1,file_id2,file_id3' as fileupload2, 'filename1ÿfilename2ÿfilename3' as fileupload2$name
    ]]>
      </text>
    </query>
  </script> 
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="" e="" o=""></text>
    </button> 
  </buttons> 
</dir>
```

<figure><img src="../.gitbook/assets/image (69).png" alt=""><figcaption></figcaption></figure>

fileupload3 bị hidden, fileupload4 readonly giống fileupload5 nhưng không có value nên nó cũng bị ẩn
