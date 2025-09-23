# ConfigTable

ConfigTable là thông tin cấu hình của một màn hình. Mọi màn hình list, form, filter, lookup đều có config riêng của nó. Nó được sinh ra như sau: dev code xml, từ xml => json (lúc app gọi lấy cấu  hình), từ json => class (app sẽ biến đổi thành dạng app sử dụng được)

Cách xem configTable: p.options.configTable hoặc[ **p.options.configSet.get(index)**](configset.md#phuong-thuc)&#x20;

Định nghĩa class

## Thuộc tính

config: là object lấy được từ server

name: tên cấu hình

state: được dùng để quản lý các component trên màn hình
