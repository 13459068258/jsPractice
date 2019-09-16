# jsPractice
 js练习

#demo3笔记  
**1、window.load 和$(document).ready() 区别**  
a.执行时间  
window.onload必须等到页面内包括图片的所有元素加载完毕后才能执行。   
$(document).ready()是DOM结构绘制完毕后就执行，不必等到加载完毕。  
b.编写个数不同   
window.onload不能同时编写多个，如果有多个window.onload方法，只会执行一个   
$(document).ready()可以同时编写多个，并且都可以得到执行  
以下代码无法正确执行：   
window.onload = function(){   
alert(“text1”);   
};   
window.onload = function(){   
alert(“text2”);   
};   
结果只输出第二个 能同时编写多个   
以下代码正确执行：   
$(document).ready(function(){   
alert(“Hello World”);   
});   
$(document).ready(function(){   
alert(“Hello again”);   
});   
结果两次都输出   

c.简化写法   
window.onload没有简化写法   
$(document).ready(function(){})可以简写成$(function(){});  

另外，需要注意一点，由于在 $(document).ready() 方法内注册的事件，只要 DOM 就绪就会被执行，因此可能此时元素的关联文件未下载完。例如与图片有关的 html 下载完毕，并且已经解析为 DOM 树了，但很有可能图片还没有加载完毕，所以例如图片的高度和宽度这样的属性此时不一定有效。要解决这个问题，可以使用 Jquery 中另一个关于页面加载的方法 ---load() 方法。 Load() 方法会在元素的 onload 事件中绑定一个处理函数。如果处理函数绑定给 window 对象，则会在所有内容 ( 包括窗口、框架、对象和图像等 ) 加载完毕后触发，如果处理函数绑定在元素上，则会在元素的内容加载完毕后触发。
Jquery 代码如下：   
$(window).load(function (){   
// 编写代码   
});等价于 JavaScript 中的以下代码   
Window.onload = function (){   
// 编写代码   
}  

**2、javascript 中 click 和onclick有什么区别呢?**  
区别如下：  

1、onclick是绑定事件，告诉浏览器在鼠标点击时候要做什么。  
2、click本身是方法作用是触发onclick事件，只要执行了元素的click()方法，就会触发onclick事件  

3、click可以理解为一次简单的触发，只执行一次，找不到以后就不再执行；  

4、onclick则是给这个id注册一种行为，可以重复触发  

5、click 是方法；onclick是事件；执行click就是模拟鼠标点击，同时会触发onclick事件。  

**3、HTML DOM getElementsByTagName() 方法**  
  let img1 = document.getElementsByTagName('img')[0];//注意后面要定位看取哪个数。  
