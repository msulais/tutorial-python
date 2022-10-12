## Scopes

Program selalu berjalan dari atas ke bawah. Karena itu, mendeklarasikan variabel harus di dahulukan sebelum di akses.

```python
x = 10
print(x) # [OK] 10
print(y) # [ERROR] x = ?
y = 3
```

Variabel tidak seluruhnya bisa diakses oleh function atau class lain. Tiap variabel memiliki scope (daerah) sendiri yang bisa diakses.

```python
x = 10
def printLn():
    x = 100 # ini membuat variabel baru
    print(x)

printLn() # 100
print(x) # 10
```

**Penjelasan:**

- Nilai variable `x = 10` tidak berubah, padahal sudah dirubah menjadi `x = 100` di fungsi `printLn()`. Itu karena `x = 100` di dalam fungsi `printLn()` adalah variabel baru (namanya aja yang sama).

### Global Scope (global)

`global` menjadikan variabel dapat diakses dimanapun oleh siapapun secara global.

```python
x = 10
def printLn():
    global x
    x = 100
    print(x)

printLn() # 100
print(x) # 100

def printLn2():
    global y
    y = 99
    print(y)

printLn2() # 99

# mengakses variable meski variable di dalam fungsi
print(y) # 99
```

**Penjelasan:**

- Nilai variable `x` dari `10` berubah menjadi `100` di dalam fungsi `printLn()`. Itu karena `x = 100` di dalam fungsi `printLn()` adalah variable dari `x = 10` berkat bantuan `global x`. Tanpa `global x`, variable `x` di dalam fungsi `printLn()` hanyalah variable baru, bukan dari variable `x = 10`.
- Variable baru `y = 99` yang ada di dalam fungsi `printLn2()` bisa diakses diluar fungsi berkat bantuan `global y`. Tanpa `global y`, variable `y` tidak akan bisa diakses diluar fungsi.

### NonLocal Scope (nonlocal)

`nonlocal` digunakan untuk menggunakan variabel lokal dapat diakses inner function.

```python
# tanpa nonlocal
def myfun1():
  x = "A"

  # inner function
  def myfun2():
    x = "B"

  myfun2() # memanggil fungsi untuk merubah variable `x`
  return x

print(myfun1()) # A
```

**Penjelasan:**

- Nilai variable `x = "A"` tidak berubah menjadi `"B"`, padahal `x = "B"` yang ada di fungsi `myfun2()` sudah dipanggil.

```python
# dengan nonlocal
def myfunc1():
  x = "A"

  # inner function
  def myfunc2():
    nonlocal x
    x = "B"

  myfunc2() # memanggil fungsi untuk merubah variable `x`
  return x

print(myfunc1()) # B
```

**Penjelasan:**

- Nilai variable `x = "A"` berubah menjadi `"B"` berkat bantuan `nonlocal x` didalam fungsi `myfun2()`.