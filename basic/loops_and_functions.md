## حلقه‌های تکرار در پایتون

### حلقه `for`

```python
for variable in collection:
    commands
```

#### مثال:

```python
for i in range(5):
    print(i)
```

#### خروجی:

```
0
1
2
3
4
```

#### توضیحات:

- `range(5)` عددهای ۰ تا ۴ را تولید می‌کند.
- می‌توان از بازه‌های دلخواه استفاده کرد: `range(start, end, step)`

#### مثال با گام:

```python
for i in range(10, 0, -2):
    print(i)
```

#### خروجی:

```
10
8
6
4
2
```

### حلقه `while`

```python
while condition:
    commands
```

#### مثال:

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

#### خروجی:

```
0
1
2
3
4
```

---

### دستورات کنترلی در حلقه‌ها

| دستور      | توضیح                      |
| ---------- | -------------------------- |
| `break`    | خروج از حلقه               |
| `continue` | پرش به تکرار بعدی          |
| `pass`     | بدون عمل (برای پر کردن جا) |

#### مثال `break`:

```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

#### خروجی:

```
0
1
2
3
4
```

#### مثال `continue`:

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

#### خروجی:

```
0
1
3
4
```

## توابع در پایتون

### تعریف تابع

```python
def function_name(parameters):
    commands
    return value
```

#### مثال ساده:

```python
def salam(name):
    return "سلام " + name

print(salam("سارا"))
```

#### خروجی:

```
سلام سارا
```

---

### پارامترهای پیش‌فرض

```python
def greet(name="دوست عزیز"):
    print("سلام", name)
```

#### خروجی:

```
سلام دوست عزیز
```

---

### تابع با تعداد نامشخص پارامتر

#### پارامترهای (`*args`):

```python
def sum_numbers(*nums):
    return sum(nums)

print(sum_numbers(1, 2, 3, 4))
```

#### خروجی:

```
10
```

#### پارامترهای (`**kwargs`):

```python
def show_information(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

show_information(name="محمد", age=25, city="تهران")
```

#### خروجی:

```
name: محمد
age: 25
city: تهران
```

---

### توابع بازگشتی (Recursive)

تابعی که خودش را فراخوانی می‌کند.

#### مثال: فاکتوریل

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)

print(factorial(5))
```

#### خروجی:

```
120
```
