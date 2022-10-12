## Operators

### Arithmetic operators

Aritmatika operator digunakan untuk melakukan operasi yang biasanya berhubungan dengan angka.

| Operator | Nama | Contoh |
| --- | --- | --- |
| `+` | Pertambahan | `x + y` |
| `-` | Pengurangan | `x - y` |
| `*` | Perkalian | `x * y` |
| `/` | Pembagian | `x / y` |
| `%` | Modulus (sisa bagi) | `x % y` |
| `**` | Perpangkatan | `x ** y` |
| `//` | Floor division (hasil bagi) | `x // y` |

Di python, perkalian & pembagian lebih didahulukan daripada pertambahan & pengurangan.

```python
x = 10
y = 8
print(x + y * x) # 90
print((x + y) * x) # 180
```

### Assignment operators

Assignment operator digunakan untuk mempermudah Arithmetic operators dan Bitwise operator.

| Operator | Contoh | Sama seperti |
| --- | --- | --- |
| `=` | `x = 10` | `x = 10` |
| `+=` | `x += 10` | `x = x + 10` |
| `-=` | `x -= 10` | `x = x - 10` |
| `*=` | `x *= 10` | `x = x * 10` |
| `/=` | `x /= 10` | `x = x / 10` |
| `%=` | `x %= 10` | `x = x % 10` |
| `**=` | `x **= 10` | `x = x ** 10` |
| `//=` | `x //= 10` | `x = x // 10` |
| `&=` | `x &= 10` | `x = x & 10` |
| `\|=` | `x \|= 10` | `x = x \| 10` |
| `^=` | `x ^= 10` | `x = x ^ 10` |
| `<<=` | `x <<= 10` | `x = x << 10` |
| `>>=` | `x >>= 10` | `x = x >> 10` |

### Comparison operators

Comparison operator digunakan untuk membandingkan dua data. Hasilnya adalah boolean `True` (jika benar) atau `False` (jika salah).

| Operator | Nama | Contoh |
| --- | --- | --- |
| `==` | Sama dengan | `x == y` |
| `!=` | Tidak sama dengan | `x != y` |
| `>` | Lebih dari | `x > y` |
| `<` | Kurang dari | `x < y` |
| `>=` | Lebih dari atau sama dengan | `x >= y` |
| `<=` | Kurang dari atau sama dengan | `x <= y` |

Python juga mendukung perbandingan seperti  `x < y <= z` yang maksudnya sama dengan `x < y and y <= z`.


### Logical operators

Logical operator digunakan untuk menggabungkan pernyataan (statement).

| Operator | Deskripsi | Contoh
| --- | --- | --- |
| `and` | Menghasilkan `True` jika kedua pernyataan benar. | `x > 9 and y > 10` |
| `or` | Menghasilkan `True` jika salah satu pernyataan benar | `x > 9 or x > 10` |
| `not` | Membalikkan hasil. Jika hasilnya `True`, maka akan menjadi `False`. Begitu pula sebaliknya. | `not(x > 9)` |

### Identify operators

Identify operator digunakan untuk membandingkan objek, bukan jika mereka sama, tetapi jika mereka benar-benar objek yang sama dengan lokasi memori yang sama pula.

| Operator | Deskripsi | Contoh |
| --- | --- | --- |
| `is` | Menghasilkan `True` jika kedua variabel adalah objek yang sama. | `x is y` |
| `is not` | Menghasilkan `True` jika kedua variabel bukan objek yang sama. | `x is not y` |

### Membership operators

Membership operators digunakan untuk mencari tahu apakah objek ada di dalam objek lain. Biasanya digunakan untuk mengecek item di dalam ***list***, ***tuple***, ***set***.

| Operator | Deskripsi | Contoh |
| --- | --- | --- |
| `in` | Menghasilkan `True` jika objek ada di dalam objek lain | `x in y` |
| `not in` | Menghasilkan `True` jika objek tidak ada di dalam objek lain | `x not in y` |

### Bitwise operators

Bitwise operator digunakan untuk operasi boolean atau angka (dalam binary).

| Operator | Nama | Deskripsi* |
| --- | --- | --- |
| `&` | AND | `0 & 0 = 0`<br>`0 & 1 = 0`<br>`1 & 0 = 0`<br>`1 & 1 = 1` |
| `\|` | OR | `0 \| 0 = 0`<br>`0 \| 1 = 1`<br>`1 \| 0 = 1`<br>`1 \| 1 = 1` |
| `^` | XOR | `0 ^ 0 = 0`<br>`0 ^ 1 = 1`<br>`1 ^ 0 = 1`<br>`1 ^ 1 = 0` |
| `~` | NOT | `~ 0 = 1`<br>`~ 1 = 0` |
| `>>` | RIGHT SHIFT | |
| `<<` | LEFT SHIFT | |

\* `0` = `False`, `1` = `True`

Ini adalah contoh penggunaan RIGHT SHIFT dan LEFT SHIFT. Gunakan built-in `bin()` function untuk mendapatkan nilai biner dari angka (`bin()` -> ***str***).

```python
x = 10
print(bin(x)[2:], bin(x >> 2)[2:]) # 1010 10
print(bin(x)[2:], bin(x << 2)[2:]) # 1010 10100
```