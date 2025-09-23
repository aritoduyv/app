# AClock

## 1. Giới thiệu

AClock được dùng để hiển thị thời gian trên điện thoại hiện tại

## 2. Khai báo xml

* **componentName:** AClock
* **name:** Tên field
* **width:** Độ rộng của component, nên là "100%"

## 3. Data

* AComponent này nhận data là kiểu ngày. Nếu AComponent nhận được data (từ valForm hoặc từ khởi tạo mặc định), thì đồng hồ sẽ ngừng đếm, ngược lại nó sẽ chạy liên tục

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
          <field name="thoi_gian_1" width="100%" componentName="AClock">
            <text v="=" e="" o="" />
          </field>
          <field name="thoi_gian_2" width="100%" componentName="AClock">
            <text v="=" e="" o="" />
          </field>
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[
select '2024-11-20T15:16:21.000' as thoi_gian_2
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

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

Ở ví dụ trên, đồng hồ đầu tiên sẽ chạy liên tục vì không có data, trong khi đồng hồ thứ 2 sẽ dừng tại thời điểm 2024-11-20T15:16:21.000
