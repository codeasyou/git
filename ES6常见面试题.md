1.es5和es6的区别，说一下你所知道的es6

ECMAScript5，即ES5，是ECMAScript的第五次修订，于2009年完成标准化

ECMAScript6，即ES6，是ECMAScript的第六次修订，于2015年完成，也称ES2015

ES6是继ES5之后的一次改进，相对于ES5更加简洁，提高了开发效率

ES6新增的一些特性：

1）let声明的变量和const声明的常量，两个都有块级作用域ES5中是没有块级作用域的，并且var有变量提升，在let中

使用的变量一定要进行声明。

2)箭头函数ES6中的函数定义不再使用关键字function(),而利用了()=>来进行定义

3)模板字符串是增强版的字符串，用（`）标识，可以当做普通字符串使用，也可以用来定义多行字符串

4)解构赋值ES6中允许按照一定模式，从数组和对象中提取值，对变量进行赋值。

5)for of 循环和for ...of 循环可以遍历数组、Set和Map结构、某些类似数组的对象、对象，以及字符串。

6)import、export导入导出ES6标准中，JS原生支持模块(module)。将JS代码分隔成不同功能的小块进行模块化，

将不同功能的代码分别写在不同的文件中，各模块只需导出公共接口的部分，然后通过模块的导入的方式可以在其他地方使用。

7)set数据结构，类似数组。所有的数据都是唯一的，没有重复的值。他本身就是一个构造函数。

8)...展开符可以将数组或对象里面的值展开；还可以将多个值收集为一个变量。

9)修饰器@decorator是一个函数，用来修改类甚至方法的行为，修饰器本质就是编译时执行的函数

10)class类的继承ES6中不再像ES5一样使用原型链实现继承，而是引入Class这个概念。

11)async、await使用async/await,搭配promise，可以通过编写形似同步的代码来处理异步流程，提高代码的简洁性和可读性async用于声明一个function是异步的，而await用于等待一个异步方法执行完成。

12)promise是异步编程的一种解决方案，比传统的解决方案(回调函数和事件)更合理、强大。

13)Symbol是一种基本类型。Symbol通过调用symbol函数产生，他接收一个可选的名字参数，该函数返回的symbol是唯一的。

14)Proxy代理使用代理(Proxy)监听对象的操作，然后可以做一些相应的事情。

2.var、let、const之间的区别

var 声明的变量可以重复声明，而let不可以重复声明。

var 是不受限于块级的，而let是受限于块级的。

var 会与window相映射(会挂一个属性),而let不与window相映射。

var 可以在声明的上面访问变量，而let有暂存死区，在声明的上面访问变量会报错。

const和let一样不会与window相映射，支持块级作用域、在声明的上面访问变量会报错。

3.使用箭头函数应注意什么？

(1)用了箭头函数，this就不是指向window，而是父级(指向是可变的)。

(2)不能使用arguments对象。

(3)不能用作构造函数，这就是说不能够使用new命令，否则会抛出一个错误。

(4)不可以使用yield命令，因此箭头函数不能用作Generator函数

4.ES6的模板字符串有哪些新特性？并实现一个类模板字符串的功能。

基本的字符串格式化。将表达式嵌入字符串中进行拼接。用${}来界定。

在ES5时我们通过反斜杠()来做多行字符串或者字符串一行行拼接。ES6反引号(``)就能解决。

类模板字符串的功能

let name='web';

let age=10;

let str=`你好，${name}已经${age}岁了`

str=str.replace(/\$\{([^}]*)\}/g,function(){

​     return eval(arguments[1]);

})

console.log(str);//你好，web已经10岁了

5.介绍下Set、Map的区别？

应用场景Set用于数据重组，Map用于数据存储。

Set:

(1)成员不能重复

(2)键值没有键名，类似数组(3)可以遍历，方法有add,delete,has

Map:

(1)本质上是键值对的集合，类似集合

(2)可以遍历，可以跟各种数据格式转换。

6.ECMAScript 6怎么写calss，为何会出现class?

ES6的class可以看做是一个语法糖，他的绝大部分功能ES5都可以做到。新的class写法只是让对象原型的写法更加清晰、更像面向对象编程的语法。

//定义类

class Point{

   constructor(x,y){

​     //构造方法

​    this.x=x;//this关键字代表实例对象

​    this.y=y;

  } toString(){

​    return '(' +this.x + ',' +this.y + ')';

  }

}

7.Promise构造函数时同步执行还是异步执行，那么then方法呢？

promise构造函数时同步执行的，then方法是异步执行的

8.setTimeout、Promise、Async/Await的区别？

事件循环中分为宏任务队列和微任务队列

 

其中setTimeout的回调函数放到宏任务队列里，等到执行栈清空以后执行。

 

promise.then里的回调函数会放到相应宏任务的微任务队列里，等宏任务里面的同步代码执行完再执行。

 

async函数表示函数里面可能会有异步方法，await后面跟一个表达式。

 

async方法执行时，遇到await会立即执行表达式，然后把表达式后面的代码放到微任务队列里，让出执行栈让同步代码先执行。

9.promise有几种状态，什么时候会进入catch?

三个状态：pending、fulfilled、reject

两个过程：pedding->fulfilled、pedding->rejected

当pending为rejected时，会进入catch

10.下面的输出结果是多少？

const promise =new Promise((resolve,reject)=>{

   console.log(1);

   resolve();

   console.log(2);

})

 

promise.then(()=>{

  console.log(3);

})

 

console.log(4);

Promise新建后立即执行，所以会先输出1,2而Promise.then()内部的代码在当次事件循环的结尾立刻执行，所以会继续输出4，最后输出3

11.使用结构赋值，实现两个变量的值的交换。

let a=1; let b=2;

[a,b] =[b,a];

12.设计一个对象，键名的类型至少包含一个symbol类型，并且实现遍历所有key

let name=Symbol('name');

let product={

[name]: "洗衣机"，

   "price":799

};

Reflect.ownKeys(product);

13.下面Set结构，打印出来的size值是多少

let s=newSet();

s.add([1]);

s.add([1]);

console.log(s.size);

答案：2

两个数组[1]并不是同一个值，他们分别定义的数组，在内存中分别对应着不同的存储地址，因此并不是相同的值。

都能存储到Set结构中，所以size为2。

14.Promise中reject和catch处理上有什么区别？

reject是用来抛出异常的，catch是用来处理异常。

reject是Promise的方法，而catch是Promise实例的方法。

reject后的东西，一定会进入then中的第二个回调，如果then中没有写第二个回调，则进入catch

网络异常(比如断网)，会直接进入catch而不会进入then的第二个回调。

15.使用class手写一个Promise

//创建一个Promise的类

class Promise{

   constructor(executer){//构造函数constructor里面是个执行器

​    this.status='pending';//默认的状态 pending

​    this.value=undefined //成功的值默认undefined

​    this.reason=undefined //失败的值默认undefined

​    //状态只有在pending时候才能改变

​     let resolveFn= value =>{

​    //判断只有等待时才能resolve成功

​    if(this.status==pending){

​      this.status='resolve';

​      this.value=value;

​    }

  }

try{

   //把resolve和reject两个函数传给执行器executer

​    executer(resolve,reject);

 }.catch(e){

   reject(e);//失败的话进catch

  }

}

then(onFufilled.onReject){

  //如果状态成功回调用onFufilled

  if(this.status='resolve'){

   onFufilled(this.value);

 }

 //如果状态失败调用onReject

if(this.status = 'reject' ){

  onReject(this.reason);

 }

 }

}

16.如何使用Set去重

let arr=[12,43,23,43,68,12];

let item=[...new Set(arr)];

console.log(item);//[12,43,23,68]

 

17.将下面for循环改成for of 形式

let arr=[11,22,33,44,55];

let sum=0;

for(let i=0;i<arr.length;i++){

  sum+=arr[i];

}

答案：

let arr=[11,22,33,44,55];

let sum=0;

for(value of arr){

  sum+=value;

}

18.理解async/await以及对Generator的优势

async await是用来解决异步的，async函数是Generator函数的语法糖

 

使用关键字async来表示，在函数内部使用await来表示异步。

 

async函数返回一个Promise对象，可以使用then方法添加回调函数

 

当函数执行的时候，一旦遇到await就会先返回，等到异步操作完成，再接着执行函数体内后面的语句

async较Generator优势：

(1)内置执行器，Generator函数的执行必须依靠执行器，而Aysnc函数自带执行器，调用方式跟普通函数的调用一样。

(2)更好的语义。async和await相较于*和yield更加语义化

(3)更广的适用性。yield命令后面只能是Thunk函数或Promise对象，async函数的await后面可以是Promise也可以是原始类型的值

(4)返回值是Promise,async函数返回的是Promise对象，比Generator函数返回的lterator对象方便，可以直接使用then()方法进行调用。

19.forEach、for in、for of 三者区别

forEach更多的用来遍历数组

for in 一般用来遍历对象或json

for of 数组对象都可以遍历，遍历对象需要通过和Object.keys()

for in 循环出的是key,for of 循环的是value

20.说一下es6的导入导出模块

导入通过import关键字

//导入通过import关键字

import {sum} from "./example.js"

//导入多个

import {sum.multiply.time} from "./exportExample.js"

//导入一整个模块

import * as example from "./exportExample.js"

//导出通过export关键字

//可以将export放在任何变量，函数或类声明的前面

export var firstName ='Michael';

export var lastName='Jackson';

export var year=1958;

//也可以使用大括号指定所要输出的一组变量

var firstName='Michael';

var lastName='Jackson';

var year=1958;

export {firstName,lastName,year};

//使用export default时，对应的import语句不需要使用大括号

let bosh=function crs( ){ }

export default bosh;

import crc from 'crc';

//不使用export default 时，对应的import语句不需要使用大括号

let bosh=function crs( ){ }

export bosh;

import {crc} from 'crc';