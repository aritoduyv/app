# AListItemDatHang

## 1. Giới thiệu&#x20;

<mark style="color:red;">**LƯU Ý: Muốn sử dụng AListItem này thì khi show list phải sử dụng action là EDIT, ví dụ:**</mark>

<mark style="color:red;">**p.showList(controller,{action:"EDIT"}, vì list này có hành động thay đổi data trên item**</mark>

Item dành cho chức năng đặt hàng, sẽ có các thành phần sau:

* Checkbox
* Ảnh
* 4 texts
* 1 text đậm
* 1 ô tăng giảm số lượng

## 2. Khai báo xml

* **field0:**
  * **name:** tên field
* **field1:**
  * **name:** tên field
  * **viewInfo:**
    * **imageUrlType:** Loại ảnh được load, mặc định PUBLIC200
* **field2 -> field6**
  * **name:** tên field
* **field7**
  * **name:** tên field
  * **viewInfo**:
    * **minValue**: giá trị nhỏ nhất của field
    * **maxValue**: giá trị lớn nhất của field

## 3. Data

* **field0**: number, optional, giá trị 0 hoặc 1, nếu giá trị là null thì không hiện checkbox
* **field1:** string, required, id của ảnh
* **field2->field6**: string, optional, nếu giá trị là null thì không hiện
* **field7:** numbe&#x72;**,** required

## 4. Css

AListItem này không nhận css

## 5. Click target

* Nếu user bấm vào field1 (ảnh), thì sẽ gọi handleListItemPress với target là tên field1

## 6. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<dir id="@@controller">
  <title v="Màn hình hướng dẫn" e="" o=""></title>
  <grids>
    <grid table="list_dat_hang" fieldKey="id"  componentName="AListItemDatHang"  componentType="MapList" pageMode="LoadMore"> 
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
            <field name="field7">
              <viewInfo minValue="0" maxValue="25"/> 
            </field>
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
select 1 as id, 1 as field0, 'f1197a70eb1e4b33a9dd6379e973782a' as field1, 'field22222' as field2, 'field33333' as field3, 'field44444' as field4, 'field55555' as field5, 'field66666' as field6, 15 as field7
         ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids> 
</dir>
```

<figure><img src="../.gitbook/assets/image (19).png" alt="" width="360"><figcaption></figcaption></figure>
