---
description: Hàm dùng để show một hình ảnh lớn
---

# showFullImage

**Return type:** void

**Arguments:** (image\_uri: string, header\_Authorization:string)

* **image\_uri:** strin&#x67;**,** required, màn hình sẽ show ra ảnh này, format: fileId (công ty Arito) sẽ mở dưới dạng private0 hoặc url có http
* **header\_Authorization**: string, required, app sẽ dùng field authorization để chứng thực với server để show ra ảnh

**Example:**

```javascript
p.showFullImage("https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Domestic_Goose.jpg/250px-Domestic_Goose.jpg")
```
