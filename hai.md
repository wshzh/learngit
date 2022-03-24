# python 笔记 #
##数据结构
dict字典不是数组，实际上是一个映射，用大括号括起来，元素用逗号分开，间隔值间有一个冒号；set用大括号括起来，元素间用逗号分开；字符串数组，用一对单引号或一对双引号引起来的元素；array是一个阵列，所有元素都是同一类型的数。first in/first out? 双端口形式

>3.1数值对象 

int,float等等
complex复数（python中不需定义，既见既所得）复数1+j应当写成1+1j，若需要1为复数，则输入1+0j
内置函数 如power（）（指数），abs（）（求绝对值  ）
公用模块 如operator,math（实数运算）,cmath(把所有数当做复数),random  
专业扩展（对数据进行分析，专业的库）  
23** 25也可写成power(23,25)  
pow(23,25,20)  
3  
(23** 25)%20  
3  
import math  
dir(math)/看模块中有哪些东西  
import cmath  
cmath.sin(20+10J)  
(10054.47868956549+4494.302778739991j)  
相当于  
——import——('cmath').sin(20+10j)为双下划线  
(10054.47868956549+4494.302778739991j)  
但是__import__('cmath').sin(20+10j)还未引入cmath库  
不能直接dir(cmath)  
要用dir(__import__cmath)  

> 3.2 list列表对象 

列表是序列对象，可包含任意的python数据信息，如字符串、数字、列表、元组  
list table=[‘’a’’,’’b’’,’’c’’]字符串列表  
list table=[1,2,3,4]数字的列表  
list table=[[1,2,3,4] ，[‘’a’’,’’b’’,’’c’’]]列表的列表  
list table=[(1,2,3,4),( ‘’a’’,’’b’’,’’c’’)]元组的列表  
如何访问列表中的元素，用index的方式访问  
list table=[‘’a’’,’’b’’,’’c’’] “a”是index0，”b”是index1……index3超出范围  
用索引，list[0:2]返回第一个和第二个元素  
访问列表的列表，list[1][0]访问第二个列表中的第一个元素  
亦可以从后往前访问。最后一个元素记为-1，倒数第二个元素记为-2  
l=[1,2,3,4,5,'a','b','c']  
l[0]
1
l[7]
'c'
l[-1]
'c'
l[-4]
5
l[0:4]
[1, 2, 3, 4]
ll=[1,2,3,4,5]
l=[1,2,3,4,5,'a','b','c']
len(l)
8/l中有8个元素
max(l)
Traceback (most recent call last):  
  File "<pyshell#28>", line 1, in <module>  
    max(l)  
TypeError: '>' not supported between instances of 'str'   and 'int'  
max(ll)    
5  
**切片**
l[1:3:1]  
[2, 3]  
访问第1到3位，步长为1，实际上步长为1是可以省略的；  
切片到2个元素  
l[1:3]  
[2, 3]  
 l[-1:-3:-2]  
['c']#‘a’是不能访问的  
l[-1:-3:-1]  
['c', 'b']  
list的方法：
append（x）：把一个元素添加到列表的结尾，相当于a[len(a):]=[x]  
extend（L）：添加指定列表的所有元素来扩充列表  
insert（i，x）在index位置插入元素  
remove（x）删除表中与index0最近的一个值为x的元素。若没有这样的元素，则返回一个错误。  
pop([i])删除指定位置的元素并将其返回  
index（x）返回列表中第一个值为x的索引  
count(x):返回x在链表中出现的次数  
sort（）排序，若不指定则从小到大  
reverse（）倒排（对折）  
copy（）浅拷贝（shallow copy，还有deep copy）  
clear（）清除元素  
输入l.  则十一个方法全部自动浮现  
l.append('abc')  
l  
[1, 2, 3, 4, 5, 'a', 'b', 'c', 'abc']   
l.pop()  
'abc'  
l  
[1, 2, 3, 4, 5, 'a', 'b', 'c']  
l.extend(l)  
l  
[1, 2, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l.count(1)  
2  
l.remove(1)  
l  
[2, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']
l.index(2)  
0   

l2=l.copy()#浅拷贝  
l  
[2, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l2  
[2, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l[0]=100#此时把l【0】改成100  
l  
[100, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l2#l2中l2【0】不变  
[2, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l2[0]=200  
l2  
[200, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l  
[100, 3, 4, 5, 'a', 'b', 'c', 1, 2, 3, 4, 5, 'a', 'b', 'c']  
l1=[1,2,3,[1,2,3]]  
l1  
[1, 2, 3, [1, 2, 3]]
l2=l1.copy()
l2
[1, 2, 3, [1, 2, 3]]
l1[0]=100
l1
[100, 2, 3, [1, 2, 3]]
l2
[1, 2, 3, [1, 2, 3]]
l1[3][0]=100
l1
[100, 2, 3, [100, 2, 3]]
l2
[1, 2, 3, [100, 2, 3]]  
**l2是l1的浅拷贝，不完全是l1的复制**   
l2[3][0]=200
l2
[1, 2, 3, [200, 2, 3]]
l1
[100, 2, 3, [200, 2, 3]]
l2[2]=300
l2
[1, 2, 300, [200, 2, 3]]
l1
[100, 2, 3, [200, 2, 3]]  
**解决此问题：深拷贝，使l2完全为l1的副本**
l3=l2[::]  
**起始值，终止值和步长全部一样的循环**
l2
[1, 2, 300, [200, 2, 3]]
l3
[1, 2, 300, [200, 2, 3]]
l2[0]=400
l2
[400, 2, 300, [200, 2, 3]]
l3
[1, 2, 300, [200, 2, 3]]
l2[3][2]=500
l2
[400, 2, 300, [200, 2, 500]]
l3
[1, 2, 300, [200, 2, 500]]    
**说明这种拷贝跟copy一样 ** 
import copy
dir(copy)
['Error', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', '_copy_dispatch', '_copy_immutable', '_deepcopy_atomic', '_deepcopy_dict', '_deepcopy_dispatch', '_deepcopy_list', '_deepcopy_method', '_deepcopy_tuple', '_keep_alive', '_reconstruct', 'copy', 'deepcopy', 'dispatch_table', 'error']    
**copy里的deepcopy才能解决该问题**  
l3[0]=600
l3
[600, 2, 300, [200, 2, 500]]
l4
[1, 2, 300, [200, 2, 500]]
l3[3][0]=700
l3
[600, 2, 300, [700, 2, 500]]
l4
[1, 2, 300, [200, 2, 500]]  
或者直接重写一遍，l5=……不会受后续别的list的变化的影响
深拷贝是建立了一个副本，浅拷贝实际上没有建立副本。  
>3.3 tuple元组对象
t=(1,2,3,4,5,'a','b','c')
    
type(t)
    
<class 'tuple'>
t=(1,2,3,4,5,'a','b','c')
    
type(t)
    
<class 'tuple'>
t[0]
    
1
t[-1]
    
'c'
t[1:5:2]
    
(2, 4)
t[-5:-2:1]
    
(4, 5, 'a')
t[-2:-5:1]
    
()


t[-2:-5:1]
    
()
t[-2:-5:-2]]
SyntaxError: unmatched ']'

t[-2:-5:-2]
('b', 5)
t.index(5)
4

>3.4 dict字典对象 

键key和值value  
monthdays={‘Jan’:31,’Feb’:28,’Mar’:31}   
由键来访问值  
字典不是一个序列，序列是有顺序的，字典中键值对的排列是随机的  
d={'a':1,23:23}（后一个键是23，值也是23）  
type(d)  
<class 'dict'>  
d['a']  
1  
d[23]  
23  
字典有11种方法：  
dict.keys():返回所有关键字组成的列表（如果需要它有序，则调用返回列表的sort（）方法）  
dict.values（）返回子店内所有的值  
dict.get():根据关键字返回值，如果不存在输入的关键字返回None  
dict.fromkeys():根据关键字建立新的字典  
dict.update（another dict）**类似于合并**，把一个字典的关键字和值合并到另一个，没有的添加一项，相同的覆盖原来的  
dict.pop()字典中删除一个键值对，**删除是随机的，但是会返回删除的值，删的是关键字不是位置  **
dict.clear（）删除所有关键字  
dict.copy()浅复制  
dict.items()将所有字典项以列表的方式返回，没有特殊顺序  

d.keys()  
dict_keys(['a', 23])  
d.values()  
dict_values([1, 23])  
d.pop('a')  
1  
d  
{23: 23}  

d.setdefault('a')#查询是否you’a’，若没有则直接将‘a’写入字典，然后值为缺省值None  
d
{23: 23, 'a': None}

d.setdefault('c','hello')
'hello'
d
{23: 23, 'a': None, 'b': None, 'c': 'hello'}
说明字典是可更改的对象
字典中，键是唯一的


>3.5 set集合对象 

大括号，每个元素用逗号分开，但是它只有值，没有键  
字典中，键是唯一的；set中，值是不能重复的，set有去重功能  
字典可以更改，但是set不可更改  
set里不能访问的，它是无序的  
set里只能有一个参数  
set中所有的数据类型是一样的  
s={1,2,3,4,5}  
type(s)
<class 'set'>
n={1,2,3,3,4}
type(n)
<class 'set'>
n
{1, 2, 3, 4}
1 in s
True
10 in s
False  
set的操作有17种  
交集a&b  
并集a|b  
a-b  
a^b： a并b减去a和b相交  
s
{1, 2, 3, 4, 5}  
s1={5,6,7,8,9}  
s1  
{5, 6, 7, 8, 9}  
s&s1  
{5}  
s|s1  
{1, 2, 3, 4, 5, 6, 7, 8, 9} 取并去重  
s-s1  
{1, 2, 3, 4}  
s^s1  
{1, 2, 3, 4, 6, 7, 8, 9}  
s=[1,2,3,4,4,4,5,6]  
len(s)  
8  
s1=set(s)  
s1  
{1, 2, 3, 4, 5, 6}  
len(s1)  
6  
8变成6，可以判断出，s中至少有一个值是重复的，最多有两个值是重复的。  
s  
[1, 2, 3, 4, 5, 4, 5, 6]  
s1  
{1, 2, 3, 4, 5, 6}  

>3.6 str字符串对象

单引号或者双引号引起来的都是字符串  
也可以使用三对双引号或三对单引号使字符串跨行  
ss='hello,world!'
type(ss)
<class 'str'>
len(ss)
12
ss[0]
'h'
ss[-1]
'!'
ss[1:4:2]
'el'
ss[-1:-4:2]  
''
/-1加2到不了-4  
ss[-1:-4:-2]
'!l'
str.capitalize(ss)
'Hello,world!'
\
ss[5]='?'
Traceback (most recent call last):
  File "<pyshell#200>", line 1, in <module>
    ss[5]='?'
TypeError: 'str' object does not support item assignment  
**字符串是不可更改的，变化大小写也不是原地改，但是可以访问**   
ss.count('w')
1
ss.count('5')
0
ss.count('l')
3
ss.upper()
'HELLO,WORLD!'
ss
'hello,world!'
ss.split(',')
['hello', 'world!']  
/将字符串以’,’作为分隔符，然后把分隔出的元素组成一个列表   
ss.split('o')
['hell', ',w', 'rld!']  
字符串格式化  
用%操作符编写格式化的字符串  
%左边是形式的格式  ，
“%d（填一个十进制数） %s（填一个字符串）%d（填一个十进制数） you”  
"%d %s %d you"%(1,'spam',4)  
'1 spam 4 you'  

或者用format：
"The sum of 1 + 2 is {0}".format(1+2)  
'The sum of 1 + 2 is 3'  

"The sum of 1 + 2 is{0}".format(1+2)  
'The sum of 1 + 2 is3'  
"The sum of 1 + 2 is {0}".format(1+2)  
'The sum of 1 + 2 is 3'  
"%4d %s %d you"%(1,'spam',4)  
'   1 spam 4 you'  
"%-4d %s %d you"%(1,'spam',4)  
'1    spam 4 you'  
"%-4.2f %s %d you"%(1,'spam',4)  
'1.00 spam 4 you'  
"%-10.2f %s %d you"%(1,'spam',4)  
'1.00       spam 4 you'    
/**2f为两位小数的浮点数，10是1和后面spam隔了10个位置，-是左对齐**  
"%010.2f %s %d you"%(1,'spam',4)
'0000001.00 spam 4 you'

"{1} {2} {1} you".format(1,'spam',4)
'spam 4 spam you'

hi='hello,world!'
print('***{name}***')
***{name}***
print(f'***{name}***')
Traceback (most recent call last):
  File "<pyshell#231>", line 1, in <module>
    print(f'***{name}***')
NameError: name 'name' is not defined
print('***{hi}***')
      
***{hi}***
print(f'***{hi}***')
      
***hello,world!***

>3.7 array数组对象

数据类型较为简单  
import array  
x=array.array('d')
x
array('d')
x.append(12)
x.append(24)
x
array('d', [12.0, 24.0])/双精度数
x[0]
12.0
x[1]
24.0

>3.8数据结构扩展
