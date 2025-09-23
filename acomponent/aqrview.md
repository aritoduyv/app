# AQRView

## 1. Giới thiệu

AQRView hiển thị qrCode

## 2. Khai báo xml

AQRView  thuộc loại field

Các thẻ và thuộc tính cần khai

* **name:** field name sẽ nhận data từ query của sql
* **width:** Giá trị độ rộng, phần trăm hoặc số
  * Lưu ý QRView luôn luôn chiếm 100% độ rộng
* **componentName:** khai là APDFViewer
* **fieldClass:** Tên class css

## 3. Data

* Kiểu dữ liệu: String, nhằm thể hiện giá trị của qrcode&#x20;

## 4. Css

* Các giá trị css khai được là
  * **size**: number, optional, mặc định 56, kích cỡ qrcode
  * **color**: string, optional, mặc định là #000,  màu của qrcode
  * **backgroundColor**: string, optional, mặc định là #fff, màu của background
  * **level**: string, optional, mặc định là "L", các giá trị có thể khai là "L", "M",  "Q", "H", đây là độ sửa lỗi của Qrcode (mức càng cao thì app sẽ gen ra nhiều điểm hơn để chống lại việc qrcode bị mờ hoặc bị rách, còn nếu chỉ view trên app thì ưu tiên dùng L)
  * **position**: string, optional, mặc định là "left", các giá trị có thể khai là "left", "center", "right", vị trí của qrcode theo chiều ngang

<figure><img src="../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE dir [

	
<!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
<!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>
<dir id="@@controller" fieldKey="id" >
	<title v="AQRView" e="" o=""></title>
	<forms>
		<form>
			<formGroup>
				<fields>
					<field name="field0" width="100%" componentName="AQRView"></field>
					<field name="field1" width="100%" componentName="AQRView" fieldClass="fieldClass1"></field>
					<field name="field2" width="100%" componentName="AQRView" fieldClass="fieldClass2"></field>
					<field name="field3" width="100%" componentName="AQRView" fieldClass="fieldClass3"></field>
				</fields>
			</formGroup>
		</form>
	</forms>
	<script>
		<query>
			<text>
				<![CDATA[
select 'https://example.com/' as field1, 'https://wiki.arito.vn/view/6725a950cd089998a859372e' as field2, 'sss' field3
    ]]>
			</text>
		</query>
	</script>
	<css>
		<text>
			<![CDATA[ 
{
  "fieldClass1":{
	"color":"red",
    "backgroundColor":"green",
	"position":"left",
	"size": 30,
	"level":"L"
  },
  "fieldClass2":{
	"color":"green",
    "backgroundColor":"blue",
	"position":"center",
	"size":60,
	"level":"Q"
  },
  "fieldClass3":{
	"color":"pink",
	"position":"right",
	"size":90,
	"level":"H"
  }
}
    ]]>
		</text>
	</css>
	<js>
		<text>
			<![CDATA[  
afterInit = (p, initType)=>{
	setTimeout(()=>{
		p.valForm("field0", "this value change");
	},20000)
}
      ]]>
		</text>
	</js>
	<buttons>
		<button id="cancel" image="arrow-left-circle">
			<text v="" e="" o=""></text>
		</button>
	</buttons>
</dir>
```
