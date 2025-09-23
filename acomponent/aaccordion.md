# AAccordion

## 1. Giới thiệu

AAccordion là một custom component thường được sử dụng trong React Native để tạo ra một giao diện gập mở (collapse/expand) cho các phần tử hoặc danh sách. Nó cho phép người dùng ẩn hoặc hiển thị nội dung bổ sung khi nhấp vào tiêu đề hoặc biểu tượng tương ứng.

AAccordion được thiết kế để giúp tối ưu hóa không gian và cung cấp trải nghiệm người dùng tốt hơn bằng cách ẩn các phần tử không cần thiết và chỉ hiển thị khi cần thiết. Điều này thường được sử dụng trong các danh sách dữ liệu dài, menu, hoặc các phần tử có nội dung phụ. Nó cũng giúp tạo ra giao diện người dùng linh hoạt và tương tác, cho phép người dùng tùy chỉnh thông tin hiển thị và tạo trải nghiệm cá nhân hơn.

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

## 2. Khai báo xml

AAccordion thuộc loại form

Các giá trị cần khai

* **action**: Khai báo tên list nằm bên trong accordion, mặc định là null
* **collapse**: "true" hoặc "false", là accordion gập mặc định hay không, mặc định là "true"
* **componentName**: AAccordion
* **fieldClass**: Khai báo tên css cho accordion, mặc định là null
* **hidden**: optional, "true" hoặc "false", là accordion có bị ẩn hay không, mặc định là "false"
* **image**: optional, tên icon nằm bên trái của tiêu đề, nằm trong bộ [https://simplelineicons.github.io/](https://simplelineicons.github.io/). mặc định là null
* **name**: optional, Tên fieldName của accordion, được dùng khi gọi hàm p.[setHiddenAccordion](../builder/phuong-thuc/setcollapseaccordion.md), p.[setCollapseAccordion](../builder/phuong-thuc/sethiddenaccordion.md)

## 3. Data

AComponent này không đọc data

## 4. Css

Khai báo được các css sau:

actionIcon, thể hiện icon của list nằm bên trong accordion

Khai báo được các thuộc tính css liên quan tới view ngoài cùng bao bọc các item như width, height, backgroundColor, padding, margin,...&#x20;

## 5. Ví dụ

{% code lineNumbers="true" %}
```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="Hướng dẫn sử dụng" e="Debug Duy" o="Debug Duy"></title>

  <forms>
    <form componentName="AAccordion" image="plane" collapse="false" name="chi_tiet">
      <text v="Chi tiết" e="Detail" o="Detail" />
      <formGroup width="100%" flexDirection="column">
        <fields />
      </formGroup>
    </form>
  </forms> 
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button> 
  </buttons> 
</dir>
```
{% endcode %}

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>
