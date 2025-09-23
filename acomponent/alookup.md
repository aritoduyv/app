# ALookup

## 1. Giới thiệu

Được dùng để lookup giá trị từ màn hình [lookup](../man-hinh/lookup.md)

## 2. Khai báo xml

Các giá trị cần khai bá**o**

* **componentName:** required,"ALookup"
* **name:** required, tên field
* **readOnly**: optional, chỉ đọc hay không, mặc định là không
* **hidden:** optional, có ẩn hay không, mặc định là không
* **text:** optional, place holder của ALookup
* **viewInfo:**
  * **lookupType:** optional, loại lookup, mặc định là chọn 1 (One), nếu chọn nhiều thì khai "Multi"
  * **lookupMemvars:** các giá trị là các field cách nhau bởi dấu phẩy, truyền memvars từ màn hình form sang màn hình lookup
  * **lookupId:** tên contrler của màn hình lookup
  * **lookupRef:** Các trường khác cần lookup từ màn hình lookup
  *

## 3. Data

Data chính:

* **field:** Là field chính để gửi và nhận data với server, nếu có nhiều giá trị thì cách nhau bởi dấu phẩy

Data phụ:

* **field$name:** Tên hiển thị ra ngoài màn hình, nếu có nhiều giá trị thì cách nhau bởi char 255

## 4. Css

AComponent này không nhận css&#x20;

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
          <field name="id_nv" width="99%" viewType="Lookup" componentName="ALookup">
            <text v="Nhân viên" e="Employee" o="Employee"></text>
            <viewInfo lookupType="One" lookupId="sysuserinfo" lookupRef="[username] - [nickname]"/>
          </field>
          <field name="id_nv2" width="99%" viewType="Lookup" componentName="ALookup">
            <text v="Nhân viên 2" e="Employee" o="Employee"></text>
            <viewInfo lookupType="Multi" lookupId="sysuserinfo" lookupRef="[username] - [nickname]"/>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms> 
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="" e="" o=""></text>
    </button>
  </buttons>
  <script>
    <query>
      <text>
        <![CDATA[  
select '1,2,3' as id_nv2, N'Người 1ÿNgười 2ÿNgười 3' as id_nv2$name
        ]]>
      </text>
    </query>
  </script>
</dir>
```

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>
