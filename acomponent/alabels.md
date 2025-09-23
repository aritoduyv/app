# ALabels

## 1. Giới thiệu

ALabels được dùng để hiển thị nhiều dòng ALabel, thay vì phải khai báo từng ALabel trên xml

## 2. Khai báo xml&#x20;

Các thẻ và thuộc tính cần khai

* field: xml, là thẻ khai component
* name: string (required), là thuộc tính tên trường (cột) nhận data
* width: string (required), là độ rộng của component
* componentName: string (required), khai báo ALabel để sử dụng
* text: string (optional), khai báo phần text của ALabel, nếu không khai thì sẽ không hiển thị phần text

## 3. Data

ALabel sử dụng data là mảng 2 chiều được parse ra từ kết quả trả về là chuỗi

Trong các mảng con sẽ có 2 items, item thứ nhất sẽ đóng vai trò là text, item thứ 2 sẽ là value

Ví dụ: "\[\["Mã nhà cung cấp", "NCC03"],\["Tổng tiền", "5060000.00000"],\["Ngoại tệ", "VND"],\["Loại chứng từ", "5. Đơn hàng"]]"

## 4. Css&#x20;

ALabels khi khai css sẽ áp dụng lên toàn bộ ALabel bên trong nó, phần css sẽ được tác động lên text và value. Ta khai text\_\* và value\_\*, trong đó \*  là [thuộc tính style](../css.md#cac-thuoc-tinh-style)&#x20;

Style mặc định

* text\_color: string, mặc định "#172b4d"
* text\_witdh: number, mặc định là 100
* text\_paddingRight: number, mặc định 4
* &#x20;text\_fontSize: number, mặc định 16
* value\_color: string, mặc định "#172b4d"
* value\_flex: number, mặc định 1
* value\_fontSize: number, mặc định 16

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
      <text v="Danh sách khách hàng" e="" o=""></text>
      <formGroup width="100%">
        <fields>
          <field name="ds_kh" width="18" componentName="ALabels">
          <text v="Danh sách khách hàng" e="" o=""></text>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms> 
  <script>
    <query>
      <text>
        <![CDATA[  
select N'[["Mã nhà cung cấp", "NCC03"],["Tổng tiền", "5060000.00000"],["Ngoại tệ", "VND"],["Loại chứng từ", "5. Đơn hàng"]]' as ds_kh
      ]]>
      </text>
    </query>
  </script> 
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button> 
  </buttons> 
</dir>
```

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>
