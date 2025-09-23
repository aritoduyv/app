---
description: Dùng để hiển thị trang web trên app với cookie của arito, phiên bản >= 1.3.8
---

# showWebWithAritoKeycloak

**Return type:** void

**Arguments:** ({url, title, titleStatus, ud\_id, isRedirect, cacheRedirect, cookiesData})

* **url:** required, string, là đường dẫn của trang web
* **title:** optional, string, là tiêu đề của trang web, nếu tiêu đề không tồn tại hoặc trắng, thì app sẽ dùng tiêu đề của web là tiêu đề&#x20;
* **ud\_id**: required, string, id của ứng dụng
* **titleStatus:** optional, string, thể hiện trạng thái của title. Gồm 3 giá trị "FULL", "HIDDEN" và "NOMENU"
  * HIDDEN: Được dùng để ẩn title
  * NOMENU: Được dùng để ẩn toàn bộ header, nút back sẽ được đưa vào màn hình web&#x20;
  * FULL: Không ẩn gì hết&#x20;
* **isRedirect**: required, boolean, để app biết được nên dùng keycloak\_opening hay keycloak\_client lúc set cookie
* **cacheRedirect:** optional, default: false, có sử dụng cache domain hay không, ví dụ khi vào qlnb.arito.vn, thì server sẽ redirect sang qlnb3.arito.vn:44330, về sau nếu cacheRedirect được bật (true) thì app sẽ tự replace và vào thẳng qlnb3.arito.vn:44330 mà không cần thông qua server qlnb.arito.vn nữa
* **cookiesData:** optional, type: \[] cookieData, default \[], danh sách cookie muốn ghi thêm vào app
  * cookieData
    * &#x20;url: required, string, ví dụ https://example.com
    * name: required, string, ví dụ "keycloak"
    * value: string, required, ví dụ: "ABC"
    * path: string, optional, default "/"
    * domain: string, required, ví dụ ".arito.vn"
    * version: string, optional, default: "1", ví dụ "1", "0";
    * expires: string, optional, default: Ngày hôm sau, format: "yyyy-MM
    * ddTHH:mm:ss.sss+HH:MM" hoặc "yyyy-MM-ddTHH:mm:ss.sss-HH:MM"
    * secure: boolean,optional, default false;
    * httpOnly: boolean,optional, default false;

Example:

```javascript
p.showWebWithAritoKeycloak({url:"https://example.com", title:"test", isRedirect:false})
p.showWebWithAritoKeycloak({url:"https://example.com", title:"test", titleStatus:"NOMENU", ud_id: "3652",isRedirect: true}) 
```
