# AEkyc

## 1. Giới thiệu

AEkyc được dùng để hiển thị để cập nhật thông tin Ekyc người dùng hiện tại

## 2. Khai báo xml

* **componentName:** AEkyc&#x20;
* **name:** Tên field
* **width:** Độ rộng của component, nên là "100%"
* **hidden:** Có ẩn hay không
* **readOnly:** Có chỉ đọc

Thẻ viewInfo gồm thông tin sau:

* **custom**: các giá trị có thể có trong custom là phone,face,idCards,useAI&#x20;
  * phone: có hiển thị view phone không
  * face: có hiển thị phần face không
  * idCards: có hiển thị phần idCards không
  * useAI: khi verify có dùng AI không
  * phoneAccordion: mặc định có show accordion của phone không
  * faceAccordion: mặc định có show accordion của face không
  * idCardsAccordion: : mặc định có show accordion của idCards không
  * checkIdCardsWithImage: mặc định là không, có kiểm tra idCards trùng với face ảnh khi upload id cards hay không? (phiên bản ≥ 1.3.21)

## 3. Data

* Component này không nhận data

## 4. Css

* Component này không nhận css

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="Xác thực eKYC" e="eKYC Authentication" o="eKYC Authentication"/>
  <forms>
    <form>
      <formGroup>
        <fields>
          <field name="updateImageEkyc" width="100%" componentName="AEkyc" hidden="false">
			  <viewInfo custom="phone,face,idCards,useAI"></viewInfo>
            <text v="update Image Ekyc" e="update Image Ekyc" o="update Image Ekyc"></text>
          </field>
        </fields>
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

  <js>
    <text>
      <![CDATA[   
      ]]>
    </text>
  </js>

  <buttons>
    <button id="cancel" image="arrow-left">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button>
  </buttons>
  <messages>
    <message val="abc">
      <text v="Message abc " e="Message abc " o="Message abc "/>
    </message>
  </messages>
</dir>
```

<figure><img src="../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>
