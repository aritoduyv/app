# ADeleteRow

## 1. Giới thiệu

Với mục đích để user có thể xóa item của list (list nằm trên form), thì lập trình viên khai báo ADeleteRow trên xml để có thể hiển thị nút xóa đó.

Component liên quan: [ANumberedOrder](anumberedorder.md)

## 2. Khai báo xml

Các thông tin cần khai báo:

* width: Độ rộng của component, khai báo dưới dạng số hoặc phần trăm

## 3.  Data

AComponent này không sử dụng data

## 4. Css

AComponent này không css được

## 5. Ví dụ

```xml
<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="Hướng dẫn sử dụng" e="Debug Duy" o="Debug Duy"></title> 

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
            <field name="deleteRow" width="10%" componentName="ADeleteRow">
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

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption><p>Ví dụ sau khi bấm vào item xóa nguyễn văn A</p></figcaption></figure>
