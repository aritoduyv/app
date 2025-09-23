---
description: Cho phép lập trình code react native code trên xml
---

# buildComponent

**Return type:** Component

* Component này sẽ có các phương thức sau:
  * show() để hiển thị với data mặc định
  * updateData(newData) để hiển thị với data mới
  * hide() để ẩn component
  * delete(): để xóa component

**Arguments:** ({reactNativeCode, data})

* reactNativeCode: string, require, đoạn mã react native
* data: string, require, data mà đoạn mã react native sẽ sử dụng

**Example:**

```
<?xml version="1.0" encoding="utf-8"?>

<!DOCTYPE dir [
  <!ENTITY DefaultButton SYSTEM "..\Include\XML\DefaultButtonDir.xml">
  <!ENTITY QRCodeScan SYSTEM "..\Include\Script\QRCodeScan.txt">
]>


<dir id="@@controller" table="sysmenu" fieldKey="ma_nv" >
  <title v="Phương thức p.buildComponent" e="Phương thức p.alert" o="Phương thức p.alert"/> 
  <forms>
    <form>
      <formGroup>
        <fields>
          <field name="build_1" width="100%" componentName="AButton">
            <text v="build 1" e="build 1" o="build 1"></text>
          </field> 
		<field name="build_bottom_menu" width="100%" componentName="AButton">
            <text v="build bottom menu" e="build bottom menu" o="build bottom menu"></text>
          </field> 
        </fields>
      </formGroup>
    </form>
  </forms>
  <script>
    <query>
      <text>
        <![CDATA[ 
        
      ]]>
      </text>
    </query>
  </script> 

  <js>
    <text>
      <![CDATA[  
beforeButtonDialogClick = (id, p) => {
    switch (id) {
        case "build_1": {
            let reactNativeCodeAlert = `
        <View style={containerStyle}>
          <Text style={titleStyle}>{title}</Text>
          <Text style={messageStyle}>{message}</Text>
          <TouchableOpacity onPress={() => handleAction('confirm', {id: entityId})} style={buttonStyle}>
            <Text style={buttonTextStyle}>OK</Text>
          </TouchableOpacity>
        </View>
      `;

            let dataAlert = {
                title: "Server Alert!",
                message: "This message is for user. Please review your settings.",
                entityId: "item-123",
                containerStyle: {
                    position: 'absolute',
                    top: 100,
                    left: 20,
                    right: 20,
                    padding: 20,
                    backgroundColor: 'rgba(230, 230, 250, 0.9)',
                    borderRadius: 10,
                    zIndex: 1000,
                    elevation: 5,
                },
                titleStyle: {
                    fontSize: 18,
                    fontWeight: 'bold',
                    color: '#333',
                    marginBottom: 10,
                    textAlign: 'center',
                },
                messageStyle: {
                    fontSize: 15,
                    color: '#555',
                    marginBottom: 20,
                    textAlign: 'center',
                },
                buttonStyle: {
                    backgroundColor: '#007bff',
                    padding: 12,
                    borderRadius: 5,
                },
                buttonTextStyle: {
                    color: 'white',
                    textAlign: 'center',
                    fontWeight: 'bold',
                },
                handleAction: (status, data) => {
                    p.alert({
                        message: "Kiểm tra hàm builder trong callback của custom alert",
                        title: "Test Alert"
                    });
                }
            };

            let myAlertComponent = p.buildComponent({
                reactNativeCode: reactNativeCodeAlert,
                data: dataAlert
            });
            myAlertComponent.show();

            setTimeout(() => {
                myAlertComponent.delete();
            }, 5000);
            return true;
        }

        case "build_bottom_menu": {
            let reactNativeCodeBottomMenu = `
        <View style={containerStyle}>
          {buttons.map((button, index) => [
            <TouchableOpacity
              key={button.id}
              onPress={() => handleButtonPress(button.id, button.text)}
              style={buttonStyle}
            >
              {/* View này sẽ làm nền cho icon trắng */}
              <View style={imageIconContainerStyle}>
                <Image source={{ uri: button.imageUrl }} style={imageStyle} />
              </View>
              <Text style={textStyle}>{button.text}</Text>
            </TouchableOpacity>,
            index < buttons.length - 1 ? (
              <View
                key={'separator-' + button.id}
                style={separatorStyle}
              />
            ) : null
          ])}
        </View>
      `;

            let dataBottomMenu = {
                buttons: [
                    // QUAN TRỌNG: Thay thế bằng URL đến các icon TRẮNG của bạn
                    { id: 'home', text: 'Trang chủ', imageUrl: 'https://arito-assets.pages.dev/img18.png' },
                    { id: 'search', text: 'Tìm kiếm', imageUrl: 'https://arito-assets.pages.dev/img18.png' },
                    { id: 'profile', text: 'Cá nhân', imageUrl: 'https://arito-assets.pages.dev/img18.png' }
                ],
                containerStyle: {
                    position: 'absolute',
                    bottom: 0,
                    left: 0,
                    right: 0,
                    flexDirection: 'row',
                    alignItems: 'center',
                    backgroundColor: 'rgba(245, 245, 245, 0.95)',
                    paddingVertical: 8,
                    paddingHorizontal: 5,
                    borderTopWidth: 1,
                    borderTopColor: '#e0e0e0',
                    zIndex: 1000,
                    elevation: 8,
                },
                buttonStyle: {
                    flex: 1,
                    alignItems: 'center',
                    paddingVertical: 5,
                },
                // Style cho View chứa icon (làm nền)
                imageIconContainerStyle: {
                    width: 30, // Kích thước của vùng nền
                    height: 30,
                    borderRadius: 15, // Để tạo nền tròn (bằng một nửa width/height)
                    backgroundColor: '#007bff', // Màu nền tương phản (ví dụ: màu xanh của text)
                    // Hoặc một màu tối khác bạn thích: '#555555'
                    justifyContent: 'center', // Căn giữa icon bên trong
                    alignItems: 'center',     // Căn giữa icon bên trong
                    marginBottom: 4, // Giữ khoảng cách với text bên dưới
                },
                // Style cho Image (icon trắng) bên trong container
                imageStyle: {
                    width: 18, // Kích thước icon trắng, nhỏ hơn container một chút để có padding
                    height: 18,
                    // Không cần tintColor ở đây nếu bạn muốn giữ icon màu trắng
                },
                textStyle: {
                    fontSize: 11,
                    color: '#007bff',
                },
                separatorStyle: {
                    width: 1,
                    height: '60%',
                    backgroundColor: '#cccccc',
                    alignSelf: 'center',
                },
                handleButtonPress: (buttonId, buttonText) => {
                    p.alert({
                        message: `Bạn đã nhấn nút: "${buttonText}" (ID: ${buttonId})`,
                        title: "Thông báo Menu"
                    });
                }
            };

            let myBottomMenuComponent = p.buildComponent({
                reactNativeCode: reactNativeCodeBottomMenu,
                data: dataBottomMenu
            });
            myBottomMenuComponent.show();

            setTimeout(() => { myBottomMenuComponent.delete(); }, 10000);
            return true;
        }


        default:
            return true;
    }
};


 

      ]]>
    </text>
  </js>
  
  <buttons>
    <button id="cancel" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button>
    <button id="cancel2" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button>
    <button id="cancel3" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button>
    <button id="cancel4" image="arrow-left-circle">
      <text v="$AddToolbar" e="$AddToolbar" o="$AddToolbar"></text>
    </button>
  </buttons>
  <messages>
    <message val="abc">
      <text v="Message abc " e="Message abc " o="Message abc "/>
    </message>
  </messages>
</dir>
```
