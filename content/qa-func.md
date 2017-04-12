## die 和 exit 的区别是什么?
问题[链接](https://stackoverflow.com/questions/1795025/what-are-the-differences-in-die-and-exit-in-php)
没有却别，在php参考文档中，他们是等效的

## == 和 === 的区别
$a == $b  当经过类型转化(date juggling)后相等时为true
$a === $b $a$b 为同一类型，且值相同时为true

== 会涉及到类型转化(date juggling)简单说明下类型转化规则
convert to boolean
  1.本身为false
  2.数字为0
  3.浮点为0.0
  4.空字符串或者“0”
  5.空数组
  6.NULL
  7.simpleXML oject create from empty tag

convert to integer
  1.true转化为1 false 转化为0
  2.浮点值取round,特别的是，超出int值范围的浮点数转化为int的值是不确定的，而且转化的过程不会有任何提示产生
  3.字符串，不包含. E e 字符且全部是数字的字符串字节转化为int，其它所有情况转化为float，在从float的转化中，第一部分的值代表了string转化为int的转化，转化有正负之分
  4.其它类型的转化不可确定

convert to float
   1.字符串，不包含. E e 字符且全部是数字的字符串字节转化为int，其它所有情况转化为float，在从float的转化中，第一部分的值代表了string转化为int的转化，转化有正负之分
   2.其它类型的转化先转成int类型，再有int转为float

convert to string
   1.bool true 转化为1  bool false 转化为 0
   2.数字直接转化
   3.浮点直接转化
   4.数组转化为“array”
   6.obj无法转化string，必须实现魔法方法__toString()

convert to array
   1.基本类型 boolean int float string 转化为array直接生成一个单元素数组
   2.对象专为为数组讲properties生成数组，数组名为key，值为value，注意int unaccessiable  private 前置* 


## empty isset is_null的却别

## require include require_once 的区别
include和require 在功能上是等效的，却别在错误的处理上，include 碰到错误生成一个警告，程序继续执行，require生成致命错误(fatal error）中断程序执行。

## echo print print_r A

## display php errors

   ini_set('display_errors', 1)
   ini_set('display_startup_errors', 1);
   error_reporting(E_ALL);

this does not display parse errors,the only way to display parse error is modify you php.ini file 

   display_erros = on

