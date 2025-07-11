# دستورات شرطی

در برنامه‌نویسی، دستورات شرطی برای **تصمیم‌گیری** استفاده می‌شوند. با استفاده از شرط‌ها می‌توان رفتار برنامه را بر اساس مقادیر مختلف تغییر داد.

## دستور `if`

```python
x = 10
if x > 5:
    print("x بزرگتر از ۵ است")
```

توجه: بعد از if باید **کدهای مربوطه تورفتگی (indentation)** داشته باشند (معمولاً ۴ فاصله یا یک تب).

## دستور `if-else`

```python
x = 3
if x > 5:
    print("x بزرگتر از ۵ است")
else:
    print("x کوچکتر یا مساوی ۵ است")
```

---

## دستور `if-elif-else`

```python
grade = 17

if grade >= 18:
    print("عالی")
elif grade >= 14:
    print("خوب")
elif grade >= 10:
    print("قابل قبول")
else:
    print("مردود")
```

از `elif` برای چندین شرط پشت سر هم استفاده می‌شود.

از `elif` می‌توان چند بار استفاده کرد، ولی `else` فقط یک‌بار و در انتها می‌آید.

## شرط‌های تو در تو (Nested if)

```python
x = 10
if x > 0:
    if x % 2 == 0:
        print("x عددی مثبت و زوج است")
    else:
        print("x عددی مثبت و فرد است")
else:
    print("x صفر یا منفی است")
```

## عملگرهای مقایسه‌ای

| عملگر | توضیح           | مثال      |
| ----- | --------------- | --------- |
| `==`  | مساوی           | `x == 5`  |
| `!=`  | نامساوی         | `x != 3`  |
| `>`   | بزرگتر          | `x > 7`   |
| `<`   | کوچکتر          | `x < 9`   |
| `>=`  | بزرگتر یا مساوی | `x >= 2`  |
| `<=`  | کوچکتر یا مساوی | `x <= 10` |

## عملگرهای منطقی

| عملگر | کاربرد | مثال               |
| ----- | ------ | ------------------ |
| `and` | و      | `x > 5 and x < 10` |
| `or`  | یا     | `x < 5 or x > 15`  |
| `not` | نقیض   | `not x > 5`        |

## دستور شرطی کوتاه (Inline if)

```python
x = 10
result = "even" if x % 2 == 0 else "odd"
print(result)
```

## تابع `bool()`

برای بررسی اینکه یک مقدار به صورت منطقی **True** یا **False** در نظر گرفته می‌شود.

```python
print(bool(0))      # False
print(bool(5))      # True
print(bool(""))     # False
print(bool("hi"))   # True
```

# حلقه‌های تکرار در پایتون

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

# ساختارهای داده در پایتون

## لیست (List)

### تعریف:

```python
my_list = [20, 10, 40, 30]
```

### توابع و عملیات مهم:

| تابع / عملیات  | توضیح                                                           | مثال                                             |
| -------------- | --------------------------------------------------------------- | ------------------------------------------------ |
| `append(x)`    | اضافه کردن عنصر به انتهای لیست                                  | `my_list.append(50)` → `[20, 10, 40, 30, 50]`    |
| `insert(i, x)` | اضافه کردن عنصر `x` در موقعیت `i`                               | `my_list.insert(1, 15)` → `[20, 15, 10, 40, 30]` |
| `remove(x)`    | حذف اولین تکرار از عنصر `x`                                     | `my_list.remove(20)` → `[10, 40, 30]`            |
| `pop([i])`     | حذف و بازگرداندن عنصر با ایندکس `i` (اگر مشخص نشود، آخرین عنصر) | `my_list.pop()` → `[20, 10, 40]`                 |
| `clear()`      | حذف همه عناصر لیست                                              | `my_list.clear()` → `[]`                         |
| `index(x)`     | بازگرداندن اندیس اولین تکرار از `x`                             | `my_list.index(30)` → `2`                        |
| `count(x)`     | تعداد تکرار `x` در لیست                                         | `my_list.count(10)` → `1`                        |
| `sort()`       | مرتب‌سازی لیست (صعودی)                                          | `my_list.sort()` → `[10, 20, 30, 40]`            |
| `reverse()`    | معکوس کردن ترتیب لیست                                           | `my_list.reverse()` → `[30, 40, 10, 20]`         |
| `len(list)`    | اندازه لیست                                                     | `len(my_list)` → `4`                             |
| `in`           | بررسی وجود یک مقدار در لیست                                     | `20 in my_list` → `True`                         |

## تاپل (Tuple)

### تعریف:

```python
my_tuple = (1, 2, 3, 2)
```

### توابع و عملیات مهم:

| تابع / عملیات | توضیح                 | مثال                       |
| ------------- | --------------------- | -------------------------- |
| `count(x)`    | تعداد تکرار مقدار `x` | `my_tuple.count(2)` → `2`  |
| `index(x)`    | اولین اندیس مقدار `x` | `my_tuple.index(3)` → `2`  |
| `len(tuple)`  | تعداد عناصر           | `len(my_tuple)` → `4`      |
| `in`          | بررسی وجود مقدار      | `2 in my_tuple` → `True`   |
| `slicing`     | دسترسی به زیربخش‌ها   | `my_tuple[1:3]` → `(2, 3)` |

چون تاپل **غیرقابل‌تغییر** است، توابعی مثل `append` یا `remove` ندارد.

## دیکشنری (Dictionary)

### تعریف:

```python
my_dict = {"name": "Ali", "age": 25}
```

### توابع و عملیات مهم:

| تابع / عملیات | توضیح                               | مثال                                                                                  |
| ------------- | ----------------------------------- | ------------------------------------------------------------------------------------- |
| `get(key)`    | دسترسی ایمن به مقدار یک کلید        | `my_dict.get("name")` → `Ali`                                                         |
| `keys()`      | دریافت لیست کلیدها                  | `my_dict.keys()` → `["name", "age"]`                                                  |
| `values()`    | دریافت لیست مقادیر                  | `my_dict.values()` → `["Ali", "25"]`                                                  |
| `items()`     | دریافت لیست زوج‌های (کلید، مقدار)   | `my_dict.items()` → `[('name', 'Ali'), ('age', 25)]`                                  |
| `update({})`  | به‌روزرسانی یا افزودن مقدار         | `my_dict.update({"city": "Tehran"})` → `{'name': 'Ali', 'age': 25, 'city': 'Tehran'}` |
| `pop(key)`    | حذف کلید و مقدار و بازگرداندن مقدار | `my_dict.pop("age", None)` → `{'name': 'Ali', 'city': 'Tehran'}`                      |
| `popitem()`   | حذف آخرین جفت (کلید، مقدار)         | `my_dict.popitem()` → `{'name': 'Ali', 'age': 25}`                                    |
| `clear()`     | حذف همه کلیدها و مقادیر             | `my_dict.clear()` → `{}`                                                              |
| `in`          | بررسی وجود یک کلید                  | `"name" in my_dict` → `True`                                                          |

## رشته (String)

### تعریف:

```python
text = "Python is great"
```

### توابع و عملیات مهم:

| تابع / عملیات       | توضیح                         | مثال                                                        |
| ------------------- | ----------------------------- | ----------------------------------------------------------- |
| `upper()`           | حروف بزرگ                     | `text.upper()` → `"PYTHON IS GREAT"`                        |
| `lower()`           | حروف کوچک                     | `text.lower()` → `"python is great"`                        |
| `title()`           | اولین حرف بزرگ                | `text.title()` → `"Python Is Great"`                        |
| `strip()`           | حذف فاصله‌ها از ابتدا و انتها | `" hello ".strip()` → `"hello"`                             |
| `replace(old, new)` | جایگزینی                      | `text.replace("great", "awesome")` → `"Python is awesome"`  |
| `find(sub)`         | پیدا کردن اندیس اولین وقوع    | `text.find("is")` → `7`                                     |
| `split()`           | تبدیل به لیست با جداکننده     | `text.split()` → `"['Python', 'is', 'great']"`              |
| `join(list)`        | اتصال لیست به رشته            | `" ".join(["Python", "is", "great"])` → `"Python is great"` |
| `len(text)`         | طول رشته                      | `len(text)` → `15`                                          |
| `slicing`           | دسترسی به بخشی از رشته        | `text[0:6]` → `"Python"`                                    |

## نکات تکمیلی کلی

| تابع عمومی                             | توضیح                |
| -------------------------------------- | -------------------- |
| `len()`                                | اندازه ساختار        |
| `type()`                               | نوع داده             |
| `del`                                  | حذف عنصر یا کل متغیر |
| `in`                                   | بررسی وجود یک مقدار  |
| `for`                                  | پیمایش اعضای ساختار  |
| `list()`, `set()`, `tuple()`, `dict()` | تبدیل بین ساختارها   |

### `len()`

**کاربرد:** محاسبه طول (تعداد عناصر)

```python
my_list = [10, 20, 30]
print(len(my_list))
```

#### خروجی:

```
3
```

### `type()`

**کاربرد:** تشخیص نوع داده

```python
my_dict = {"name": "Ali"}
print(type(my_dict))
```

#### خروجی:

```
<class 'dict'>
```

### `del`

**کاربرد:** حذف عنصر یا کل متغیر

```python
my_list = [1, 2, 3]
del my_list[1]
print(my_list)

del my_list
```

#### خروجی:

```
[1, 3]
```

### `in`

**کاربرد:** بررسی وجود مقدار در ساختار

```python
colors = ["red", "green", "blue"]
print("green" in colors)
```

#### خروجی:

```
True
```

### `for`

**کاربرد:** پیمایش اعضا در ساختارهای تکرارپذیر

```python
names = ["Ali", "Sara", "Reza"]
for name in names:
    print(name)
```

#### خروجی:

```
Ali
Sara
Reza
```

### تبدیل نوع داده (`list()`, `set()`, `tuple()`, `dict()`)

**کاربرد:** تبدیل بین ساختارهای داده

#### تبدیل لیست به مجموعه:

```python
numbers = [1, 2, 2, 3]
unique_numbers = set(numbers)
print(unique_numbers)
```

#### خروجی:

```
{1, 2, 3}
```

#### تبدیل دیکشنری به لیست کلیدها:

```python
info = {"name": "Sara", "age": 22}
keys_list = list(info)
print(keys_list)
```

#### خروجی:

```
['name', 'age']
```

#### تبدیل لیست جفت‌ها به دیکشنری:

```python
pairs = [("name", "Ali"), ("age", 30)]
d = dict(pairs)
print(d)
```

#### خروجی:

```
{'name': 'Ali', 'age': 30}
```

# کار با فایل ها

در پایتون، فایل‌ها با استفاده از تابع `open()` باز می‌شوند. پس از انجام عملیات، باید فایل را ببندیم تا منابع سیستم آزاد شوند.

```python
file = open('example.txt', 'r')
# file operations
file.close()
```

## حالت‌های مختلف باز کردن فایل

| حالت   | توضیح                                                                   |
| ------ | ----------------------------------------------------------------------- |
| `'r'`  | فقط خواندن (پیش‌فرض)                                                    |
| `'w'`  | فقط نوشتن (اگر فایل وجود نداشته باشد ساخته می‌شود، اگر باشد پاک می‌شود) |
| `'a'`  | فقط افزودن به انتهای فایل (append)                                      |
| `'x'`  | ساخت فایل جدید (اگر فایل وجود داشته باشد خطا می‌دهد)                    |
| `'b'`  | حالت باینری (برای تصاویر، ویدیو،...)                                    |
| `'t'`  | حالت متنی (پیش‌فرض)                                                     |
| `'r+'` | خواندن و نوشتن همزمان                                                   |

## خواندن از فایل

### خواندن کل محتوا

```python
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```

### خواندن خط به خط

```python
with open('example.txt', 'r') as file:
    for line in file:
        print(line.strip())
```

### خواندن یک خط

```python
line = file.readline()
```

### خواندن به صورت لیست خطوط

```python
lines = file.readlines()
```

## نوشتن در فایل

### بازنویسی کامل فایل (`w`)

```python
with open('output.txt', 'w') as file:
    file.write("Hello, world!\n")
```

## افزودن محتوا به فایل (`a`)

```python
with open('output.txt', 'a') as file:
    file.write("This is an appended line.\n")
```

## استفاده از `with`

استفاده از `with` باعث می‌شود فایل به صورت خودکار پس از پایان بلاک بسته شود.

```python
with open('example.txt', 'r') as file:
    print(file.read())
```

## کار با فایل‌های CSV

### نوشتن CSV

```python
import csv

with open('data.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerow(['name', 'age'])
    writer.writerow(['Ali', 23])
```

### خواندن CSV

```python
with open('data.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```
