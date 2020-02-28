# python 核心编程

## 安装python 修改内容

linux环境中

安装依赖包

    yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel

下载python包

    wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tgz

解压Python-3.7.0.tgz

    tar -zxvf Python-3.7.0.tgz

创建文件夹存放python

    mkdir /usr/local/python3 

执行配置文件，编译，编译安装

    cd Python-3.7.0
    ./configure --prefix=/usr/local/python3
    make && make install

建立软连接

    ln -s /usr/local/python3/bin/python3.7 /usr/bin/python3
    ln -s /usr/local/python3/bin/pip3.7 /usr/bin/pip3

查看python版本

    python3 -V


## 数据类型

> 基本数据类型:
> 整型(`int`)，浮点型(`float`)，字符串(`str`)，列表(`list`)，元组(`tuple`)，字典(`dict`)，集合(`set`),布尔(`bool`)

> 数值类型（整数，浮点，布尔）
> 序列类型（字符串，列表，元组）
> 散列类型（字典，集合）

> 字节类型 a=bytes(‘123’)/a=b’123’
> 字节数组bytearrary(‘123’)

> 可变序列:列表，集合，字典
> 不可变序列:字符串，元组

# 数据类型方法

## —字符串方法

**增**：
字符串拼接
1.str1+str2+str3
2.””.join([str1,str2,str3])
3."%s %s %s"%(str1,str2,str3)
4."{} {} {}".format(str1,str2,str3)

**删**：
`x.replace(m,n,x) m:`准备替换的内容 n:替换的内容 x:替换的个数

**查**：
`x.index(m) m:`索引的内容
`x.find(m) m:`索引的内容
`x.count(m) m:`计数的内容
`x.isdigit() x`是否是数字
`x.isalpha() x`是否是字母
`x.isupper() x`是否是大写
`x.islower() x`是否是小写
`x.startswith(m) x`是否以m开头
`x.endswith(m) x`是否以m结尾

**改**：
`x.upper() x`转化为大写
`x.lower() x`转化为小写
`x.strip()`去x左右空白/lstrip去左空白/rstrip去右空白
`x.title() x`标题化
`x.capitalize() x`第一个字母大写
`x.split(m,x)` 以m为界分割 分割x次
# —列表方法

**增**：
`li.append(m) m:`添加的内容
`li.insert(x,m) x:`元素下标位置 m:插入的内容
`li.extend(list) list:`为另一个列表

**删**：
`li.pop(x) x:`删除一个元素并返回该元素的值 若无参数x则从最后开始删除
`li.remove(m) m:`需要删除的内容
`li.clear() `清空列表li

查：
`li.index(m) m:`索引的内容
`li.count(m) m:`计数的内容

**改**：
`list[n]=x`

其他：
`copy()` 浅复制
`import copy` 深复制 适用于两层列表
`list1=copy.deepcopy(list2)`
永久排序
`li.sort(reverse=True/False) `m:列表 True倒排序 False正排序
`m.reverse() `永久倒排序
临时排序
`sorted(li,reverse=True/False) `m:列表 True倒排序 False正排序
`reversed(m)` 临时倒排序
# —元组方法

**查**：
`t.index(m) `m:索引的内容
`t.count(m)`	 m:计数的内容
#—集合方法

交集& 并集| 差集-

增：
a.add(m) m:向集合里面添加的内容
删：
a.pop() 随机删除集合内容
a.remove() 指定删除集合内容
查：
a.isdisjoint(b) a与b是否存在交集
a.issubset(b) a是b的子集吗
a.issuperset(b) a是b的父集吗
改：
a.update(m) 向集合里面添加元素m可以为字符串 列表 元组 集合 字典
—字典方法

增：
d=dict.fromkeys(m,n) m:键的来源可迭代对象 n:设置值的默认值
d.setdefault(m,n) 查询有则返回无则添加m:键 n:值

删：
d.clear() 清空字典
d.pop(m) m:键 删除以m为键的字典
d.popitem() 删除最后一个字典

改：
d.update(m) m:添加的字典
dic[m]=n m:键 n:值

查：
d.get(m) m:键 返回m键对应的值
d.keys() 获得键的列表
d.values() 获得值的列表
d.items() 同时获得键与值的元组 再通过遍历获得键与值

判断类型：type() isinstance(变量,类型)
运算符及其优先级
运算符 	说明
** ^ ! 	指数 按位翻转 非
* / % // 	乘 除 取模 整除
+ - 	加 减
>> << 	右移 左移
>> == >= <= > < != 	是否 /等于 大于等于 小于等于 大于 小于 不等于
>> = += -= *= /= %= **= //= 	赋值
>> is is not 	判断内存地址是否相同
>> in not in 	判断成员是否存在
>> and or not 	与 或 非
>> 流程控制

if-else
语法:

if 条件:
    语句
else:
    语句

    1
    2
    3
    4

例子:

a=1
#使用方式一
if a>1:
    print('大于1')
else:
    print('小于等于1')
#使用方式二
print('大于1') if a>1 else print('小于等于1')
输出:
>>小于等于1
>>小于等于1

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11

if-elif-else
语法:

if 条件:
    语句
elif 条件:
    语句
else:
    语句

    1
    2
    3
    4
    5
    6

例子:

a=1
if a>1:
    print('大于1')
elif a<1:
    print('小于1')
else:
    print('等于1')
输出:
>>等于1

    1
    2
    3
    4
    5
    6
    7
    8
    9

while
语法:

while 条件:
    语句

    1
    2

例子:

a=5
while a>0:
    print(a)
    a-=1
输出:
>>5
>>4
>>3
>>2
>>1

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10

while-else
语法:

while 条件:
    语句
else:
    循环结束后执行的语句

    1
    2
    3
    4

例子:

a=5
while a>0:
    print(a)
    a-=1
    #循环中若出现break则跳出循环，且不再执行else中的语句
else:
    print('ok')
输出:
>>5
>>4
>>3
>>2
>>1
>>ok

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14

for循环

for i in 可迭代对象:
    语句

    1
    2

例子:实现九九乘法表

for i in range(1,10):
    for j in range(1,i+1):
        print(str(i)+'x'+str(j)+'='+str(i*j),end=' ')
    print('\n',end='')
输出:
>>1x1=1 
>>2x1=2 2x2=4 
>>3x1=3 3x2=6 3x3=9 
>>4x1=4 4x2=8 4x3=12 4x4=16 
>>5x1=5 5x2=10 5x3=15 5x4=20 5x5=25 
>>6x1=6 6x2=12 6x3=18 6x4=24 6x5=30 6x6=36 
>>7x1=7 7x2=14 7x3=21 7x4=28 7x5=35 7x6=42 7x7=49 
>>8x1=8 8x2=16 8x3=24 8x4=32 8x5=40 8x6=48 8x7=56 8x8=64 
>>9x1=9 9x2=18 9x3=27 9x4=36 9x5=45 9x6=54 9x7=63 9x8=72 9x9=81 

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14

函数
—函数的定义

定义函数

def myfunc(x):
    if x >= 0:
        return x
    else:
        return -x

    1
    2
    3
    4
    5

空函数

def emptyfunc():
    pass

    1
    2

参数检查

def checkfunc(x):
    if not isinstance(x,(int,float)):
        raise TypeError("must be int or float type!")
    if x >= 0:
        return x
    else:
        return -x

    1
    2
    3
    4
    5
    6
    7

返回多个值

def price(x):
    apple=x*2
    banana=x*2.5
    return apple,banana
a,b=price(1)

    1
    2
    3
    4
    5
    
    函数返回多值其实就是返回一个元组

—函数的参数

必选参数parameter

def printdetail1(name,age,telephone):
    print("姓名:",name)
    print("年龄:",age)
    print("电话:",telephone)
printdetail1("Jack",12,12356435678)

    1
    2
    3
    4
    5

默认参数parameter=value

def printdetail2(name,age,telephone,gender='fale'):
    print("姓名:",name)
    print("性别:",gender)
    print("年龄:",age)
    print("电话:",telephone)
printdetail2("Jack",12,12356435678,gender='female')

    1
    2
    3
    4
    5
    6

可变参数*
1.不定长传参

def fun1(*number):
    for i in number:
        print(i)
fun1(1,2,3,4,5,6,7,8)

    1
    2
    3
    4

2.元组和列表的压包

def fun2(*number):
    s=0
    for i in number:
        s+=i
    print(s)
fun2(*[1,2,3,4,5])
fun2(*(1,2,3,4,5))

    1
    2
    3
    4
    5
    6
    7

关键参数**
使用方法一

def fun(id,name,**kargs):
    print("id:",id)
    print("name:",name)
    print("others:",kargs)
fun(2,"xiaohua",sex="man",age='12')

    1
    2
    3
    4
    5

使用方法二

extra={'sex': 'man', 'age': 12}
def fun(id,name,**kargs):
    print("id:",id)
    print("name:",name)
    print("others:",kargs)
fun(2,"xiaohua",sex=extra['sex'],age=extra['age'])

    1
    2
    3
    4
    5
    6

使用方法三

extra={'sex': 'man', 'age': 12}
def fun(id,name,**kargs):
    print("id:",id)
    print("name:",name)
    print("others:",kargs)
fun(2,"xiaohua",**extra)

    1
    2
    3
    4
    5
    6

关键字参数*

def fun(name,age,*,city,job,completion):
    print("name:",name)
    print("age:",age)
    print("city:",city)
    print("job:",job)
    print("completion:",completion)
fun('Jack',12,city='shanghai',job='teacher',completion=True)

    1
    2
    3
    4
    5
    6
    7
    
    命名关键字参数需要一个特殊分隔符*，后面的参数被视为命名关键字参数
    如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符*了

参数组合

def fun(parameter,*args,keyparameter,**kargs):
    print(parameter)
    print(args)
    print(keyparameter)
    print(kargs)
fun(1,*(1,2,3,4),keyparameter=True,**{'id':2})

    1
    2
    3
    4
    5
    6
    
    参数定义的顺序必须是：必选参数、默认参数、可变参数、命名关键字参数和关键字参数

—函数的递归

#阶乘计算
def fact(n):
    if n == 1:
        return 1
    return n * fact(n-1)

    1
    2
    3
    4
    5
    
    必须设置函数终止条件
    使用递归函数的优点是逻辑简单清晰，缺点是过深的调用会导致栈溢出。

—函数的回调

def add(x,y):
    return x+y

def multiply(x,y):
    return x*y

def use(func,x,y):
    return func(x,y)

print(use(add,1,2))
print(use(multiply,1,2))
输出:
>>3
>>2

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    
    通过向函数里传入已定义的不同功能的函数名来使用不同的功能函数

函数作用域
global：在函数内部修改函数外部的值，需要在函数内用global声明需要修改的变量
nonlocal：在多层函数嵌套的情况下，在里层函数里修改外层函数里面的变量值
1.外部不能访问函数内部变量
2.函数内部能够访问函数外部变量
3.函数里面不能修改函数外部变量(若要修改需声明global x x=n)
4.函数里面和函数外部变量名相同
函数式编程
—高阶函数

map()
map(函数名,列表/元组/集合/字符串)

a='12345'
def square(x):
    return int(x)*int(x)

b=list(map(square,a))
print(b)
输出:
>>[1, 4, 9, 16, 25]

    1
    2
    3
    4
    5
    6
    7
    8
    
    map()把传入的函数依次作用于每个元素，处理完后返回的是生成器类型，需要用list生成数据

filter()
filter(函数名,列表/元组/集合/字符串)

a=[1,2,3,4,5,6,7,8,9,10]
def even_number(x):#筛选偶数
    return x%2==0
b=list(filter(even_number,a))

print(b)
输出:
>>[2, 4, 6, 8, 10]

    1
    2
    3
    4
    5
    6
    7
    8

a=['A', '', 'B', None, 'C', '  ']
def remove_blank(x):#去除空元素
    return x and x.strip()

b=list(filter(remove_blank,a))
print(b)
输出:
>>['A', 'B', 'C']

    1
    2
    3
    4
    5
    6
    7
    8
    
    filter()把传入的函数依次作用于每个元素，然后根据返回值是True还是False决定保留还是丢弃该元素，处理完后返回的是生成器类型，需要用list生成数据

—返回函数

def delay_sum(*args):
    def sumfunc():
        s=0
        for i in args:
            s+=i
        return s
    return sumfunc
f=delay_sum(1,2,3,4)
print(f())
输出:
>>10

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11

—函数的闭包

闭包：动态的生成函数

def f_out(times):
    print('in f_out')
    #times在f_out函数中相对于f_in函数的外部变量
    def f_in(num):
        return times*num   # f_in可以调用外部变量times
    return f_in            #函数f_in()的地址f_in返回给f_out()

f_10_times=f_out(10)
f_20_time=f_out(20)

print(f_10_times(5))
print(f_20_time(5))
输出:
>>in f_out          #给外部函数f_out传参后会先执行该函数内的所有语句
>>in f_out
>>50
>>100

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17

def count():
    fs = []
    for i in range(1, 4):
        def f():
             return i*i
        fs.append(f)
    return fs

f1, f2, f3 = count()
print(f1())
print(f2())
print(f3())
输出:
>>9
>>9
>>9

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16

def count():
    def f(j):
        def g():
            return j*j
        return g
    fs = []
    for i in range(1, 4):
        fs.append(f(i)) # f(i)立刻被执行，因此i的当前值被传入f()
    return fs
f1,f2,f3=count()
print(f1())
print(f2())
print(f3())
输出:
>>1
>>4
>>9

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17

—匿名函数

lambda 形参:含形参的表达式

f = lambda x:x+1
print(list(map(f,[1,2,3,4,5])))
输出:
>>[2, 3, 4, 5, 6]

    1
    2
    3
    4
    
    lambda返回的是函数地址
    lambda常与map和filter函数联用

—装饰器

装饰器：我们要增强函数的功能，比如，在函数调用前后自动打印日志，但又不希望修改函数的定义，这种在代码运行期间动态增加功能的方式，称之为“装饰器”（Decorator）
定义装饰器

import time
#计算函数运行时间
def run_time(func):
    def wrapper():
        start_time=time.time()
        func()
        spend_time=time.time()-start_time
        return spend_time
    return wrapper

@run_time       #等价于multiply=run_time(multiply)
def multiply():
    sum=0
    for i in range(100000):
        sum+=i
    print(sum)

print(multiply())
输出:
>>4999950000
>>0.004987001419067383

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21

使用装饰器

#使用方法一
now=decorator(函数名)#装饰器不传入参数时
now=decorator(参数)(函数名)#装饰器传入参数时
now()#执行被装饰过的函数

#使用方法二
@decorator#已定义的装饰器
def f():#自定义函数
	pass
f()#执行被装饰过的函数

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10

自身不传入参数的装饰器

def login(func):
    def wrapper(*args,**kargs):
        print('函数名:%s'% func.__name__)
        return func(*args,**kargs)
    return wrapper
@login
def f():
    print('inside decorator!')
f()
输出:
>>函数名:f
>>函数本身:inside decorator!

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12

自身传入参数的装饰器

def login(text):
    def decorator(func):
        def wrapper(*args,**kargs):
            print('%s----%s'%(text,func.__name__))
            return func(*args,**kargs)
        return wrapper
    return decorator

@login('this is a parameter of decorator')
def f():
    print('2019-06-13')
f()
输出:
>>this is a parameter of decorator----f
>>2019-06-13

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15

传参装饰器实例1

class Profile():
    def __init__(self):
        self.name='peter'
        self.sex='man'
        self.age=12
        self.city='Wuhan'

def pass_token(symbol):
    def decorator(func):
        def wrapper():
            if symbol =='20191202':
                profile = Profile()
                func(profile)
            else:
                print('pass_token错误！')
        return wrapper
    return decorator

@pass_token('20191202')
def get_info(info):
    print(f'姓名:{info.name}\n性别:{info.sex}\n年龄:{info.age}\n所在地:{info.city}')

get_info()

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23

传参装饰器实例2

class Profile():
    def __init__(self):
        self.name='peter'
        self.sex='man'
        self.age=12
        self.city='Wuhan'

class Message():
    def __init__(self):
        self.type='text'
        self.content='hello'
        self.sender='peter'

def choose_func(symbol):
    def decorator(func):
        if symbol == 'user':
            def wrapper():
                    profile = Profile()
                    func(profile)
        elif symbol == 'message':
            def wrapper():
                    message = Message()
                    func(message)
        else:
            print('请检查装饰器参数！')
        return wrapper
    return decorator

@choose_func('user')
def get_user(user):
    print(f'姓名:{user.name}\n性别:{user.sex}\n年龄:{user.age}\n所在地:{user.city}')

@choose_func('message')
def get_message(message):
    print(f'消息类型:{message.type}\n内容:{message.content}\n发送者:{message.sender}')


get_user()
get_message()

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33
    34
    35
    36
    37
    38
    39

内置装饰器
@property：就像访问属性一样和普通访问少了一个(),将函数名作为一个返回值 被装饰的类方法不可回调
@staticmethod： 可以直接通过类名.函数名直接调用被装饰的方法
@classmethod： 可以直接通过类名.函数名直接调用被装饰的方法

class Myclass():
    a=100#类属性
    def __init__(self,height,width):
        self.height=height#实例属性
        self.width=width

    @property    #属性装饰器:将函数名作为一个返回值 被装饰的类方法不可回调
    def get_area(self):
    #因为外部可以直接通过实例对象.函数名调用来获得结果 所以必须得有返回值
    #通过类名.函数名调用只能得到该方法的地址 等于下面的cls.get_area
        return self.height*self.width
    
    @classmethod #类方法装饰器:可以通过类名.函数名直接调用被装饰的方法
    def info(cls):
        print('you can use class attribution and class method!')
        print(cls.a,cls.get_area)#可以通过cls调用类属性和类方法
    
    @staticmethod#静态装饰器:可以直接通过类名.函数名直接调用被装饰的方法
    def help():
        print('there is no cls and self!')

a=Myclass(20,50)
print('-----------实例化对象.函数名调用----------------')
print(a.get_area)

print('---------实例化对象.函数调用----------')
a.info()
a.help()

print('---------类名.函数直接调用----------')
Myclass.info()
Myclass.help()


输出:
>>-----------实例化对象.函数名调用----------------
>>1000
>>---------实例化对象.函数调用----------
>>you can use class attribution and class method!
>>100 <property object at 0x0000025D9322D958>
>>there is no cls and self!
>>---------类名.函数直接调用----------
>>you can use class attribution and class method!
>>100 <property object at 0x0000025D9322D958>
>>there is no cls and self!

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33
    34
    35
    36
    37
    38
    39
    40
    41
    42
    43
    44
    45

@staticmethod和@classmethod的区别:

    @staticmethod不需要表示自身对象的self和自身类的cls参数，就跟使用函数一样。
    @classmethod也不需要self参数，但第一个参数需要是表示自身类的cls参数。
类装饰器
—内置函数

常用函数
len()求长度
min()求最小值
max()求最大值
sorted()排序
sum()求和
进制转换函数
bin()转换为二进制
oct()转换为八进制
hex()转换为十六进制
ord()字符转ASCII码
chr()ASCII码转字符

内置对象查看：dir(_builtins_)
—高级内置函数

enumerate() 转化为元组标号
eval(str)只能运行一行字符串代码
exec(str)执行字符串编译过的字符串 可以运行多行字符串代码
filter(函数名,可迭代对象)过滤器
map(函数名,可迭代对象)对每个可迭代对象的每个元素处理
zip(可迭代对象,可迭代对象)将对象逐一配对
高级特性
—切片

字符串的切片

s='hello world!'
print(s[0])#取0对应的下标值
print(s[::])#取全部值
print(s[::2])#步长为2
print(s[1:5])#左闭右开区间
print(s[1:])#包含下标为1对应的值
print(s[:5])#不包含下标为5对应的值
输出:
>>h
>>hello world!
>>hlowrd
>>ello
>>ello world!
>>hello

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    
    列表，元组的切片同理

—迭代

可迭代对象：可以直接作用于for循环的对象统称为可迭代对象(Iterable)
判断对象是否可迭代

from collections import Iterable
a=isinstanc(对象，Iterable)
print(a)
输出:
>>True为可迭代
>>False为不可迭代

    1
    2
    3
    4
    5
    6

可迭代对象的遍历
对字符串的遍历

s='hello world!'
for i in s:
    print(i,end="")
输出:
>>hello world!

    1
    2
    3
    4
    5

对字典的遍历

#遍历键
d={'name':'Jack','age':12}
for key in d.keys():
    print(key)
#遍历值
d={'name':'Jack','age':12}
for value in d.values():
    print(value)

    1
    2
    3
    4
    5
    6
    7
    8
    
    可迭代对象:字符串，列表，元组，字典，集合
    对列表，集合，元组的遍历同理

—生成式

列表生成式
语法:[返回的参数 for循环 条件判断]
使用方法一 单层循环

l=[i for i in range(11) if i%2==0]
print(l)
输出:
>>[0, 2, 4, 6, 8, 10]

    1
    2
    3
    4

使用方法二 多层循环

l=[m+n for m in 'ABC' for n in '123']
print(l)
输出:
>>['A1', 'A2', 'A3', 'B1', 'B2', 'B3', 'C1', 'C2', 'C3']

    1
    2
    3
    4

例一 对列表中的数据批量操作

import os
l=[d.upper() for d in os.listdir('.')]
print(l)
输出:
>>['2345看图王.LNK','DESKTOP.INI', 'DEVC++.LNK', 'FIDDLER.LNK']

    1
    2
    3
    4
    5

例二 取出字典中的键值保存到列表中

d={'a':1,'b':2,'c':3}
l=[k+'='+str(v) for k,v in d.items()]
print(l)
输出:
>>['a=1', 'b=2', 'c=3']

    1
    2
    3
    4
    5

例三 判断列表中数据的类型

li=[1,1.5,7j+1,'a',True,False,None]
p=[type(x) for x in li]
print(p)
输出:
[<class 'int'>, <class 'float'>, <class 'complex'>, <class 'str'>, <class 'bool'>, <class 'bool'>, <class 'NoneType'>]

    1
    2
    3
    4
    5

集合生成式
语法:{返回的参数 for循环 条件判断}

s = {i for i in range(1,10) if i%2==0}
print(s)
输出:
>>{8, 2, 4, 6}

    1
    2
    3
    4

字典生成式
语法:{key:value for循环 条件判断}

li=['a','b','c','d','e','f','g','h']
d={i:j for i,j in enumerate(li) if i%2==0}
print(d)
输出:
>>{0: 'a', 2: 'c', 4: 'e', 6: 'g'}

    1
    2
    3
    4
    5

—生成器

生成器：为了节省内存空间，提高程序速度，这种一边循环一边计算的机制，称为生成器。
next()取值

li=[1,2,3,4,5]
g=(x for x in li)
print(g)
print(next(g))
print(next(g))
print(next(g))
print(next(g))
print(next(g))
输出:
>><generator object <genexpr> at 0x0000018F628397C8>
>>1
>>2
>>3
>>4
>>5

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15

for循环遍历取值

li=[1,2,3,4,5]
g=(x for x in li)
print(g)
for i in g:
    print(i)
输出:
>><generator object <genexpr> at 0x0000018F628397C8>
>>1
>>2
>>3
>>4
>>5

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12

函数的yield返回
next()取值

def fun():
    yield 1
    yield 2
    yield 3
a=fun()
print(next(a))
print(next(a))
print(next(a))
输出:
>>1
>>2
>>3

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12

for循环遍历取值

def fun():
    yield 1
    yield 2
    yield 3
a=fun()
print(a)
for i in a:
    print(i)
输出:
<generator object fun at 0x00000233B8C697C8>
1
2
3

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13

例一 斐波拉契数列的推算值生成

def fib(max):
    n, a, b = 0, 0, 1
    while n < max:
        yield b
        a, b = b, a + b
        n = n + 1
    return 'done'
a=fib(5)
for i in a:
    print(i)
输出:
>>1
>>1
>>2
>>3
>>5

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    
    generator是非常强大的工具，在Python中，可以简单地把列表生成式改成generator，也可以通过函数实现复杂逻辑的generator
    要理解generator的工作原理，它是在for循环的过程中不断计算出下一个元素，并在适当的条件结束for循环。对于函数改成的generator来说，遇到return语句或者执行到函数体最后一行语句，就是结束generator的指令，for循环随之结束
    请注意区分普通函数和generator函数，普通函数调用直接返回结果

—迭代器

迭代器：可以被next()函数调用并不断返回下一个值的对象称为迭代器(Iterator)
可迭代对象转化为迭代器
使用iter(可迭代对象)实现将可迭代对象转化为迭代器

# 首先获得Iterator对象:
it = iter([1, 2, 3, 4, 5])
# 循环:
while True:
    try:
        # 获得下一个值:
        x = next(it)
        print(x)
    except StopIteration:
        # 遇到StopIteration就退出循环
        break

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    
    凡是可作用于for循环的对象都是Iterable类型
    凡是可作用于next()函数的对象都是Iterator类型，它们表示一个惰性计算的序列
    集合数据类型如list、dict、str等是Iterable但不是Iterator，不过可以通过iter()函数获得一个Iterator对象
    Python的for循环本质上就是通过不断调用next()函数实现的

类
—定义和实例化

类的定义

class Flower(object):
    pass

    1
    2

添加实例属性值

class Flower(object):
    def __init__(self,name,color,height):
    #默认值
        self.name=name
        self.color=color
        self.height=height

    1
    2
    3
    4
    5
    6

类的实例化

class Flower(object):
    def __init__(self,name,color,height):
        self.name=name
        self.color=color
        self.height=height
f=Flower('玫瑰','红色',20)
print(f.name)
print(f.color)
print(f.height)
输出:
>>玫瑰
>>红色
>>20

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13

—实例属性和类属性

类没有实例属性时会调用类属性

class Flower(object):
    height=20
    def __init__(self,name,color):
        self.name=name
        self.color=color
f=Flower('玫瑰','红色')
print(f.height)
输出:
>>20

    1
    2
    3
    4
    5
    6
    7
    8
    9

实例属性的优先级高于类属性

class Flower(object):
    height=20
    def __init__(self,name,color,height):
        self.name=name
        self.color=color
        self.height=height
f=Flower('玫瑰','红色',10)
print(f.height)
输出:
>>10

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10

删除实例属性

class Flower(object):
    height=20
    def __init__(self,name,color,height):
        self.name=name
        self.color=color
        self.height=height
f=Flower('玫瑰','红色',10)
del f.height
print(f.height)
输出:
>>20#由于此时实例属性被删除，自动调用了类属性height=20

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11

—访问限制

私有属性
伪私有属性_attrname:可以访问但是不要随意访问
私有属性__attrname:一般不可以访问

访问和修改私有属性

访问私有属性

class Student(object):
    def __init__(self,name,score):
        self.__name=name
        self.__score=score

    def get_name(self):
        return self.__name
    
    def get_score(self):
        return self.__score

s=Student('Jack',88)
#通过自定义方法来访问私有属性
print(s.get_name())
print(s.get_score())
#直接访问私有属性
print(s._Student__name）
print(s._Student__score)
输出:
>>Jack
>>88
>>Jack
>>88
>>a

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24

修改私有属性

class Student(object):
    def __init__(self,name,score):
        self.__name=name
        self.__score=score

    def get_name(self,newname):
        self.__name=newname
        return self.__name
    
    def get_score(self,newscore):
        self.__score=newscore
        return self.__score

s=Student('Jack',88)
#通过自定义方法修改私有属性
print(s.get_name('Peter'))
print(s.get_score('85'))
#直接修改私有属性
s._Student__name='Mark'
s._Student__score='86'
print(s._Student__name)
print(s._Student__score)
输出:
>>Peter
>>85
>>Mark
>>86

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27

—继承和多态
—获取对象信息

type()函数获取对象信息
判断函数类型

import types
def fn():
    pass

print(type(fn)==types.FunctionType)#判断是否是自定义函数
print(type(abs)==types.BuiltinFunctionType)#判断是否是内置函数
print(type(lambda x: x)==types.LambdaType)#判断是否是lambda函数
print(type((x for x in range(10)))==types.GeneratorType)#判断是否是生成器类型
输出:
>>True
>>True
>>True
>>True

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13

isinstance()函数获取对象信息
判断类对象

class Animal(object):
    pass
class Dog(Animal):
    pass
class Xiaohuang(Dog):
    pass
a=Xiaohuang()
b=Dog()
c=Animal()
print(isinstance(a,Dog))#Xiaohuang是否属于Dog类
print(isinstance(b,Animal))#Dog是否属于Animal类
print(isinstance(c,object))#Animal是否属于object类
输出:
>>True
>>True
>>True

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16

判断基本类型数据

a=[1,2,3,4,5]
print(isinstance(a,(list,dict)))#判断a是否属于列表或者字典类型
输出:
>>True

    1
    2
    3
    4

dir()获取一个对象的所有属性和方法

s='hello'
print(dir(s))
输出:
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']

    1
    2
    3
    4

内置方法的重写

class myclass():
    def __len__(self):
        return 10
    def __repr__(self):
        return 'rewrite repr!'
    def __str__(self):
        return  'rewrite str!'

a=myclass()
print(len(a)
print(repr(a))
print(str(a))
输出:
>>10
>>rewrite repr!
>>rewrite str!

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16

定制属性访问
hasattr(m,’n’) m:实例 n:类里面的属性 确定属性是否存在
getattr(m,‘n’) m:实例 n:类里面的属性 得到指定类属性的值
setattr(m,’n’,x) m:实例 n:类里面的属性 x:设置属性的值 有则改无则添加
delattr(m,’n’) m:实例 n:类里面的属性 删除一个类属性

    实例属性的优先级高于类属性

—单例模式

重写__new__方法实现单例模式

class myclass(object):
    __instance=None
    def __new__(cls, *args, **kwargs):#cls代表myclass类本身
        if cls.__instance == None:
            cls.__instance=super().__new__(cls)#调用base父类的new方法
        return cls.__instance


a=myclass()
b=myclass()

print(id(a))
print(id(b))
输出:
>>3032841896736
>>3032841896736

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    
    new方法会在初始化方法init方法之前运行
    new方法实现的单例模式可节约不必要重复实例化带来的内存消耗
    new方法是实现单例模式的其中的一种方法

4.类的析构（销毁无用变量）
5.继承 重写
6.多继承 重写
在类中
super()可以调用父类里面的方法
self.方法()可以调用父类里面的方法
类中查询相关信息
1、class	查看类名
格式： 实例.class
2、dict	查看全部属性，返回属性和属性值键值对形式
格式：实例.dict
3、doc	查看对象文档，即类中(用三个引号引起来的部分)
格式：类名.dict
4、bases 查看父类
格式：类名.base
5.mro 查看多继承的情况下，子类调用父类方法时，搜索顺序
格式：子类名.mro 实例.class.mro
魔术方法：
str repr call init add

描述符
class Myattr():
def get(self,instance,owner):
print(“this is get”)
def set(self,instance,value):
print(“this is set”)
def delete(self,instance):
print(“this is delete”)
class Myclass():
attr=Myattr()
a=Myclass()
a.attr #访问属性来激活__get__方法
a.attr=1 #赋值来激活__set__方法
del a.attr #删除来激活 __delete__方法
IO编程
—文件操作

文件方法
fp=open(地址,模式,encoding=’utf-8’,errors=’none’/’ignore’) 打开文件
fp.close() 关闭文件
with open() as f1,open() as f2: 上下文管理(可以自动关闭文件)
fp.seek(m) 移动文件指针 当前位置向后移动m个字节
fp.tell() 查看文件指针
fp.flush() 刷新缓冲区和fp.close()类似

文件读取
fp.read(m) 文件读取 读取m个字节
fp.readline() 按行文件读取
fp.readlins() 列表形式读取文件

遍历文件内容
for i in fp:
for i in fp.readlins()
文件写入
fp.write(内容) 文件中写入内容
fp.writelines(list) 文件中写入列表类型内容
文件内容清空
fp.truncate() 文件内容清空
—IO流操作

引入模块io
f=io.StringIO()
f=io.BytesIO()
f.getvalue()
异常

try:
    print(a)                      #尝试运行代码
except Exception as e:            #将错误类型储存在e中
    print("error!")
    print(e)
    raise Myerror                 #抛出自定义异常
else:
    print("right!")               #不出异常才执行
finally:
    print("display all the time") #无论是否异常都会执行

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10

模块和包的管理

导入一个同级1.py文件 import 1 导入一个只可以被引用不可执行的同级1.py文件import .1
导入上一级的 1.py文件 import …1
from a.b.c import hi表示从a下面的b下面的c中导入一个hi函数
from 和 import 后面既可以接目录名也可以接不带后缀的文件名
import sys
sys.path.append(r"filedir") filedir:目录路径 可以是绝对路径也可以是相对路径
进程和线程
—多进程

引入模块

from multiprocess import Process

    1

实例化进程
process=Process(target=函数名,args=(参数,),name='进程名')
启动进程
process.start()(创建进程，开始执行)
process.run()(运行start()创建进程后最后会执行该方法，用于之自定义进程)
多个进程之间共享一个全局变量

from multiprocessing import Process
import time
import os
n=0
def task1(name):
    global n
    while True:
        n+=1
        time.sleep(1)
        print(os.getppid(),os.getpid(),name,n)

def task2(name):
    global n
    while True:
        n+=1
        time.sleep(2)
        print(os.getppid(),os.getpid(),name,n)

if __name__ == '__main__':
    process1=Process(target=task1,args=('task1...',),name='任务1')
    process2=Process(target=task2,args=('task2...',),name='任务2')
    print(process1.name)
    print(process2.name)
    process1.start()
    process2.start()
    while True:
        time.sleep(1)
        n+=1
        print("主进程",n)
输出:
>>任务1
>>任务2
>>主进程 1
>>12172 11308 task1... 1
>>主进程 2
>>12172 11308 task1... 2
>>12172 5372 task2... 1
>>主进程 3
>>12172 11308 task1... 3
>>主进程 4
>>12172 11308 task1... 4
>>12172 5372 task2... 2

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33
    34
    35
    36
    37
    38
    39
    40
    41
    42
    
    由输出结果可知：当多个进程共享一个全局变量时，会各自创建该变量的副本，互不影响。
    全局变量包括全部的数据类型

自定义进程

from multiprocessing import Process
class MyProcess(Process):
    def __init__(self,name):
        #重写init方法
        super(MyProcess,self).__init__()
        self.name=name
    #因为运行start()方法后最后会执行run(),所有自定义部分放在run()方法中
    def run(self):
        while True:
            print("进程:"+self.name)

if __name__=='__main__':
    p1=MyProcess('自定义进程1')
    p2=MyProcess('自定义进程2')
    p1.start()
    p2.start()

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    
    需重写run方法，如果传入参数则还需重写init方法

非阻塞式进程池

from multiprocessing import Pool

    1

特点：将任务全部添加进入队列，立刻执行返回，并没有等待其他进程，回调函数是等任务完成后有返回值才传入才调用

from multiprocessing import Pool
import time
import random
import os
def task(name):
    print("任务:{} 进程id:{}".format(name,os.getpid()))
    start=time.time()
    time.sleep(random.random()*2)
    end=time.time()
    return '任务完成！{} 进程id:{} 用时:{}'.format(name,os.getpid(),start-end)
def callback_fun(s):#s相对于task(name)
    print(s)

if __name__=='__main__':
    pool = Pool(5)
    tasks=['听音乐','看电影','散步','玩游戏','吃东西','daw','ffde']
    for i in tasks:
        pool.apply_async(task,args=(i,),callback=callback_fun)
    pool.close()#参数传入完成后需要用close()方法关闭函数参数入口
    pool.join()#进程池会随着主进程的结束而结束所以要用进程阻塞join()方法

    print('主进程结束')
    
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    
    参数传入完成后需要用close()方法关闭函数参数入口
    进程池会随着主进程的结束而结束所以要用进程阻塞join()方法

阻塞式进程池

from multiprocessing import Pool

    1

特点：添加一个任务则执行一个任务，当前任务没有完成，另一个任务将等待

from multiprocessing import Pool
import time
import random
import os
def task(name):
    print("任务:{} 进程id:{}".format(name,os.getpid()))
    start=time.time()
    time.sleep(random.random()*2)
    end=time.time()
    print('任务完成！{} 进程id:{} 用时:{}'.format(name,os.getpid(),start-end))

if __name__=='__main__':
    pool = Pool(5)#定义进程池可调度最大进程数
    tasks=['听音乐','看电影','散步','玩游戏','吃东西','extra_1','extra_2']
    for i in tasks:
        pool.apply(task,args=(i,))
    pool.close()
    pool.join()
    print('主进程结束')

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19

进程通信
原理：进程之间的通信是依赖队列作为桥梁来实现的
模拟多进程分工下载图片

from multiprocessing import Process
from multiprocessing import Queue
#下载图片
def download(q):
    download_list=['1.jpg','2.jpg','3.jpg']
    for i in download_list:
        q.put(i)
        print('下载完成!')
#保存图片
def savefile(q):
    while True:
        try:
            image_data=q.get(timeout=5)
            print('已保存图片:{}'.format(image_data))
        except:
            break
    print('任务完成!')

if __name__ == '__main__':

    q=Queue(20)
    process1=Process(target=download,args=(q,))
    process2=Process(target=savefile,args=(q,))
    process1.start()
    process2.start()
    process1.join()
    process2.join()
    
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27

—多线程

引入模块:

import threading

    1

实例化线程
对象=threading.Thread(target=函数名,args=(参数,)

设置线程名
对象.setName(‘线程名’)

获取线程名
对象.getName()

线程守护(主线程结束它的子线程就结束)

对象.setDaemon(True)

线程阻塞(主线程等子线程结束后才接着往下走)
对象.join()

判断线程是否存活
对象.is_alive()

获取线程id
对象.ident

开启线程
对象.start()

获取所有线程详细信息
threading.enumerate()
在函数执行过程中获取所在线程名
threading.current_thread().name
在函数执行过程中获取线程存活数量
threading.active_count()

from threading import Thread
import threading
import time
def task1(param):
    time.sleep(1)
    print(threading.current_thread().name,param)
def task2(param):
    time.sleep(1)
    print(threading.current_thread().name,param)
t1=Thread(target=task1,args=(1,))
t2=Thread(target=task2,args=(2,))
t1.setName('线程1')
t2.setName('线程2')
#守护线程 由于下面存在线程阻塞 子线程结束后主线程才结束 所以此时不起作用
t1.setDaemon(True)
t2.setDaemon(True)
t1.start()
t2.start()
t1.join()
t2.join()     #开启了线程阻塞 主线程最后结束
print("主线程")
输出:
>>线程1 1
>>线程2 2
>>主线程

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25

自定义线程

多个线程之间共享变量
(处理小数据时由python 全局解释器锁GIL保护变量安全)

import threading
money=1000

def task1():
    global money
    for i in range(100):
        money-=1

def task2():
    global money
    for i in range(100):
        money-=1

if __name__ == '__main__':
    t1=threading.Thread(target=task1,name='线程1')
    t2=threading.Thread(target=task2,name='线程2')
    t1.start()
    t2.start()
    t1.join()
    t2.join()
    print(money)
    print('主线程结束')
输出:
>>800
>>主线程结束

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25

(处理大数据时由python 全局解释器锁GIL被释放数据处于不安全状态)

import threading
money=0

def task1():
    global money
    for i in range(1000000):
        money-=1

def task2():
    global money
    for i in range(1000000):
        money-=1

if __name__ == '__main__':
    t1=threading.Thread(target=task1,name='线程1')
    t2=threading.Thread(target=task2,name='线程2')
    t1.start()
    t2.start()
    t1.join()
    t2.join()
    print(money)
    print('主线程结束')
输出结果应该是:
>>-2000000
>>>主线程结束
>>>实际输出结果:
>>>-1328830
>>>主线程结束

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    
    因为在处理大数据时全局解释器锁GIL会自动释放，数据会处于不安全状态，所以在处理大数据时用线程锁代替全局解释器锁GIL

线程锁

from threading import Lock

    1

实例化线程锁对象=threading.Lock()
上锁对象.acquire()
解锁对象.release()
解决线程共享变量时由于CPU资源竞争出现的数据修改错误

import threading
from threading import Lock
money=0
def task1():
    lock.acquire()
    global money
    for i in range(1000000):
        money-=1
    lock.release()

def task2():
    lock.acquire()
    global money
    for i in range(1000000):
        money-=1
    lock.release()
if __name__ == '__main__':
	lock=Lock()
    t1=threading.Thread(target=task1,name='线程1')
    t2=threading.Thread(target=task2,name='线程2')
    t1.start()
    t2.start()
    t1.join()
    t2.join()
    print(money)
    print('主线程结束')
不加线程锁的输出结果:
>>-1328830
>>主线程结束

加线程锁之后输出:
>>-2000000
>>
>>>主线程结束

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
    23
    24
    25
    26
    27
    28
    29
    30
    31
    32
    33

线程池

from concurrent.futures import ThreadPoolExecutor

    1

pool=ThreadPoolExecutor(最大线程数)设置线程池最大线程数
r=pool.submit(函数名,参数) 向线程池提交任务
r.done()检测是否执行完毕
r.result()返回函数的执行的返回值

from concurrent.futures import ThreadPoolExecutor
import threading

def task1(max_sum):
    sum=0
    for i in range(max_sum):
        print("线程名:",threading.current_thread().name,i)
        sum+=1
    return sum

if __name__ == '__main__':
	#设置线程池最大线程数
    pool=ThreadPoolExecutor(20)
    futures=[]
    #提交两个参数
    for i in [100,200]:
    #将线程放入futures列表
        futures.append(pool.submit(task1,i))
    #遍历futures列表查看执行情况与返回值
    for j in futures:
        print(j.done())
        print("结果:",j.result())

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20
    21
    22
