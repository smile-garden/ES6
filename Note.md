ES6  新语法  新特性  Harmony

各大浏览器没有对ES6完美支持   babel编译器  使其转换成ES5标准的代码，使其得到大浏览器的支持。babel的模块转换器的设计特点赢得了绝大部分JavaScript的青睐。

语法糖 <br> 
也被译为语法糖衣。指计算机语言中添加的某种语法，这种语法对语言的功能并没有影响，但是更方便程序员使用。 <br>
通常来说使用语法糖能够增加程序的可读性，从而减少程序代码出错的机会。

工程优势 <br>
ES6除了提供了语法糖外，还实现了 JavaScript的模块化构建。

1、let const <br>
let const是继var之后，新的变量定义方法。与let相比，const更容易被理解 const （constant的缩写），用于定义常量，即不可变量。

在ES6诞生之前，JavaScript确实是没有块级作用域的。let语句会使该变量处于一个块级作用域中。

2、箭头函数 <br>
使用箭头(=>)定义的函数，属于匿名函数。不推荐定义式函数。
使用方法：

a. foo => foo + 'world'  <br>
b. (foo, bar) => foo + bar <br>
c. foo => {
	return foo + 'world'
}  <br>
d.(foo, bar) => {
	return foo + bar
}

箭头函数语言简洁的特点使其特别适合用于单行回调函数的定义。 <br>
箭头函数是用于对函数内部的上下文(this)绑定为定义函数所在的作用域的上下文。

注意，箭头函数对上下文的绑定是强制性的，无法通过applu和call方法改变其上下文。 <br>
因为箭头函数会绑定上下文的特性，故不能随意在顶层作用域使用箭头函数。

模版字符串要求使用`代替原本的单/双引号来包裹字符内容  <br>
1.支持变量注入   允许字符串中引用外部力量。 <br>
2.支持换行

3、对象字面量扩展语法 <br>
方法属性省略function       <br>
支持__proto__注入  可以给一个对象硬生生的赋予其__proto__,  <br>这样他就可以成为这个值所属类的一个实例了。

4、同名方法属性省略语法  <br>
JavaScript模块化工程的时候有用。

5、可以动态计算的属性名称 <br>

6、函数参数表达、传参

7、表达式解构 <br>  多重复值
在严格模式中，arguments.callee和arguments.caller是被禁止使用的。

8、默认参数值和后续参数需要遵循顺序原则。另外根据函数调用的原则，无论是默认参数还是后续参数都需要小心使用。

9、后续参数  <br>
...args后不可添加  <br>
虽然从语言角度看，arguments和...args是可以同时使用的，但有一个特殊情况则不可：arguments在肩头函数中，会跟随上下文绑定到上层，所以不确定上下文绑定请结果的情况下，尽可能不要再箭头函数中使用arguments，而使用...args。（除非有很特殊的场景需要使用到arguments。callee 和arguments.caller，但在严格模式[Strict Mode]下，是被禁止使用的）

10、解构传参 <br>

11、新的数据结构  <br>
ES2015之前 JavaScript中之前有那些基本的数据结构  <br>
String  Number  Boolean  Object Array  值类型和引用类型 <br>

增添了集(Set)和弱集(WeakSet)。 <br>
它们都具有元素唯一性，若添加了已存在的元素，会被自动忽略。 <br>
WeakSet在JavaScript底层做出调整，检查元素的变量引用情况。另外WeakSet对元素有严格要求，必须是Object。

Map和WeakMap <br>
从数据结构的角度来说，映射（Map）跟原本的Object非常相似，都是Key/Value的键值对结构。但是Object的key必须是字符串或数字。而Map可以使用任何对象最为其key。

11、类(Classes) <br>
与JavaScript中的对象字面量不一样的是，累的属性后不能加逗号，而对象字面量则必须要加逗号。 <br>
ES2015中若要是一个类继承于另外一个类而作为其子类，只需要在子类的名字后面加上extends {SuperClass}即可

12、静态方法 <br>
ES2015中的类机制支持static类型的方法定义  instanceof返回的是一个布尔值，intanceof只能用来判断对象和函数，不能用来判断字符串和数字等。 <br>
ES2015的类并不能直接地定义静态成员变量，但可以用static加上get语句和set语句实现间接实现静态成员变量。

13、生成器（Generator） <br>

14、原生的模块化   <br>
暴露单独接口
暴露复盖模块

15、Promise <br>
Promise是一种用于解决回调函数无限嵌套的工具。作用是“免去”异步操作的回调函数，保证通过后续监听而得到返回值，或对错误处理。 <br>
基本用法： <br>
创建Promise对象 <br>
要为一个函数赋予Promise的能力，先要创建一个Promise对象，并将其作为返回值。Promise构造函数要求传入一个函数，并带有resolve和reject参数。这是用于结束Promise等待的函数，对应的成功和失败。而我们的逻辑代码就在这个函数中进行。 <br>
因为必须要让这个函数包裹逻辑代码，所以如果需要用到this时，则需要使用箭头函数或者在前面做一个this的别名。 <br>

Promise弊端 <br>
虽说Promise确实很优雅，但是这是在所有需要用到的异步方法都支持Promise且遵循标准。而且链式Promise强制性要求逻辑必须是线性单向的，一旦出现并行、回溯等情况。Promise便显得十分累赘。 <br>
Promise会作为一种接口定义方法，而不是逻辑处理工具。

16、Symbol  <br>
在JavaScript中，对象的属性名称可以是字符串或数字。而Symbol也可以。 <br>
Symbol对象是具有唯一性的，每一个Symbol对象都是唯一的，可以用它来保证一些数据的安全性。<br>
如果将一个Symbol隐藏于一个封闭作用域内，并作为一个对象中某属性的键，则外层作用域中便无法取得该属性的值，有效保障了一些私有库的代码安全性。 <br>

Symbol.iterator   iterator 迭代器  <br>
ES2015还为javascript带来了for...of语句    与之前for...in有什么区别


17、Proxy（代理）中的一种新概念  <br>
Proxy是ECMAScript中的一种新概念，其基本作用是：Proxy可以在不入侵目标对象的情况下，对逻辑进行拦截和处理。 <br>
目前Proxy的兼容性很差，降级兼容也难以实现。


更多前端学习资源  https://fenglingcong.github.io/resource/


<h4>后记</h4>
对于一个普通的JavaScript开发者来说，ES2015可能会让人觉得很模糊和难以学习，以为ES2015中带来了许多我们从前没有在JavaScript中接触过的概念和特性。但是经过长时间的考察，我们不难发现ES2015始终是JavaScript的发展方向之事不可避免的。因此我要在很长一段时间内都向身边的或是社区中的JavaScript开发者推广ES2015，推荐他们使用最新的技术。



