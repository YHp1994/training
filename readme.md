## 利用图片测试网速 上报数据
- 测网速：

```
let s = Date.now();
let img = new Image();
img.src = "u1597.png";
img.onload = function(){
let e = Date.now();
let w = 图片大小/(e-s);
console.log(w)
 }
```

###### 上报数据（系统的监控平台，系统的bug监控，打点）
transparent.gif?newmap=1&type=ms0&target=geo&ts=1533626566945&start_geo_loc=1&share_geo_all=1&html5_geo_all=1&status=2
将用户的数据传给后台，根据请求的日志获取用户一些信息（可以将任何信息作为埋点）
navigator.sendBeacon() 方法可用于通过HTTP将少量数据异步传输到Web服务器。


###### crossorigin
属性的详细解释https://developer.mozilla.org/en-US/docs/Web/HTML/CORS_enabled_image
crossorigin 所有能引入跨域资源的标签（script  link img）都有这个属性

#######跨域
跨域，指的是浏览器不能执行其他网站的脚本。它是由浏览器的同源策略造成的，是浏览器对JavaScript施加的安全限制。
所谓同源是指，域名，协议，端口均相同：
http://www.123.com/index.html 调用 http://www.123.com/server.PHP （非跨域）
http://www.123.com/index.html 调用 http://www.456.com/server.php （主域名不同:123/456，跨域）
http://abc.123.com/index.html 调用 http://def.123.com/server.php（子域名不同:abc/def，跨域）
http://www.123.com:8080/index.html调用 http://www.123.com:8081/server.php（端口不同:8080/8081，跨域）
http://www.123.com/index.html 调用 https://www.123.com/server.php（协议不同:http/https，跨域）
请注意：localhost和127.0.0.1虽然都指向本机，但也属于跨域。
jsonp
jstopng
把代码写在图片里 再用canvans画出来 得到代码  利用img进行跨域
iframe
同域之间共享cookie可以用 document.domain()

###### 判断图片加载完成的三种方式
https://www.cnblogs.com/snandy/p/3704938.html
load事件  所有浏览器都支持img的load事件
readystatechange事件 readyState为complete和loaded则表明图片已经加载完毕。测试IE6-IE10支持该事件，其它浏览器不支持
img的complete属性 轮询不断监测img的complete属性，如果为true则表明图片已经加载完毕，停止轮询。该属性所有浏览器都支持。如果图片加载失败，在IE中complete的值一直为false,而其他浏览器最后会变为true



## css远程攻击漏洞
###### color: expression(alert('XSS'));background: url(javascript:alert('script injected'))
https://blog.csdn.net/u013909970/article/details/51144639
###### 用伪类伪元素精简DOM
尽量少用DOM，CPU计算DOM，GPU渲染CSS

https://a.singlediv.com/


## iframe对远程localStorage扩容
跨域的时候不能操作dom

localStorage本地存储的最大空间是5M
https://blog.csdn.net/zhouziyu2011/article/details/61209268

## html语义化的重要性
###### 根据内容的结构化（内容语义化），选择合适的标签（代码语义化）便于开发者阅读和写出更优雅的代码的同时让浏览器的爬虫和机器很好地解析
https://juejin.im/entry/5ab5f229518825558a069304

http://www.cnblogs.com/freeyiyi1993/p/3615179.html

