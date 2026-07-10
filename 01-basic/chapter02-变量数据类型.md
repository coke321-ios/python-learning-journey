# 01-basic/chapter02-变量数据类型.md

学习日期：2026-07-10
学习耗时：2h
所属分卷：第一卷 Python零基础入门
本章目标：

1. 理解变量的含义、命名规则与赋值逻辑
2. 掌握Python 6大基础数据类型：整数、浮点数、字符串、布尔值、空值
3. 学会不同类型之间的转换方法
4. 看懂变量内存简单逻辑，规避命名、类型转换常见报错

---

## 一、什么是变量

### 1. 概念

变量就是**给数据起一个名字**，把数字、文字等数据存起来，后续代码可以直接通过名字调用这段数据。
类比：抽屉贴标签，标签名=变量名，抽屉里的东西=数据。

### 2. 赋值语法 `=`

`变量名 = 数据`
注意：单个等号 `=` 是**赋值**，不是数学里的等于；判断相等用 `==`。

```
# 把文字存入变量 name
name = "小明"
# 把数字存入变量 age
age = 18
# 打印变量里存的数据
print(name)
print(age)
```

运行结果：

```
小明
18
```

### 3. 连续赋值、多变量赋值

```
# 1. 一个值分给多个变量
a = b = c = 100
print(a, b, c)  # 输出：100 100 100

# 2. 多个变量同时赋值（一一对应）
height, weight = 175.5, 62.3
print(height, weight)  # 输出：175.5 62.3
```

## 二、变量命名硬性规则（违反直接报错）

1. 只能由**英文大小写、数字、下划线 `_`** 组成，不能包含中文、空格、特殊符号（`!@#$`等）
2. **不能以数字开头**
3. 不能使用Python内置关键字（if、for、while、print、class等）
4. 区分大小写：`Name` 和 `name` 是两个完全不同的变量

### 规范推荐（行业习惯，不报错但可读性更好）

- 普通变量：小写+下划线（蛇形命名）`user_age`、student\_name
- 禁止拼音混搭、无意义单字母（除非临时循环）
- 见名知意：不要写 `a=20`，写 `age=20`

### 错误命名示例（运行报错）

```
1age = 18      # 数字开头，非法
user-name = "小红" # 包含横杠，非法
if = 10        # 使用关键字if，非法
```

## 三、Python五大基础数据类型

### 1. 整数 int

不带小数点的正负数字，无大小限制

```
num1 = 666
num2 = -88
num3 = 0
print(type(num1)) # type()函数查看数据类型，输出 <class 'int'>
```

### 2. 浮点数 float

带小数点的小数，计算会存在微小精度误差

```
price = 9.9
score = 95.5
print(type(price)) # <class 'float'>

# 精度误差示例
print(0.1 + 0.2) # 输出 0.30000000000000004，不是标准0.3
# 财务计算后续要用decimal模块处理精度
```

### 3. 字符串 str

用**单引号/双引号/三引号**包裹的文本，文字、数字、符号都属于字符串

- 单双引号功能完全一致
- 三引号 `"""..."""` 支持多行文本

```
s1 = "我是双引号字符串"
s2 = '单引号也可以'
# 多行字符串
s3 = """
第一行文字
第二行文字
第三行文字
"""
print(type(s1)) # <class 'str'>

# 字符串拼接 +
word1 = "Hello"
word2 = "Python"
print(word1 + " " + word2) # Hello Python

# 字符串重复 *
print("加油！" * 3) # 加油！加油！加油！
```

### 4. 布尔值 bool

只有两个固定值：`True`（真）、`False`（假），用于判断条件

```
is_student = True
has_car = False
print(type(is_student)) # <class 'bool'>

# 布尔值本质：True=1，False=0
print(True + 10)  # 11
print(False + 5)   # 5
```

### 5. 空值 NoneType

`None` 代表空、无数据，区别于数字0、空字符串`""`

```
data = None
print(type(data)) # <class 'NoneType'>

# 判断变量是否为空
if data is None:
    print("变量里没有存任何数据")
```

## 四、数据类型转换

### 常用转换函数

1. `int(数据)`：转整数
2. `float(数据)`：转浮点数
3. `str(数据)`：转字符串
4. `bool(数据)`：转布尔值

### 代码示例

```
# 1. 数字转字符串（拼接必备）
age = 18
print("我的年龄是" + str(age))

# 2. 字符串数字转数值计算
num_str = "20"
print(int(num_str) + 10) # 30

# 3. 浮点数转整数（直接舍弃小数，不四舍五入）
print(int(9.99)) # 9

# 4. 数字转布尔：0/空字符串/None 为False，其余全True
print(bool(0))      # False
print(bool(123))    # True
print(bool(""))     # False
print(bool("文字")) # True
```

### 转换报错场景

```
# 纯文字字符串无法转数字，直接报错
text = "python"
int(text) # ValueError: invalid literal for int()
```

## 五、新手高频报错&解决方案

1. **SyntaxError: invalid syntax**
原因：变量名非法、引号中英文混用、赋值符号写错
解决：变量名只用英文下划线，所有标点切换英文输入法
2. **NameError: name 'xxx' is not defined**
原因：变量名拼写错误，或者使用前没有定义赋值
解决：检查变量名字大小写、拼写，先赋值再print
3. **TypeError: can only concatenate str (not "int") to str**
原因：字符串和数字直接用`+`拼接
解决：数字先用`str()`转换成字符串再拼接

## 六、课后练习

### 题目

1. 定义4个变量：姓名、年龄、身高、是否学生，分别对应字符串、整数、浮点数、布尔值，完整打印个人信息
2. 定义两个数字字符串，转换成整数后求和并打印结果
3. 判断空字符串、数字0、数字100、None转布尔值分别是什么

### 参考答案

```
# 练习1
name = "小李"
age = 19
height = 172.3
is_student = True
print("姓名：" + name)
print("年龄：" + str(age))
print("身高：" + str(height))
print("是学生：" + str(is_student))

# 练习2
a = "15"
b = "25"
sum_num = int(a) + int(b)
print("两数之和：", sum_num)

# 练习3
print(bool(""))    # False
print(bool(0))     # False
print(bool(100))   # True
print(bool(None))  # False
```

## 七、本节遗留疑问（待后续章节解决）

1. 除了这5种基础类型，列表、字典是什么类型？
2. 浮点数精度误差该怎么彻底解决？
3. 三引号字符串和普通引号还有什么区别？

---

## 配套README跳转链接（你直接加到README目录里）

`[2.变量、数据类型、运算符](01-basic/chapter02-变量数据类型.md)`

