## Exceptions handling

Exception handling digunakan untuk mengatasi error pada program.

```python
x = 10
try: # mencoba program
  print(x)
except: # jika terjadi error
  print("ERROR")
else: # jika tidak terjadi error
  print(x, 's')
finally: # jika terjadi error/tidak error
  print(x, 'a')
```
**Catatan:**

- `try` block digunakan untuk tempat untuk mencoba menjalankan program.
- `except` block akan berjalan jika terjadi error pada program di dalam `try` block.
- `else` block akan berjalan jika tidak terjadi error pada `try` block.
- `finally` block akan tetap berjalan, entah ada error atau tidak.
- `try` harus memiliki `except`.
- `except` harus di bawah `try`.
- `else` harus di bawah `except`. `else` disini tidaklah wajib.
- `finally` harus di bawah `except` dan `else` (jika ada). `finally` tidaklah wajib.

### Raise keyword

Kita juga bisa membuat error sendiri dengan `raise` keyword, seperti ini

```python
x = "hello"
if type(x) is not int:
  raise Exception("Bukan int")

# output:
# Traceback (most recent call last):
#  File "...\pyfile.py", line 3, in <module>
#    raise Exception("Bukan int")
# Exception: Only integers are allowed
```