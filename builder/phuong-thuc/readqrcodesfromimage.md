---
description: Dùng để đọc qrcodes từ ảnh
---

# readQrCodesFromImage

**Return type:** Promise Object

```json
{
   "qrcodes":[
      {
         "cornerPoints":[
            {
               "y":1509,
               "x":1218
            },
            {
               "y":1513,
               "x":2036
            },
            {
               "y":2321,
               "x":2026
            },
            {
               "y":2325,
               "x":1223
            }
         ],
         "type":256,
         "data":"http://en.m.wikipedia.org",
         "bounds":{
            "size":{
               "width":818,
               "height":816
            },
            "origin":{
               "y":1509,
               "x":1218
            }
         }
      },
      {
         "cornerPoints":[
            {
               "y":2984,
               "x":1948
            },
            {
               "y":2982,
               "x":2528
            },
            {
               "y":3545,
               "x":2517
            },
            {
               "y":3555,
               "x":1944
            }
         ],
         "type":256,
         "data":"https://lightburnsoftware.com/collections/merchandise/products/swag-pack",
         "bounds":{
            "size":{
               "width":584,
               "height":573
            },
            "origin":{
               "y":2982,
               "x":1944
            }
         }
      }
   ]
}
```

**Arguments:** ({ imageUrl, localUrl, base64})

* **imageUrl:** link ảnh
* **localUrl:** link file ảnh trên máy
* **base64:** base64 của ảnh

{% hint style="warning" %}
Lưu ý: ảnh phải là format png hoặc jpg và yêu cầu nhập chính xác 1 trong 3 nguồn
{% endhint %}

**Example:**

```javascript

p.readQrCodesFromImage({imageUrl:"https://i0.wp.com/www.cssscript.com/wp-content/uploads/2020/03/SVG-Based-QR-Code-Generator-QRcode.js.png"}).then((results)=>{
        console.log(results);
})
p.readQrCodesFromImage({localUrl:"file:///data/user/0/com.arito.erp/cache/rn_image_picker_lib_temp_d03884ee-cd3a-4655-8cd8-5573fd989e3d.jpg"}).then((results)=>{
      console.log(results);
});
let base64 = "iVBORw0KGgo..."
p.readQrCodesFromImage({base64}).then((results)=>{
        console.log(results);
});
```
