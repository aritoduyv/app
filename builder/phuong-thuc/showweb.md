---
description: Dùng để hiển thị trang web trên app
---

# showWeb

**Return type:** void

**Arguments:** ({url, title, incognito, titleStatus})

* **url:** required, string, là đường dẫn của trang web
* **title:** optional, string, là tiêu đề của trang web, nếu tiêu đề không tồn tại hoặc trắng, thì app sẽ dùng tiêu đề của web là tiêu đề&#x20;
* **incognito**: optioanl, boolean, mặc định là false, mở trang web với chế độ ẩn danh hay không. Mỗi lần showWeb với chế độ ẩn danh là true thì đây được xem như là một trình duyệt mới, không có lưu trữ lại cookie của lần showWeb trước (kể cả lần show trước là ẩn danh hay không)
* **titleStatus:** optional, string, thể hiện trạng thái của title. Gồm 3 giá trị "FULL", "HIDDEN" và "NOMENU"
  * HIDDEN: Được dùng để ẩn title
  * NOMENU: Được dùng để ẩn toàn bộ header, nút back sẽ được đưa vào màn hình web&#x20;
  * FULL: Không ẩn gì hết&#x20;



Example:

```javascript
p.showWeb({url:"https://example.com", title:"test})
p.showWeb({url:"https://example.com", title:"test, titleStatus:"NOMENU"}) 
```
