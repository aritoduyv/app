# handleListItemLongPress

## 1. Giới thiệu

handleListItemLongPress  là hàm sẽ được gọi ngay khi người dùng bấm giữ vào item ở trên list, trừ những [AListItem](../alistitem/) chỉ cho phép bấm một số khu vực nhất định.

## 2. Định nghĩa hàm

**Return type:** any

**Arguments:** ({listName, memvars, itemData, p, target, rowIndex})

* **memvars:** Memvars, memvars này được sinh ra tự động từ fieldKey của list
* **itemData:** Object, required,là data của của item&#x20;
* **p:** Builder, required, là builder của màn hình
* **target:** string, là tên field thể hiện vị trí mà user đã bấm trên item, ví dụ "avatar", "ma\_vt", ...
* **listName:** string, optional, tên list mà hàm này tác động vào. Nếu không truyền thì mặc định sẽ sử dụng list đầu tiên (thường dùng cho list view), nếu truyền thì sẽ dùng listNametrong dataTable (trong tình huống list nằm trong form)
* **rowIndex:** number (optionsal), số thự tự dòng của item trong data

