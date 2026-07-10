# 01-basic/chapter01-环境搭建&HelloWorld.md
## 文档头部统一模板（固定格式，每次写笔记都套用）
学习日期：2026-07-10
学习耗时：1.5h
所属分卷：第一卷 Python零基础入门
本章目标：
1. 完成Python解释器安装，配置环境变量
2. 学会使用VS Code编写、运行Python代码
3. 写出并理解第一行Hello World程序
4. 掌握代码运行报错基础排查方法

---

## 一、什么是Python？（基础认知）
1. 编程语言分类：解释型、高级语言
2. 优势：语法简洁、易上手、生态库丰富（爬虫/数据分析/自动化/AI）
3. 版本区分：优先使用 **Python 3.10 ~ 3.12**，彻底淘汰Python2

## 二、Windows系统安装Python步骤
### 1. 下载安装包
官网地址：https://www.python.org/downloads/windows/
选择 Stable 稳定版，下载 Windows Installer

### 2. 安装关键操作（必看！90%新手报错来源）
安装界面底部勾选：
✅ Add Python to PATH
不勾选会出现 `python不是内部或外部命令` 报错

### 3. 验证是否安装成功
1. 按下 `Win + R`，输入 `cmd` 打开命令提示符
2. 输入命令：
```bash
python --version
```
3. 出现版本号（例如 `Python 3.11.4`）代表安装成功；提示不是命令=环境变量没配置

### 4. 环境变量修复方案（没勾选PATH补救）
1. 右键此电脑 → 属性 → 高级系统设置 → 环境变量
2. 在系统变量 `Path` 里新增两条路径（替换成你的安装目录）
```
C:\Python311
C:\Python311\Scripts
```
3. 关闭所有cmd窗口，重新打开再验证版本

## 三、代码编辑器 VS Code 配置Python环境
### 1. 安装VS Code
官网：https://code.visualstudio.com/
### 2. 必备插件安装
左侧扩展栏搜索安装：
1. Python（微软官方插件，核心）
2. Chinese (Simplified) 中文语言包
### 3. 运行代码两种方式
1. 右键文件 → 在终端中运行Python文件
2. 代码行右上角 ▶ 运行按钮

## 四、第一个程序：Hello World
### 完整代码
```python
# 我的第一行Python代码
print("Hello Python! 开启我的学习之旅")
print("今天开始从零学习Python")
```

### 代码逐行讲解
1. `#` 单行注释，解释代码，不会被程序执行
2. `print()` 内置函数：功能是向控制台输出文字/数字
3. 引号 `"内容"`：代表字符串文本，单双引号都可以

### 运行结果
```
Hello Python! 开启我的学习之旅
今天开始从零学习Python
```

## 五、新手高频报错&解决方案
### 报错1：SyntaxError: invalid syntax
原因：符号用了中文逗号/引号、括号不匹配
解决：所有代码符号必须切换英文输入法输入

### 报错2：NameError: name 'xxx' is not defined
原因：拼写错误，变量/函数名字打错

### 报错3：文件路径含中文，运行异常
建议：存放代码的文件夹全部用英文命名，不要出现中文

## 六、课后练习
1. 输出自己的名字、年龄，两行print打印
2. 尝试打印数字，比如 `print(2026)`
### 练习参考答案
```python
print("我的名字：小明")
print("今年年龄：25")
print(2026)
```

## 七、本节遗留疑问（存入待解决清单）
> 学到这里暂时不懂，后续章节再深入学习
1. print为什么必须加括号？
2. 解释器和编辑器的区别是什么？

---

# 配套README总目录更新片段（放到根目录README.md）
```markdown
## 📖 第一卷：Python零基础入门
1. chapter01 环境搭建 & 第一个HelloWorld
```

# 提交备注（提交时填写）
`feat: 01-basic 第一章 环境搭建&HelloWorld完整学习笔记`
