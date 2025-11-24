---
order: 6
---

# 列表和列表操作

## 简介

列表是Python中最通用的数据结构之一。它们是有序的、可变的集合，可以存储不同类型的项目。列表使用方括号`[]`定义。

## 创建列表

```python
# 空列表
empty_list = []

# 包含项目的列表
fruits = ["苹果", "香蕉", "橙子"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "你好", 3.14, True]

print(fruits)
print(numbers)
print(mixed)
```

## 访问列表元素

使用索引访问元素（索引从0开始）：

```python
fruits = ["苹果", "香蕉", "橙子", "葡萄"]

print(fruits[0])   # 第一个元素: 苹果
print(fruits[1])   # 第二个元素: 香蕉
print(fruits[-1])  # 最后一个元素: 葡萄
print(fruits[-2])  # 倒数第二个: 橙子
```

## 列表切片

使用切片提取列表的部分：

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

print(numbers[2:5])    # [2, 3, 4]
print(numbers[:4])     # [0, 1, 2, 3]
print(numbers[6:])     # [6, 7, 8, 9]
print(numbers[::2])    # [0, 2, 4, 6, 8] (每隔一个元素)
print(numbers[::-1])   # 反转列表
```

## 修改列表

列表是可变的，因此您可以更改其内容：

```python
fruits = ["苹果", "香蕉", "橙子"]

# 更改元素
fruits[1] = "葡萄"
print(fruits)  # ['苹果', '葡萄', '橙子']

# 添加元素
fruits.append("芒果")        # 添加到末尾
fruits.insert(1, "猕猴桃")   # 在指定位置插入
print(fruits)

# 删除元素
fruits.remove("橙子")        # 按值删除
popped = fruits.pop()        # 删除并返回最后一项
del fruits[0]                # 按索引删除
print(fruits)
```

## 常用列表方法

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]

# 排序
numbers.sort()
print(numbers)  # [1, 1, 2, 3, 4, 5, 6, 9]

# 反转
numbers.reverse()
print(numbers)  # [9, 6, 5, 4, 3, 2, 1, 1]

# 计数出现次数
count = numbers.count(1)
print(f"1出现了{count}次")

# 查找索引
index = numbers.index(5)
print(f"5在索引{index}处")

# 扩展（添加多个项目）
numbers.extend([7, 8])
print(numbers)
```

## 列表推导式

以简洁的方式创建列表：

```python
# 传统方式
squares = []
for i in range(10):
    squares.append(i ** 2)

# 列表推导式
squares = [i ** 2 for i in range(10)]
print(squares)

# 带条件
even_squares = [i ** 2 for i in range(10) if i % 2 == 0]
print(even_squares)
```

## 练习：待办事项列表管理器

创建一个简单的待办事项列表应用程序。

### 示例解决方案

```python
def todo_list_manager():
    todos = []

    print("=== 待办事项列表管理器 ===")
    print("命令: 添加, 查看, 完成, 删除, 退出")

    while True:
        command = input("\n请输入命令: ")

        if command == '退出':
            print("再见！")
            break

        elif command == '添加':
            task = input("请输入任务: ")
            if task:
                todos.append({"task": task, "completed": False})
                print(f"已添加: {task}")
            else:
                print("任务不能为空！")

        elif command == '查看':
            if not todos:
                print("您的列表中没有任务！")
            else:
                print("\n您的待办事项列表:")
                for i, todo in enumerate(todos, 1):
                    status = "✓" if todo["completed"] else " "
                    print(f"{i}. [{status}] {todo['task']}")

        elif command == '完成':
            if not todos:
                print("没有任务可完成！")
                continue

            try:
                index = int(input("请输入要完成的任务编号: ")) - 1
                if 0 <= index < len(todos):
                    todos[index]["completed"] = True
                    print(f"已完成: {todos[index]['task']}")
                else:
                    print("无效的任务编号！")
            except ValueError:
                print("请输入有效的数字！")

        elif command == '删除':
            if not todos:
                print("没有任务可删除！")
                continue

            try:
                index = int(input("请输入要删除的任务编号: ")) - 1
                if 0 <= index < len(todos):
                    deleted = todos.pop(index)
                    print(f"已删除: {deleted['task']}")
                else:
                    print("无效的任务编号！")
            except ValueError:
                print("请输入有效的数字！")

        else:
            print("无效命令！")

# 运行管理器
todo_list_manager()
```

## 练习：列表统计

创建一个程序，计算数字列表的统计信息。

### 示例解决方案

```python
def list_statistics():
    print("=== 列表统计计算器 ===")

    # 从用户获取数字
    numbers = []
    print("请输入数字（输入'完成'结束）:")

    while True:
        user_input = input("请输入数字: ")
        if user_input == '完成':
            break
        try:
            numbers.append(float(user_input))
        except ValueError:
            print("无效的数字！请重试。")

    if not numbers:
        print("未输入任何数字！")
        return

    # 计算统计信息
    total = sum(numbers)
    count = len(numbers)
    average = total / count
    minimum = min(numbers)
    maximum = max(numbers)

    # 排序以计算中位数
    sorted_numbers = sorted(numbers)
    if count % 2 == 0:
        median = (sorted_numbers[count//2 - 1] + sorted_numbers[count//2]) / 2
    else:
        median = sorted_numbers[count//2]

    # 显示结果
    print(f"\n=== 统计信息 ===")
    print(f"数量: {count}")
    print(f"总和: {total}")
    print(f"平均值: {average:.2f}")
    print(f"最小值: {minimum}")
    print(f"最大值: {maximum}")
    print(f"中位数: {median}")
    print(f"范围: {maximum - minimum}")

# 运行计算器
list_statistics()
```

## 关键概念

1. **创建列表**：使用方括号`[]`
2. **索引**：按位置访问元素（从0开始）
3. **切片**：提取列表的部分
4. **可变性**：列表创建后可以修改
5. **方法**：内置函数如`append()`、`remove()`、`sort()`
6. **列表推导式**：创建列表的简洁方式

## 练习挑战

1. 创建一个程序，从列表中删除重复项
2. 编写一个函数，查找列表中第二大的数字
3. 创建一个程序，将两个已排序的列表合并为一个已排序的列表
4. 使用列表构建购物车系统
5. 编写一个函数，将列表旋转n个位置
