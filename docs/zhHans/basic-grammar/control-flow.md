---
order: 4
---

# 控制流：条件和循环

## 简介

控制流语句允许您根据条件执行不同的代码块或重复执行代码。Python提供了`if`语句、`for`循环和`while`循环来控制程序的执行流程。

## 条件语句（if-elif-else）

条件语句允许您根据条件执行不同的代码：

```python
age = 18

if age < 13:
    print("你是儿童")
elif age < 18:
    print("你是青少年")
elif age < 65:
    print("你是成年人")
else:
    print("你是老年人")
```

## For 循环

`for`循环用于遍历序列（如列表、字符串或范围）：

```python
# 遍历列表
fruits = ["苹果", "香蕉", "橙子"]
for fruit in fruits:
    print(f"我喜欢{fruit}")

# 使用range()
for i in range(5):
    print(f"数字: {i}")

# 遍历字符串
for char in "Python":
    print(char)
```

## While 循环

`while`循环在条件为真时重复执行代码：

```python
count = 0
while count < 5:
    print(f"计数: {count}")
    count += 1

print("循环结束！")
```

## Break 和 Continue

- `break`：退出循环
- `continue`：跳过当前迭代，继续下一次迭代

```python
# Break 示例
for i in range(10):
    if i == 5:
        break
    print(i)

# Continue 示例
for i in range(5):
    if i == 2:
        continue
    print(i)
```

## 练习：猜数字游戏

创建一个游戏，计算机选择一个随机数字，玩家尝试猜测它。

### 示例解决方案

```python
import random

def guess_number_game():
    print("=== 猜数字游戏 ===")
    print("我想了一个1到100之间的数字。")

    # 生成随机数字
    secret_number = random.randint(1, 100)
    attempts = 0
    max_attempts = 10

    while attempts < max_attempts:
        try:
            guess = int(input(f"\n尝试 {attempts + 1}/{max_attempts} - 请输入您的猜测: "))
            attempts += 1

            if guess < 1 or guess > 100:
                print("请输入1到100之间的数字！")
                continue

            if guess < secret_number:
                print("太小了！再试一次。")
            elif guess > secret_number:
                print("太大了！再试一次。")
            else:
                print(f"🎉 恭喜！您在{attempts}次尝试中猜对了！")
                break

        except ValueError:
            print("无效输入！请输入一个数字。")
            attempts -= 1  # 不计入无效尝试

    else:
        print(f"\n游戏结束！正确答案是{secret_number}。")

    # 询问是否再玩一次
    play_again = input("\n想再玩一次吗？(是/否): ").lower()
    if play_again in ['是', 'y', 'yes']:
        guess_number_game()

# 运行游戏
guess_number_game()
```

## 练习：九九乘法表

创建一个打印九九乘法表的程序。

### 示例解决方案

```python
def multiplication_table():
    print("=== 九九乘法表 ===\n")

    # 外层循环：行
    for i in range(1, 10):
        # 内层循环：列
        for j in range(1, 10):
            result = i * j
            print(f"{i} × {j} = {result:2}", end="  ")
        print()  # 换行

# 运行程序
multiplication_table()
```

## 嵌套循环

循环可以嵌套在其他循环内：

```python
# 打印图案
for i in range(5):
    for j in range(i + 1):
        print("*", end="")
    print()
```

输出：

```
*
**
***
****
*****
```

## 关键概念

1. **条件语句**：使用`if`、`elif`和`else`根据条件执行代码
2. **For循环**：遍历序列或执行固定次数的操作
3. **While循环**：在条件为真时重复执行代码
4. **Break**：立即退出循环
5. **Continue**：跳过当前迭代，继续下一次
6. **嵌套循环**：在循环内使用循环

## 练习挑战

1. 创建一个程序，打印1到100之间的所有质数
2. 编写一个程序，计算数字的阶乘
3. 创建一个FizzBuzz程序（1-100，3的倍数打印Fizz，5的倍数打印Buzz，15的倍数打印FizzBuzz）
4. 构建一个简单的菜单驱动程序，提供多个选项
5. 创建一个程序，反转字符串或数字
