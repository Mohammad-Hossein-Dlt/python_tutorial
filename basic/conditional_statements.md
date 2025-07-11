در برنامه‌نویسی، دستورات شرطی برای **تصمیم‌گیری** استفاده می‌شوند. با استفاده از شرط‌ها می‌توان رفتار برنامه را بر اساس مقادیر مختلف تغییر داد.

## دستور `if`

```python
x = 10
if x > 5:
    print("x بزرگتر از ۵ است")
```

⛔ توجه: بعد از if باید **کدهای مربوطه تورفتگی (indentation)** داشته باشند (معمولاً ۴ فاصله یا یک تب).

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

---

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

## ⚖️ عملگرهای مقایسه‌ای

| عملگر | توضیح           | مثال      |
| ----- | --------------- | --------- |
| `==`  | مساوی           | `x == 5`  |
| `!=`  | نامساوی         | `x != 3`  |
| `>`   | بزرگتر          | `x > 7`   |
| `<`   | کوچکتر          | `x < 9`   |
| `>=`  | بزرگتر یا مساوی | `x >= 2`  |
| `<=`  | کوچکتر یا مساوی | `x <= 10` |

## 🔗 عملگرهای منطقی

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

---

## تابع `bool()`

برای بررسی اینکه یک مقدار به صورت منطقی **True** یا **False** در نظر گرفته می‌شود.

```python
print(bool(0))      # False
print(bool(5))      # True
print(bool(""))     # False
print(bool("hi"))   # True
```
