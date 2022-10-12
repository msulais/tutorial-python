## Classes

`class` digunakan untuk membuat objek (Instance) baru atau sebagai pengelompokan dari variable-variable dan fungsi-fungsi saja.

```python
# syntax: (<name>: identifier, <members>: function | variable | class, <parent_class>: class)
# `class <name>:
#   <members>
# `
# `class <name>(<parent_class>):
#   <members>
# `
```

```python
# Penggunaan class untuk mengelompokkan variabel-variabel & fungsi-fungsi & class-class
class Koordinat:
    x = 10
    y = 7
    def add(x:float, y:float) -> float:
        return x + y
    def substract(x:float, y:float) -> float:
        return x - y

k = Koordinat() # membuat objek dengan tipe data: Koordinat
print(k.y) # 7
print(k.add(10, 5)) # 15
print(Koordinat.add(10, 5)) # 15 (tidak membuat objek Koordinat, hanya mengakses fungsi)
print(Koordinat.x) # 10 (tidak membuat objek Koordinat, hanya mengakses variabel)
```

### Constructor

Constructor adalah fungsi `class` spesial yang selalu dipanggil pertama kali ketika membuat objek. Setiap `class` pasti memiliki fungsi `__init__()` di dalamnya meskipun tidak ditulis secara manual. Fungsi `__init__()` digunakan sebagai **constructor `class`**. Jika ingin membuat objek dengan argumen tertentu, maka pasang parameter pada fungsi ini.

```python
class Koordinat:
    def __init__(self, x=0, y=0) -> None:
        self.other_x = x
        self.other_y = y
        print('init')

    def __str__(self) -> str:
        return f"Koordinat(x: {self.other_x}, y: {self.other_y})"

koor1 = Koordinat()
koor2 = Koordinat(10, 2)
print(koor1)
print(koor2)

# output:
# init
# init
# Koordinat(x: 0, y: 0)
# Koordinat(x: 10, y: 2)
```

**Penjelasan:**

- `koor1 = Koordinat()` dan `koor2 = Koordinat(10, 2)` akan memanggil fungsi `__init__()` dan menjalankan `print('init')`.
- Argumen dari `Koordinat(10, 2)` akan masuk ke `__init__(self, x=0, y=0)`, dimana `x` akan menjadi `10` dan `y` akan menjadi `2`. Parameter `self` akan diabaikan.
- Fungsi `__str__(self)` juga termasuk fungsi class spesial sama seperti `__init__()`. Fungsi class spesial ada banyak sebenarnya dan setiap fungsi class spesial memiliki kegunaan khusus. Fungsi `__str__(self)` digunakan agar ketika hendak print `class` dengan fungsi `print()` dapat mendapatkan hasil yang sesuai.

Setiap fungsi dari `class` yang diberi parameter `self` disebut "class method" atau "method". Untuk penjelasan class method akan dibahas nanti. self berarti objek itu sendiri (mirip seperti `this` pada bahasa pemrograman lain). Jika class objek memiliki variabel tersendiri (contoh: self.x = 0), maka mengaksesnya juga harus menggunakan self.

### Destructor

Destructor adalah kebalikan dari constructor. Jika constructor dipanggil pertama kali, maka destructor dipanggil terakhir kali ketika objek tidak digunakan lagi. Ingat, kita bisa menghapus objek menggunakan `del` keyword. Ketika itu terjadi maka fungsi class spesial `__del__()` akan terpanggil dari class.

```python
class Koordinat:
    def __init__(self, x=0, y=0) -> None:
        self.other_x = x
        self.other_y = y

    def __del__(self):
        print('Objek dihancurkan')

koor1 = Koordinat()
del koor1

# output:
# Objek dihancurkan
```

### Methods

Pada contoh-contoh sebelumnya, ada beberapa fungsi class yang menggunakan parameter `self`. Fungsi yang menggunakan parameter `self` adalah method. Method adalah fungsi khusus untuk objek. Parameter `self`, tidak memerlukan argumen, jadi argumen untuk `self` akan digunakan oleh parameter selanjutnya.

```python
class Koordinat:
    def __init__(self, x=0, y=0) -> None:
        self.other_x = x
        self.other_y = y

    def add(self, x, y):
        self.other_x += x
        self.other_y += y

    def __str__(self) -> str:
        return f'Koordinat(x: {self.other_x}, y: {self.other_y})'

koor1 = Koordinat(2, 3)
koor2 = Koordinat(10, 3)
print(koor1) # Koordinat(x: 2, y: 3)
print(koor2) # Koordinat(x: 10, y: 3)

koor1.add(3, 3) # tidak ada argumen untuk self
print(koor1) # Koordinat(x: 5, y: 6)
print(koor2) # Koordinat(x: 10, y: 3)
```

### Special methods (fungsi class spesial)

Setiap class memiliki special method yang hanya digunakan pada saat tertentu. Contohnya pada contoh diatas terdapat `__init__()`, `__str__()`, dan `__del__()`. Ada pula special method untuk operator seperti `__add__()` untuk mendukung operator `+`, atau `__sub__()` untuk mendukung operator `-`. Ada banyak sekali special method pada class yang bisa kita implementasikan sesuai keinginan.

```python
class Koordinat:
    def __init__(self, x=0, y=0) -> None:
        self.other_x = x
        self.other_y = y

    def __add__(self, other):
        return Koordinat(self.other_x + other.other_x, self.y + other.other_y)

    def __str__(self) -> str:
        return f'Koordinat(x: {self.other_x}, y: {self.other_y})'

koor1 = Koordinat(2, 3)
koor2 = Koordinat(10, 3)
koor3 = koor1 + koor2 # menggunakan __add__() method
print(koor3) # Koordinat(x: 12, y: 6) (menggunakan __str__() method)
```

### Inheritance

Setelah mempelajari cara membuat objek dari class, sekarang bagaimana caranya menggabungkan objek dengan objek lain. Contoh:

```
Hewan [Objek]
├─ Kepala [Objek]
├─ Tangan [Objek]
├─ Badan [Objek]
├─ ...
└─ Kaki [Objek]
```

Inheritance dapat membuat objek bergabung dengan objek lain

```python
class A:
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek A -> {name}')

class B(A): # objek A didalam objek B. A = parent class dari B
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek B -> {name}')
        A.__init__(self, name)

class C(B): # objek B didalam objek C. B = parent class dari C
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek C -> {name}')
        B.__init__(self, name)

x = C('Laptop')
# output:
# Objek C -> Laptop
# Objek B -> Laptop
# Objek A -> Laptop
```

Gunakan fungsi `super()` jika ingin lebih simpel dalam mengakses parent class.

```python
class A:
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek A -> {name}')

class B(A):
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek B -> {name}')
        super().__init__(name) # sama seperti A.__init__(name)

class C(B):
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek C -> {name}')
        super().__init__(name) # sama seperti B.__init__(name)

x = C('Laptop')

# output:
# Objek C -> Laptop
# Objek B -> Laptop
# Objek A -> Laptop
```

Seperti ini juga tak apa. Hanya saja fungsi `super()` hanya akan mengambil dari objek terdepan argumen.

```python
class C(B, A):
    def __init__(self, name) -> None:
        self.name = name
        print(f'Objek C -> {name}')
        super().__init__(name) # sama seperti B.__init__(name)
```