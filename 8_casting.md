## Casting

Python dapat merubah suatu data menjadi tipe data lain menggunakan built-in function.

### str() -> str

Untuk mengubah data ke dalam bentuk string. Untuk parameternya bisa untuk semua jenis tipe data.

```python
integer = 90
floating = 0.45
dictionary = {'a': 0, 'b': 3}
myList = ['a', 'b', 'c']
mySet = {'a', 'b', 'c'}
myTuple = {'a', 'b', 'c'}
boolean = True
print(
  str(integer), str(floating), str(dictionary),
  str(myList), str(mySet), str(myTuple), str(boolean)
)
# output:
# 90 0.45 {'a': 0, 'b': 3} ['a', 'b', 'c'] {'b', 'a', 'c'} {'b', 'a', 'c'} True
```

### int() -> int

Untuk mengubah data ke dalam bentuk integer. Untuk parameternya hanya tipe data ***str***, ***int***, dan ***float***.

```python
string = '94'
floating = 9.87
print(int(string), int(floating)) # 94 9
```

Jika di dalam string terdapat karakter lain selain angka atau karakter yang tidak berhubungan dengan integer, maka akan error.

```python
string = '94abc'
print(int(string)) # [ERROR]
```

### float() -> float

Untuk mengubah data ke dalam bentuk float. Untuk parameternya hanya tipe data ***str***, ***int***, dan ***float***.

```python
string = '94.9'
integer = 9
print(float(string), float(integer)) # 94.9 9.0
```

Jika di dalam string terdapat karakter lain selain angka atau karakter yang tidak berhubungan dengan float, maka akan error.

```python
string = '98.1324e-10'
print(string) # [OK] 98.1324e-10
string = '9.4abc'
print(float(string)) # [ERROR]
```

### bool() -> bool

Untuk mengubah data ke dalam bentuk boolean.

```python
string = '0'
integer = 0
floating = 0.0
print(bool(string), bool(integer), bool(floating)) # True False False
```

### list() -> list

Untuk mengubah data ke dalam bentuk list. Untuk parameternya hanya tipe data ***str***, ***list***, ***tuple***, ***set***, ***dict***, atau iterable objek lainnya.

```python
string = "100"
dictionary = {'a': 0, 'b': 3}
myList = ['a', 'b', 'c']
mySet = {'a', 'b', 'c'}
myTuple = {'a', 'b', 'c'}

print(list(string), list(dictionary), list(mySet), list(myTuple))
# output:
# ['1', '0', '0'] ['a', 'b'] ['a', 'c', 'b'] ['a', 'c', 'b']
```

### tuple() -> tuple

Untuk mengubah data ke dalam bentuk tuple. Untuk parameternya hanya tipe data ***str***, ***list***, ***tuple***, ***set***, ***dict***, atau iterable objek lainnya.

```python
string = "100"
dictionary = {'a': 0, 'b': 3}
myList = ['a', 'b', 'c']
mySet = {'a', 'b', 'c'}
myTuple = {'a', 'b', 'c'}

print(tuple(string), tuple(dictionary), tuple(myList), tuple(mySet))
# output:
# ('1', '0', '0') ('a', 'b') ('a', 'b', 'c') ('a', 'c', 'b')
```

### set() -> set

Untuk mengubah data ke dalam bentuk set. Untuk parameternya hanya tipe data ***str***, ***list***, ***tuple***, ***set***, ***dict***, atau iterable objek lainnya.

```python
string = "100"
dictionary = {'a': 0, 'b': 3}
myList = ['a', 'b', 'c']
mySet = {'a', 'b', 'c'}
myTuple = {'a', 'b', 'c'}

print(set(string), set(dictionary), set(myList), set(myTuple))
# output:
# {'1', '0'} {'a', 'b'} {'a', 'c', 'b'} {'a', 'c', 'b'}
```