---
order: 3
---

# 变量和数据类型

## 简介

变量是存储数据值的容器。Python有多种数据类型，包括数字、字符串、布尔值等。理解这些基本概念对任何Python程序员都至关重要。

## 基本数据类型

### 数字

Python支持整数、浮点数和复数：

```python
# 整数
age = 25
print(f"年龄: {age}, 类型: {type(age)}")

# 浮点数
price = 19.99
print(f"价格: {price}, 类型: {type(price)}")

# 复数
complex_num = 3 + 4j
print(f"复数: {complex_num}, 类型: {type(complex_num)}")
```

### 字符串

字符串是用引号括起来的字符序列：

```python
# 单引号
name = 'Alice'

# 双引号
message = "你好，世界！"

# 三引号用于多行字符串
description = """这是一个
多行字符串
在Python中。"""

print(name)
print(message)
print(description)
```

### 布尔值

布尔值表示真或假：

```python
is_student = True
has_graduated = False

print(f"是学生: {is_student}")
print(f"已毕业: {has_graduated}")
```

## 类型转换

您可以在不同数据类型之间进行转换：

```python
# 字符串转整数
age_str = "25"
age_int = int(age_str)
print(f"转换后: {age_int}, 类型: {type(age_int)}")

# 整数转字符串
number = 42
number_str = str(number)
print(f"转换后: {number_str}, 类型: {type(number_str)}")

# 字符串转浮点数
price_str = "19.99"
price_float = float(price_str)
print(f"转换后: {price_float}, 类型: {type(price_float)}")
```

## 练习：温度转换器

创建一个在摄氏度和华氏度之间转换温度的程序。

### 示例解决方案

```python
def temperature_converter():
    print("=== 温度转换器 ===")
    print("1. 摄氏度转华氏度")
    print("2. 华氏度转摄氏度")

    choice = input("\n请输入您的选择 (1/2): ")

    if choice == '1':
        celsius = float(input("请输入摄氏度温度: "))
        fahrenheit = (celsius * 9/5) + 32
        print(f"{celsius}°C = {fahrenheit:.2f}°F")

    elif choice == '2':
        fahrenheit = float(input("请输入华氏度温度: "))
        celsius = (fahrenheit - 32) * 5/9
        print(f"{fahrenheit}°F = {celsius:.2f}°C")

    else:
        print("无效选择！")

# 运行转换器
temperature_converter()
```

## 关键概念

1. **变量赋值**：使用`=`为变量赋值
2. **动态类型**：Python自动确定数据类型
3. **类型检查**：使用`type()`检查变量的类型
4. **类型转换**：使用`int()`、`float()`、`str()`等进行类型转换
5. **字符串格式化**：使用f-strings进行简单的字符串插值

## 练习挑战

1. 创建一个BMI（身体质量指数）计算器，接受体重和身高作为输入
2. 构建一个执行基本算术运算的简单计算器
3. 创建一个交换两个变量值的程序
4. 编写一个检查数字是偶数还是奇数的程序
5. 构建一个在不同货币之间转换的货币转换器
