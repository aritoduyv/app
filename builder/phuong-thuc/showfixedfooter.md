---
description: Phiên bản >= 2.0.0
---

# showFixedFooter

## Fixed Footer (showFixedFooter) <a href="#fixed-footer-showfixedfooter" id="fixed-footer-showfixedfooter"></a>

Thanh chân cố định với 3 vùng Trái – Giữa – Phải. Nhấn vào phần tử sẽ gọi `beforeButtonDialogClick(name, builder)` trên FormScreen.

### Cách gọi <a href="#c-c3-a1ch-g-e1-bb-8di" id="c-c3-a1ch-g-e1-bb-8di"></a>

```js
// Hiện / cập nhật
builder.showFixedFooter({
  visible: true,
  leftElement:   { icon: 'arrow-left', name: 'left_back' },
  centerElement: { text: 'Sẵn sàng',   name: 'center_ready' },
  rightElement:  { icon: 'check', text: 'Lưu', name: 'right_save', color: '#10b981' },
});

// Ẩn
builder.showFixedFooter({ visible: false });
```

### Props <a href="#props" id="props"></a>

* `visible` (boolean): Bật/tắt footer.
* `leftElement`, `centerElement`, `rightElement` (optional): Định nghĩa từng vùng.
  * `name` (string): Id truyền vào `beforeButtonDialogClick(name, builder)`.
  * `text` (string, optional)
  * `icon` (string, optional, SimpleLineIcons)
  * `size` (number, optional, mặc định 18)
  * `color` (string, optional, mặc định `ATheme.textColorPrimary`)
  * `backgroundColor` (string, optional)

### Bố cục & căn lề <a href="#b-e1-bb-91-c-e1-bb-a5c-c-c4-83n-l-e1-bb-81" id="b-e1-bb-91-c-e1-bb-a5c-c-c4-83n-l-e1-bb-81"></a>

* Tỉ lệ chiều rộng: Trái 20% – Giữa 60% – Phải 20%.
* Căn trong từng vùng:
  * Trái: bám mép trái.
  * Giữa: căn giữa.
  * Phải: bám mép phải.
* Gọi lại với `visible: true` để cập nhật nội dung.
* Text tự động xuống dòng tối đa 2 dòng (ellipsis nếu dài hơn).

### Sự kiện click <a href="#s-e1-bb-b1-ki-e1-bb-87n-click" id="s-e1-bb-b1-ki-e1-bb-87n-click"></a>

* Trên FormScreen, khi nhấn phần tử sẽ phát sự kiện và gọi `beforeButtonDialogClick(name, builder)` nếu được định nghĩa trong JS của màn hình.

### Lưu ý <a href="#l-c6-b0u-c3-bd" id="l-c6-b0u-c3-bd"></a>

* Không set `name` thì nhấn sẽ không phát sự kiện.
* Tên icon theo SimpleLineIcons (vd: `home`, `arrow-right`, `cloud-upload`).
