# AHeader

## 1. Giới thiệu

AHeader là phần header của màn hình (một màn hình gồm 2 thành phần header và body). Các thành phần của AHeader bao gồm 1 button bên trái, 1 tiêu đề và danh sách các buttons bên phải.

Nếu chỉ có  nhỏ hơn (<) 2 button bên phải thì app sẽ hiển thị ra button(s), ngược lại app sẽ hiển thị ra menu

## 2. Khai xml

AHeader được builder sử dụng để xây dựng nên header, trên xml sẽ khai trong thẻ \<title> và \<buttons>&#x20;

Với thẻ title khai tên tiêu đề. Lưu ý thứ tự ưu tiên tiêu đề từ: setTitle, title truyền từ màn hình cha, title nhận được data, rồi mới tới thẻ title

Với thẻ buttons khai các thành phần sau: image, text, label. với độ ưu tiên (label > image > text)

image là icon của button (thuộc bộ [https://simplelineicons.github.io/](https://simplelineicons.github.io/))&#x20;

text là tên button, nó sẽ được sử dụng nếu image không có.

label là tên button, nó sẽ được sử dụng nếu được khai

## 3. Data

Data mà component này nhận được chỉ là $title (nó có thể là messageId) để set lại title ví dụ:

```sql
select N'Tiêu đề mới' as $title
```

## 4. Css

AComponent này không css được

## 5. Các button đặc biệt

Các button được coi là đặc biệt khi mà nó có sự kiện riêng của nó mà không cần phải gọi trong beforeButtonDialogClick (nếu có khai báo thì hàm trong beforeButtonDialogClick sẽ chạy trước), các id đó bao gồm:

* **cancel:** Khi ấn nút này, app sẽ tự động goback về màn hình trước
* **copy (chưa test lại):** Khi ấn nút này, app sẽ mở [form ](../man-hinh/form.md)với action là NEW và data màn hình được mở sẽ là data của màn hình cần copy
* **lookupSave:** Button đặc biệt của [màn hình lookup](../man-hinh/lookup.md), khi ấn, nó sẽ gán giá trị được chọn về [ALookup](alookup.md)
* **ok:** Khi ấn nút ok, app sẽ tạo ra memvars từ form,  nếu đang ở trong trạng thái form là NEW, thì app sẽ gọi request code là "beforesave,insert,aftersave". Nếu ở trong trạng thái form là EDIT, thì app sẽ gọi request code là "beforesave,update,aftersave". Nếu đang trong trạng thái VIEW thì chả làm gì cả
* **reload:** Khi nút này được bấm, nó sẽ reload lại form hoặc list. Hàm [afterInit ](../js/afterinit.md)có thể bắt được sự kiện này với initType =="RELOAD"
* **refresh:** Hàm này làm nhiệm vụ y chang hàm reload, chỉ khác cái tên
* **view:** Button này chưa làm gì cả
* **delete:** Khi button này được bấm, nó sẽ hỏi câu $VoucherDelete, nếu người dùng tiếp tục ấn có thì app sẽ tạo memvars và gửi lên server với request code là delete, nếu delete thành công thì nó sẽ goback về màn hình trước
* **edit(chưa test):** Nếu là màn hình view (dấu hiệu là \_v), thì app sẽ lấy data của màn hình view và tạo ra màn hình form với action là EDIT
* **filter:** Khi bấm vào button với id này, nó sẽ tự động show ra màn hình filter (thư mục form) với controller của màn hình filter là controller màn hình list + \_filter
* **find:** Chưa cài đặt sự kiện cho button này
* **logout:** Khi ấn button này thì người dùng sẽ đăng xuất trên server, sau đó đăng xuất trên app để về màn hình login.

## 6. Ví dụ

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
      <field/>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[ 
select N'Tiêu đề đã bị thay đổi' as [$title]
    ]]>
      </text>
    </query>
  </script> 
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="" e="" o=""></text>
    </button>
    <button id="filter" image="filter">
      <text v="" e="" o=""></text>
    </button>
    <button id="ok" image="check">
      <text v="Lưu" e="" o=""></text>
    </button> 
    <button id="delete" image="trash">
      <text v="xoá" e="" o=""></text> 
    </button>
  </buttons> 
</dir>
```

<figure><img src="../.gitbook/assets/image (71).png" alt=""><figcaption><p>Hình bên trái là tiêu đề đã bị thay đổi do nhận $title từ server, hình bên phải là khi ấn vào nút 3 chấm (menu)</p></figcaption></figure>
