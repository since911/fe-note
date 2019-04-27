# 目录

## JS 篇

### 1：箭头函数和普通函数的区别
> - 箭头函数不可以被当作构造函数
> - 箭头函数没有arguments对象,用rest解构参数（...params）代替
> - 不可以使用yield命令，因此箭头函数不能用作 Generator 函数
> - 普通函数this指向它的调用者,箭头函数this继承它的定义者（在哪个对象定义，就指向当前对象）
      ```javascript
      var obj = {
        fun1 : () => {
          console.log(this)
        },
        fun2 : function(){
          console.log(this)
        }
      }
      obj.fun1() // window
      obj.fun2() // obj
      ```
> - 非严格模式下，没有找到直接调用者的函数，this指向window
> - 严格模式下，没有直接调用者的函数，this为undefined
> - call,apply,bind可以改变普通函数this指向

### 2：var let const 区别
> - var存在变量提升，只有函数作用域
> - let不存在变量提升，有块级作用域
> - const指向当前变量的内存地址，声明时必须赋值，如果是值类型声明后不可修改，引用类型可修改当前对象的属性，但改变当前变量的内存地址（即不可重新赋值）
> - let 和 const存在暂时性死区