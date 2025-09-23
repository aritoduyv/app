# AListItemMonthView

## 1. Giới thiệu

AListItemMonthView được dùng để show lịch trong vòng 1 tháng

1 item gồm 7 field, tương ứng với CN, Thứ 2, Thứ 3,... Thứ 7

## 2. Khai báo xml

Các field sẽ có name là :  T1, T2, T3, T4, T5, T6, T7 tương ứng CN-> T7

## 3. Data

* Từ field T1->T7 có data như sau: Date + \[char(255) + id + char(254)+text+char(254)+color+char(254)+fontColor +char(254)+borderColor+char(254)+fontSize+char(254)+wrap]
  * **Date**: required, Kiểu ngày yyyy-MM-ddThh:mm:ss
  * **id:** string, required, id của sự kiện
  * **text:** string, nội dung sự kiện
  * **color:** Màu background của sự kiện
  * **fontColor:** Màu của text nội dung sự kiện (version>= 1.3.20)
  * **borderColor:** Màu của border  (version>= 1.3.20)
  * **fontSize:** optiona&#x6C;**,** kiểu số, phải parseInt được, là kích cỡ chữ
  * **wrap:** optional, kiểu any, chỉ cần có giá trị là wrap

## 4. Css

Không nhận css

## 5. Target

Khi user bấm vào sự kiện, target là id của sự kiện

## 6. Ví dụ

Màn hình hrbcc

<figure><img src="../.gitbook/assets/image (21).png" alt="" width="360"><figcaption></figcaption></figure>
