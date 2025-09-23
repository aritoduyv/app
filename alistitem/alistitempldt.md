# AListItemPLDT

## 1. Giới thiệu

Item gồm 2 field

* **field 0**: thể hiện text
* **field 1:** thể hiện màu sắc&#x20;

## 2. Khai báo xml

Cả 2 field khai báo&#x20;

* **name:** tên field

## 3. Data

* **field 0:** string, required, nội dung của item
* **field 1:** string, optional, mặc định là màu đen, thể hiện màu sắc của item

## 4. Css

Không nhận css

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>
<dir id="@@controller">
  <title v="Màn hình hướng dẫn" e="" o=""></title>
  <grids>
    <grid table="list_dat_hang" fieldKey="id"  componentName="AListItemPLDT"  componentType="MapList" pageMode="LoadMore"> 
      <form>
        <formGroup width="100%" flexDirection="row">
          <fields>
            <field name="field0"/>
            <field name="field1"/>  
          </fields>
        </formGroup>
      </form>

      <buttons>
        <button id="cancel" image="arrow-left-circle">
          <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
        </button> 
      </buttons>
      <script>
        <query>
          <text>
            <![CDATA[
select 1 as id, 'tieu de 1' as field0 ,'green' as field1
         ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids> 
</dir>
```

<figure><img src="../.gitbook/assets/image (20).png" alt="" width="360"><figcaption></figcaption></figure>
