## Fungsi

Fungsi (sama seperti istilah fungsi dalam matematika) digunakan untuk membuat program khusus yang bisa dipanggil berkali-kali. Fungsi dalam python diawali dengan kata `def`.

```python
# syntax: (<name>: identifier, <statements>: any, <param>: any)
# `def <name>():
#   <statements>
# `
# `def <name>(<param>, <param>, ...):
#   <statements>
# `
```

```python
def fungsiku():
    print("Hello, world")

fungsiku() # memanggil fungsi
fungsiku() # memanggil fungsi

# output:
# Hello, world
# Hello, world
```

**Catatan:**

- Saat memanggil fungsi, harus selalu diakhiri `()`.
- Fungsi bisa dipanggil berkali-kali.

### Parameter dan argumen

Fungsi juga bisa mendapatkan data dari luar ketika dipanggil dengan parameter dan argumen. Banyak parameter boleh kosong, satu, atau lebih dari satu. Jumlah parameter dan argumen haruslah sama dan sesuai ***urutannya***.

```python
# `id` dan `nama` adalah parameter (wajib terisi ketika memanggil fungsi)
def login(id, nama):
    print(f"{id}: HALO", nama)

login(0, 'A') # memanggil fungsi (`0` dan `'A'` adalah argumen)
login(1, 'B') # memanggil fungsi (`1` dan `'B'` adalah argumen)

# output:
# 0: Halo A
# 1: Halo B
```

Di bawah ini juga tidak dipermasalahkan. Karena memang pada dasarnya parameter adalah variabel baru yang datanya diambil dari argumen.

```python
def myFungsi(id:int, nama:str):
```

### Default parameter value

Parameter dari fungsi juga bisa memiliki default value sehingga tidak wajib terisi dengan argumen ketika memanggil fungsi.

```python
def someProgram(x, y=''):
    if y == '':
        print(f'Halo {x}')
    else:
        print(f'Halo {x} dan {y}')

someProgram('A')
someProgram('A', 'B')

# output:
# Halo A
# Halo A dan B
```

**Penjelasan:**

- Argumen kedua dari `someProgram('A')` tidak ada, maka akan menggunakan default value dari `y`, yaitu `''`.
- Argumen kedua dari `someProgram('A', 'B')` ada, maka default value akan diganti dengan `'B'`.

### *args dan **kwargs

Sebelumnya, kita harus membuat banyak argumen sama dengan banyak parameter. Tapi bagaimana jika membuat banyak argumen untuk satu parameter? Dengan `*args` dan `**kwargs`, hal seperti itu bisa dilakukan. Lebih tepatnya dengan menaruh `*` atau `**` sebelum nama parameter.

```python
def fun1(x, *y):
    print(x)
    print(y, type(y))

fun1(0, 1, 2, 3, 4, 5)

# output:
# 0
# (1, 2, 3, 4, 5) <class 'tuple'>
```

**Penjelasan:**

- Tipe data `*y` adalah ***tuple***.
- Argumen `0` adalah untuk parameter `x`.
- Argumen `1, 2, 3, 4, 5` adalah untuk parameter `*y`.

```python
def fun2(x, **y):
    print(x)
    print(y, type(y))

fun2(0, satu=1, dua=2, tiga=3)

# output:
# 0
# {'satu': 1, 'dua': 2, 'tiga': 3} <class 'dict'>
```

**Penjelasan:**

- Tipe data `**y` adalah ***dict***.
- Argumen `0` adalah untuk parameter `x`.
- Argumen `satu=1`, dan seterusnya untuk parameter `**y`.
- `satu`, `dua`, `tiga` adalah key untuk dictionary `**y`.
- `1`, `2`, `3` adalah value dari tiap key dari dictionary `**y`.

### Argumen dengan nama parameter

Argumen tidak harus dimasukkan secara urut jika menggunakan nama parameter.

```python
def myFungsi(id, nama):
    print(f"{id}: HALO", nama)

myFungsi(nama='A', id=0) # sama seperti myFungsi(0, 'A')
myFungsi(1, 'B')

# output
# 0: HALO A
# 1: HALO B
```

### Return keyword

Fungsi juga bisa menghasilkan data ketika operasi sudah selesai dengan `return`.

```python
def fun(x, y):
    if x == y:
        return 0 # jika ini dieksekusi, maka program selanjutnya terabaikan
                 # `0` adalah data yang dihasilkan dari fungsi ini
    if x > y:
        return 1
    if x < y:
        return -1

number = fun(10, 2) # data dari `return` akan masuk ke variabel `number`
print(number) # 1
```

Dibawah ini juga bisa untuk memberikan tipe data spesifik pada data dari `return`.

```python
def fun(x, y) -> int:
```

Jika tipe data dari `return` adalah `None`, maka cukup dikosongi setelah `return`.

```python
def fun():
    print('Hello, world')
    return # tipe data dari return adalah None
    print('Ini gak akan dieksekusi')

fun()
print(type(fun()))

# output:
# Hello, world
# <class 'NoneType'>
```
