# python 常用模块
## 如何自定义模块，并且调用定义模块
####  定义模块
- 模块就是一个.py文件，模块名就是文件名。例如定义一个person 模块:
-  person.py (文件名)
-  def eat(self):
-    print("eat")
-  class action():
-    def walk():
-        print("work")
-    def run(self):
-        print("run")
-    def sing(self):
-        print("sing")
####  调用模块
-   我们要知道python中，导入默认模块，只需要import 模块名，不需要指定路径。那是因为python 会去默认的路径找默认的模块。如果我们调用自己定义的模块，- -   我们就要给python 解释器加一个存放我们模块的路径，也就是告诉python ，去哪里找我们自定义的模块。他的语法是：
-   sys.path.append('your module path')
####  调用模块中的方法
-    person.eat()
#### 实例化模块中的类，调用类方法
-   robin=person.aciton()
-   robin.walk()
-   robin.run()
## os模块
- 1.os.getcwd()                           #获取python当前的工作路径
- 2.ch=os.chdir("c:/windows")	            #改变当前工作路径到指定目录		
- 3.print(os.curdir)		                  #curdir是一个属性 返回当前目录('.')
- 4.print(os.pardir)		                  #pardir也是一个属性 返回当前目录的父目录('..')
- 5.os.makedirs("web/webroot")            #可以创建多层级的目录
- 6.os.removedirs('dirname1')             #若目录为空，则删除，并递归到上一级目录，如若也为空，则删除，依此类推
- 7.os.mkdir('web')                       #生成单级目录
- 8.os.rmdir('dirname')                   #删除单级空目录，若目录不为空则无法删除
- 9.os.listdir('dirname' )                # 列出指定目录下的所有文件和子目录，包括隐藏文件，返回一个列表
- 10.os.stat('dirname' or 'filename')     #查看目录或者文件的状态信息，例如，修改时间，大小等
- 11.os.name                              #输出字符串指示当前使用平台。win->'nt'; Linux->'posix'
- 12.os.system('shell command')           #os.system("bash command")  运行shell命令，直接显示
- 13.os.environ                           #environ是一个属性，返回系统变量
- 14.os.path.abspath('path')              #返回规范化的绝对路径
- 15.os.path.split(path)                  #将路径的目录和文件分离成一个有2个元素的元组
- 16.os.path.dirname(path)                # 返回path的目录。其实就是os.path.split(path)的第一个元素
- 17.os.path.exists(path)                 #如果path存在，返回True；如果path不存在，返回False
- 18.os.path.isabs(path)                  #如果path是绝对路径，返回True
- 19.os.path.isfile(path)                 #如果path是一个存在的文件，返回True。否则返回False
- 20.os.path.isdir(path)                  #如果path是一个存在的目录，则返回True。否则返回False
- 21.os.path.join(path1[, path2[, ...]])  #将多个路径组合后返回，第一个绝对路径之前的参数将被忽略
- 22.os.path.getatime(path)               #返回path所指向的文件或者目录的最后存取时间
- 23.os.path.getmtime(path)               #返回path所指向的文件或者目录的最后修改时间
## time和datetime模块
- 1.time
