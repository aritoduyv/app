# ALabel

## 1. Giới thiệu

ALabel là một component được dùng để hiện thị 2 thành phần text (khai trong xml) và value (data từ database).

ALabel không thể chỉnh sửa với thao tác người dùng, tuy nhiên nó có thể chỉnh sửa thông qua một số hàm (ví dụ valForm) của [builder](../builder/) khai báo trong thẻ [js](../js/)

## 2. Khai báo xml

ALabel thuộc loại field

Các thẻ và thuộc tính cần khai

* **field**: xml, là thẻ khai component
* **name**: string (required), là thuộc tính tên trường (cột) nhận data
* **width**: string (required), là độ rộng của component
* **componentName**: string (required), khai báo ALabel để sử dụng
* **text**: string (optional), khai báo phần text của ALabel, nếu không khai thì sẽ không hiển thị phần text
* **hidden**: Có ẩn hay không, mặc định là không

## 3. Data

Data được dùng để hiển thị value.&#x20;

* Kiểu dữ liệu: string
* Ví dụ: "Nguyễn văn A", "03994444", "BAO", ...

## 4. Css&#x20;

ALabel khi khai css, thì phần css sẽ được tác động lên text và value của ALabel. Ta khai text\_\* và value\_\*, trong đó \*  là [thuộc tính style](../css.md#cac-thuoc-tinh-style)&#x20;

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
<forms>
    <form>
      <formGroup>
        <fields>  
          <field name="ten_kh" width="100%" componentName="ALabel" fieldClass="css1">
            <text v="Tên khách hàng" e="" o=""></text>
          </field> 
          <field name="mst" width="100%" componentName="ALabel" fieldClass="css2">
            <text v="Mã số thuế" e="" o=""></text>
          </field>
          <field name="sdt" width="100%" componentName="ALabel" fieldClass="css3">
            <text v="Số điện thoại" e="" o=""></text>
          </field>
        </fields>
      </formGroup>
    </form>  
  </forms>   
  <script>
    <query>
      <text>
        <![CDATA[   
select 'abc' as ten_kh, '2365522-001' as mst, '0399444445' as sdt
        ]]>
      </text>
    </query>
  </script>
  <css>
    <text>
    <![CDATA[
{
  "css1":{
    "text_fontWeight":"bold",
    "text_width":200
  },
  "css2":{
    "value_fontStyle":"italic",
    "value_fontSize":20
  },
  "css3":{
    "text_color":"red",
    "value_color":"blue"
  }
}
    ]]>
    </text>
  </css>
```

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>
