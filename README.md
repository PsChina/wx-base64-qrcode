# npm

```bash
npm i wx-base64-qrcode -S
```

# 为什么使用wx-base64-qrcode

微信小程序二维码生成如果用 canvas 

1 无法在scroll-view中正常使用。

2 无法跟随页面滚动。

3 canvas默认显示在最高层级如需遮罩需增加cover-view添加不必要的页面结构。

而使用 image 的 src 可以完美解决以上问题。

# How to use it.

Only for WeChat Mini Program.

```xml
<image src="{{imageSrc}}"></image>
```
```js
import QR from "./wxqrcode.js";
Page({
  data: {
      imageSrc:'',
  },
  onLoad(){
    const size = 100; //宽高

    const base64Data = QR.createQrCodeImg( 'any str code', size) // base64的数据

    this.setData({
        imageSrc:base64Data
    })
  }
})
```
