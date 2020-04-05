# 类型

#### 内置类型

​	JavaScript有七种内置类型：

​		空值（null）

​		未定义（undefined）

​		布尔值（boolean）

​		数字（number）

​		字符串（string）

​		对象（object）

​		符号（symbol，ES6中新增）

​	函数function是JavaScript的object的一个子类型，还可以拥有属性。

​	数组也是对象，同为object的一个子类型。

#### 值和类型

​	JavaScript中的变量是没有类型的，只有值才有，变量可以随时持有任何类型的值。

​	在对变量执行typeof操作时，得到的时该变量持有的值得类型。

​	已在作用域中声明但是还没有赋值的变量，是undefined；还没有在作用域中声明过的变量，是undeclared的。

# 值

​	在JavaScript中，数组可以容纳任何类型的值，如：var a = [1, "2", [3]];

​	数组声明后可向其中加入值，不需要预先设定大小。

​	JavaScript中的字符数组和字符串不是一回事，只是看上去相似。字符串是不可变得，字符数组可变。

​	反转函数reverse()在数组中有，在字符串中没有。

​	可以使用join("")将字符数组转换为字符串。

​	数字值可以使用Number对象进行封装，因此数字值可以调用Number.prototype中的方法。

​	比较两个数字（小数）是否相同（直接用==可能会有精度问题）：

```
function numberCloseEnoughToEqual(n1, n2){
	return Math.abs(n1 - n2) < Number.EPSILON;   //Number.EPSILON的值为2^-52，表示机械精度。
}
```

​	JavaScript中最大的整数是2^53 - 1，即99007199254740991，在ES6中被定义为Number.MAX_SAFEINTEGER

​	JavaScript中保存较大的数会把他们转换成字符串。

​	Number.isInteger()    判断一个数是否为 整数。

​	null指曾赋过值，但是目前没有值（空值）；undefined值从未赋过值

​	null是个特殊关键字，不是标识符，不能当做变量，undefined是标识符，可以当做变量。

​	如果数学运算的操作数不是数字类型，就无法返回有效数字，此时会返回NaN，NaN是数字类型，NaN和自身不相等，是唯一一个非自反的值。

​	可以用isNaN(num)来判断num是否是NaN

​	JavaScript运算结果溢出时结果为Infinity（分正负）

​	简单值总是通过复制的方法来赋值/传递，复合值（对象，函数等）通过引用复制的方式来赋值/传递。

# 强制类型转换

 	ToString负责处理非字符串到字符串的强制类型转换。

​	普通对象来说，除非自行定义，否则 toString()返回 内部属性 [[Class]] 的值

​	ToNumber将非数值转化为数字

​	true 转换为 1，false 转换为 0。undefined 转换为 NaN，null 转换为 0

​	ToBoolean转化为布尔值

​	undefined，null，false，+0，-0，NaN，""都转为false，其他转为true

#### 显示类型转换

String()，Number()，Boolean()

#### 显式解析数字字符串

```
var a = "42"; 
var b = "42px"; 
Number( a );    // 42 
parseInt( a );  // 42 
 
Number( b );    // NaN 
parseInt( b );  // 42
```

#### 显式转换为布尔值

```
var a = "0"; 
var b = []; 
var c = {}; 
 
var d = ""; 
var e = 0; 
var f = null; 
var g; 
 
Boolean( a ); // true 
Boolean( b ); // true 
Boolean( c ); // true 
 
Boolean( d ); // false 
Boolean( e ); // false 
Boolean( f ); // false 
Boolean( g ); // false
```

```
var a = "3.14"; 
var b = a - 0; 
b; // 3.14

var a = [3]; 
var b = [1]; 
a - b; // 2
```

#### &&和||

​	&&和||返回值是两个操作数中的一个（且仅一个）。即选择两个操作数中的一个，然后返回它的值（短路原则）

```
"0" == null;           // false 
"0" == undefined;      // false 
"0" == false;          // true -- 晕！ 
"0" == NaN;            // false 
"0" == 0;              // true 
"0" == "";             // false 
 
false == null;         // false 
false == undefined;    // false 
false == NaN;          // false 
false == 0;            // true -- 晕！ 
false == "";           // true -- 晕！ 
false == [];           // true -- 晕！ 
false == {};           // false 
 
"" == null;            // false 
"" == undefined;       // false 
"" == NaN;             // false 
"" == 0;               // true -- 晕！ 
"" == [];              // true -- 晕！ 
"" == {};              // false 
 
0 == null;             // false 
0 == undefined;        // false 
0 == NaN;              // false 
0 == [];               // true -- 晕！ 
0 == {};               // false
```

