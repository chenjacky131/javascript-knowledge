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
