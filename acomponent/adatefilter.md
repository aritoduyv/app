# ADateFilter

## 1. Giới thiệu

ADateFilter là một menu cho phép người dùng chọn nhanh ngày từ đến của 2 field ngày gần nó nhất.

## 2. Khai báo xml

* **componentName:** ADateFilter
* **name:** Tên field (tên bất kì, nhưng đừng trùng với field khác)
* **width:** Độ rộng của cột

## 3. Data

ADateFilter không nhận data

## 4. Css

ADateFilter không thể css

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
          <field name="dateFrom" width="44%" componentName="ADatePicker">
            <text v="ngày từ"/>
          </field>
          <field name="dateTo" width="44%" componentName="ADatePicker">
            <text v="ngày đến"/>
          </field>
          <field name="dateFilter" width="12%" componentName="ADateFilter">
            <text v="ngày lọc"/>
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

<figure><img src="../.gitbook/assets/image (66).png" alt=""><figcaption></figcaption></figure>
