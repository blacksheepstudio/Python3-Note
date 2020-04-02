# 1.2 字符串
### 简介
在Python程序中，如果我们把单个或多个字符用单引号或者双引号包围起来，就可以表示一个**字符串**。
```python
s1 = 'hello, world!'
s2 = "hello, world!"
# 以三个双引号或单引号开头的字符串可以折行
s3 = """
hello, 
world!
"""
print(s1, s2, s3)
```
### 格式化输出
**整数**
```python
# %d
print('love = %d' % 520)
# love = 520
```
**浮点数** 
```python
# %f
print('π = %.5f' % 3.1415926)
# π = 3.14159
```
**字符串** 
```python
# %s
print('Hello %s!' % 'Black Sheep')
# Hello Black Sheep!
```
**format() 方法**
```python
print('我是 {}我的手机号是 {}!'.format('knights', 'Ni'))
```

**自动换行**
print 会自动在行末加上回车，如果不需要回车可以对end赋值使end值为空，这个换行就消除了。
```python
print('Hello ',end='')
print('world!')
#Hello world!
```
### 为什么Python支持两种引号
```python
#单引号作用
print('Black Sheep:“Hello world!”')
#Black Sheep:“Hello world!”

#双引号作用
print("Let's Python!")
#Let's Python!

#混合输出使用\转意符
print('Black sheep:"Let\'s Python!"')
#Black sheep:"Let's Python!"
```

