# Filter

## 1. Giới thiệu

Màn hình filter được mở ra sau khi ấn button với id = filter trên màn hình list

controller của màn hình filter = controller màn hình list + \_filter

Định nghĩa màn hình filer trong thư mục Form/controller.xml

## 2. Luồng

Khi ấn filter trên List, memvars trên List sẽ truyền qua màn hình Filter. Màn hình filter có thể query dựa trên memvars này

Khi ấn nút "Lọc" trên màn hình filter, memvars của màn hình filter sẽ kết hợp (ghi mới và ghi đè lên memvars của màn hình List), sau đó List sẽ tự động reload lại, có thể bắt sự kiện reload của list thông qua afterInit(p, initType) với initType="FILTER".

## 3. Lưu ý

Hiện chỉ có 1 cách để mở màn hình filter là ấn vào button với id là filter

