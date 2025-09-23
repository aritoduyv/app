# ANumberedOrder

## 1. Giới thiệu

Component hỗ trợ này được dùng để đánh số thứ tự item trên list (list trong form)

AComponent liên quan: [ADeleteRow](adeleterow.md), được dùng để xóa dòng

## 2. Khai báo xml

Các thông tin cần khai báo:

* width: Độ rộng của component, khai báo dưới dạng số hoặc phần trăm

## 3. Data

AComponent này không sử dụng data

## 4. Css

AComponent này sử dụng css tác động lên phần text, ví dụ có thể css để tô đậm, tăng kích thước, canh giữa,...

## 5. Ví dụ

```xml
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="Hướng dẫn sử dụng" e="" o=""></title> 

  <forms>
    <form componentName="AAccordion" image="people" collapse="false">
      <text v="Danh sách khách hàng" e="" o=""></text>
      <formGroup width="100%">
        <fields>
          <field name="approvers" width="100%" componentName="Custom" viewType="List">
            <text v="Danh sách khách hàng" e="" o=""></text>
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <grids>
    <grid id="approvers" fieldKey="line" readOnly="true">
      <form>
        <formGroup width="100%">
          <fields>
            <field name="stt" width="18" componentName="ANumberedOrder" fieldClass="SttInItemList">
              <text v="stt" e="" o=""></text>
            </field>
            <field name="ten_kh" width="70%" componentName="ALabel" readOnly="true">
              <text v="" e="" o=""></text>
            </field> 
          </fields>
        </formGroup>
      </form>
      <script>
        <query>
          <text>
            <![CDATA[
select 'Nguyen Van A' as ten_kh, 1 as line union select 'Tran Van B' as ten_kh, 2 as line
union
select 'Dang Van C' as ten_kh, 3 as line union select 'Tran Van D' as ten_kh, 4 as line
            ]]>
          </text>
        </query>
      </script>
    </grid>
  </grids>
  <script>
    <query>
      <text>
        <![CDATA[ 
select 1
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
    <button id="cancel" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button> 
  </buttons> 
</dir>
```

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>
