# Sysmenu

## 1. Giới thiệu

Màn hình sysmenu là màn hình chức năng với công dụng thể hiện thông tin người dùng, menu, và các tính năng cứng như đổi mật khẩu, đăng xuất

<figure><img src="../.gitbook/assets/image (51).png" alt="" width="360"><figcaption><p>Màn hình sysmenu</p></figcaption></figure>

## 2. Khai báo menu

Danh sách menu được khai trong bảng sysmenu3

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

id là id của menu

id0 là menu cha&#x20;

text, text2, text3 là tiêu đề tương ứng với 3 ngôn ngữ v, e, o

controller là tên controller sẽ được sử dụng

xtype:&#x20;

* EXPAND là accordion, thường sẽ được dùng trong menu cha
* LIST là màn hình list, khi bấm vào sẽ show ra list
* FORM là màn hình form, khi bấm vào sẽ show ra form
* SCREEN là màn hình cứng trên app
* BUTTON, khi bấm vào sẽ chạy sự kiện button click với id là controller

icon là thể hiện icon bên trái của text

status: là có sử dụng menu đó hoặc không



