HTML5 Geolocation（地理定位）用于获得用户的地理位置。
鉴于该特性可能侵犯用户的隐私，除非用户同意，否则用户位置信息是不可用的。

### 浏览器支持

![浏览器](http://www.devdoc.me/uploads/html5/images/browser.png)

Internet Explorer 9+, Firefox, Chrome, Safari 和 Opera 支持Geolocation（地理定位）.
> **注意:** Geolocation（地理定位）对于拥有 GPS 的设备，比如 iPhone，地理定位更加精确。

### HTML5 - 使用地理定位

请使用 `getCurrentPosition()` 方法来获得用户的位置。  
下例是一个简单的地理定位实例，可返回用户位置的经度和纬度:

```javascript
var x=document.getElementById("demo");
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  }
  else{
    x.innerHTML="该浏览器不支持获取地理位置。";
  }
}
function showPosition(position) {
  x.innerHTML="纬度: " + position.coords.latitude + 
  "<br>经度: " + position.coords.longitude;	
}
```
[去看一下效果](http://www.devdoc.me/uploads/html5/geolocation.html)

- 检测是否支持地理定位
- 如果支持，则运行 `getCurrentPosition()` 方法。如果不支持，则向用户显示一段消息。
- 如果 `getCurrentPosition()` 运行成功，则向参数 `showPosition` 中规定的函数返回一个 `coordinates` 对象
- `showPosition()` 函数获得并显示经度和纬度

上面的例子是一个非常基础的地理定位脚本，不含错误处理。

### 处理错误和拒绝

`getCurrentPosition()` 方法的第二个参数用于处理错误。它规定当获取用户位置失败时运行的函数：

```javascript
function showError(error) {
  switch(error.code) {
    case error.PERMISSION_DENIED:
      x.innerHTML="用户拒绝对获取地理位置的请求。"
      break;
    case error.POSITION_UNAVAILABLE:
      x.innerHTML="位置信息是不可用的。"
      break;
    case error.TIMEOUT:
      x.innerHTML="请求用户地理位置超时。"
      break;
    case error.UNKNOWN_ERROR:
      x.innerHTML="未知错误。"
      break;
  }
}
```

[去看一下效果](http://www.devdoc.me/uploads/html5/geolocation_error.html)

错误代码：

- PERMISSION_DENIED：用户不允许地理定位
- POSITION_UNAVAILABLE：无法获取当前位置
- TIMEOUT：操作超时

### 在地图中显示结果

如需在地图中显示结果，您需要访问可使用经纬度的地图服务，比如谷歌地图或百度地图：

谷歌地图：

```javascript
function showPosition(position) {
  var latlon=position.coords.latitude+","+position.coords.longitude;

  var img_url="http://maps.googleapis.com/maps/api/staticmap?center="
  +latlon+"&zoom=14&size=400x300&sensor=false";
  document.getElementById("mapholder").innerHTML="<img src='"+img_url+"'>";
}
```

百度地图：

```javascript
function showPosition(position) {
  var latlon=position.coords.latitude+","+position.coords.longitude;

  var img_url="http://api.map.baidu.com/staticimage?center="
  +latlon+"&width=300&height=200&zoom=14";
  document.getElementById("mapholder").innerHTML="<img src='"+img_url+"'>";
}
```
[去看一下效果](http://www.devdoc.me/uploads/html5/geolocation_map.html)

在上例中，我们使用返回的经纬度数据在地图中显示位置（使用静态图像）。

### 给定位置的信息

本页演示的是如何在地图上显示用户的位置。不过，地理定位对于给定位置的信息同样很有用处。

实例:

- 更新本地信息
- 显示用户周围的兴趣点
- 交互式车载导航系统 (GPS)

### getCurrentPosition() 方法 - 返回数据

若成功，则 `getCurrentPosition()` 方法返回对象。始终会返回 `latitude`、`longitude` 以及 `accuracy` 属性。如果可用，则会返回其他下面的属性。

<table>
<tbody>
<tr>
<th style="30%">属性</th>
<th>描述</th>
</tr>
<tr>
<td>coords.latitude</td>
<td>十进制数的纬度</td>
</tr>
<tr>
<td>coords.longitude</td>
<td>十进制数的经度</td>
</tr>
<tr>
<td>coords.accuracy</td>
<td>位置精度</td>
</tr>
<tr>
<td>coords.altitude</td>
<td>海拔，海平面以上以米计</td>
</tr>
<tr>
<td>coords.altitudeAccuracy</td>
<td>位置的海拔精度</td>
</tr>
<tr>
<td>coords.heading</td>
<td>方向，从正北开始以度计</td>
</tr>
<tr>
<td>coords.speed</td>
<td>速度，以米/每秒计</td>
</tr>
<tr>
<td>timestamp</td>
<td>响应的日期/时间</td>
</tr>
</tbody>
</table>

### Geolocation 对象 - 其他有趣的方法

`watchPosition()` - 返回用户的当前位置，并继续返回用户移动时的更新位置（就像汽车上的 GPS）。  
`clearWatch()` - 停止 watchPosition() 方法

下面的例子展示 `watchPosition()` 方法。您需要一台精确的 GPS 设备来测试该例（比如 iPhone）：

```javascript
var x=document.getElementById("demo");
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.watchPosition(showPosition);
  }
  else{x.innerHTML="该浏览器不支持获取地理位置。";}
}
function showPosition(position) {
  x.innerHTML="纬度: " + position.coords.latitude + 
  "<br>经度: " + position.coords.longitude;	
}
```
[去看一下效果](http://www.devdoc.me/uploads/html5/geolocation_watchposition.html)
