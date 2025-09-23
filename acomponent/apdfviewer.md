# APDFViewer

## 1. Giới thiệu

APDFViewer được dùng để hiển thị file pdf (file không có mật khẩu), component này sẽ hiển thị pdf dạng thumbnail, khi click vào thumbnail thì sẽ hiển thị ra đầy đủ

## 2. Khai báo xml

APDFViewer thuộc loại field

Các thẻ và thuộc tính cần khai

* **name:** field name sẽ nhận data từ query của sql
* **width:** Giá trị độ rộng, phần trăm hoặc số
* **componentName:** khai là APDFViewer
* **fieldClass:** Tên class css

## 3. Data

* Kiểu dữ liệu: String, nhằm thể hiện url
* Component sẽ sử dụng url để tải và hiển thị pdf

## 4. Css

* Css khai báo sẽ tác động lên layout của component, có thể thay đổi width, height, padding, margin, ...

## 5. Ví dụ

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
          <field name="pdf_url" width="80%" componentName="APDFViewer" fieldClass="pdfViewer"/> 
				</fields>
			</formGroup>
		</form>
	</forms> 
	<buttons>
		<button id="cancel" image="arrow-left-circle">
			<text v="" e="" o=""></text>
		</button>
	</buttons>
  <script>
    <query>
      <text>
        <![CDATA[  
select 'file_id' as pdf_url
        ]]>
      </text>
    </query>
  </script>
</dir>
```

<figure><img src="../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>
