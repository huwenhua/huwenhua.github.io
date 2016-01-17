### 互联网上的音频

直到现在，仍然不存在一项旨在网页上播放音频的标准。  
今天，大多数音频是通过插件（比如 Flash）来播放的。然而，并非所有浏览器都拥有同样的插件。  
HTML5 规定了在网页上嵌入音频元素的标准，即使用 `<audio>` 元素。

### 浏览器支持

![浏览器](http://www.devdoc.me/uploads/html5/images/browser.png)

Internet Explorer 9+, Firefox, Opera, Chrome, 和 Safari 都支持 `<audio>` 元素.
> **注意:** Internet Explorer 8 及更早IE版本不支持 `<audio>` 元素.

### HTML5 Audio - 如何工作

如需在 HTML5 中播放音频，你需要使用以下代码：

```html
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
您的浏览器不支持 audio 元素。
</audio>
```
[去看一下效果](http://www.devdoc.me/uploads/html5/audio_all.html)

control 属性供添加播放、暂停和音量控件。  
在 `<audio>` 与 `</audio>` 之间你需要插入浏览器不支持的 `<audio>` 元素的提示文本 。  
`<audio>` 元素允许使用多个 `<source>` 元素. `<source>` 元素可以链接不同的音频文件，浏览器将使用第一个支持的音频文件

### 音频格式及浏览器支持

目前, `<audio>` 元素支持三种音频格式文件: MP3, Wav, 和 Ogg:

<table> <tbody><tr> <th width="25%" align="left">浏览器</th> <th width="25%" align="left">MP3</th> <th width="25%" align="left">Wav</th> <th width="25%" align="left">Ogg</th> </tr> <tr> <td>Internet Explorer 9+</td> <td>YES</td> <td>NO</td> <td>NO</td> </tr> <tr> <td>Chrome 6+</td> <td>YES</td> <td>YES</td> <td>YES</td> </tr> <tr> <td>Firefox 3.6+</td> <td>NO</td> <td>YES</td> <td>YES</td> </tr> <tr> <td>Safari 5+</td> <td>YES</td> <td>YES</td> <td>NO</td> </tr> <tr> <td>Opera 10+</td> <td>NO</td> <td>YES</td> <td>YES</td> </tr> </tbody></table>

### 音频格式的MIME类型

<table> <tbody><tr> <th width="50%" align="left">Format</th> <th width="50%" align="left">MIME-type</th> </tr> <tr> <td>MP3</td> <td>audio/mpeg</td> </tr> <tr> <td>Ogg</td> <td>audio/ogg</td> </tr> <tr> <td>Wav</td> <td>audio/wav</td> </tr> </tbody></table>

### HTML5 Audio 标签

<table> <tbody><tr> <th align="left" width="150">标签</th> <th align="left">描述</th> </tr> <tr> <td>&lt;audio&gt;</td> <td>定义了声音内容</td> </tr> <tr> <td>&lt;source&gt;</td> <td>规定了多媒体资源, 可以是多个，在 &lt;video&gt; 与 &lt;audio&gt;标签中使用</td> </tr> </tbody></table>