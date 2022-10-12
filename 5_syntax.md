## Syntax

### Indentation

Python menggunakan indentation (lekukan) untuk tiap block program. Block program adalah program yang ada di dalam statement (pada contoh di bawah, `print("Hello, world")` berada di dalam block `if 0 > 9:`). Jika statement berakhiran dengan `:`, maka baris selanjutnya harus diberi indent. Jumlah spasi pada indent minimal 1 spasi.

```python
if 0 > 9:
  # di belakang kata "print" terdapat 2 spasi sebagai indent
  print("Hello, world")
  # print() digunakan untuk menampilkan objek pada console
```

Python akan memberikan error jika meng-skip indent.

```python
# ERROR CODE
if 0 > 9:
print("Hello, world")
```

Kita harus menggunakan jumlah spasi yang sama di block kode yang sama, jika tidak Python akan memberikan error.

```python
# ERROR CODE
if 98 == 8:
  print("Jumlah space indent = 2")
      print("Jumlah space indent = 6") # indent tidak konsisten
  print('Jumlah space indent = 2')
```

### Comments

Comment tidak akan dieksekusi ketika program dijalankan. Comment dapat digunakan untuk menjelaskan kode Python, membuat kode lebih mudah dibaca, dan untuk mencegah eksekusi saat menguji kode. Comment dimulai dengan `#` dan berakhir dengan baris baru (newline).

```python
# ini adalah comment
def main():
  print("Hello,", "world", sep=' ') # ini juga comment
  # print(12, "Angka")
  # pass
```
### Identifier

Identifiers adalah nama yang mengidentifikasikan variable, function, module, class, dan objek lain di python. Identifier haruslah huruf/angka/garis bawah (_) tapi tidak boleh diawali angka. Python identifiers termasuk case-sensitive, misalnya `x` dan `X` adalah identifier yang berbeda. Anda tidak dapat menggunakan Python keyword untuk identifiers.

```python
var1_debug = 19 # var1_debug adalah identifier
2var = 90 # [ERROR] 2var tidak boleh dijadikan identifier karena diawali angka
if = 89 # [ERROR] if tidak boleh dijadikan identifier karena termasuk keyword
```

### Keywords

Berikut adalah keyword-keyword yang ada pada Python

```python
False  class    finally is       return
None   continue for     lambda   try
True   def      from    nonlocal while
and    del      global  not      with
as     elif     if      or       yield
assert else     import  pass
break  except   in      raise
```

### Tanda kurung '()'

Dalam program python, tanda kurung juga dapat digunakan untuk meng-group kan program yang akan dieksekusi terlebih dahulu.

```python
print(10 * 9 + 10) # 100
print(10 * (9 + 10)) # 190
```
Tanda kurung juga berguna untuk membuat 1 baris program menjadi multiline.

```python
print(90 - 90, end="") # 0
print(
  90 - 90,
  end=""
) # 0
```

### Spasi ' '

Spasi dalam bahasa pemrograman tidak seluruhnya diperlukan, misal

```python
x     =            10
```

Sama dengan

```python
x=10
```

Tetapi memang ada space yang diperlukan, seperti untuk indentation, pemisah antar karakter, pemisah keyword, dan sebagainya.

### Semi colon ';'

Semicolon `;` sering digunakan bahasa pemrograman sebagai pembatas program. Tapi dalam python, semicolon dianggap tidak wajib tapi tetap boleh digunakan untuk meminimalkan tampilan code.

```python
x = 90; print(x)
```

Sama dengan

```python
x = 90
print(x)
```

Tapi jika ada 2 program berbeda dalam satu line, maka harus dibatasi dengan semicolon. Jika tidak, maka akan terjadi error.

```python
y = "Woohoo"; print(y) # Tidak error
x = "Hooray"  print(x) # Error
```