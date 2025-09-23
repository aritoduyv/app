# AListItem3

## 1. Giới thiệu

Item của AListItem3 có 7 field sau:

* field 0: Link ảnh
* field 1: Tiêu đề text lớn
* field 2: Text nhỏ
* field 3: Text trắng và có màu  background là giá trị field 6
* field 4: Chữ nghiêng
* field 5: Tags
* field 6: màu background của field 3

AListItem này chỉ đọc giá trị data chứ không đọc text của xml

## 2. Khai báo xml

Các field khai các thông tin sau:

* **name:** Tên field

Riêng field 0 có khai thêm&#x20;

* **viewInfo:**
  * **imageUrlType:** string, optional, mặc định là PUBLIC200

## 3. Data

* field 0: string, required, fieldId của ảnh
* field 1: string, optional, tiêu đề lớn
* field 2: string, optional, text nhỏ
* field 3: string, optional, text trắng
* field 4: string, optional, text nghiêng
* field 5: string, optional, tags, nhiều tags thì tag cách nhau bởi char 255
* field 6: string, optional, màu background của field 3, mặc định là #ff4155

## 4. Css

* AListItem này không nhận css

## 5. Ví dụ&#x20;

```xml
<?xml version="1.0" encoding="utf-8"?>

<dir id="@@controller">
  <title v="Màn hình hướng dẫn" e="" o=""></title>
  <grids>
    <grid table="list_dat_hang" fieldKey="id"  componentName="AListItem3"  componentType="MapList" pageMode="LoadMore"> 
      <form>
        <formGroup width="100%" flexDirection="row">
          <fields>
            <field name="field0"/>
            <field name="field1"/>
            <field name="field2"/>
            <field name="field3"/>
            <field name="field4"/>
            <field name="field5"/>
            <field name="field6"/> 
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
select 1 as id, 'f1197a70eb1e4b33a9dd6379e973782a' as field0, 'field1' as field1, 'field2' as field2, 'field3' as field3, 'field4' as field4, 'field51ÿfield52ÿfield53ÿfield54ÿfield55ÿfield56' as field5, 'red' as field6
         ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids> 
</dir>
```

<figure><img src="../.gitbook/assets/image (17).png" alt="" width="360"><figcaption></figcaption></figure>
