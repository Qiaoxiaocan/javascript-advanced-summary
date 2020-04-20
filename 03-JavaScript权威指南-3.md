# 类型、值和变量

JavaScript中所有数字均用浮点数值表示。

JavaScript的最大值：+-1.7974931348623157 * 10^308。最小值：5 * 10……-324。

```
Math.pow(2,53)               // => 9007199254740992: 2的53次幂
Math.round(.6)               // => 1.0:四舍五入
Math.ceil(.6)                // => 1.0:向上求整
Math.floor(.6)               //=>0.0:向下求整
Math.abs(-5)                 // => 5:求绝对值
Math.max(x,y,z)              // => 返回最大值
Math.min(x,y,z)              // => 返回最小值
Math.random()                // => 生成一个大于等于0小于1.0的伪随机数
Math.PI                      // => π:圆周率
Math.E                       // => e:自然对数的底数
Math.sqrt(3)                 // => 3的平方根
Math.pow(3, 1/3)             // => 3的立方根.
Math.sin(0)                  // => 三角函数:还有Math.cos, Math. atan等
Math.1og(10)                 // =>  10的自然对数
Math.1og(100)/Math. LN10     // => 以10为底100的对数
Math.1og(512)/Math. LN2      // => 以2为底512的对数
Math.exp(3)                  // => e的三次幂
```

```
var s = "hello, world"         // => 定义一个字符串
s.charAt(0)                    // => "h":第一个字符
s.charAt(s.1ength-1)           // => "d":最后一个字符
s.substring(1,4)               // => "el1" :第2~4个字符
s.slice(1,4)                   // => "ell": 同. 上
s.slice(-3)                    // => "rld": 最后三个字符
s. index0f("l")                // => 2:字符1首次出现的位置
s.lastIndex0f("1")             // => 10:字符1最后- -次出现的位置
s.index0f("1", 3)              // => 3:在位置3及之后首次出现字符1的位置
s.split(", ")                  // => ["hello", "world"] 分割成子串
s.replace("h", "H")            // => "Hello, world": 全文字符替换
S.toUpperCase()                // => "HELLO, WORLD"
```

JavaScript中的字符串都是固定不变的，返回的是一个新字符串。

null是空值，typeof null 返回的是"object"

null ==undefined但是null !===undefined

在JavaScript中，只要引用了字符串的属性，JavaScript就会将字符串值通过调用new String()的方式转换成对象，这个对象继承了字符串的方法，并被用来处理属性的引用，一旦引用结束，新创建的对象就会销毁。

还可以通过String()，Number()，Boolean()构造函数显示创建包装对象。

原始值不可改变。

声明提前：变量被忽略，函数被覆盖。











