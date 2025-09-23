# emitSocket

**Return type:** void

**Arguments:** (receiverId, data)

* **receiverId**: string, required, socketId của web
* **data:** any, required, data mà app muốn gửi cho web

**Example:**

```javascript
 p.emitSocket(receiver_id, "Bây giờ thời gian trên app là "+Date.now())
```
