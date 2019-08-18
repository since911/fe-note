平时工作中虽然有eslint这些工具帮助我们规范一下基本的代码，但更多的还是需要我们自身去注重一下代码质量，以下是我个人的一些经验总结笔记
### 1.不要用var，能使用const不用let
### 2.避免隐式转换，使用全等（===）进行判断
### 3.不要写冗余判断，比如
``` javascript
flag ： a === b ? true : false     不建议
flag ： a === b                      建议
```
### 4.if判断超过3个分支需优化，考虑使用策略模式
``` javascript
if(a === 'a'){
    title = '标题1'
} else if(a === 'b'){
    title = '标题2'
} else if(a === 'c'){
    title = '标题3'
} else {
    title = '标题4'
}

建议
const objMap = {
    a:'标题1'，
    b:'标题2'，
    c:'标题3'，
}
title = objMap[a] || '标题4'
```
### 5.不要留空代码块，或空方法，如：
``` javascript
if(a){
   
}else{
  //业务逻辑
}
```
### 6.判断数组是否有值 不需要 arr.lenth > 0 ,直接 arr.length
### 7.Array类型尽量使用forEach map等这些方法，看上去更简洁，数据不多的情况下，和for循环性能，可忽略
### 8.从执行效率角度，能用Array解决的就不要用Object
### 9.遍历对象使用Object.keys方式
### 10.从某对象取多个字段时，超过3个属性赋值最好抽成一个方法，不然看上起太冗余了
``` javascript
const param = {
    name : options.name,
    phone : options.phone,
    address : options.address,
    city : options.city
}

建议

const feildArr = ['name','phone','city','address']
const param = {}
feildArr.forEach(feild => {
   param[feild] = options[feild] 
})

```
### 11.如果只是普通的方法或者回调，能用箭头函数就用箭头函数，不要在项目中显式绑定或暂存this，除非特殊场景需要
### 12.不要在template写大量的判断表达式，这样会别人看代码感觉很懵逼，可以在data内声明变量，在业务方法里进行处理和注释,比如：
``` javascript
<div v-if="obj && obj.name && obj.phone && obj.addess"></div>

```
### 13.多次判断对象深层属性时，不要增加判断次数，对于对象嵌套过深的，最好先将对象进行缓存
``` javascript
const openId = res && res.data && res.data.openId || ''
const codeId = res && res.data && res.data.codeId ||''

建议

if(res && res.data){
   const _data = res.data
   const openId = _data.openId || ''
   const codeId = _data.codeId || ''
}
或者
let openId = '',codeId = '';
try{
    const openId = res && res.data && res.data.openId
    const codeId = res && res.data && res.data.codeId
} catch(e){
    
}

```
### 14.需要入参发送给后端的字段，一定要和接口字段统一，不然在请求发送前，还要对params所有字段重新赋值一遍，这样就产生了很多冗余代码
### 15.写复杂业务代码时，最好遵循单一原则，一个方法只做一件事，方便复用
### 16.待补充
