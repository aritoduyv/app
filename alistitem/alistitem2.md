# AListItem2

## 1. Giới thiệu

Mỗi item thể hiện thông tin của 1 hoặc nhiều cặp text-value

## 2. Khai báo xml

Khai field với các giá trị sau:

* **name:** tên field
* **text:** tên label, nếu không ghi text thì phần không gian của text trên app sẽ bị ẩn
* **fieldClass:** tên class field cần css

## 3. Data

* data theo tên của field.
* data kiểu bất kỳ (string, số, ngày)

## 4. Css

* Css của từng field theo [ALabel](../acomponent/alabel.md)

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<dir id="@@controller">
  <title v="Màn hình hướng dẫn" e="" o=""></title>
  <grids>
    <grid table="list_dat_hang" fieldKey="id"  componentName="AListItem2"  componentType="MapList" pageMode="LoadMore"> 
      <form>
        <formGroup width="100%" flexDirection="row">
          <fields>
            <field name="field1">
              <text v="field1"/>
            </field>
            <field name="field2">
              <text v="field2"/>
            </field>
            <field name="field3" fieldClass="classTest">
              <text v="field3"/>
            </field>
            <field name="field4">
              <text v="field4"/>
            </field>
            <field name="field5">
              <text v="field5"/>
            </field>
            <field name="field6" fieldClass="class2">
              <text v="field6"/>
            </field>
            <field name="field7">
              <text v="field7"/>
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
select 1 as id, 'value1A' as field1, 'value2A' as field2, 'value3A' as field3, 'value4A' as field4, 'value5A' as field5, 'value6A' as field6, 'value7A' as field7
union
select 2 as id, 'value1B' as field1, 'value2B' as field2, 'value3B' as field3, 'value4B' as field4, 'value5B' as field5, 'value6B' as field6, 'value7B' as field7
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
  "classTest":{
    "text_fontWeight":"bold",
    "text_width":80
  },
  "class2":{
    "text_color":"red",
    "value_color":"green"
  }
}
          ]]>
    </text>
  </css>
</dir>
```

<figure><img src="../.gitbook/assets/image (15).png" alt="" width="360"><figcaption></figcaption></figure>
