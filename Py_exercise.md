#### 练习1：英制单位英寸与公制单位厘米互换。
```
    value = float(input('请输入长度: '))
    unit = input('请输入单位: ')
    if unit == 'in' or unit == '英寸':
        print('%f英寸 = %f厘米' % (value, value * 2.54))
    elif unit == 'cm' or unit == '厘米':
        print('%f厘米 = %f英寸' % (value, value / 2.54))
    else:
        print('请输入有效的单位')
```
#### 练习2：百分制成绩转换为等级制成绩。
```
    score = float(input('请输入成绩: '))
    if score >= 90:
        grade = 'A'
    elif score >= 80:
        grade = 'B'
    elif score >= 70:
        grade = 'C'
    elif score >= 60:
        grade = 'D'
    else:
        grade = 'E'
    print('对应的等级是:', grade)
```
#### 练习3：输入三条边长，如果能构成三角形就计算周长和面积。
```
    a = float(input('a = '))
    b = float(input('b = '))
    c = float(input('c = '))
    if a + b > c and a + c > b and b + c > a:
        print('周长: %f' % (a + b + c))
        p = (a + b + c) / 2
        area = (p * (p - a) * (p - b) * (p - c)) ** 0.5
        print('面积: %f' % (area))
    else:
        print('不能构成三角形')
```
#### 练习4：输入一个正整数判断是不是素数。
```
    from math import sqrt

    num = int(input('请输入一个正整数: '))
    end = int(sqrt(num))
    is_prime = True
    for x in range(2, end + 1):
        if num % x == 0:
            is_prime = False
            break
    if is_prime and num != 1:
        print('%d是素数' % num)
    else:
        print('%d不是素数' % num)
```
#### 练习5：输入两个正整数，计算它们的最大公约数和最小公倍数。
两个数的最大公约数是两个数的公共因子中最大的那个数；两个数的最小公倍数则是能够同时被两个数整除的最小的那个数。
```
    x = int(input('x = '))
    y = int(input('y = '))
    # 如果x大于y就交换x和y的值
    if x > y:
        # 通过下面的操作将y的值赋给x, 将x的值赋给y
        x, y = y, x
    # 从两个数中较的数开始做递减的循环
    for factor in range(x, 0, -1):
        if x % factor == 0 and y % factor == 0:
            print('%d和%d的最大公约数是%d' % (x, y, factor))
            print('%d和%d的最小公倍数是%d' % (x, y, x * y // factor))
            break
```
#### 练习6：打印如下所示的三角形图案。
    *
    **
    ***
    ****
    *****
        *
    **
    ***
    ****
    *****
        *
    ***
    *****
    *******
    *********
```
    row = int(input('请输入行数: '))
    for i in range(row):
        for _ in range(i + 1):
            print('*', end='')
        print()


    for i in range(row):
        for j in range(row):
            if j < row - i - 1:
                print(' ', end='')
            else:
                print('*', end='')
        print()

    for i in range(row):
        for _ in range(row - i - 1):
            print(' ', end='')
        for _ in range(2 * i + 1):
            print('*', end='')
        print()
```