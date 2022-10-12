## Tipe data

Setiap objek di dalam Python pasti memiliki tipe data, dan tiap tipe data memiliki karakteristiknya masing-masing. Berikut adalah tipe-tipe data yang ada di Python.

| Tipe data | Contoh | Deskripsi |
| :-------- | :----- | :-------- |
| ***str*** | `"teks"` `'teks'` | Kumpulan karakter yang diapit tanda petik tunggal `'...'` maupun tanda petik ganda `"..."` |
| ***int*** | `255` `-43` `0xff` `0b1011` `0o12` | Bilangan bulat (positif atau negatif) tanpa desimal |
| ***float*** | `2.90` `0.02` `-12.0` `9.12e-23` `9e+63` | Bilangan desimal (positif atau negatif) |
| ***complex*** | `5j` `9+80j` | Bilangan kompleks. Selalu berakhiran `j` |
| ***list*** | `[1, 2, 3]` | Kumpulan objek yang diapit `[...]`. Objek di dalamnya boleh tipe data apa saja. |
| ***tuple*** | `(1, 2, 3)` | Kumpulan objek yang diapit `(...)`. Objek di dalamnya boleh tipe data apa saja. Objek di dalam tuple tidak bisa dirubah. |
| ***set*** | `{1, 2, 3}` | Kumpulan objek yang diapit `{...}`. Objek di dalamnya boleh tipe data apa saja. Jika ada objek yang sama di dalam set, maka hanya salah satu yang disimpan. |
| ***bool*** | `True` `False` | Boolean yang hanya memiliki 2 nilai, `True` atau `False` |
| ***NoneType*** | `None` | Objek kosong |
| ***dict*** | `{'a': 99, 'b': -87}` | Menyimpan item-item berdasarkan key. Tipe data dict diapit dengan `{...}`. Dan didalamnya harus memiliki key dan value. |

Untuk mengetahui tipe dari objek, gunakan fungsi `type()`.

```python
list_person = []
print(type(list_person)) # <class 'list'>
print(type(8.2)) # <class 'float'>
```

### Karakter (str)

***str*** (String) adalah kumpulan karakter yang diapit tanda petik tunggal `'...'` maupun tanda petik ganda `"..."`. Contoh:

```python
word = "some word" # tipe data: str
word = 'some word' # tipe data: str
```

String jika sudah diapit tanda petik tunggal `'`, maka di dalamnya tidak boleh terdapat petik tunggal. Begitu pula dengan petik ganda `"`. Kecuali menggunakan special character backslash `\`

```python
print("ular "python"") # [ERROR]
print("ular \"python\"") # ular "python"
```

Jenis-jenis special character adalah berikut

```
\  => untuk escape character
\n => untuk new line (enter)
\t => untuk tab
\b => untuk backspace
\\ => untuk backslash character
```

Jika ingin menjadikan special character sebagai character biasa, dapat menambahkan `r` sebelum string. `r` = raw.

```python
print("ular \tpython")  # ular    python
print(r"ular \tpython") # ular \tpython
```

String dapat dimasukkan dengan program lain dengan menambahkan `f` sebelum string. Program yang dimasukkan ke dalam string harus diapit `{...}`. `f` = format.

```python
i = 90
myString = f'number {i}'
print(myString) # number 90
```

String dapat digabungkan dengan `+` dan dapat diulang dengan `*`.

```python
x = "ini"
print('ini' + '-' + 'itu')       # ini-itu
print('ini' * 5)                 # iniiniiniiniini
print('ini' + ('-' * 5) + 'itu') # ini-----itu
print('ini' '-' "itu")           # ini-itu
print(x 'itu')                   # [ERROR]
print(x + 'itu')                 # iniitu
print(('ini'*2) 'itu')           # [ERROR]
print(("ini" * 2) + 'itu')       # iniiniitu
```

Untuk membuat string multiline, dapat menggunakan `"""..."""` atau `'''...'''`

```python
print('''Lorem ipsum
dolor sit amet, consectetur
adipiscing elit, sed do
''')
```

Yang dimana sama seperti,

```python
print('Lorem ipsum\ndolor sit amet, consectetur\nadipiscing elit, sed do')
```

Kita juga bisa mengambil substring dengan index.

```python
x = 'python'
print(x[0]  ) # p    (index 0    )
print(x[-1] ) # n    (index -1   )
print(x[1:3]) # yt   (index 1-3  )
print(x[:3] ) # pyt  (index 0-3  )
print(x[2:] ) # thon (index 2-end)
```

Ini adalah penjelasan index pada string,

```
 +---+---+---+---+---+---+
 | P | y | t | h | o | n | <= string
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6 <= index
-6  -5  -4  -3  -2  -1     <= index
```

Untuk menghitung panjang string dapat menggunakan fungsi `len()`.

```python
print(len('python')) # 6
```


String juga memiliki method-method (penjelasan method akan dijelaskan nanti) yang memudahkan programmer untuk mengatur string. Lihat String Methods hal. 23 untuk lebih detail tentang string method.

```python
x = 'AYAM bakar'

# .count() method untuk menghitung banyak karakter tertentu pada string
y = x.count('A')
print(x.count('A')) # 4

# .index() method untuk mengetahui index awal substring
y = x.index('b')
print(y) # 5

# .lower() method untuk mengubah semua string menjadi huruf kecil
y = x.lower()
print(y) # ayam bakar

# .upper() method untuk mengubah semua string menjadi huruf besar
y = x.upper()
print(y) # AYAM BAKAR

# .replace() method digunakan untuk mengubah substring menjadi string lain
y = x.replace('bakar', 'GORENG')
print(y) # AYAM GORENG

# seperti ini juga tidak dipermasalahkan
y = 'AYAM bakar'.upper()
print(y) # AYAM BAKAR
```

Catatan: ***str*** termasuk `Iterable` objek.

### Angka(int, float, complex)

***int*** (Integer) adalah bilangan bulat (positif atau negatif) tanpa desimal.

```python
z = 45
print(z, type(z)) # 45 <class 'int'>
```

bilangan hexadesimal `0x…`, octal `0o…`, dan binary `0b…` di dalam python juga termasuk ***int***.

```python
print(0x90, type(0x90)) # 144 <class 'int'>
print(0o12, type(0o12)) # 10 <class 'int'>
print(0b1101, type(0b1101)) # 13 <class 'int'>
```

***float*** adalah bilangan desimal (positif atau negatif). ***float*** dapat menggunakan notasi `e` untuk angkanya. Nilai tertinggi ***float*** adalah `± 1.7976931348623157e+308`. Jika melebihi itu, maka akan terjadi error.

```python
print(2.5, type(2.5)) # 2.5 <class 'float'>
print(2.5e-100, type(2.5e-100)) # 2.5e-100 <class 'float'>
```

***complex*** adalah bilangan kompleks yang selalu diakhiri huruf `j`.

```python
print(2j, type(2j)) # 2j <class 'complex'>
print(3+4j, type(3+4j)) # (3+4j) <class 'complex'>
```

***int***, ***float***, dan ***complex*** juga mendukung operasi pertambahan `+`, pengurangan `-`, perkalian `*`, pembagian `/` dan banyak lagi lainnya.

```python
x = 10
y = x + 10
print(y) # 20
```

Sama seperti hukum matematika, perkalian dan pembagian lebih didahulukan daripada pertambahan dan pengurangan.

```python
x = 10
y = 8
print(x + y * x) # 90
print((x + y) * x) # 180
```

### Boolean (bool)

Boolean hanya memiliki 2 nilai, `True` atau `False`. Dalam binary True sama dengan 1 sedangkan False sama dengan 0.

```python
print(True, type(True)) # True <class 'bool'>
print(False, type(False)) # False <class 'bool'>
```

### Iterable (list, tuple, set)

***list***, ***tuple***, dan ***set*** digunakan untuk menyimpan banyak item dalam satu variabel. Item di dalamnya boleh berjenis-jenis tipe data. Tipe data ***list*** diapit dengan `[...]`, ***tuple*** diapit dengan `(...)`, dan  ***set*** diapit dengan `{...}`. Jika item di dalam ***set*** ada yang sama lebih dari satu, maka hanya salah satu saja yang akan disimpan.

```python
myList  = [12, "B", [False, 8.0], {'', 8+9j}, 0x89]
myTuple = (12, "B", [False, 8.0], {'', 8+9j}, 0x89)
mySet   = {12, "B", [False, 8.0], {'', 8+9j}, 0x89}
```

Kita dapat mengambil item di dalam ***list*** dan ***tuple*** dengan index. Sedangkan ***set*** tidak bisa, karena urutan item di dalam ***set*** selalu acak setiap saat.

```python
myList = [12, "B", [False, 8.0], {'', 8+9j}, 0x89]
myTuple = (12, "B", [False, 8.0], {'', 8+9j}, 0x89)

print(
  myList[0:2], # index 0-2
  myTuple[2:], # index 2-akhir
  myList[0]    # index 0
)

# output: [12, 'B'] ([False, 8.0], {'', (8+9j)}, 137) 12
```

Item di dalam ***list*** juga dapat diubah.

```python
myList = [12, 2, 89]
print(myList) # [12, 2, 89]
myList[0] = 24 # list pada index=0 berubah menjadi 24
print(myList) # [24, 2, 89]
```

Berbeda dengan ***list***, ***tuple*** tidak bisa mengubah item di dalamnya. Tapi tetap bisa mengurangi atau menambah item. Sedangkan ***set*** tidak bisa diubah itemnya berdasarkan index, karena urutan ***set*** selalu acak.

***list*** dan ***tuple*** juga mendukung `+` dan `*` operator

```python
print([0, 1] + [2, 3]) # [0, 1, 2, 3]
print([0, 1] * 2)      # [0, 1, 0, 1]
print((0, 1) + (2, 3)) # (0, 1, 2, 3)
print((0, 1) * 2)      # (0, 1, 0, 1)
```

***list***, ***tuple***, dan ***set*** juga memiliki method-method (lihat List Methods hal. 26, Tuple Methods hal. 26, lihat Set Methods hal. 27).

```python
# LIST
myList = [1, 2, 3]
myList.append(4) # menambah item pada list
myList.remove(4) # menghapus item pada list
myList.sort() # mengurutkan list

# TUPLE
myTuple = (1, 2, 3)
x = myTuple.count(2) # menghitung banyak item yang sama pada tuple

# SET
mySet = {1, 2, 3}
mySet.add(4) # menambah item pada set
mySet.remove(4) # menghapus item pada set
```

Catatan: ***list***, ***set***, dan ***tuple*** termasuk `Iterable` objek.

### Dictionary (dict)

***dict*** digunakan untuk menyimpan item-item berdasarkan key. Tipe data ***dict*** diapit dengan `{...}`. Dan didalamnya harus memiliki key dan value.

```python
myDictionary = {
    'a': 10,      # 'a' = key, 10 = value
    'c': 3 - 9,   # 'c' = key, -6 = value
    9: [1, False] # 9 = key, [1, False] = value
}
print(myDictionary) # {'a': 10, 'c': -6, 9: [1, False]}
```

Untuk mengambil data dari ***dict***, kita harus menggunakan key yang ada di dalam dictionary.

```python
myDictionary = {
    'a': 10,
    'c': 3 - 9,
    9: [1, False]
}
print(myDictionary['a']) # 10
print(myDictionary[9])   # [1, False]
```

Bisa juga mengubah item berdasarkan key yang ada. Jika key tidak ada di dalam dictionary, maka dictionary akan membuat key dan value baru.

```python
myDictionary = {
    'a': 10,
    'c': 3 - 9,
    9: [1, False]
}
myDictionary['a'] = 100 # mengubah value
print(myDictionary['a']) # 100
myDictionary['d'] = 90 # membuat key dan value dalam dictionary
print(myDictionary['d']) # 90
```

***dict*** juga memiliki method-method (lihat Dictionary Methods hal. 26).

```python
myDictionary = {
    'a': 10,
    'c': 3 - 9,
    9: [1, False]
}

# items() untuk mendapatkan semua item (key, value) pada dict
y = myDictionary.items()
print(list(y)) # [('a', 10), ('c', -6), (9, [1, False])]

# keys() untuk mendapatkan semua key pada dict
y = myDictionary.keys()
print(list(y)) # ['a', 'c', 9]

# values() untuk mendapatkan semua value pada dict
y = myDictionary.values()
print(list(y)) # [10, -6, [1, False]]
```