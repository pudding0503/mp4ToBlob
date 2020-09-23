# Mp4ToBlob
**mp4ToBlob.js** 是一个在前端将你的 mp4 格式视频以 `blob src` 的形式展现出来。

### 使用

引入 **mp4ToBlob.js** 在 `<header>` 与 `</header>` 之间：

```html
<script type="text/javascript" src="js/mp4ToBlob.js"></script>
```

添加配置信息到 JavaScript 中：

```javascript
var url = 'siri-white.mp4'; // 视频url
var mimeCodec = 'video/mp4; codecs="avc1.640028, mp4a.40.2"'; // 编码格式（一般情况默认即可）
Mp4ToBlob.init('#video', url, mimeCodec); // #video 是选择器id
```

在需要使用视频的位置，使用 `<video>` 标签并标明 `id  ` 即可：

```html
<video id="video"></video>
```

### 遇到错误

如果遇到了以下错误：

> Failed to execute 'endOfStream' on 'MediaSource': The MediaSource's readyState is not 'open'.

![错误](assets/wrong.png)

说明使用的 MP4 视频并不是 `fragmented` 的，需要使用 **Bento4** 工具进行转换。

#### 下载 Bento4

Bento4 下载地址：[https://www.bento4.com/downloads/](https://www.bento4.com/downloads/)

#### 使用 Bento4

需要注意的事情是，windows上的bin目录下的 exe 是需要通过命令行来运行。

1. 解压缩
2. 打开 bin 目录
3. 在 bin 目录上开启 Powershell 或者 Cmd
4. 运行如下命令：

```powershell
.\mp4fragment.exe source.mp4 new.mp4
```

其中：`mp4fragment.exe` 是命令 ， `source.mp4` 是原视频地址 ， `new.mp4` 是要输出的视频路径。

### 例子

在 `\example` 下有一个样例，需要注意的是必须要在服务器上才能表现出来，你需要搭建本地服务器或者上传至网络服务器。

还可以直接点击此链接进行在线预览：

[siri-white-blob.html](https://windmill0503.github.io/demo/mp4-to-blob/siri-white-blob.html)

[siri-black-blob.html](https://windmill0503.github.io/demo/mp4-to-blob/siri-black-blob.html)