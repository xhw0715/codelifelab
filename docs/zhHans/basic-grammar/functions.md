---
order: 5
---

# 函数

## 简介

函数是执行特定任务的可重用代码块。它们帮助组织代码，使代码更易读，并减少重复。在Python中，使用`def`关键字定义函数。

## 基本函数语法

```python
def greet():
    print("你好，世界！")

# 调用函数
greet()
```

## 带参数的函数

函数可以接受称为参数的输入值：

```python
def greet_person(name):
    print(f"你好，{name}！")

greet_person("小明")
greet_person("小红")
```

## 多个参数

函数可以有多个参数：

```python
def add_numbers(a, b):
    result = a + b
    print(f"{a} + {b} = {result}")

add_numbers(5, 3)
add_numbers(10, 20)
```

## 返回值

函数可以使用`return`关键字返回值：

```python
def multiply(a, b):
    return a * b

result = multiply(4, 5)
print(f"结果: {result}")

# 直接在表达式中使用
total = multiply(3, 7) + multiply(2, 4)
print(f"总计: {total}")
```

## 默认参数

您可以为参数提供默认值：

```python
def greet(name, greeting="你好"):
    print(f"{greeting}，{name}！")

greet("小明")              # 使用默认问候语
greet("小红", "嗨")        # 使用自定义问候语
greet("小刚", "早上好")
```

## 练习：计算器函数

创建一个计算器，为每个操作提供单独的函数。

### 示例解决方案

```python
def add(a, b):
    """加法：两数相加"""
    return a + b

def subtract(a, b):
    """减法：a减去b"""
    return a - b

def multiply(a, b):
    """乘法：两数相乘"""
    return a * b

def divide(a, b):
    """除法：a除以b"""
    if b == 0:
        return "错误：不能除以零"
    return a / b

def calculator():
    print("=== 简单计算器 ===")
    print("操作：")
    print("1. 加法")
    print("2. 减法")
    print("3. 乘法")
    print("4. 除法")
    print("5. 退出")

    while True:
        choice = input("\n请输入操作 (1-5): ")

        if choice == '5':
            print("感谢使用计算器！")
            break

        if choice not in ['1', '2', '3', '4']:
            print("无效选择！")
            continue

        try:
            num1 = float(input("请输入第一个数字: "))
            num2 = float(input("请输入第二个数字: "))

            if choice == '1':
                result = add(num1, num2)
                print(f"结果: {num1} + {num2} = {result}")
            elif choice == '2':
                result = subtract(num1, num2)
                print(f"结果: {num1} - {num2} = {result}")
            elif choice == '3':
                result = multiply(num1, num2)
                print(f"结果: {num1} × {num2} = {result}")
            elif choice == '4':
                result = divide(num1, num2)
                print(f"结果: {num1} ÷ {num2} = {result}")

        except ValueError:
            print("无效输入！请输入数字。")

# 运行计算器
calculator()
```

## 练习：文本分析器

创建函数来分析文本字符串。

### 示例解决方案

```python
def count_words(text):
    """统计文本中的单词数量"""
    words = text.split()
    return len(words)

def count_vowels(text):
    """统计文本中的元音字母数量"""
    vowels = "aeiouAEIOU"
    count = 0
    for char in text:
        if char in vowels:
            count += 1
    return count

def reverse_text(text):
    """反转文本"""
    return text[::-1]

def is_palindrome(text):
    """检查文本是否为回文"""
    # 移除空格并转换为小写
    cleaned = text.replace(" ", "").lower()
    return cleaned == cleaned[::-1]

def text_analyzer():
    print("=== 文本分析器 ===")

    text = input("请输入要分析的文本: ")

    print(f"\n分析结果:")
    print(f"单词数量: {count_words(text)}")
    print(f"元音字母数量: {count_vowels(text)}")
    print(f"反转后: {reverse_text(text)}")
    print(f"是否为回文: {is_palindrome(text)}")

# 运行分析器
text_analyzer()
```

## 变量作用域

在函数内定义的变量是该函数的局部变量：

```python
def my_function():
    local_var = "我是局部变量"
    print(local_var)

my_function()
# print(local_var)  # 这会导致错误

# 全局变量
global_var = "我是全局变量"

def another_function():
    print(global_var)  # 可以访问全局变量

another_function()
```

## 文档字符串

使用文档字符串来记录您的函数：

```python
def calculate_area(length, width):
    """
    计算矩形的面积。

    参数:
    length (float): 矩形的长度
    width (float): 矩形的宽度

    返回:
    float: 矩形的面积
    """
    return length * width

# 访问文档字符串
print(calculate_area.__doc__)
```

## 关键概念

1. **函数定义**：使用`def`定义函数
2. **参数**：传递给函数的输入值
3. **返回值**：使用`return`从函数返回值
4. **默认参数**：为可选参数提供默认值
5. **作用域**：函数内的变量默认是局部的
6. **文档字符串**：使用三引号字符串记录函数

## 练习挑战

1. 创建一个函数，检查数字是否为质数
2. 编写一个函数，生成前n项斐波那契数列
3. 创建一个函数，在不同单位之间转换（米到英尺、千克到磅等）
4. 构建一个函数，验证电子邮件地址
5. 编写一个函数，查找列表中的最大/最小数字
