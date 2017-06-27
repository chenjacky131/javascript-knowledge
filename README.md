# javascript-knowledge [ECMAScriptApi](http://www.w3school.com.cn/js/index_pro.asp)

## 1. JavaScript标签
``` javascript
	var arr = ['a','b','c','d','e'];
	list:{// JavaScript标签
		console.log(arr[0]);
		console.log(arr[1]);
		break list;//break+标签可用于跳出代码块
		console.log(arr[2]);
		console.log(arr[3]);
		console.log(arr[4]);			
	}
```
## 2. with语句
	with 语句可以方便地用来引用某个特定对象中已有的属性，但是不能用来给对象添加属性。要给对象创建新的属性，必须明确地引用该对象。
```javascript	
	var obj = {
	name:"test"
	}
	with(obj){console.log(name)}// 直接输出"test"
```	
## 3. 阻止表单的默认行为
	在form onsubmit="return false" 能阻止表单的默认提交行为
## 4. 八进制和十六进制
	1. 八进制 var x = 0377 // x = 255
	2. 十六进制 var x = 0xFF // x = 255
## 5. 返回一个from到to之间的随机数
```javascript
	function randomRange(from,to){
		return Math.floor(Math.random()*(to-from+1)+from)
	}	
```	
## 6. window对象
	1全局变量是window对象的属性
	2全局函数是window对象的方法
## 7. JavaScript中的三种消息框
	1. alert("消息");
	2. confirm("问题"); 点击确定返回true,点击取消返回false;
	3. prompt("文本","默认值");点击确定，返回文本框里面的值，点击取消返回null;
## 8. 科学计数法
	var fNum = 5.79e7 (57900000);
	Number.toExponential(n) 返回科学计数法的数字，n为小数点后面的数字。例：(13112).toExponential(2):1.31e+4
## 9. 关于数字的几个方法
	isFinite(n):n是否无穷大;
	isNaN(n);n是否为NaN;
## 10. 关于进制转换
	函数parseInt()可以解析一个字符串,用法：parseInt(string, radix),radix为要转的进制，转后后的数为number类型
	Number.toString(radix)也可以进行进制转换，转后后的数为string类型。
## 11. 强制类型转换
	bBoolen();Number();String();
## 12. 引用类型对象String
	如果该字符串中只有一个 "o" 字符串，那么 indexOf() 和 lastIndexOf() 方法返回的位置相同，可用于判断某个字符串中某字符是否只有一个。
## 13. 判断引用类型的类型
	a instanceof Number;a某实例是否为制定的引用类型。
## 14. 一元运算符
	delete：删除开发者创建的对象属性，如果属性删除成功，返回true.
	+:可将字符串转换为数字，可转10进制的和16进制的字符串。 
	-:和类似，可将字符串转为负的数值.
## 15. 位运算符
	not:对数字求负，然后-1.
## 16. 函数的length属性
	返回函数期望的参数个数
## 17. String.fromCodePoint 函数 
	返回与 Unicode UTF-16 码位关联的字符串。	
## 18. 创建对象的方法
通常用下面两种方式：
1. 构造函数/原型方式
```javascript
function Car(sColor,iDoors,iMpg) {
  this.color = sColor;
  this.doors = iDoors;
  this.mpg = iMpg;
  this.drivers = new Array("Mike","John");
}

Car.prototype.showColor = function() {
  alert(this.color);
};

var oCar1 = new Car("red",4,23);
var oCar2 = new Car("blue",3,25);

oCar1.drivers.push("Bill");

alert(oCar1.drivers);	//输出 "Mike,John,Bill"
alert(oCar2.drivers);	//输出 "Mike,John"
```
2. 动态原型方法(进行了视觉上的封装，看起来更和谐)
```javascript
	function Car(sColor,iDoors,iMpg) {
	  this.color = sColor;
	  this.doors = iDoors;
	  this.mpg = iMpg;
	  this.drivers = new Array("Mike","John");

	  if (typeof Car._initialized == "undefined") {
	    Car.prototype.showColor = function() {
	      alert(this.color);
	    };

	    Car._initialized = true;
	  }
	}
```
## 19. 对象的继承
	1. call方法；call方法第一个参数为替代this的对象，后面的参数为函数的调用参数；
	2. apply方法；自由两个参数。apply方法第一个参数和call一样，第二个参数为保持参数的数组；
## 20. String的match方法和RegExp的exec方法
	如果String的match参数里面的正则没有g修饰符，则这两个方法返回的结果一样。第一个参数为匹配的文本，还有个index属性是匹配文本在stringObjec中的位置。input属性是对stringObject的引用；如果Sring的match参数有g修饰符，则返回的数组为存放所有的匹配子串。没有前面提到的两个属性。
## 21. 数组迭代器方法
	1. forEach()方法：该方法接受一个函数作为参数，对数组中每个元素使用该函数，函数的参数为对应的每个元素。
	2. every()方法：该方法接受一个返回值为布尔类型的函数，对数组中每个元素使用该函数。如果对于所有的元素，该函数返回true，则该方法返回true。
	3. some()方法：和every类似，但是只要对于一个元素返回true，则该方法就返回true。
	4. map()方法：和forEach类似，但是它返回一个新的数组，该数组的元素是对原有元素应用某个函数得到的结果。
	5. filter()方法：和every类似。不同的是，对数组所有的元素应用该函数，返回一个新的数组，该数组包含应用改函数后结果为true的元素。
## 22. 返回一个0到n的随机数
```javascript
	Math.floor(Math.random()*(n+1));
```	
## 23.数组去重
```javascript
Array.prototype.unique = function(){
    var res = [];
    // forEach方法中的function回调有三个参数：
    //第一个参数是遍历的数组内容，第二个参数是对应的数组索引，第三个参数是数组本身
    this.forEach(function(v){
        if(res.indexOf(v)<0){
            res.push(v);
        }
    })
    return res;
}
```
## 24.快速排序
```javascript
function quickSort(arr){
  if(arr.length <= 1) return arr;
  var index = Math.floor(arr.length/2);
  var key = arr.splice(index,1)[0];
  var left = [],right = [];
  arr.forEach(function(v){
      v <= key ? left.push(v) : right.push(v);
  });
  return quickSort(left).concat([key],quickSort(right));
}
```
## 25.加入收藏代码
```javascript
	<a onclick="AddFavorite(window.location,document.title)" href="javascript:void(0)">收藏本站</a>
	function AddFavorite(sURL, sTitle) {

	    sURL = encodeURI(sURL);
	    try{

		window.external.addFavorite(sURL, sTitle);

	    }catch(e) {

		try{

		    window.sidebar.addPanel(sTitle, sURL, "");

		}catch (e) {

		    alert("加入收藏失败，请使用Ctrl+D进行添加,或手动在浏览器里进行设置.");

		}

	    }

	}
```
## 26.IE兼容nth-child选择器的方法
1. *:first-child+li{匹配第二个}

2. *:first-child+li+li{匹配第三个}
 
 
## 27.防止键盘把当前输入框给挡住
```javascript
$$('input[type="text"],textarea').on('click', function () {
  var target = this;
  setTimeout(function(){
        target.scrollIntoViewIfNeeded();
        console.log('scrollIntoViewIfNeeded');
      },400);
});
```
## 28.数组操作
	1.push:从数组后面添加值
	2.pop:从数组后面移除值，并返回移除的值，原数组改变
	3.shift:从数组前面移除值，并返回移除的值，原数组改变
	3.unshift:从数组前面添加值
## 29.深拷贝
	1.两个参数
```javascript
	function clone(o1,o2){
	    for(var key in o2){
		if(typeof o2[key] == 'object'){
		    o1[key] = {};
		    clone(o1[key],o2[key])
		}else{
		    o1[key] = o2[key];
		}
	    }
	}	
```	
	2.一个参数
```javascript
	function clone(o){
		var temp = {};
		for(var key in o){
			if(typeof o[key] =='object'){
				temp[key] = clone(o[key]);
			}else{
				temp[key] = o[key];
			}
		}
		return temp;
	}	
```
## 30.位操作符（js高级程序设计62页）
	1.~（按位非）:二进制位取反
	2.&（按位与）:二进制位进行and操作，当同时为1时返回1，否则返回0
	3.|（按位或）:二进制位进行or操作，当同时为0时返回0，否则返回1
	4.^（按位异或）:二进制位进行xor操作，当相同时返回0，放着返回1
	5.<<（左移）:二进制位左移操作，后面补0。负数不影响符号位。
	6.>>（有符号右移）:二进制位右移操作，符号位后面用符号位填充。
	7.>>>（无符号右移）:
## 31.闭包知识点
参考:ttp://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html
