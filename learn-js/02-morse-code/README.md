## 需求描述

国际摩尔斯密码定义一种标准编码方式，将每个字母对应于一个由一系列点和短线组成的字符串，  比如: "a" 对应 ".-", "b" 对应 "-...", "c" 对应 "-.-.", 等等。现在请你根据提供的摩尔斯密码实现一个翻译器，效果如下：

![1.gif](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/77e72fac8666466ca449f5869d039855~tplv-k3u1fbpfcp-watermark.image?)

下面的资料将为你提供帮助：

-   [MDN 视频和音频 API(opens new window)](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)
-   [MDN CSS 教程(opens new window)](https://developer.mozilla.org/zh-CN/docs/Web/CSS)
-   [MDN JavaScript 教程(opens new window)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)
-   [编码：隐匿在计算机软硬件背后的语言 (opens new window)](https://awesome-programming-books.github.io/computer-system/%E7%BC%96%E7%A0%81%EF%BC%9A%E9%9A%90%E5%8C%BF%E5%9C%A8%E8%AE%A1%E7%AE%97%E6%9C%BA%E8%BD%AF%E7%A1%AC%E4%BB%B6%E8%83%8C%E5%90%8E%E7%9A%84%E8%AF%AD%E8%A8%80.pdf)你可以通过这本书学习摩斯电码原理，以及计算机底层的原理。

## 任务步骤

### 1. 技术栈选项

HTML5、CSS3、JavaScript

### 2. 翻译与加密

利用 JavaScript 实现摩斯码的翻译与加密工作。

- 点击翻译按钮，可以把明文输入框中输入的内容翻译为摩尔斯密文
- 点击点击解码按钮，可以把密文输入框中的摩尔斯码翻译为明文

### 3. 摩斯码播放

利用 JavaScript 操作 Audio 实现音频播放。

- 点击播放按钮，在类名为 playlist 的 div 中，显示摩尔斯码，并且模仿摩尔斯电报音，摩尔斯高亮与音频同步，点播放短的音频，横线播放长音频

## 编码阶段

请根据提供的初始代码，`index.html` 初始代码如下：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>摩尔斯码翻译器</title>
</head>

<body>
   <div class="panels">
        <div class="panel">
            <h3>Morse Code Translation</h3>
            <h1>摩尔斯码翻译器</h1>
            <textarea rows="4" placeholder="輸入英文" id="input">MorseCode</textarea>
            <div class="symbol">⇵</div>
            <textarea rows="4" placeholder="輸入密碼" id="output"></textarea>
            <div class="playlist"> </div>
            <div class="buttons">
                <button class="purple" id="btnMorse">翻译</button>
                <button class="yellow" id="btnEng">解密</button>
                <button class="white" id="btnPlay">播放</button>
            </div>
        </div>
        <div>
            <h3>翻译清单</h3>
            <hr />
            <ul class="morselist"></ul>
        </div>

        <script>
            //需要用到的摩尔斯加密列表
            var morseCode = "A;.-|B;-...|C;-.-.|D;-..|E;.|F;..-.|G;--.|H;....|I;..|J;.---|K;-.-|L;.-..|M;--|N;-.|O;---|P;.--.|Q;--.-|R;.-.|S;...|T;-|U;..-|V;...-|W;.--|X;-..-|Y;-.--|Z;--..|/;-..-.|1;.----|2;..---|3;...--|4;....-|5;.....|6;-....|7;--...|8;---..|9;----.|0;-----"
        </script>
</body>

</html>
```
 
 