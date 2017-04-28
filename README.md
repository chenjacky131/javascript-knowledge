# javascript-knowledge

## 1. JavaScript标签
	<script type="text/javascript">
		var arr = ['a','b','c','d','e'];
		list:{// JavaScript标签
			console.log(arr[0]);
			console.log(arr[1]);
			break list;//break+标签可用于跳出代码块
			console.log(arr[2]);
			console.log(arr[3]);
			console.log(arr[4]);			
		}
	</script>
## 2. with语句
	with 语句可以方便地用来引用某个特定对象中已有的属性，但是不能用来给对象添加属性。要给对象创建新的属性，必须明确地引用该对象。
	var obj = {
	name:"test"
	}
	with(obj){console.log(name)}// 直接输出"test"
## 3. 阻止表单的默认行为
	在form onsubmit="return false" 能阻止表单的默认提交行为
## 4. 八进制和十六进制
	1. 八进制 var x = 0377 // x = 255
	2. 十六进制 var x = 0xFF // x = 255
## 5. 返回一个from到to之间的随机数
	function randomRange(from,to){
		return Math.floor(Math.random()*(to-from+1)+from)
	}	
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
