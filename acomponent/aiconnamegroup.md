# AIconNameGroup

## 1. Giới thiệu

AIconNameGroup là một thành phần, nó hiển thị được 1 hoặc nhiều cặp (ảnh và tên). Nó được sử dụng trong tình huống như hiển thị avatar và tên user, hiển thị ảnh đơn vị tính và tên đơn vị tính, ...

## 2. Khai xml

Các giá trị cần khai như sau:

* **componentName:** AIconNameGroup
* **hidden:** "true" hoặc "false"
* **name:** Tên field
* **text:** Hiển thị tiêu đề của group
* **viewInfo:**
  * **imageUrlType:** Ảnh mà app sử dụng, mặc định là PRIVATE1 (Các giá trị khác có thể sử dụng như PUBLIC200 PUBLIC350 PUBLIC800 PRIVATE0)
* **width :** Độ rộng của group

## 3. Data&#x20;

Các loại data:

**data chính:**

* **field**: Là danh sách id của field, cách nhau bởi dấu phẩy

**data phụ:**

* **field$image\_id:** Là danh sách image\_id của field, được dùng để hiển thị data, danh sách ảnh này cách nhau bởi char(255)
* **field$name:** là danh sách tên hiển thị bên phải của ảnh (danh sách này cách nhau bởi char(255))
* **field$footer:** Là dòng ghi chú bên dưới, gồm có 2 phần cách nhau bởi char(255) gồm:\
  color + char(255) + value

## 4. Css

AComponent này không nhận css

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
          <field name="ds_vt" width="100%" componentName="AIconNameGroup">
            <viewInfo imageUrlType="PUBLIC200"/> 
            <text v="Danh sách vật tư" e="" o="" />
          </field> 
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select '1,2,3,4' as ds_vt, N'Vật tư 1 ÿVật tư 2 ÿVật tư 3 ÿVật tư 4' as ds_vt$name, 'f1197a70eb1e4b33a9dd6379e973782aÿf1197a70eb1e4b33a9dd6379e973782aÿf1197a70eb1e4b33a9dd6379e973782aÿf1197a70eb1e4b33a9dd6379e973782a' as ds_vt$image_id, N'redÿDanh sách vật tư chờ duyệt' as ds_vt$footer
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

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
