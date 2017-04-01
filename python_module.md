# 国平学python之 常用模块
- python 模块module 相当于java中类文件，但也不是完全相同。java中类 和文件名必须一样，python 则不用， java中所有的方法和属性必须写在 该类的大括号内， 建议一个类文件内只写一个类，但python 中，一个模块中可以有多个类，和多个与类同级多个方法。与其说像java中的类文件，不如说像java中的package ，但是package 又不是文件，所有python  兼有java中类文件和package的功能
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
- 在Python中，通常有这几种方式来表示时间：
- b时间戳
- 格式化的时间字符串
- 元组（struct_time）共九个元素。
- 由于Python的time模块实现主要调用C库，所以各个平台可能有所不同。 
- UTC（Coordinated Universal Time，世界协调时）亦即格林威治天文时间，世界标准时间。在中国为UTC+8。DST（Daylight Saving Time）即夏令时。  
- 时间戳（timestamp）的方式：通常来说，时间戳表示的是从1970年1月1日00:00:00开始按秒计算的偏移量。我们运行“type(time.time())”，返回的是float类 - 型。返回时间戳方式的函数主要有time()，clock()等。 
- 元组（struct_time）方式：struct_time元组共有9个元素，返回struct_time的函数主要有gmtime()，localtime()，strptime()。
### time模块
- time.time()  # 获取时间戳：当前时间减1970-1-1 00:00 ==> 秒
-  time.localtime()  # 本地时间，元组方式（tm_isdst() 是否夏令时）
- time.struct_time(tm_year=2016, tm_mon=8, tm_mday=29, tm_hour=0, tm_min=51, tm_sec=37, tm_wday=0, tm_yday=242, tm_isdst=0) 
- help(time)  # 模块帮助
- time.timezone  # 查看时区
- -28800  # 28800/60秒/60分 = 8时 ==> utc --> 标准+8 
- time.sleep()  # 时间睡几秒
- time.gmtime()   # 不加时间戳，为国际标准时间
- time.localtime()   # 不加时间戳，本地时间
- 加上则从1970年开始算。
### 时间转为时间戳
- x = time.localtime()
- time.struct_time(tm_year=2016, tm_mon=8, tm_mday=29, tm_hour=1, tm_min=0, tm_sec=8, tm_wday=0, tm_yday=242, tm_isdst=0)
- time.mktime(x)  得到 1472403608.0 
### 转化时间戳和元组到时间字符串
- time.asctime(time.localtime())  # tuple -> string
- 'Mon Aug 29 01:10:47 2016' 
- time.ctime(888888888)  # seconds -> string
- 'Tue Mar  3 09:34:48 1998' 
### 时间加减
- import datetime
- datetime.datetime.now() # 返回 2016-08-19 12:47:03.941925
- datetime.date.fromtimestamp(time.time())  # 时间戳直接转成日期格式 2016-08-19
- datetime.datetime.now() + datetime.timedelta(3) # 当前时间+3天
- datetime.datetime.now() + datetime.timedelta(-3) # 当前时间-3天
- datetime.datetime.now() + datetime.timedelta(hours=3) # 当前时间+3小时
- datetime.datetime.now() + datetime.timedelta(minutes=30) # 当前时间+30分
##  sys模块
- sys.argv[index]       命令行参数list ，第一个元素是程序本身的路径
- 在命令行执行python 文件时 可以带参数，这些参数可以在py文件里面使用，例如： 
- 在命令行中 ： python firstproject.py  'parm1' 'param2' 'parm3'   #切记：参数用空格隔开
- 然后在py文件里面 我们可以使用sys.argv[index] 接收这些参数
- a=sys.argv[1]='parm1'    b=sys.argv[2]='param2'    c=sys.argv[3]='param3'
- sys.exit()   退出程序
- sys.path      返回模块的搜索路径  
- sys.path.append('path')   增加 指定路径为 模块的搜索路径
-  sys.platform 返回操作系统平台名称 
## shutil模块 ：高级的文件，文件夹，拷贝，压缩包等处理模块
- shutil.copy(src,dst)            拷贝src文文件 到指定的dst目录 如果目标位置存在 该文件会报 file is exists错误
- shutil.move(src,dst)            剪切  src文件  到指定的dst目录 如果目标位置存在 该文件会报 file is exists错误
- shutil.copytree(src,dst)        拷贝目录 ，用法与上面2个相似，不在赘述
- shutil.rmtree('dst')            删除目录及该目录下所有子目录
- shutil.make_archive('src',format)      把 指定文件压缩 成zip 或者 tar. src是源文件，format有zip 和tar 2中格式。默认创建到源文件路径。
- shutil.unpack_archive(filename, extract_dir=None, format=None)     解压指定文件
## re 正则表达式模块
### 常用正则表达式符号
- '.'     默认匹配除\n之外的任意一个字符，若指定flag DOTALL,则匹配任意字符，包括换行
- '^'     匹配字符开头，若指定flags MULTILINE,这种也可以匹配上(r"^a","\nabc\neee",flags=re.MULTILINE)
- '$'     匹配字符结尾，或e.search("foo$","bfoo\nsdfsf",flags=re.MULTILINE).group()也可以
- '*'     匹配*号前的字符0次或多次，re.findall("ab*","cabb3abcbbac")  结果为['abb', 'ab', 'a']
- '+'     匹配前一个字符1次或多次，re.findall("ab+","ab+cd+abb+bba") 结果['ab', 'abb']
- '?'     匹配前一个字符1次或0次
- '{m}'   匹配前一个字符m次
- '{n,m}' 匹配前一个字符n到m次，re.findall("ab{1,3}","abb abc abbcbbb") 结果'abb', 'ab', 'abb']
- '|'     匹配|左或|右的字符，re.search("abc|ABC","ABCBabcCD").group() 结果'ABC'
- '(...)' 分组匹配
- '\A'    只从字符开头匹配，re.search("\Aabc","alexabc") 是匹配不到的
- '\Z'    匹配字符结尾，同'$'
- '\d'    匹配数字0-9
- '\D'    匹配非数字
- '\w'    匹配[A-Za-z0-9]
- '\W'    匹配非[A-Za-z0-9]
- '\s'    匹配空白字符、\t、\n、\r , re.search("\s+","ab\tc1\n3").group() 结果 '\t'
### re 顶级方法
- re.match('mode','str')   从头开始检测mode和str是否完全一样
- re.search('mode','str')   检测str是否包含mode ，找到第一个就返回，也就是匹配一次
- re.findall('mode','str')    检测str是否包含mode ，返回所有匹配到的元素，并存储到一个list里面。
### Json module 
-  As we all  konw ,Json now is the most widely-used format to transport the data .当然python 也支持对json的解析，下面是2个常用的方
- 法 ，用于 json 和 python中数据的互相 解析
#### json.dumps(json)
  把json 解析成python中的 dict
#### json.loads(dict)
  把dict 转化为json 格式
  
