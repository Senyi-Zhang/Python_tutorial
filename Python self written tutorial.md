# Python 基础内容自编教程
by  张 森燚
***
## 〇、基础
### 执行顺序
通常，代码是由上到下执行的。对同一对象后执行的操作会基于先执行的操作的基础上进行，也会覆盖先执行的操作的结果。
### 赋值符=
大多数编程语言中，=都代表赋值，即“为等号左边的内容赋予等号右边内容的值”，即“只改变等号左边内容的值，不改变右边的”。
```python
b = 1
a = 5
a = b
```
最后结果为a=b=1
### 注释
在python中有两种编写注释的方法：
+ “#”：一行中“#”**之后**的内容为注释，程序会直接无视这段内容。作用范围为单行。
+ 连续三个单引号和三个反引号之间的内容为注释。
```python
a = 1 # a = 2（这里是注释，a此时依然等于1）
b = 0
'''
b = 1
这段内容也是注释，b此时等于0
'''
```
## 一、Python数值类型
+ 整数（int）  
>顾名思义，包括正整数、负整数和零，不多解释。

+ 浮点数（float)
> 即小数。
```python
a = 1 #整数
b = 2.5 #浮点数
```
### 数值类型操作
+ 整数和浮点数支持各种数学运算。以下是一些常见的操作：
> 先了解，不必强记，用时自然会记住。
### 1. **基本算术操作**
   - **加法 (`+`)**：两个数相加。
     ```python
     x = 5 + 3  # 结果是 8
     y = 2.5 + 3.1  # 结果是 5.6
     ```
   - **减法 (`-`)**：两个数相减。
     ```python
     x = 10 - 4  # 结果是 6
     y = 3.5 - 1.2  # 结果是 2.3
     ```
   - **乘法 (`*`)**：两个数相乘。
     ```python
     x = 4 * 3  # 结果是 12
     y = 2.0 * 1.5  # 结果是 3.0
     ```
   - **除法 (`/`)**：两个数相除，结果为浮点数。
     ```python
     x = 7 / 2  # 结果是 3.5
     y = 9.0 / 3  # 结果是 3.0
     ```
   - **自增、自减、自乘、自除**
     ```python
     a = 2
     a += 1 #等效于a = a + 1
     a -= 1 #等效于a = a - 1
     a *= 2 #等效于a = a * 2
     a /= 2 #等效于a = a / 2
     ```
### 2. **整数除法 (`//`)**
   - 整数除法会返回商的整数部分。
     ```python
     x = 7 // 2  # 结果是 3
     y = 9 // 2  # 结果是 4
     ```

### 3. **取余数 (模运算) (`%`)**
```python
x = 7 % 2  # 结果是 1
y = 9 % 4  # 结果是 1
   ```

### 4. **指数运算 (`**`)**
```python
x = 2 ** 3  # 结果是 8 (2^3)
y = 4.0 ** 0.5  # 结果是 2.0 (开方)
   ```

### 5. **绝对值 (`abs()`)**
```python
x = abs(-10)  # 结果是 10
y = abs(-3.7)  # 结果是 3.7
   ```

### 6. **取整 (`round()`)**
   - 对浮点数进行四舍五入，返回整数或指定小数位数的浮点数。
     ```python
     x = round(3.14159)  # 结果是 3
     y = round(3.14159, 2)  # 结果是 3.14
     ```

### 7. **取整 (`int()`) 和 转浮点数 (`float()`)**
   - **`int()`**：将浮点数转换为整数（直接截断小数部分，不四舍五入）。
     ```python
     x = int(3.99)  # 结果是 3
     y = int(-2.8)  # 结果是 -2
     ```
   - **`float()`**：将整数转换为浮点数。
     ```python
     x = float(5)  # 结果是 5.0
     y = float(-2)  # 结果是 -2.0
     ```

## 二、列表
**列表**是用于表示数据的集合的数据类型。列表中的每一个数据都称为**元素**，每个元素都有对应的序号，从左到右分别为0,1,2,3，...称为**下标**或**索引**。  
使用方括号[ ]来创建列表。
```python
list1 = [2, 4, 6, 8, 10, 12]
empty_list = []#空列表
```
可以通过下标访问和修改元素。
```python
list1[0]#2
list1[1]#4
list1[2]=list1[1]#将list[2]的值修改为list[1]的值，即4
list1[-1]#列表倒数第一个元素，即12
```
通过.index()来查找元素，获得对应元素的下标
```python
list2 = [2, 4, 2, 4, 2, 6]
idx1 = list2.index(2)
idx2 = list2.index(6)
#idx1为0（index()会返回符合条件的下标中最小的那一个，list2[0]=2）  
#idx2为5(list2[5]=6)
```
添加和删除元素
```python
my_list = [1, 2, 3, 4, 5]
my_list.append(6)# .append(x)在列表末尾添加x
# 现在my_list=[1, 2, 3, 4, 5, 6]
my_list.insert(1, 0)# .insert(a, b)在索引a处插入b
# 现在my_list=[1, 0， 2, 3, 4, 5, 6]
my_list.remove(0)# .remove(x)删除第一个匹配的x,即下标最小的那一个
# 现在my_list=[1, 2, 3, 4, 5, 6]
my_list.pop(1)# .pop(a)删除索引a处的元素，后面的元素前移
# 现在my_list=[1, 3, 4, 5, 6]
```
列表的切片（获取子列表）
```python
my_list = [1, 2, 3, 4, 5]
sub_list = my_list[1:4]  # 获取索引 1 到 3 的元素，结果是 [2, 3, 4]
sub_list2 = my_list[:3]  # 获取从开始到索引 2 的元素，结果是 [1, 2, 3]
sub_list3 = my_list[2:]  # 获取从索引 2 到末尾的元素，结果是 [3, 4, 5]
sub_list4 = my_list[1:-1] # 获取从索引2到倒数第二个元素，结果是 [2, 3, 4]
another_list = my_list[:] #复制整个列表，如果不加[:]，在修改another_list时会同时修改my_list
```
此外，列表还有排序，翻转等操作。
## 三、字符串
### 字符
> 通常用单引号或双引号括起，其中只有一个符号。例如 ' 1 ', " 2 ", ' a ', ' , ', " ? "

在 Python 中，**字符串**（`str`）是一种用于表示文本的数据类型。字符串是由**字符**组成的有序序列，表示为单引号 `' '` 或双引号 `" "` 中的一段文字。

字符串可以用单引号、双引号或三引号（用于多行字符串）来定义：
```python
single_quote_str = 'Hello'
double_quote_str = "World"
multi_line_str = """This is
a multi-line string"""
empty_str = ''#空字符串
```
使用 `len()` 函数来获取字符串的长度，即字符数。
```python
s = "Hello"
length = len(s)  # 结果是 5
```

使用 `+` 操作符来连接两个或多个字符串。
```python
s1 = "Hello"
s2 = "World"
result = s1 + " " + s2  # 结果是 "Hello World"
```

使用 `*` 操作符重复一个字符串。
```python
s = "Hello"
result = s * 3  # 结果是 "HelloHelloHello"
```

通过索引获取字符串的子串，支持正索引和负索引。
```python
s = "Hello World"
result1 = s[0:5]  # 结果是 "Hello"
result2 = s[-5:]  # 结果是 "World"
```
和列表相同，字符串的索引从 `0` 开始，负索引表示从末尾开始，例如 `s[-1]` 是最后一个字符。

**大小写转换**
   - **`upper()`**：将字符串转换为全大写字母。
     ```python
     s = "hello"
     result = s.upper()  # 结果是 "HELLO"
     ```
   - **`lower()`**：将字符串转换为全小写字母。
     ```python
     s = "HELLO"
     result = s.lower()  # 结果是 "hello"
     ```
   - **`capitalize()`**：将字符串的首字母大写，其他字母小写。
   - **`title()`**：将字符串中的每个单词的首字母大写。

**去除空格**
   - **`strip()`**：移除字符串首尾的空格或指定字符。
     ```python
     s = "  hello  "
     result = s.strip()  # 结果是 "hello"
     ```
   - **`lstrip()`**：只移除左边的空格。
   - **`rstrip()`**：只移除右边的空格。

**查找与替换**
   - **`find()`**：查找子字符串的索引，若未找到则返回 `-1`。
     ```python
     s = "Hello World"
     index = s.find("World")  # 结果是 6
     ```
   - **`replace()`**：将字符串中的指定子字符串替换为另一个字符串。
     ```python
     s = "Hello World"
     result = s.replace("World", "Python")  # 结果是 "Hello Python"
     ```

**字符串分割与连接**
   - **`split()`**：将字符串按指定的分隔符拆分为列表。
     ```python
     s = "apple,banana,cherry"
     result = s.split(",")  # 结果是 ['apple', 'banana', 'cherry']
     ```
   - **`join()`**：将列表中的元素用指定的分隔符连接为一个字符串。
     ```python
     fruits = ['apple', 'banana', 'cherry']
     result = ", ".join(fruits)  # 结果是 "apple, banana, cherry"
     ```
**字符串的判断操作**
   - **`startswith()`**：判断字符串是否以指定子字符串开头。
     ```python
     s = "Hello World"
     result = s.startswith("Hello")  # 结果是 True
     ```
   - **`endswith()`**：判断字符串是否以指定子字符串结尾。
     ```python
     s = "Hello World"
     result = s.endswith("World")  # 结果是 True
     ```
   - **`isalnum()`**：判断字符串是否只包含字母和数字。
   - **`isalpha()`**：判断字符串是否只包含字母。
   - **`isdigit()`**：判断字符串是否只包含数字。
## 输入和输出
使用input()来获取用户输入
```python
my_string=input("Please Enter Your String:")
```
用户界面会显示
```python
> Please Enter Your String:
```
此时用户输入一个字符串
```python
> Please Enter Your String: Hello, world
```
此时
```python
my_string="Hello, world"
```
需要注意的是输入的格式默认为字符串，如果需要输入整数或浮点数需要进行类型转换
```python
my_number = input()
# 假设用户输入1
# 此时my_number = '1' 而非 1
my_number = int(my_number) #需要转换为浮点数则使用float()
# 此时my_number = 1
```
使用print()来将内容打印在屏幕上，print()能自行处理大部分数据类型，不需要手动转换成字符串
```python
print('Hello world')
> Hello world
print(10086)
> 10086
my_list = [1, 2, 3, 4, 5]
print(my_list)
> [1, 2, 3, 4, 5]
```
print()可以同时打印多个数据，默认以空格" "分隔，以换行符（"\n")结尾。
> 换行符(\n): 一种约定俗成的标记方法，实际作用为在打印字符串时换行
```python
print("Hello","world")
> Hello world
> #末尾换行
print("Hello\n", "world")
> Hello#换行符换行
> world
> #末尾换行
```
可以通过手动设置sep和end参数改变分隔和结尾
```python
print("Hello","World",sep='!', end='')
#以！分隔，末尾为空而不是默认的换行符
> Hello!World#末尾没有换行
```
字符串中如果含有某些符号，容易引起歧义，比如单引号、双引号
```python
string_with_error = 'Henry's cat is cute'
# python会认为Henry两边的单引号是互相匹配的，导致错误
```
这时需要在这些符号前加上转义符（"\")
```python
correct_string = 'Henry\'s cat is cute'
```
常见的需要加转义符的字符有单引号，双引号以及**斜杠本身**。
```python
print("2024\\07")
> 2024\07
```
## 四、可迭代对象和循环语句
聪明的你可能已经发现了，无论是列表还是字符串，都是由更小的单位组成的。而我们可以通过依次访问这些小的单位（称为**遍历**），来有序地访问列表或字符串。
```python
list1 = [1, 2, 3]
#列表是由一个个元素组成的，可以通过依次访问list1[0],list[1],list[2]来访问整个列表
str1 = "Me."
#字符串是由一个个字符组成的，可以通过依次访问str1[0],str1[1],str1[2]来访问整个字符串
```
具有这种性质的对象叫**可迭代对象**  
这种性质的最大作用是**方便遍历**  
使用for循环遍历一个可迭代对象：
```python
words = ['I', 'You', 'He']
for word in words:
    print(word)
>I
>You
>He
```
其实很好理解。for word in words: 对于words(列表）里的每一个word（元素）,打印word。  
这里的words是要遍历的列表，而word只是为列表里的元素起的一个暂用名，换成其他的也可以。  
需要注意的是，Python中的循环语句的范围是由**缩进**来决定的，循环体内的语句在每一行内的起始位置会比for靠后四个空格（或一个Tab)
```python
words = ['I', 'You', 'He']
for w in words:
    print(w)#这行的开头空了四格
    print("A")#同上
print("OK!")#没有空四格

> I
> A
> You
> A
> He
> A #参与了循环
> OK!#没有参与循环
```
使用len()会获得任何可迭代对象的长度
```python
len("Hello world") #11,别忽略了中间的空格也是一个字符
```
而range()会将一个整数n变成由0到n-1的列表
```python
range(4)#[0, 1, 2, 3]
```
将它们组合起来便获得了遍历可迭代对象的新方法
```python
my_list = ['I', 'am', 'Senyi', 'Zhang']
for i in range(len(my_list)):
    '''
len(my_list)是4，所以range(len(my_list))是[0, 1, 2, 3]
i也会从0遍历到3
所以实际上i是在遍历my_list的所有下标
'''
    print(my_list[i], end=' ')

> I am Senyi Zhang
```
而略简单的用法，例如把几条语句循环执行100遍，就可以这样用：
```python
a = 0
b = 100
for i in range(100):
    a += 1
    b -= 1
print(a, b)

> 100 0
```
## 五、条件语句
我们总是热衷于研究两个对象间的关系，于是为此我们发明了**条件运算符**  
条件运算符判断左右两个对象是否满足某种关系，并返回一个**布尔值**(True or False)  
条件运算符的优先级仅仅高于"="，所以它总是会等到两边的算式运算结束后再判断
```python
a = 5
b = -6
c = a > b #c=True
c = a + b > 0 #-1<0, c=False
```
常用条件运算符
+ \> ,<,>=,<=
> 大于，小于，大于等于，小于等于
+ ==，!=
> 等于，不等于
+ in （或者not in)
> 一个元素是否在（或不在）一个可迭代对象中
+ and (or)
> 与(或)
```python
my_list = [0, 1, 2]
print( 0 in my_list )#True
print( 1 not in my_list)#False
print( 0 in my_list and 1 not in my_list)#False
# and 表示与，只有两边的两个表达式都为真才会返回True
print( 0 in my_list or 1 not in my_list)#True
```
条件分支语句：
```python
if 1 < 0:#False
    print("a")
elif 2 > 0:#True
    print("b")
else:
    print("c")

> b
```
if 如果；elif = else if 否则如果； else 否则  
如果 1 < 0, print("a"), 否则如果 2 > 0, print("b"), 否则print("c")  
**整数**也可以起布尔值的效果，整数0相当于False，而非零整数都相当于True
```python
if -1:#等于 if True
    print("Yes")

> Yes
```
条件语句的范围也是由缩进决定的：
```python
if a:
    if b:
    elif c:
        if d:
        else: #这个else与if d 的 if对应
    else: #这个else与 if b和elif c 对应
else: #这个else与 if a的 if对应
```
## 再论循环
了解了条件运算符后，我们就可以学习另一种循环方式**while**了  
直观理解，while的意思是“当...时”，事实上也确实是这样：
```python
a = 5
while a > 0:
    print(a)
    a -= 1
> 5
> 4
> 3
> 2
> 1
```
当a大于0时，打印a并让a自减1，所以循环进行了五次。
## 六、函数
有时我们需要使用一段代码很多次，但又不想每次都写一遍，怎么办呢？这时就需要函数。  
```python
def increase_by_1(number):
    number += 1
    return number
```
这是一个简单的函数，包含了函数的所有重要组成部分    
def: define的缩写，用来告诉电脑你要定义一个函数了  
increase_by_1: 函数名，即你为函数起的名字，不能与其他函数重复  
(number): 函数名后紧跟的括号里是这个函数的参数列表，用于从外界向函数内部传递值  
number+=1: 函数中的代码块  
return (something): 函数的返回值   
**函数的领域也是由缩进决定的**  
编写完函数后，就可以开始调用它了
```python
def increase_by_1(number):
    number += 1#缩进，表示在函数内部
    return number#缩进，表示在函数内部

a = 5#没有缩进了，即在函数的外部
b = increase_by_1(a)#b = 6
c = increase_by_1(7)#c = 8
```
函数只有在被调用时才会执行内部语句，程序自动从上到下执行时会跳过函数。  
并且，函数内部和外界是相互隔离的两个空间，通过**参数**和**返回值**联系。  
```python
def increase_by_1(number):
    number += 1
    return number
a = 1
increase_by_1(a)
print("a =",a)

> a = 1
```
为什么a的值没有改变？因为没有通过返回值将函数内部a的值传递回外界，正确的做法是
```python
a = increase_by_1(a)
```
函数可以有不止一个参数，也可以有不止一个返回值。
```python
def process_list(a_list, number):
    new_list = a_list.append(number)
    return new_list, len(new_list)
my_list = [1, 2, 3]
list2, length = process_list(my_list, 4)
# list2 = [1, 2, 3, 4]
# length = 4
```
函数也可以没有返回值和参数
```python
def say_hello():
    print("Hello!")
    return
    
say_hello()
say_hello()
say_hello()

> Hello!
> Hello!
> Hello!
```
函数内部可以调用其他函数，也可以调用本身：
> 如果难以理解可以跳过
```python
def keep_decrease(n):
    if n <= 0:
        return 0
    else:
        print("n =", n)
        return keep_decrease(n-1)

n = 4
a = keep_decrease(n)
print("a =",a)

> n = 4
> n = 3
> n = 2
> n = 1
> a = 0
```
## 七、类
有时，一类对象是具有一些共性的，我们想要刻画这些共性。  
比如一些银行卡，它们里面都会有一些钱，并且我可以往其中存钱或者取钱。这时我们就可以用类刻画它们。  
```python
class bank_card:
    def __init__(self, money, id):
        self.money = money
        self.id= id
    def save_money(self, money):
        self.money += money
    def take_money(self, money):
        self.money -= money
```
这里的bank_card就是一个类，让我来详细解释一下它：  
class 是用于声明类的关键字，告诉程序你要创建一个类了。  
__init__是初始化函数， 它有三个参数：self, money和id  
self指的是类本身，在初始化函数__init__中，我们需要定义类的成员变量，比如银行卡的卡号和里面的钱，并且初始化它们。类的成员变量用 self.成员变量名 表示
> 成员变量： 一直伴随着一个类的属性，比如银行卡的卡号和里面的钱
```python
def __init__(self, money, id):
        self.money = money
        self.id= id
```
这个函数初始化了bank_card类，使它里面的钱等于从外部传进来的参数money，卡号亦如此；  
__init__函数会在一个类被创建时直接被调用，它的参数也是在创建类时需要传递的参数（除了self)
```python
card1 = bank_card(1000, 1) #里面有1000块钱，卡号为1
card2 = bank_card(2000, 2) #里面有2000块钱，卡号为2
```
在类被创建后，成员变量便会一直伴随着类，并且可以通过 类名.成员变量名 的形式访问
```python
print(card1.money)#1000
print(card2.id)#2
```
之前我们在类里还定义了一些函数，同样可以通过 类名.函数名 的形式调用  
函数对成员变量的改变是实时保存的，不需要通过返回值
```python
class bank_card:
    def __init__(self, money, id):
        self.money = money
        self.id= id
    def save_money(self, money):
        self.money += money
    def take_money(self, money):
        self.money -= money

card = bank_card(0, 123)
print(card.money)#0
card.save_money(10000)
print(card.money)#10000
```
关于类的学问还有很多，这里就不深入介绍了
## 八、文件操作
Python 的文件操作涉及到打开文件、读取或写入文件、关闭文件等几个步骤。

使用 `open()` 函数可以打开一个文件。它的基本语法是：
```python
file = open("filename", "mode")
```
- `"filename"` 是想要操作的文件名或路径。
- `"mode"` 决定你如何操作文件。常用的模式包括：
  - `"r"`：以读模式打开文件（文件必须存在）。
  - `"w"`：以写模式打开文件（文件不存在时会创建新文件，存在时会清空原有内容）。
  - `"a"`：以追加模式打开文件，内容会被加到文件末尾。
  - `"rb"`、`"wb"`、`"ab"`：分别以二进制的读、写、追加模式打开文件。

```python
file = open("example.txt", "r")
```

常用的读取文件的方法有以下几种：

- `read()`：一次性读取整个文件内容为一个字符串。
  ```python
  content = file.read()
  ```
- `readline()`：每次读取一行内容。
  ```python
  line = file.readline()
  ```
- `readlines()`：读取文件的所有行，返回一个列表，每一行是列表中的一个元素。
  ```python
  lines = file.readlines()
  ```

示例：
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

要写入文件，可以使用 `write()` 或 `writelines()` 方法。

- `write()`：写入字符串到文件。
  ```python
  with open("example.txt", "w") as file:
      file.write("Hello, World!")
  ```
- `writelines()`：写入一个字符串列表。
  ```python
  lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
  with open("example.txt", "w") as file:
      file.writelines(lines)
  ```

使用 `open()` 函数打开的文件在操作完成后必须关闭，使用 `close()` 方法：
```python
file.close()
```
不过推荐使用 `with` 语句，它会自动关闭文件：
```python
with open("example.txt", "r") as file:
    content = file.read()
```

使用 `"a"` 模式可以将新的内容追加到文件末尾：
```python
with open("example.txt", "a") as file:
    file.write("This will be appended to the file.")
```
## 九、关于python的更多
以上我们所说的这些，都是python的内置功能，它们构成了python体系的基础，但只是它的冰山一角。  
Python在今天拥有如此重要的地位，几乎全要归功于它代码的无与伦比的可共享性。你可以随心所欲地将代码上传到python社区，也可以通过非常简单的过程下载他人的杰出代码，让它们为你所用。
全世界每天都有几百万名程序员为社区做出贡献，一点点丰富着python的功能。
### 导入代码
如果在本地的某个.py文件里编写了一个函数，现在想在另一个.py文件里调用它，可以吗？  
当然可以。只需
```python
from 文件路径 import 函数名
```
假设要从file1里调用function1和function2到file2,而file1和file2在同一文件夹里，只需在file2里编写
```python
from file1 import function1, function2
```
### 导入代码库
诚然，python的一切功能都是可以通过从头一行行地手撸代码来实现的，然而那样既费时费力，也没有必要。过去已有许多先贤探索并实现了在各自领域发挥重大作用的功能，
并留下了珍贵的智慧结晶——代码库。只需通过简单的
```python
import 代码库名
```
便可以使用其中所有的函数和类。  
不同领域的开发者可能需要学习不同代码库的使用方法，然而相同的是，生于这个时代的我们已经不再需要理解这些功能如何从头实现，只需阅读、学习前人的说明，
站在他们的肩膀上眺望更遥远的彼方。

## 结语
如果你认真阅读了前八章的内容，恭喜你已经掌握了成为一名python开发者所必须掌握的一切。而从第九章起，python的学习之路便没有了必经的路径。
此后，身处不同的领域，面对不同的需求，我们会吸取不同前人的智慧结晶，学习它们每个都不会太简单，但总没有创造它们时难。身处现在的我们，又会为这个世界留下怎样的波纹呢？
