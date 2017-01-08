#PIE使用说明

##下载地址：[单击我下载：1.0.0版本](https://cloud.github.com/downloads/lojjic/PIE/PIE-1.0.0.zip)

##官方网站：http://css3pie.com/

###PIE功能（简单的功能）

- border-radius圆角 
- box-shadow 盒阴影 
- gradient渐变 
- multiple background images多背景

### 准备：

1.下载好PIE文件。

![image](http://a3.qpic.cn/psb?/V13eqRud0c3Eb1/2LSrMbpnuExF9z3wQmva4urKevJzkRg3h7ule*vxmv8!/b/dPYAAAAAAAAA&ek=1&kp=1&pt=0&bo=SAJxAEgCcQADGTw!&su=456260561&tm=1483851600&sce=0-12-12&rf=2-9)

2.弄一个本地服务器(我这里使用phpStudy)。会用其他的本地服务器也可以。不会的就没办法了，圆角是可以看到的
![image](http://a4.qpic.cn/psb?/V13eqRud0c3Eb1/XGk*UzraDtIPAjlfCiLVNM*DO8R1d69rdM7Fft03cBw!/b/dB8BAAAAAAAA&ek=1&kp=1&pt=0&bo=RwBOAEcATgADGTw!&su=545148529&tm=1483851600&sce=0-12-12&rf=2-9);

3.IE浏览器是必不可少的，这里了，我是用了最古老的测试工具IETester
![image](http://a1.qpic.cn/psb?/V13eqRud0c3Eb1/.NiqTKzdOnk54rNEF2T30UeUUII2mq1xiXhe4SMKTqc!/b/dNwAAAAAAAAA&ek=1&kp=1&pt=0&bo=RgBLAAAAAAADFz8!&su=219166769&tm=1483851600&sce=0-12-12&rf=2-9)

4.要准备几张图片（PNG透明图片）

**开始**：在我的www目录中，放入了对应的文件。

###使用有两种方法：
**方法一：**
> 使用js方法（可以在本地打开，不用本地服务器）；

***第一步：引入JS文件***

> 最好使用css的hack来控制IE读取，这样减少宽带

![image](http://a2.qpic.cn/psb?/V13eqRud0c3Eb1/NwbQesaXGuhyHDe8qxTkLZREKeLgOUAs7mlrIhN0wOI!/b/dOUAAAAAAAAA&ek=1&kp=1&pt=0&bo=tgEqAQAAAAADF64!&su=3108160145&tm=1483851600&sce=0-12-12&rf=2-9)

**第二步： 写好样式：**

> 给第一个div有圆角。第二个div给阴影、第三个div给渐变(这里要给前缀-pie-background: linear-gradient(red,pink);)、第四个div给多背景图片(这里要给前缀-pie-background-image: url(图片地址1),url(图片地址2))。

![image](http://a4.qpic.cn/psb?/V13eqRud0c3Eb1/nuu41XqLeDHmqZGtGbi1Cp5Em2wVsEyR2FGc2RGbtzQ!/b/dHcBAAAAAAAA&ek=1&kp=1&pt=0&bo=EAKOAAAAAAADF64!&su=5162276385&tm=1483851600&sce=0-12-12&rf=2-9)

![image](http://a3.qpic.cn/psb?/V13eqRud0c3Eb1/m9JBOhPhBpzUP1kOx6a9ecixe21xYmSTisn9AO08VGU!/b/dHoBAAAAAAAA&ek=1&kp=1&pt=0&bo=OgK.AAAAAAADF7Q!&su=486568737&tm=1483851600&sce=0-12-12&rf=2-9)

**第三步：在IE低版本浏览器进行实现；**

> 先得把咱们要的js引进页面，然后测试下是否引进成功；在js中alert(window.PIE);，弹出object就是成功，如果是unfinished的就是未成功。获取class名字为attribute的。然后进行for循环。

**注意**：这里使用封装好的获取class属性值。

![image](http://a3.qpic.cn/psb?/V13eqRud0c3Eb1/.bp7avoz0xj3ZoRjI7dzWfq7MnoWURbe34RGVHvI6OE!/b/dAoBAAAAAAAA&ek=1&kp=1&pt=0&bo=7gH5AAAAAAADBzQ!&su=4155881265&tm=1483851600&sce=0-12-12&rf=2-9)

```javascript
// 获取元素：
var cssSX = getByClassName(document,'attribute');
// 判断window.PIE对象是否存在
if (window.PIE) {
		    for(var i=0;i<cssSX.length;i++){
		        PIE.attach(cssSX[i]);
		    }
		}
```
