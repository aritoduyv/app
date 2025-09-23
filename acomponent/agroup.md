# AGroup

## 1. Giới thiệu

AGroup là một component được sử dụng để chứa các component khác, nó chỉ khác với AAccordion là nó không gập được (collapse).

Với khả năng lồng nhau (formGroup nằm trong formGroup) thì hiện tại có thể vẽ được mọi layout

## 2. Khai xml

Tên thẻ là formGroup

* **fieldClass**: Tên css
* **flexDirection**: "row" hoặc "column", mặc định là row, xem thêm tại [https://reactnative.dev/docs/flexbox](https://reactnative.dev/docs/flexbox)
* **width**: Độ rộng của AComponent, đơn vị là số hoặc phần trăm

## 3. Data

AComponent này không nhận data

## 4. Css

Khu vực tác động css là vùng mà AGroup bao bọc, một số css thường dùng như padding, height, backgroundColor, border, borderColor,...

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" fieldKey="id" >
  <title v="Hướng dẫn sử dụng" e="" o=""></title>
  <forms>
    <form>
      <formGroup width="100%" flexDirection="column"> 
        
      </formGroup>
      <formGroup width="100%">
        <formGroup width="30%" fieldClass="red heigth100">

        </formGroup>
        <formGroup width="70%" fieldClass="green heigth100">

        </formGroup>
      </formGroup>
      <formGroup width="100%">
        <formGroup width="200" fieldClass="pink heigth200">
          <formGroup width="50" fieldClass="special">

          </formGroup>
        </formGroup>
        <formGroup width="-" fieldClass="blue heigth200">

        </formGroup>
      </formGroup>
      <formGroup width="100%" fieldClass="violet heigth500"> 
        
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[ 
    ]]>
      </text>
    </query>
  </script> 
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="" e="" o=""></text>
    </button> 
  </buttons>

  <css>
    <text>
      <![CDATA[  
{
    "red":{ 
      "backgroundColor":"red"
    },
    "green":{ 
      "backgroundColor":"green"
    },
    "pink":{ 
      "backgroundColor":"pink"
    },
    "blue":{ 
      "backgroundColor":"blue"
    },
    "violet":{
      "backgroundColor":"violet"
    },
    "heigth100":{
      "height":100
    },
    "heigth200":{
      "height":200
    },
    "heigth500":{
      "height":500
    },
    "special":{
      "height":50,
      "backgroundColor":"yellow",
      "margin":75
    }
}
    ]]>
    </text>
  </css>
</dir>
```

<figure><img src="../.gitbook/assets/image (70).png" alt=""><figcaption></figcaption></figure>
