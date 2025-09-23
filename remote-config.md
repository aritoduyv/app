# Remote config

## I. Giới thiệu

## II. Các khai báo remote config và ý nghĩa của nó đối với app

1. **Khai báo secret**

* name: string, giá trị là "secret"
* value: string, secret của app, ví dụ:&#x20;

```
TjdhcUFsZEswVnE3L1JjODBmOEorZDdHNmJjV1RwSGdMazk2UGtiYkxRWHZRRmhFTTQwSG82bVFJcHJXbitRU3ErYnNBUVJZUlJIamhIM3BpcGFXWXN1OVpncFAySGpqcmVDOGVMOThKSklLQjU5YVBpa3BaTWJla3RvendCbC9rN0pCNGpjNGF6MDZoWHpXWXFPTHptQT09
```

2. **Khai báo host url**

* name: string, giá trị là "url"
* value: string, url của app, ví dụ:

```
https://appapi.arito.vn/api/v1
```

3. **Khai báo config của secret cụ thể**

* name: string, secret mà client sử dụng, ví dụ:

```
TjdhcUFsZEswVnE3L1JjODBmOEorZDdHNmJjV1RwSGdMazk2UGtiYkxRWHZRRmhFTTQwSG82bVFJcHJXbitRU3ErYnNBUVJZUlJIamhIM3BpcGFXWXN1OVpncFAySGpqcmVDOGVMOThKSklLQjU5YVBpa3BaTWJla3RvendCbC9rN0pCNGpjNGF6MDZoWHpXWXFPTHptQT09
```

* value: string, ví dụ:

```
{"isForgetPassword":"https://id.arito.vn/forgetpass", "isRegister":"https://id.arito.vn/register"}
```

* config có thể chứa các giá trị sau:
  * isForgetPassword: string, link quên mật khẩu, nếu không khai thì ẩn link bấm
  * isRegister: string, link đăng ký tài khoản, nếu không khai thì ẩn link bấm
  * logo: string, link ảnh, nếu không khai thì sử dụng ảnh mặc định trên app
