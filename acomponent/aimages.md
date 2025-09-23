# AImages

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
* **hidden**: string (optional), format boolean ("true" hoặc false), có ẩn component này hay không? mặc định là "false"
* **readOnly:** Ảnh này có phải chỉ đọc hay không, mặc định là "false"
* **\<viewInfo>**: xml con, được dùng để định nghĩa các thành phần của app
  * **fileGroup**: required, là xgroup trong dmttin (xgroup được dùng để nhóm (gom cụm hay cluster))
  * **fileFieldId0**: require, app lấy data từ tên trường này ra thông qua valForm, để lưu trong cột id0 của dmttin
  * **allowCamera**: optional, format boolean ("true" hoặc "false"), có dùng camera hay không? mặc định là "false"
  * **allowLibrary**: optional, format boolean ("true" hoặc "false"), có dùng thư viện hay không? mặc định là "false"
  * image
  * **maxImageSize**:  optional, format width,height, kích thước ảnh tối đa, ví dụ: "500,500", mặc định là "2048,2048"
    * Lưu ý từ phiên bản ≥ 1.3.21 thì mặc định là 2048,2048, phiên bản < 1.3.21 thì mặc định là 9999,9999
  * **maxFileCount:** optional, Số lượng file tối đa, mặc định là 10
  * **cameraType:** optional, "front" hoặc "back", khi mở camera, sử dụng camera trước hay sau, mặc định là "back", camera sau&#x20;

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
  <title v="AImages" e="Màn hình form" o="Màn hình form"/> 
  <forms>
    <form>
      <formGroup>
        <fields>
          <field name="ten_field_images" width="100%" componentName="AImages">
            <viewInfo fileGroup="dmvt" fileFieldId0="id" imageUrlType="PUBLIC200" allowCamera="true" allowLibrary="true" maxImageSize="1000,1000" maxFileSize="10240" cameraType="front" maxFileCount="5"/>
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
select 'e5efbbe1fa3542d7b629df7d583c5a34,8c372752543e46b2a1c2b12ada80dbec,b28798f7f3304d5ea5dcd955ee00603a' as ten_field_images
      ]]>
      </text>
    </query>
  </script> 
  
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button>  
  </buttons> 
  
</dir>
```

<figure><img src="../.gitbook/assets/image (75).png" alt="" width="375"><figcaption><p>Ví dụ về AImages</p></figcaption></figure>
