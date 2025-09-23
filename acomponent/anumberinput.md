# ANumberInput

## 1. Giới thiệu&#x20;

ANumberInput là một thành phần quan trọng trong giao diện người dùng của React Native, được sử dụng để cho phép người dùng nhập số

## 2. Khai báo xml

Các giá trị cần khai báo gồm:

* **componentName:** "ANumberInput"
* **name:** Tên field
* **hidden:** Có ẩn component này hay không
* **text**: Là label
* **width:** Độ rộng, bằng cách khai theo kiểu "Number" hoặc phần trăm
* **readOnly**: "true" hoặc "false"
* **rows**: Số dòng,

## 3. Data&#x20;

AComponent này nên nhận data là kiểu số chuỗi

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
  <title v="ANumberInput" e="ANumberInput" o="ANumberInput"></title>

  <forms>
    <form>
      <text v="Số lượng sản phẩm" e="" o=""></text>
      <formGroup width="100%">
        <fields>
          <field name="so_luong" width="100%" componentName="ANumberInput" rows="2">
            <text v="Số lượng" e="" o=""></text>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[  
select 123 as so_luong
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
