# AListItemImageTexts

## 1. Giới thiệu

Item gồm 2 thành phần

* Thành phần 1, field0: id ảnh
* Thành phần 2, field1 đến fieldn: 1 hoặc nhiều cặp text-value (không giới hạn)

## 2. Khai báo xml

* **field0**:&#x20;
  * **name**: string, required, tên field
  * **viewInfo**
    * **imageUrlType**: string, optional, mặc định là PUBLIC 200
* **field1->fieldn**
  * **name**: string, required, tên field
  * **fieldClass**: string, optional, là css

## 3. Data

* **field0:** string, data là id ảnh cần hiển thị hoặc "./icons/tên icon.png" để sử dụng icon trên app
* **field1 -> n:** any

## 4. Css

css của field0 tác động lên ảnh, có thể thay đổi borderRadius, backgroundColor,...

css từ field1 -> fieldn theo css của [ALabel](../acomponent/alabel.md)

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<dir id="@@controller">
  <title v="Màn hình hướng dẫn" e="" o=""></title>
  <grids>
    <grid table="list_dat_hang" fieldKey="id"  componentName="AListItemImageTexts"  componentType="MapList" pageMode="LoadMore"> 
      <form>
        <formGroup width="100%" flexDirection="row">
          <fields>
            <field name="field0">
              <viewInfo imageUrlType="PUBLIC200"/>
            </field>
            <field name="field1">
              <text v="field1: "></text>
            </field>
            <field name="field2:" fieldClass="text">
              <text v="field2: "></text>
            </field>
            <field name="field3"/> 
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
select 1 as id, 'f1197a70eb1e4b33a9dd6379e973782a' as field0, 'value1' as field1, 'value2' as field2, 'value3' as field3
union
select 2 as id, './icons/img45.png' as field0, 'value1' as field1, 'value2' as field2, '2023-11-21T15:33:15' as field3
         ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids>
  <css>
    <text>
      <![CDATA[
{
  "text":{
    "text_fontWeight":"bold",
    "text_width":80
  }
}
          ]]>
    </text>
  </css>
</dir>
```

<figure><img src="../.gitbook/assets/image (18).png" alt="" width="360"><figcaption></figcaption></figure>
