## Struktur program

```python
x = 10
if x > 3:
    print("nilai x lebih dari 3")

print("Hello, world") # Hello, world
```

- Baris 1: `x = 10`

  Mendeklarasikan variabel dengan nama `x` dan datanya adalah integer `10`. Variable digunakan untuk menyimpan data. Data dari variabel dapat berubah. Baris ini termasuk statement (pernyataan).

- Baris 2: `if x > 3:`

  `if` digunakan untuk membuat program dapat berjalan sesuai kondisi. Kondisi akan menghasilkan `True` (benar) atau `False` (salah). Jika kondisi dari `x > 3` (dibaca: data dari x lebih dari 3) adalah benar `True`, maka program `print("nilai x lebih dari 3")` akan berjalan. Jika salah `False`, maka tak akan berjalan. Tanda titik dua `:` menandakan bahwa ada program di dalam `if`. `print("nilai x lebih dari 3")` adalah program di dalam `if` karena terdapat beberapa spasi sebelum `print("nilai x lebih dari 3")`.

- Baris 3, 5: `print()`

  `print()` adalah built-in function yang digunakan untuk menampilkan objek pada terminal. `print("nilai x lebih dari 3")` akan menampilkan `nilai x lebih dari 3` pada terminal. `print("Hello, world")`  juga akan menampilkan `Hello, world` pada terminal. Objek yang diapit tanda petik ganda `"..."` adalah objek string.

- Baris 4: Baris kosong

  Baris kosong tidak memiliki pengaruh apapun pada program. Baris kosong biasanya digunakan untuk membuat tampilan kode lebih rapi.

- Baris 5: ` Hello, world`

  Comment tidak akan dieksekusi ketika program dijalankan. Comment dapat digunakan untuk menjelaskan kode Python, membuat kode lebih mudah dibaca, dan untuk mencegah eksekusi saat menguji kode. Comment dimulai dengan `#` dan berakhir dengan baris baru (newline).