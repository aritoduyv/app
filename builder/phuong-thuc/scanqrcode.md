---
description: >-
  Dùng để quét qr code, có thể gọi trực tiếp bằng hàm AScanQR mà không cần thông
  qua builder
---

# scanQrCode

**Return type:** void

**Arguments:** ({data})

* data:&#x20;
  * data.visible: required, boolean: có mở camera lên hay không
  * data.isAccuracy: required, boolean, nếu là false thì khi quét, camera sẽ bắt qr code đầu tiên nó bắt được, nếu là true, camera sẽ cho phép người dùng tự chọn qr code (trong tình huống nhiều qr)
  * callback: function(qrdata) sau khi thực hiện qr code

**Example:**

<pre class="language-javascript"><code class="lang-javascript"><strong>p.scanQrCode({
</strong>  data: {
    callback: function (stringQR) {
      //web, type-data, còn lại (hiện textbox lên)
      if (stringQR.startsWith('http://') || stringQR.startsWith('https://')) {
        p.getMessage('$questionGotoSite').then(msg => {
          let func = v => {
            if (v) p.showWeb({url: stringQR});
          };
          p.question({message: msg + ' \n' + stringQR, func});
        });
      } else {
        try {
          let qr = JSON.parse(stringQR);
          if (qr.hasOwnProperty('type') &#x26;&#x26; qr.hasOwnProperty('data')) {
            if (qr.type == 'Item') {
         
            }
          } else {
            //Trường hợp ngược lại, hiện textbox lên
            p.showTextBox({message: stringQR});
        
          }
        } catch (e) {
          //Trường hợp ngược lại, hiện textbox lên
          //p.showTextBox({message: stringQR});
          let memvars = {ma_vt: stringQR};
          p.showForm('hwsanpham_v', {memvars: memvars, action: 'VIEW'});
        }
      }
    },
    isAccuracy: true,
    visible: true,
  },
});
</code></pre>
