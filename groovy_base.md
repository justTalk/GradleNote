## 基础语法
1.变量定义
  def a = 1
2.函数定义:函数不用自己return，默认情况下，函数的最后一行就是返回的结果
  def add(x,y){
     x + y
  }
3.函数调用：
  当函数的参数个数大于等于1时，可以省略调用的括号，当没有参数时不能省略括号
4.闭包，可以当成参数传递的函数,闭包能访问到当前文件的变量值
  def myClosure = {
     println "hello form a closure"
  }
  myClosure()
  def bar = myClosure
  bar()
  -------------------------------
  def doubleit = { x-> x+x}
  def applyTwice(func, args){
      doubleit(doubleit(args))
  }
5.数据结构：
  数组：def myList = ["a", "b", "c"]
  遍历并对每一项执行动作：
  def printlnItem = {item -> println "list item:  $item"}
  myList.each(printlnItem)
6.类：gradle中可以使用java语言定义类，也可以使用groovy语言定义一个类
  class GroovyClass{
     String name = "LMM"
     def printlnName() {
        println "$name"
     }
  }
  def groovyClass = new GroovyClass()
  groovyClass.printlnName()
  闭包和类的结合：闭包可以设置代表对象
  def objClosure = {
     name = "objClosure "
     printlnName()
  }
  objClosure.delegate = groovyClass
  objClosure()