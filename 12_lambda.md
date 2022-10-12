## Lambda

Lambda adalah fungsi kecil yang bisa dibuat pada variabel. Untuk membuat lambda, kita harus menggunakan `lambda` keyword.

```python
# syntax: (<variable>: identifier, <param>: any, <expression>: any)
# `<variable> = lambda <param>, <param>, ...,<param>: <expression>`
```

```python
lam = lambda x, y: x*y
y = lam(2, 2)
print(y) # 4
```

Yang dimana sama seperti
```python
def lam(x, y):
    return x * y

y = lam(2, 2)
print(y) # 4
```