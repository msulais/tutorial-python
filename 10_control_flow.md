## Control flow

### if, elif, else statement

`if`, `elif`, `else` statement digunakan untuk mengatur jalannya code.

```python
# Syntax: (<conditions>: bool, <statements>: any)
# `if <conditions>:
#    <statements>
# `
# `elif <conditions>:
#    <statements>
# `
# `else:
#    <statements>
# `
```

```python
x = 10
y = 100

if x < y:
   print(f'{x} kurang dari {y}') # statement
elif x == y:
   print(f'{x} sama dengan {y}') # statement
   print(f'{x} sama dengan {y}') # statement
elif x == 11:
   print(f'{x} sama dengan 11') # statement
   print(f'{x} sama dengan 11') # statement
   print(f'{x} sama dengan 11') # statement
else:
   print(f'{x} lebih dari y') # statement

print("SELESAI")

# Output:
# 10 kurang dari 100
# SELESAI
```

**Catatan:**

- `if` artinya "jika".
- `elif` = **else if** artinya "selainnya jika".
- `else` artinya "selainnya".
- Banyak statement setelah `if`, `elif`, `else` boleh lebih dari satu.
- `if` harus berada paling atas.
- `elif` harus setelah `if`. Penggunaan `elif` boleh lebih dari sekali. `elif` tidak wajib.
- `else` harus berada paling bawah dari `if` dan `elif`. `else` tidak wajib.
- Kondisi dari `if` dan `elif` boleh berbentuk apapun yang kalian mau selama hasilnya bool (`True` atau `False`). Artinya, seperti

  `if someFunctionThatReturnBool():`,

  `elif True:`,

  `if 10 < x or x > 0 and y == "some":`,

  `elif 10 + 8.2 > 10:`,

  atau bentuk lainnya tidak akan dipermasalahkan selama hasilnya bool (`True` atau `False`).

**Ingat:**

- `<`, `==` termasuk [Comparison Operator (Operator Perbandingan)](#comparison-operators).
- Setelah `:`, baris selanjutnya harus di beri [indent](#indentation).
- `if`, `elif`, dan `else` juga termasuk statement. Artinya, seperti

  ```python
  if condition:
    if condition2:
      if condition3:
        # statements
      elif condition4:
        # statements
    else:
      # statements
    # statements
  ```

  tidak masalah.

**Penjelasan:**

```python
if x < y:
   print(f'{x} kurang dari {y}') # statement
```

- `if x < y:` selalu dijalankan pertama kali dan statement akan dijalankan jika `x < y` menghasilkan `True`

```python
if x < y:
   print(f'{x} kurang dari {y}')
elif x == y:
   print(f'{x} sama dengan {y}') # statement
   print(f'{x} sama dengan {y}') # statement
```
- `elif x == y:` akan dijalankan jika `x < y` dari `if` menghasilkan `False`. Dan statement akan dijalankan jika `x < y` menghasilkan `True`.

```python
elif x == y:
   print(f'{x} sama dengan {y}')
   print(f'{x} sama dengan {y}')
elif x == 11:
   print(f'{x} sama dengan 11') # statement
   print(f'{x} sama dengan 11') # statement
   print(f'{x} sama dengan 11') # statement
```

- `elif x == 11:` akan dijalankan jika `x == y` dari `elif` sebelumnya menghasilkan `False`. Dan statement akan dijalankan jika `x == 11` menghasilkan `True`.

```python
else:
   print(f'{x} lebih dari y') # statement
```

- `else:` akan dijalankan jika kondisi dari semua `elif` dan `if` menghasilkan `False`. Dan statement akan dijalankan.

### Match case statement

`match case` statement hampir mirip dengan `switch case` statement pada bahasa pemrograman lain. `match case` statement digunakan untuk mempermudah dalam mencocokkan data tanpa banyak menggunakan `if`, `elif`, `else`. Contoh,

```python
x = 3
if x == 1 or x == 2:
    # statements
elif x == 3:
    # statements
else:
    # statements
```

Dan jika menggunakan `match case` statement, maka akan menjadi seperti ini

```python
# syntax: (<var>: any, <value>: any, <statements>: any)
# `match <var>:
#    case <value1>:
#       <statements>
#    case <value2>:
#       <statements2>
#    case ...:
#       ...
# `
```

```python
x = 3
match x:
    case 1 | 2:
        # statements
    case 3:
        # statements
    case _: # sama seperti else
        # statements
```

**Ingat:**

- `or` termasuk [Logical Operator](#logical-operators).

### For loop statement

`for` loop digunakan untuk melakukan perulangan pada program dengan batasan index pada suatu `Iterable` objek.

**Ingat:**

- [***str***](#karakter-str), [***list***](#iterable-list-tuple-set), [***set***](#iterable-list-tuple-set), dan [***tuple***](#iterable-list-tuple-set) termasuk `Iterable` objek.

```python
# syntax: (<iterable>: Iterable, <new_variable>: identifier, <statements>: any)
# `for <new_variable> in <iterable>:
#    <statements>
# `
```

```python
for i in range(3): # `range()` = Iterable[range]
    print(i)
print('end')
# output:
# 0
# 1
# 2
# end
```

```python
for i in ['a', 'b', 'c']: # `[...]` = Iterable[list]
    print(i)
print('end')
# output:
# a
# b
# c
# end
```

```python
for item in {1,2,3,4,5,3}: # `{...}` = Iterable[set]
    print(item)
print('end')
# output:
# 1
# 2
# 3
# 4
# 5
# end
```

```python
for a in ('a', 'b', 'c'): # `(...)` = Iterable[tuple]
    print(a)
print('end')
# output:
# a
# b
# c
# end
```

```python
for char in 'Python': # `'...'` = Iterable[str]
    print(char)
print('end')
# output:
# P
# y
# t
# h
# o
# n
# end
```

```python
for var in range(3):
    print("Hello, world") # statement
print('end')
# output:
# Hello, world
# Hello, world
# Hello, world
# end
```

**Catatan:**

- `in` pada for loop bukan termasuk [Membership operators](#membership-operators).

**Ingat**:

- `for` loop juga termasuk statement. Artinya, seperti

  ```python
  for i in range(10):
    for j in range(22):
      for k in range(3):
        # statements
      # statements
  ```

  tidak masalah.

**Penjelasan**:

```python
for i in ['a', 'b', 'c']:
    print(i) # statement
```

- `i` adalah variable baru yang merupakan item dari `['a', 'b', 'c']`. Artinya `i` = `'a'`, `'b'`, `'c'`.
- Banyak perulangan sama dengan banyak item dari iterable. Artinya `print(i)` akan terus dijalankan selama 3x. 3 itu dari panjang `['a', 'b', 'c']`. Untuk mempermudah, gunakan fungsi `range()` untuk banyak perulangannya.

`for` loop juga dapat digunakan sebagai iterable objek generator.

```python
# syntax: (<iterable>: Iterable, <new_variable>: identifier, <expression>: any)
# `[ <expression> for <new_variable> in <iterable> ]`
# `{ <expression> for <new_variable> in <iterable> }`
# `( <expression> for <new_variable> in <iterable> )`
```

```python
a = [i for i in range(10)]
print(a) # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

b = {item*2 for item in range(3)}
print(b) # {0, 2, 4}

c = ['a' for i in range(3)]
print(c) # ['a', 'a', 'a']
```

### while loop

Fungsi dari `while` loop sama seperti `for` loop. Yang membedakan yaitu, `while` loop memerlukan syarat/kondisi yang mengharuskan untuk mengulang program.

```python
# syntax: (<conditions>: bool, <statements>: any)
# `while <conditions>:
#    <statements>
# `
```

```python
x = 0
while x < 5: # syarat loop
    x += 1
    print(x, end=', ')

# output:
# 1, 2, 3, 4, 5,
```

**Ingat:**

- `<` termasuk [Comparison Operator (Operator Perbandingan)](#comparison-operators).
- `+=` termasuk [Assignment Operator](#assignment-operators)
- `while` loop juga termasuk statements. Artinya, seperti

  ```python
  while True:
    while y == 'abc':
      # statements
    # statements
  ```

  tidak masalah.

**Penjelasan:**

```python
while x < 5:
    x += 1 # statement
    print(x, end=', ') # statement
```

- Statement akan terus dijalankan selama nilai `x` kurang dari `5`. Jika `x` lebih dari atau sama dengan `5`, maka statement tidak akan dijalankan lagi.

### Continue, break, pass statement
`continue` statement digunakan untuk melanjutkan looping (perulangan). Sedangkan `break` statement sebaliknya, yaitu untuk menghentikan looping.

```python
for i in range(1, 10): # `range(1, 10)` artinya 1, 2, 3, ..., 9
    if i % 4 == 0:
        print(f'Loop berhenti pada index={i}')
        break
    else:
        print(f'index={i}')
        continue

# output:
# index=1
# index=2
# index=3
# Loop berhenti pada index=4
```

***Catatan:***

- `continue` tidak wajib. Karena dengan/tanpa `continue`, program tetap akan berjalan.

**Ingat:**

- `%` termasuk [Arithmetic operator](#arithmetic-operators).

`pass` statement hanya digunakan sebagai minimalisasi dalam mendefinisikan function, class, loop dan lain-lain. Ketika programmer bingung isi dari program yang akan dibuat, maka tinggal menggunakan `pass` statement untuk mencegah error untuk sementara.

```python
# penjelasan `def` akan dibahas nanti.
def myfunction():
    pass # masih gak tau mau diisi apaan, dipasang pass biar gak error aja...

# penjelasan `class` akan dibahas nanti.
class myClass:
    pass

for i in range(10):
    pass
```