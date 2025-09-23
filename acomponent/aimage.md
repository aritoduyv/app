# AImage

## 1. Giới thiệu

AImage được dùng để hiển thị một image lên trên app

## 2. Data

Data được dùng để app chuyển đổi thành link ảnh và hiển thị ảnh, sử dụng trường **fileId**

* Kiểu dữ liệu: string
* ví dụ: "642a11c522a55sa2cc2ac"

## 3. Khai báo xml

AImage thuộc loại field

Các thẻ và thuộc tính cần khai:

* **name:** string (required), là tên trường (cột) mà component nhận và thao tác với data
* **width**: string (required), dạng số ("64") hoặc % ("50%"), dùng để khai báo độ rộng của component
* **componentName**: string, (required) = "AImage"
* **hidden**: string (optional), format boolean ("true" hoặc false), có ẩn component này hay không? mặc định là "false"&#x20;
* **\<viewInfo>**: xml con, được dùng để định nghĩa các thành phần của app
  * **fileGroup**: required, là xgroup trong dmttin (xgroup được dùng để nhóm (gom cụm hay cluster))
  * **fileFieldId0**: require, app lấy data từ tên trường này ra thông qua valForm, để lưu trong cột id0 của dmttin
  * **allowCamera**: optional, format boolean ("true" hoặc "false"), có dùng camera hay không? mặc định là "false"
  * **allowLibrary**: optional, format boolean ("true" hoặc "false"), có dùng thư viện hay không? mặc định là "false"
  * **maxImageSize**:  optional, format width,height, kích thước ảnh tối đa, ví dụ: "500,500", mặc định là "9999,9999"
  * **maxFileSize**: optional, format number, kích cỡ file tối đa trong KB, ví dụ: "300", mặc định là 10240 (10MB)
  * **cameraType:** optional, "front" hoặc "back", khi mở camera, sử dụng camera trước hay sau, mặc định là "back", camera sau
  * **imageUrlType:** optional, mặc định là PRIVATE0

## 4. Css

AImage khi khai css, khu vực tác động css sẽ là phần View bao bọc ảnh, có thể sử dụng các thuộc tính như padding, margin, border, ... Xem thêm tại [css](../css.md#cac-thuoc-tinh-style)

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="Hướng dẫn sử dụng" e="Debug Duy" o="Debug Duy"></title>
  <forms>
    <form>
      <formGroup>
        <fields> 
          <field name="avatar" width="50" componentName="AImage">
            <viewInfo fileGroup="dmvt" fileFieldId0="id" imageUrlType="PUBLIC200" allowCamera="true" allowLibrary="true" maxImageSize="1000,1000" maxFileSize="10240" cameraType="front"/> 
            <text v="" e="" o="" />
          </field> 
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select 'f1197a70eb1e4b33a9dd6379e973782a' as avatar
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

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>
