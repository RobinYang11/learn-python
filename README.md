# python中的变量
python 中定义变量不像java，c#,c++需要指定类型，也不像javascirpt 中那样需要关键字var 。而是直接写变量名就可以了。例如要定义一个字符串变量name<br>
Java中       String name;<br>
c#中         String name;<br>
javacript中     var name;<br>
而在python中，直接写 name 就可以了
# python 中的数据类型
## 1.Number(数字）
Number又可分为<br>
     <b>int</b>--整型 ：1,-4,34,0<br> 
     <b>float</b>--浮点型：34.4 ,0.4<br>
     <b>bool</b>--布尔型：因为布尔型只有2个结果，即：1和0，所有布尔型在python中归类为数字型<br>
     <b>complex</b>--复数：不是很了解，等弄明白了 ，回来再补充<br>
## 2.String (字符串）
  python 中可以用单引号，双引号，三引号定义字符串。<br>
  三引号可以中的字符串可以换行。<br>
  需要注意的是在java c#中，String 类型不是基本数据类型，而是引用数据类型，也就是说要定义一个字符串，必须要调用String类的构造方法，虽然我们可以这样定义一个字符串<br>
    <code> String name ="国平"</code><br>
 但其实 是这样 <br>
     <code>String name =new String ("国平")</code> <br>
       
## 3.list(列表)
## 4.turple(元组)
## 5.sets (集合)
## 6.Dictionary(字典)
# python中面向对象的实现
##  继承
-  定义一个基本的类:
-  class base_class():
-      def __init__(self,args):              # __init__()是python中的构造函数 
-           self.args=args
-      def method_to_be_overrided():
-           print("i will be overrided ,if  some class extend me")
-  继承基本类
-  class extend_class(base_class):           # 在后面的括号里面加上其他类的名称就可以了
-      def __init__(self,arg):
-           self.arg=arg
-      def method_to_be_overrided():
-            print("overrided);
-  需要特别注意，python的派生类实例化对象时，并不会自动基类的构造方法。派生类对象会首先在本类查找init方法，如果找到就调用然后完成实例化，如果找不到，则会在基类中寻找init方法完成实例化。如果有多个基类，则会按照继承的顺序依次寻找init方法，这个后面还会讲到。
### 多重继承
- class base1():  
-    def __init__(self):  
-        print "base1 called";  
-          
- class base2():  
-    def __init__(self):  
-        print "base2 called";  
-  
- class derive1(base1,base2):  
-    def __init__(self):  
-        #base1.__init__(self);  
-        #base2.__init__();  
-        print "derive1 called";  
-  
- class derive2(base2,base1):  
-    pass;  
