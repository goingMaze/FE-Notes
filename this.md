##this含义
this是函数内部的特殊对象，引用的是函数执行的环境对象

1. 作为函数调用：this==window

	```
	(function(){
		console.log(this);
		console.log(this === window);
	})();
	
	```

2. 作为方法调用：this==方法所属对象

	```
	var obj = {};
	obj.method = function(){
		console.log(this);
		console.log(this === obj);
	}
	obj.method();
	
	```

3. 作为构造函数调用：this==新对象

	```
	function Obj(){
		this.x = 0;
	}
	Obj.prototype.method = function(){
		console.log(this);
		console.log(this === obj);
	}
	
	var obj = new Obj();
	obj.method();
	
	```

4. call和apply调用：this==传入的参数对象

	```
	function method(){
		console.log(this);
		console.log(this === obj);
	}
	var obj = {};
	method.call(obj);
	method.apply(obj);
	```

