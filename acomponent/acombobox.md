# ACombobox

## 1. Giới thiệu

ACombobox được dùng để hiển thị dropdown cho user lựa chọn. ACombobox có 2 loại là chọn 1 (single) và chọn nhiều (multi), nhưng hiện tại chỉ mới test trên chọn 1 nên khuyến khích dùng chọn 1. Nếu muốn chọn nhiều thì nên dùng ALookup

## 2. Khai báo xml

* **componentName:** ACombobox
* **hidden:** "true" hoặc "false", có ẩn hay không
* **name:** Tên field
* **readOnly**: "true" hoặc "false", chỉ đọc hay không, nếu true thì khi ấn sẽ không ăn&#x20;
* **text:** Tiêu đề của combobox nếu chưa chọn option nào
* **viewInfo**
  * **options**
    * &#x20;**option:** Gồm val và text, val là giá trị còn text là phần hiển thị
* **width:** Độ rộng của combobox, khai báo bằng đơn vị % hoặc số

## 3. Data

AComponent này sau khi nhận data nó sẽ show option được chọn với val = data.

## 4. Css

AComponent này không nhận css

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
      <formGroup>
        <fields>
          <field name="testCombobox" viewType="Combobox" componentName="ACombobox" width="100%">
            <text v="Loại đơn từ" e="Type" o="Type"></text>
            <viewInfo>
              <options>
                <option val="0">
                  <text v="Tất cả" e="All" o="All"></text>
                </option>
                <option val="1">
                  <text v="test1" e="" o=""></text>
                </option>
                <option val="2">
                  <text v="test2" e="" o=""></text>
                </option>
              </options>
            </viewInfo>
          </field>

          <field name="testCombobox2" viewType="Combobox" componentName="ACombobox" width="100%">
            <text v="Loại đơn từ 2" e="Type" o="Type"></text>
            <viewInfo>
              <options>
                <option val="0">
                  <text v="Tất cả" e="All" o="All"></text>
                </option>
                <option val="1">
                  <text v="test1" e="" o=""></text>
                </option>
                <option val="2">
                  <text v="test2" e="" o=""></text>
                </option>
              </options>
            </viewInfo>
          </field>
          
          <field name="ma_loai_tk" viewType="Combobox" componentName="ACombobox" width="100%">
            <text v="Phân loại tài khoản" e="Account Type" o="Account Type"></text>
            <viewInfo>
              <options query="select ma_loai_tk, ten_loai_tk[%lg] from dmloaitk where status = 1 order by stt">
              </options>
            </viewInfo>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select '2' as testCombobox2
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

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>
