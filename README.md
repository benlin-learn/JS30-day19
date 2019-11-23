# JS30-day19

## 邏輯順序

1. 建立一個 localhost 伺服器
2. 取得影像
3. 擷取視訊影像放入 canvas
4. 新增拍照功能
5. 新增濾鏡效果
   - 紅色濾鏡效果
   - 色彩分離效果
   - 綠色濾鏡效果

> strip: 產生圖檔的位置

### 細項

- 建立一個 localhost 伺服器

  > 新增 package.json

  ```json
  {
    "name": "gum",
    "version": "1.0.0",
    "description": "",
    "main": "scripts.js",
    "scripts": {
      "start": "browser-sync start --server --files \"_.css, _.html, *.js\""
    },
    "author": "",
    "license": "ISC",
    "devDependencies": {
      "browser-sync": "^2.12.5 <2.23.2"
    }
  }
  ```

      npm start

* 取得影像

> navigator.mediaDevices.getUserMedia() 可以取得攝影鏡頭權限，返回一個 promise 對象

```js
function getVideo() {
  navigator.mediaDevices
    .getUserMedia({ video: true, audio: false })

    .then(localMediaStream => {
      // video.src = URL.createObjectURL(localMediaStream);
      // createObjectURL已經不能再取得影像, 故改用srcObject
      // input.controls = false;

      video.srcObject = localMediaStream;
      video.play();
    })
    .catch(err => {
      console.error(`Oh no!!`, err);
    });
}
```

- 擷取視訊影像放入 canvas

```js
```
