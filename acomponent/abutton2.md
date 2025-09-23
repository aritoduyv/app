# AButton2

## 1. Giới thiệu

AButton2 về giao diện sẽ là button bình thường nhưng có ảnh, nó sẽ kích hoạt sự kiện beforeButtonDialogClick

## 2. Khai báo xml

Các giá trị cần khai báo:

* **componentName:** khai là "AButton2"
* **fieldClass:** Tên class css, vùng tác động là ảnh của button
* **hidden:** "true" hoặc "false", có ẩn nút bấm này hay không, mặc định là "false"
* **name :** Id của button, được dùng trong sự kiện [beforeButtonDialogClick](../js/beforebuttondialogclick.md)
* **text:**  Khai trong thẻ text, là giá trị hiển thị trong ô bấm&#x20;

## 3. Data

AComponent này nhận giá trị là Number hoặc "Number", giá trị này được dùng để hiển thị ra góc trên bên phải của butotn, nếu giá trị này bằng 0 hoặc null, nó sẽ không hiển thị.

## 4. Css

Các tham số mà AButton2 đọc được từ thẻ css:

* uri: chấp nhận 3 loại tham số:&#x20;
  * base64&#x20;
  * https://...
  * icon của app: cách khai: "./icons/"+ tên icon&#x20;

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
          <field name="button1" componentName="AButton2" fieldClass="image1">
            <text v="Button demo 1" e="" o="" />
          </field>
          <field name="button2" componentName="AButton2" fieldClass="image2">
            <text v="Button demo 2" e="" o="" />
          </field>
          <field name="button3" componentName="AButton2" fieldClass="image3">
            <text v="Button demo 3" e="" o="" />
          </field>
          <field name="button4" componentName="AButton2" fieldClass="image4" hidden="true">
            <text v="Button demo 4" e="" o="" />
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select 5 as button1, '10' as button2, 15 as button3;
         ]]>
      </text>
    </query>
  </script>

  <css>
    <text>
      <![CDATA[
{ 
   "image1":{
      "uri":"data:image/png;base64,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"
   },
   "image2":{
      "uri":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQj86R3eLQIEuFP5i1w5Jg0Mdcc35jzahtLVF22YhdJqFLuWqU1eAp0nC6TNfdQ9-6wv1w&usqp=CAU"
   },
   "image3":{
       "uri":"./icons/img15.png"
   },
   "image4":{
       "uri":"./icons/img15.png"
   }
}
  ]]>
    </text>
  </css>
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="" e="" o=""></text>
    </button> 
  </buttons> 
</dir>
```

Ghi chú

fieldClass bổ sung uri ảnh cho AButton2 thông qua thẻ css&#x20;

Button này là field có thể nhận data (kiểu chuỗi hoặc số), để hiển thị số góc phải trên

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

