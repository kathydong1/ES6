1.let
      1）-- 同var相似，声明变量的，但是let在预解析时不会提前解析，不可命名重复，类似下边的代码块在外是不能获取道的
      2）--let在for循环中，在for循环括号内声明的let是父作用域，在{}内声明的是子作用于

    
2.const
    声明常量（简单类型：不可以更改的量；引用类型：只要引用地址不变，里边的值是可以改变的）,声明的时候必须赋值
    


3.解构赋值
     let[a,b,c]=[1,2,3]//==>abc一一对应赋值123；
     数组的解构赋值：只要=两边的结构相同，就能正常赋值
          let [a=1]=[]//设置了默认项：a=1
     对象的解构赋值：
        let{a,b}={b:'bbb',a:'aaa'}//属性名相同后赋值
     
4.set：类似数组，但是成员是唯一的不能能重复
    集合：let set=new Set()
    set属性只有一个size====>表示长度
    set方法：
        set.add(value)==>添加数据
        set.delete(value)===>删除数据，返回布尔值，删除成功TRUE，删除不成功false
        set.has(value)====>有该value，返回TRUE，没有返回false
        set.clear====>清空
        set.key()==>返回值
        set.values()===>返回键
        set.entries()===>返回键值对
        set.foreach(function(a,b,c){
               a==>值
               b===>下标
               c====>整个set
           })
        
5.map:类似json,但是是值：值
   let map=new Mao([
         ['a',1],
         ['b',2]
   ])=====>map(2){'a'==>1,'b'==>2}
   map属性：map.size
   map方法：
       map.set('value1','vlaue2')==>添加键值对
       map.get(key)==>找到key的值，有返回值，否则underfine;
       map.delete(key)==>删除：返回布尔值
       map.has(key)==>判断是否有：返回布尔值
       map.clear()===>清除
       map.keys()===>返回键名
       map.values（）===>返回键对应的值
       map.entries()===>返回键值对
       map.foreach(function(a,b,c){
           a===>键
           b====>值
           c=====>map
       })
      注意项：map添加两个NAN，map认为NAN是同一个键
             map添加两个{}，因为对象地址不同，两个都可以添加到map内
             map里边key的顺序是按照添加顺序添加的
             
  6.iterator和for...of循环
      ES6定义了只要改数据具有Symbol.iterator（）就具有iterator接口
      对象不具备该接口
      具备该接口的数据结构可以进行解构赋值，还有扩展运算符[...str]
     for(let i of arr){
        i===>数组每一项
  7.class
       类：面向对象的ES6写法
       class Person{//人类
           constructor(参数a，参数b){//属性,指定构造函数,this代表实例化对象
                this.a=a
                this.b=b
           }//不能加，
           say(){//方法
             console.log(a,b)
           }
       }
       var p=new Person().say()
  8.class的继承
      class human extends Person{
          constructor(参数a,参数b，自身参数c){
              super(参数a,参数b)
              this.c=c
      }
      
      sing(){
        console.log('继承方法')
      }
  9.  箭头函数：
                    var fn=()=>alert(1);//相当于return alert（1），且当不传参数时必须用（）
		    fn()
		    var f=()=>{执行的代码}
		    var fn=(a)=>代码       ||  var fn= a =>代码
   		    var fn=(a,b,c)=>代码|返回值     括号不能省略,否则报错
   		       
   		       箭头函数的this，永远指向“定义时”的父级，
   		       事件函数是不能用箭头函数的，因为this指向改变了，是Window
   		    "use strict"==严格模式，
   		                        如果直接函数名（），this指向是underfine（主要是用在this，上，正常能够指向Windows的用了严格模式，就是underfine）
   		                        如果在事件绑定中，this指向不变 
