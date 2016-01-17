### HTML5 新的 Input 类型

HTML5 拥有多个新的表单输入类型。这些新特性提供了更好的输入控制和验证。  
本章全面介绍这些新的输入类型：

- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

> **注意:** 并不是所有的主流浏览器都支持新的input类型，不过您已经可以在所有主流的浏览器中使用它们了。即使不被支持，仍然可以显示为常规的文本域。

### Input 类型: color

color 类型用在 input 字段主要用于选取颜色，如下所示：

**实例**   
从拾色器中选择一个颜色:

```html
选择你喜欢的颜色: <input type="color" name="favcolor">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_chrome.png)

---

### Input 类型: date

date 类型允许你从一个日期选择器选择一个日期。

**实例**   
定义一个时间控制器:

```html
生日: <input type="date" name="bday">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_chrome_safari.png)

---

### Input 类型: datetime

datetime 类型允许你选择一个日期（UTC 时间）。

**实例**   
定义一个日期和时间控制器（本地时间）:

```html
生日 (日期和时间): <input type="datetime" name="bdaytime">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_safari.png)

---

### Input 类型: datetime-local

datetime-local 类型允许你选择一个日期和时间 (无时区).

**实例**   
定义一个日期和时间控制器（本地时间）:

```html
生日 (日期和时间): <input type="datetime-local" name="bdaytime">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_chrome_safari.png)

---

### Input 类型: email

email 类型用于应该包含 e-mail 地址的输入域。

**实例**   
在提交表单时，会自动验证 email 域的值是否合法有效:

```html
E-mail: <input type="email" name="email">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

> **提示:** iPhone 中的 Safari 浏览器支持 email 输入类型，并通过改变触摸屏键盘来配合它（添加 @ 和 .com 选项）。

![浏览器支持](http://www.devdoc.me/uploads/html5/images/ie_firefox_opera_chrome.png)

---

### Input 类型: month

month 类型允许你选择一个月份。

**实例**   
定义月与年 (无时区):

```html
生日 (月和年): <input type="month" name="bdaymonth">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_chrome_safari.png)

---

### Input 类型: number

number 类型用于应该包含数值的输入域。  
您还能够设定对所接受的数字的限定：

**实例**   
定义一个数值输入域(限定):

```html
数量 ( 1 到 5 之间 ): <input type="number" name="quantity" min="1" max="5">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

使用下面的属性来规定对数字类型的限定：

- `max` \- 规定允许的最大值
- `min` \- 规定允许的最小值
- `step` \- 规定合法的数字间隔（如果 step="3"，则合法的数是 -3,0,3,6 等）
- `value` \- 规定默认值

![浏览器支持](http://www.devdoc.me/uploads/html5/images/ie_opera_chrome_safari.png)

---

### Input 类型: range

range 类型用于应该包含一定范围内数字值的输入域。  
range 类型显示为滑动条。

**实例**   
定义一个不需要非常精确的数值（类似于滑块控制）:

```html
<input type="range" name="points" min="1" max="10">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

请使用下面的属性来规定对数字类型的限定：

- `max` \- 规定允许的最大值
- `min` \- 规定允许的最小值
- `step` \- 规定合法的数字间隔（如果 step="3"，则合法的数是 -3,0,3,6 等）
- `value` \- 规定默认值

![浏览器支持](http://www.devdoc.me/uploads/html5/images/ie_opera_chrome_safari.png)

---

### Input 类型: search

search 类型用于搜索域，比如站点搜索或 Google 搜索。

**实例**   
定义一个搜索字段 (类似站点搜索或者Google搜索):

```html
Search Google: <input type="search" name="googlesearch">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/chrome_safari.png)

---

### Input 类型: tel

**实例**   
定义输入电话号码字段:

```html
电话号码: <input type="tel" name="usrtel">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/no_browser.png)

---

### Input 类型: time

time 类型允许你选择一个时间。

**实例**   
定义可输入时间控制器（无时区）：

```html
选择时间: <input type="time" name="usr_time">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_chrome_safari.png)

---

### Input 类型: url

url 类型用于应该包含 URL 地址的输入域。  
在提交表单时，会自动验证 url 域的值。

**实例**   
定义输入URL字段:

```html
添加您的主页: <input type="url" name="homepage">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

> **提示:** iPhone 中的 Safari 浏览器支持 url 输入类型，并通过改变触摸屏键盘来配合它（添加 .com 选项）。

![浏览器支持](http://www.devdoc.me/uploads/html5/images/ie_firefox_opera_chrome.png)

---

### Input 类型: week

week 类型允许你选择周和年。

**实例**   
定义周和年 (无时区):

```html
选择周: <input type="week" name="week_year">
```
[去看一下效果](http://www.devdoc.me/uploads/html5/input_type.html)

![浏览器支持](http://www.devdoc.me/uploads/html5/images/opera_chrome_safari.png)

---


