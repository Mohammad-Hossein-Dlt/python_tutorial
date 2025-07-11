در پایتون، فایل‌ها با استفاده از تابع `open()` باز می‌شوند. پس از انجام عملیات، باید فایل را ببندیم تا منابع سیستم آزاد شوند.

```python
file = open('example.txt', 'r')
# file operations
file.close()
```

## 📂 حالت‌های مختلف باز کردن فایل

| حالت   | توضیح                                                                   |
| ------ | ----------------------------------------------------------------------- |
| `'r'`  | فقط خواندن (پیش‌فرض)                                                    |
| `'w'`  | فقط نوشتن (اگر فایل وجود نداشته باشد ساخته می‌شود، اگر باشد پاک می‌شود) |
| `'a'`  | فقط افزودن به انتهای فایل (append)                                      |
| `'x'`  | ساخت فایل جدید (اگر فایل وجود داشته باشد خطا می‌دهد)                    |
| `'b'`  | حالت باینری (برای تصاویر، ویدیو،...)                                    |
| `'t'`  | حالت متنی (پیش‌فرض)                                                     |
| `'r+'` | خواندن و نوشتن همزمان                                                   |

---

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

---

## نوشتن در فایل

### بازنویسی کامل فایل (`w`)

```python
with open('output.txt', 'w') as file:
    file.write("Hello, world!\n")
```

---

## افزودن محتوا به فایل (`a`)

```python
with open('output.txt', 'a') as file:
    file.write("This is an appended line.\n")
```

---

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
