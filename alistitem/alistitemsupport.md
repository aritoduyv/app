# AListItemSupport

## 1. Giới thiệu

AListItem support gồm 6 thành phần:

* **field0**: ảnh&#x20;
* **field1:** Text lớn
* **field2:** Text nhỏ
* **field3:** Text nghiêng
* **field4:** Số
* **field5:** Có mũi tên phải hay không

## 2. Khai báo xml

**field0**: name, viewInfor (imageUrlType)

**field1->field5**: name

## 3. Data

**field0**:  optional, string, fileId hoặc "./icons/tên ảnh.png", nếu giá trị null sẽ sử dụng ảnh mặc định

**field1->field3**: optional, string, nếu giá trị null sẽ không hiển thị

**field4:** optional, number, nếu giá trị null sẽ không hiển thị, nếu giá trị >= 100, giá trị hiển thị 99+

**field5**: optional, number, giá trị 0 hoặc 1, mặc định là 0

## 4. Css

Không nhận css

## 5. Target

Nhận 4 target sau:

field0, field4, filed5 và phần còn lại là "$ALL"

## 6. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<dir id="@@controller">
  <title v="Màn hình hướng dẫn" e="" o=""></title>
  <grids>
    <grid table="list_dat_hang" fieldKey="id"  componentName="AListItemSupport"  componentType="MapList" pageMode="LoadMore"> 
      <form>
        <formGroup width="100%" flexDirection="row">
          <fields>
            <field name="field0"/>
            <field name="field1"/>
            <field name="field2"/>
            <field name="field3"/>
            <field name="field4"/>
            <field name="field5"/>
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
select 1 as id, './icons/img105.png' as field0 , N'Text lớn' as field1, N'Text nhỏ' as field2, N'Text nghiêng' as field3, 25 as field4, 1 as field5
         ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids> 
</dir>
```

<figure><img src="../.gitbook/assets/image (72).png" alt="" width="360"><figcaption></figcaption></figure>
