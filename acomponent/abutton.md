# AButton

## 1. Giới thiệu&#x20;

Button cho phép người dùng thực hiện một hành động cụ thể khi nhấp vào nút đó.

Một hành động hoặc một chuỗi các hành động được kích hoạt thông qua khai báo beforeButtonDialogClick trong thẻ js.

## 2. Khai báo xml

Các giá trị cần khai

* **componentName:** khai là "AButton"
* **fieldClass:** Tên class css
* **hidden:** "true" hoặc "false", có ẩn nút bấm này hay không, mặc định là "false"
* **name :** Id của button, được dùng trong sự kiện [beforeButtonDialogClick](../js/beforebuttondialogclick.md)
* **text:**  Khai trong thẻ text, là giá trị hiển thị trong ô bấm
* **width:** "Number" hoặc phần trăm, đây là độ rộng của button, ví dụ: "50" hoặc "30%"

## 3. Data

AComponent này không nhận data

## 4. Css

AComponent này không cho phép css

## 5. Ví dụ

```xml
<forms>
  <form>
    <formGroup>
      <fields>
        <field name="button1" width="60%" componentName="AButton">
          <text v="Button demo 1" e="" o="" />
        </field>
        <field name="button2" width="70%" componentName="AButton">
          <text v="Button demo 2" e="" o="" />
        </field>
        <field name="button3" width="20%" componentName="AButton">
          <text v="Button demo 3" e="" o="" />
        </field>
        <field name="button4" width="100%" componentName="AButton" hidden="true">
          <text v="Button demo 4" e="" o="" />
        </field>
      </fields>
    </formGroup>
  </form>
</forms>
```

Chú thích

Khai báo 3 button với lần lượt width = 60%, 70%, 20% và id của button lần lượt là button1, button2, button3

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>
