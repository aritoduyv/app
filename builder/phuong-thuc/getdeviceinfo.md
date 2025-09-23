---
description: Dùng để lấy thông tin thiết bị của người dùng
---

# getDeviceInfo

**Return type:** Promise\<object | null>

Một Promise sẽ được giải quyết (resolve) với một đối tượng (object) chứa thông tin thiết bị. Nếu một thông tin cụ thể không thể lấy được, giá trị của nó trong object sẽ là null. Promise cũng có thể trả về null nếu có lỗi nghiêm trọng xảy ra.

**Arguments:** ()

Hàm này không nhận bất kỳ tham số nào.

**Returned Object Keys:**

Đối tượng deviceInfo trả về sẽ chứa các key sau đây. Giá trị của mỗi key sẽ là dữ liệu tương ứng hoặc null nếu không thể truy xuất.

'applicationName', 'locationProviders', 'batteryLevel', 'buildId', 'brand', 'buildNumber',\
'bundleId', 'carrier', 'deviceId', 'deviceName', 'firstInstallTime', 'fontScale',\
'freeDiskStorage', 'freeDiskStorageOld', 'ipAddress', 'installerPackageName', 'macAddress',\
'manufacturer', 'model', 'powerState', 'readableVersion', 'systemName', 'systemVersion',\
'totalDiskCapacity', 'totalDiskCapacityOld', 'totalMemory', 'uniqueId', 'usedMemory',\
'userAgent', 'version', 'batteryCharging', 'isEmulator', 'isLandscape',\
'isLocationEnabled', 'headphonesConnected', 'pinOrFingerprintSet', 'isTablet', 'supportedAbis'

**Example:**&#x20;

```javascript
p.getDeviceInfo()
  .then((deviceInfo) => {
    if (deviceInfo) {
      console.log('Tên thiết bị:', deviceInfo.deviceName);
      console.log('Có phải máy ảo không?', deviceInfo.isEmulator);
      console.log('Toàn bộ thông tin:', deviceInfo);
    } else {
      console.log('Không thể lấy được thông tin thiết bị.');
    }
  })
  .catch((error) => {
    console.error("Đã xảy ra lỗi khi lấy thông tin thiết bị:", error);
  });
```
