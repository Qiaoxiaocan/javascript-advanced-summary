1、ECMAScript是JavaScript规范的名字。

2、JavaScript的两大语法类别：语句和表达式。

3、JavaScript的注释方法：单行注释（//）和多行注释（/*    */）。

4、JavaScript的变量在声明后使用，变量的声明和赋值可以同时进行或者对已有变量单独赋值。

5、标识符是JavaScript中各种语法的名称，区分大小写，标识符第一个字符不能是数字。

6、JavaScript所有的值都有属性，每个属性都有一个key和一个value，可以通过点（.）操作符读取属性：var str = "abc"; str.lenght = 3 或者给属性赋值：var obj = {}; obj.foo = 123; 还可以通过点操作符调用方法：'hello'.toUpperCase()  结果为'HELLO'

7、原始值包括布尔值，数字，字符串，NULL和undefined，其他的值都是对象。

​	每个对象都有唯一的表示且严格等于自己，原始值只要编码值相同就被认为相等。

​	原始值的属性不能被改变，添加或者删除（读取一个未知属性总会返回undefined）

8、常见的对象：

​	简单对象，通过字面量创建：

```
{
	firstName: 'Jane',
	lastName: 'Doe'
}
```

​	数组，通过数组字面量创建：

```
['apple', 'banana', 'cherry']   //通过索引读取
```

​	正则表达式

9、对象的特点：

​	按照引用进行比较

​	对象属性可以自由地被改变，添加和移除。

10、undefined表示没有值，未被初始化的变量，丢失的参数，不存在的属性都是undefined

​	null表示没有对象，用作对象的时候表示空值

11、typeof会返回原始值的分类    //typeof value    返回value类型

​	instanceof会返回是否属于对象     //value instanceof Constr   返回true/false

12、undefined、null、false、-0、NaN、''(空串)都会被解释称false，其他的都是true

13、二元逻辑运算符具有短路原则

​	与（&&）如果第一个数是假值，返回它，否则，返回第二个运算数

​	或（||）如果第一个数是真值，返回它，否则，返回第二个运算数

14、JavaScript中所有数字都是浮点数，NaN表示一个错误的值，Infinity多数情况也是一个错误的值，它比任何一个数（NaN除外）都要大。

15、字符串可以直接通过字符串字面量来创建，反斜杠（\）用于转义字符及产生一些控制字符。

​	字符串是不可以被改变的，要改变一个已有的字符串，必须创建一个新的才可以。

​	字符串可以通过" + "进行拼接

16、条件语句：

​	if语句，switch语句

```
if(){                   switch(){
	//then					case '':    //case的运算数可以是任意表达式
}else if(){						//...
	//then						break;
}else{						default:   //all other case
	then						//...
}							}
```

17、循环语句：

​	for循环语句，while循环语句，do-while语句，

​	break会跳出循环，continue会开始一个新的迭代循环

18、函数：

​	可以通过函数声明的 方式定义函数

​	还可以给变量赋值为函数表达式

​	函数声明具有提升特性，他们的实体会被移动到所在作用域的开始处，使我们可以引用后面生命的函数。（var声明也具有提升特性，但通过他们执行的赋值不具备该特性）

​	在JavaScript中，函数的所有参数都可以被arguments对象来调用，arguments是一个类数组对象，像一个数组，但不具备数组的方法。（arguments具有length属性）

​	在函数中，多余的参数会被忽略，丢失的参数会得到undefined。

​	如果想强制一个参数长度，可以通过arguments.length来检查。

​	将arguments转换成数组：

```
function toArray(arrayLikeObject){
	return Array.prototype.slice.call(arrayLikeObject);
}
```

19、严格模式：

​	严格模式激活更多的警告以及使JavaScript变得更干净

​	切换到严格模式：在\<script\>标签第一行输入：'use strict'; 或者在函数第一行输入：'use strict';

20、变量作用域和闭包

​	变量作用域

​		通过在变量前使用var语句声明变量

​		一个变量的作用域总是完整的函数（相对于当前模块）

​		所有变量声明都会被提升到函数的开始处，但是赋值仍然会在原来的位置进行

​	闭包

​		每个函数都和它周围的变量保持着连接，哪怕它离开被创建的作用域也是如此

```
function creatIncrementor(start){
	return function(){
		start ++;
		return start;
	}
}
var inc creatIncrementor(5);
inc();   //6
inc();   //7
inc();   //8
```

​		函数以及他所连接的周围作用域中的变量即为闭包，上函数的返回值就是一个闭包。

21、变量和构造函数

​	单一对象：和所有的值一样，对象也具有属性，可以直接通过对象字面量去创建普通对象

​		可以用in运算符检查属性是否存在：'属性名' in obj

​		使用delete运算符移除属性：delete obj.shuxing

​		对象的属性值可以是任何值，获取属性方法：obj['属性名'] = value;

​		对方法进行提取，则会失去域对象的连接，如：

```
var jane = {
	name: 'Jane',
	describe: function() {
		return this.name;
	}
}
var func = jane.describe;   //错误
var func = jane.describe.bind(jane);
```

​	构造函数：构造函数名称以大写字母开头，使用new运算符使用构造函数。

22、数组字面量可以方便地创建数组

​	length表明数组元素个数

​	in操作运算符也可以用在数组： 1 in arr    //1表示的是数组是否有这个下标

​	用forEach遍历数组：arr.forEach(elem);     //elem表示数组元素

​	map可以通过应用一个函数映射到现有的数组的每个已经存在的元素创建一个新的数组。

23、Math

```
	Math.abs(-2);     //2       （求绝对值）
​	Math.pow(3, 2);    //9
​	Math.max(2, -1, 5);      //5    （求最大值）
​	Math.round(1.9)     //2   (四舍五入)
​	Math.PI      //3.1415926...
​	Math.cos(Math.PI);       //-1
```

24、其他标准库：

​	Date

​	JSON

​	console.*系列方法

