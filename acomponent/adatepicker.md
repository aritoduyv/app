# ADatePicker

## 1. Giới thiệu&#x20;

ADatePicker là một thành phần quan trọng được sử dụng để cho phép người dùng chọn ngày từ một giao diện tương tác. &#x20;

## 2. Khai báo xml&#x20;

AComponent này nhận các data sau:

* **allowBlank:** "true" hoặc false, mặc định là false, nếu true thì có thể xóa trắng để sử dụng data là null
* **hidden:** "true" hoặc "false", có ẩn component này hay không, mặc định là "false"
* **name:** Tên fieldName
* **readOnly:** "true" hoặc "false" Có đang ở chế độ chỉ đọc hay không, mặc định là "false"
* **text:** Label text của field
* **width:** Độ rộng của field, sử dụng 2 loại khai báo là số và phần trăm

## 3. Data&#x20;

AComponent này nhận data kiểu ngày (dạng chuỗi) hoặc null, có thể sử dụng format "yyyy-MM-ddThh:mm:ss.sss" hoặc "yyyy-MM-ddThh:mm:ss" hoặc "yyyy-MM-dd"

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
          <field name="dateFrom" width="100%" componentName="ADatePicker">
            <text v="ngày từ"/>
          </field> 
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select '2' as testCombobox2
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

<figure><img src="../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>
