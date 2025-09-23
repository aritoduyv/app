---
description: Hàm được dùng để chọn (chụp ảnh), sử dụng từ phiên bản 1.1.34
---

# pickImage

**Return type:** void

**Argument:** (viewInfo, callback)

* **viewInfo**:
  * &#x20;**allowCamera**: string|boolean, required, Có cho phép chụp ảnh không
  * **allowLibrary**: string|boolean, required Có cho phép chọn ảnh từ thư viện không
  * **isMulti**: string|boolean, required, có cho phép chụp/chọn nhiều không
  * **maxImageSize**: string, required, size ảnh tối đa
  * **fileFieldId0**: string, required, fileId0
  * **fileGroup**: string, required, xgroup
* **callback**
  * **fileIds: \[String],** sau khi chụp/chọn ảnh thì sẽ có mảng các fileId của ảnh,&#x20;

**Example:**&#x20;

```javascript
p.pickImage({ 
   allowCamera:true,
   allowLibrary:true,
   isMulti:false,
   maxImageSize:"1000,1000",
   fileFieldId0:"123456",
   fileGroup: "test"
},(fileIds)=>{
 //do something with fileIds
})
```
