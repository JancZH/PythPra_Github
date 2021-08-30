### 数据类型
#### 1. 整数
#### 2. 浮点数
#### 3. 字符串 : '' ; ""
> Python 3 中的字符串是用Unicode编码的
> 对于单个字符，可以用 **ord()** 函数获取字符的整数表示，**chr()** 函数将编码转换成对应的字符

> Python的字符串类型是str，在内存中用Unicode表示。如果在网络上传播或存储在磁盘中就需要把**str** 变为以字节为单位的**bytes** 
> Python对**bytes** 类型的数据用**b** 前缀的单引号或者双引号表示
> 例如 ：x = b'abc'
> 以Unicode编码的**str** 可以通过**encode()** 编码为指定的**bytes** 
> 例：'ABC'.encode('ascii')    #b'ABC'
> 要把 **bytes** 编程**str** 就要用**decode()** 
> 可以用**errors='ignore'** 忽略无效的字节

> **len()** 函数可以计算**str** 包含的字符数量，**bytes** 的字节数

> 编译python文件时最好在前面加上 **# -*- coding: utf-8 -*-** 告诉python解释器用utf-8编码来读取源代码

#### 4. 布尔值 : True/False
>  可以用 **and or not** 运算
#### 5. 空值： None
> None 和 0 不同，0是有意义的，None是一个特殊的空值
#### 6. 变量
> 在python中 用 **=** 赋值，可以将任意数据类型赋给变量，同一个变量可以反复赋值，而且可以是不同类型的变量，因此Python是动态语言
#### 7. 常量
> / : 除法的结果是浮点数
> // : 地板除的结果是整数， //只取整数部分
```
n = 123
f = 456.789
s1 = 'Hello, world'
s2 = 'Hello, \'Adam\''
s3 = r'Hello, "Bart"'
s4 = r'''Hello,
Lisa!'''
```

### 输入和输出
#### 1. 输出：print()
```
print('100 + 200 =', 100 + 200) # 100 + 200 = 300
print('This is','an','apple.') # This is an apple.逗号输出空格
```
##### 格式化输出字符串：用 *%* 来实现
```
print('hello,%s' % 'world')
```
##### 格式化字符串：用**format()** 
```
'Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)
'Hello, 小明, 成绩提升了 17.1%'
```
##### 格式化字符串：用**f-string** 
```
r = 2.5
s = 3.14 * r ** 2
print(f'The area of a circle with radius {r} is {s:.2f}')
The area of a circle with radius 2.5 is 19.62
```
#### 2. 输入：input()
**input()** 可以将用户输入的字符存放在变量中
```
name = input()
```
**input()** 可以给予用户输入提示
```
name = input('请输入姓名：')
print('Hello',name)
```
### 直接运行py文件的方法
> #!/usr/bin/env python3

这种方法只在MAC和Linux中可行，然后通过命令给py文件权限

> $chmod a+x XXXX.py

运行py文件
> ./XXXXX.py

### Python中条件分支、循环等的写法
1. 条件分支
   ```
   if username == 'admin' and password == '123456':
      print('身份验证成功!')
   else:
      print('身份验证失败!')
   ```
   if - elif - else结构
   ```
   if x > 1:
      y = 3 * x - 5
   elif x >= -1:
      y = x + 2
   else:
      y = 5 * x + 3
   ```
   嵌套
   ```
   if x > 1:
      y = 3 * x - 5
   else:
      if x >= -1:
         y = x + 2
      else:
         y = 5 * x + 3
   ```
2. for-in循环
   > 明确的知道循环执行的次数或者要对一个容器进行迭代
   ```
   sum = 0
   for x in range(101):
      sum += x
   print(sum)
   ```
   > range(101)：可以用来产生0到100范围的整数，需要注意的是取不到101。
     range(1, 101)：可以用来产生1到100范围的整数，相当于前面是闭区间后面是开区间。
     range(1, 101, 2)：可以用来产生1到100的奇数，其中2是步长，即每次数值递增的值。
     range(100, 0, -2)：可以用来产生100到1的偶数，其中-2是步长，即每次数字递减的值。
3. while循环
   > 构造不知道具体循环次数的循环结构
   ```
   import random

   answer = random.randint(1, 100)
   counter = 0
   while True:
      counter += 1
      number = int(input('请输入: '))
      if number < answer:
        print('大一点')
      elif number > answer:
        print('小一点')
      else:
        print('恭喜你猜对了!')
        break
   print('你总共猜了%d次' % counter)
   if counter > 7:
      print('你的智商余额明显不足')
   ```
   >break：终止它所在的循环
    continue：放弃本次循环后续代码，直接进入下次循环
   
   嵌套的循环：
   ```
   for i in range(1, 10):
      for j in range(1, i + 1):
        print('%d*%d=%d' % (i, j, i * j), end='\t')
      print()
   ```


### Python中变量特性
1. 大小写敏感
2. 用小写字母拼写，多个单词用下划线连接。
3. 受保护的实例属性用单个下划线开头
4. 私有的实例属性用两个下划线开头

### Python中内置函数
1. int()：将一个数值或字符串转换成整数，可以指定进制。
2. float()：将一个字符串转换成浮点数。
3. str()：将指定的对象转换成字符串形式，可以指定编码。
4. chr()：将整数转换成该编码对应的字符串（一个字符）。
5. ord()：将字符串（一个字符）转换成对应的编码（整数）。
6. 使用input()函数获取键盘输入(字符串)
7. 使用print()函数输出带占位符的字符串

### Python注释 ：“”“,#

-----

##### 纪念上传成功的第一次
````
Last login: Thu Aug 12 16:53:33 on ttys000
ttz@192 ~ % cd Code
ttz@192 Code % git clone git@github.com:JancZH/PythPra_Github.git
Cloning into 'PythPra_Github'...
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (5/5), done.
ttz@192 Code % cd PythonPra_Github
cd: no such file or directory: PythonPra_Github
ttz@192 Code % PythPra_Github
zsh: command not found: PythPra_Github
ttz@192 Code % cd PythPra_Github
ttz@192 PythPra_Github % git add .
ttz@192 PythPra_Github % git commit -m "First Commit"
[main 4bebee6] First Commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 PythonWiki.md
ttz@192 PythPra_Github % git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 342 bytes | 342.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:JancZH/PythPra_Github.git
   ceed1b4..4bebee6  main -> main
ttz@192 PythPra_Github % 

``````