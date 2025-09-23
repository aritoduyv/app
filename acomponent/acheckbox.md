# ACheckbox

## 1. Giới thiệu&#x20;

Checkbox là một thành phần quan trọng trong giao diện người dùng của React Native, được sử dụng để cho phép người dùng chọn hoặc bỏ chọn một hoặc nhiều tùy chọn từ một danh sách.

Checkbox thường có hình dạng hộp vuông và một biểu tượng hoặc văn bản bên cạnh để mô tả tùy chọn tương ứng. Khi người dùng nhấp vào checkbox, trạng thái của nó có thể chuyển từ "chưa chọn" sang "đã chọn" và ngược lại.

## 2. Khai báo xml

Các giá trị cần khai báo gồm:

* **componentName:** "ACheckBox"
* **name:** Tên field
* **hidden:** Có ẩn component này hay không
* **text**: Là label
* **width:** Độ rộng, bằng cách khai theo kiểu "Number" hoặc phần trăm

## 3. Data&#x20;

AComponent này nên nhận data là kiểu số (0 hoặc 1), nếu là 0 thì là không chọn, nếu là 1 thì chọn

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
          <field name="checkbox1" width="50%" componentName="ACheckbox">
            <text v="checkbox demo 1" e="" o="" />
          </field>
          <field name="checkbox2" width="50%" componentName="ACheckbox">
            <text v="checkbox demo 2" e="" o="" />
          </field>
          <field name="checkbox3" width="100%" componentName="ACheckbox">
            <text v="checkbox demo 3" e="" o="" />
          </field>
          <field name="checkbox4" width="100%" componentName="ACheckbox" hidden="true">
            <text v="checkbox demo 4" e="" o="" />
          </field>
          <field name="checkbox5" width="50%" componentName="ACheckbox">
            <text v="checkbox demo 5" e="" o="" />
          </field>
          <field name="checkbox6" width="50%" componentName="ACheckbox" readOnly="true">
            <text v="checkbox demo 6" e="" o="" />
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select 1 as checkbox1, '' as checkbox2, 0 as checkbox3, '1000' as checkbox4
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

Ghi chú: Nếu checkbox nhận được data và if(data) thì nó sẽ show ra ô đó có được check hay không, lưu ý if(false)  sẽ không show nhưng if("false") sẽ show (vì "false" là chuỗi có giá trị)

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>
