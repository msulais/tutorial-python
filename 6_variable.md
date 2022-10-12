## Variabel

Variabel adalah identifier untuk menyimpan objek. Data dalam variabel dapat diubah-ubah.

```python
x = 10 # Data dalam x adalah 10
x = 90 # Data dalam x berubah menjadi 90
x = x + 1 # x berubah menjadi (90+1) = 91
```

Aturan penulisan variabel ada pada [identifier](#identifier). Tiap variabel memiliki tipe data sesuai datanya. Pada contoh diatas, variabel `x` termasuk dalam tipe data `int`. Karena python adalah dynamic programming language, maka penulisan tipe data tidak diharuskan. Jika ingin dengan penulisan tipe data, maka dapat dilakukan dengan

```python
x :int = 10 # tipe data x adalah integer, int adalah tipe datanya
```

Konsekuensi dari penulisan tipe data adalah variabel tidak bisa berubah menjadi tipe data lain.

```python
x :int = 10 # Ini sudah pasti integer dan tidak dapat berubah tipe datanya
x = "Lain" # [ERROR] tipe data x adalah integer (tidak boleh berubah)

y = 9 # tipe data y adalah integer
y = ['a', 'b', 'c'] # tipe data y berubah menjadi list
```

Membuat multi-variable dalam 1 line juga bisa

```python
a, b, c, d = 1, 2, 3, 4
a, b, c, d = 1, 2, 3    # [ERROR] kurang 1 value
```

Objek dari variable dapat dihapus dengan menggunakan `del` keyword

```python
x = 10
del x
print(x) # [ERROR]
```