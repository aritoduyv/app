# ALink

## 1. Giới thiệu

ALink Linking gives you a general interface to interact with both incoming and outgoing app links.

## 2. Khai báo xml

ALink  thuộc loại field

Các thẻ và thuộc tính cần khai

* **field**: xml, là thẻ khai component
* **name**: string (required), là thuộc tính tên trường (cột) nhận data
* **width**: string (required), là độ rộng của component
* **componentName**: string (required), khai báo ALabel để sử dụng
* **text**: string (optional),&#x20;
* **hidden**: Có ẩn hay không, mặc định là không

## 3. Data

Data được dùng để hiển thị value.&#x20;

* Kiểu dữ liệu: string
* Ví dụ:  "tel:03994444", "mailto:vuduy08021999@gmail.com","sms:0399446439","https://example.com"

## 4. Css&#x20;

&#x20;Component này không nhận css

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="ALabels" e="Debug Duy" o="Debug Duy"></title>

  <forms>
    <form>
      <text v="Danh sách khách hàng" e="" o=""></text>
      <formGroup width="100%">
        <fields>
          <field name="link1" width="100%" componentName="ALink">
            <text v="link1" e="" o=""></text>
          </field>
		 <field name="link2" width="100%" componentName="ALink">
            <text v="link2" e="" o=""></text>
          </field>
           <field name="link3" width="100%" componentName="ALink">
            <text v="link3" e="" o=""></text>
          </field>
           <field name="link4" width="100%" componentName="ALink">
            <text v="link4" e="" o=""></text>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[  
select N'tel:03994444' as link1,  N'mailto:vuduy08021999@gmail.com' as link2,  N'sms:0399446439' as link3 ,  N'https://example.com' as link4
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

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
