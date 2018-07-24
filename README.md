# 为什么使用wx-qrcode-img

微信小程序二维码生成如果用 canvas 

1 无法在scroll-view中正常使用。

2 无法跟随页面滚动。

3 canvas默认显示在最高层级如需遮罩需增加cover-view添加不必要的页面结构。

而使用 image 的 src 可以完美解决以上问题。

# How to use it.
```js
import QR from "./wxqrcode.js";

const size = 100; //宽高

const base64Data = QR.createQrCodeImg( 'any str code', size) // base64的数据

this.setDate({
    imageSrc:base64Data
})
```