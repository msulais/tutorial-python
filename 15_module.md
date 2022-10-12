## Module

Module adalah file python yang berisikan variable/fungsi/class yang dapat diakses dari file lain. Module python ada yang sudah built-in (contoh: `os`, `datetime`, `sys`, `re`, dll) dan dapat langsung di `import`, tapi ada juga yang harus mendownload/membuat file module sendiri.

Untuk built-in module python sudah menyediakan banyak sekali dokumentasinya. [Untuk lebih detail tentang built-in module](https://docs.python.org/3/library/index.html).

Jika ingin mendownload module dari [pypi](https://pypi.org/), caranya dengan mengetik "*pip3 install module_name*" pada command line.

```python
# syntax: (<module>, <alias>, <members>: identifier)
# `import <module>`
# `import <module> as <alias>`
# `from <module> import <members>`
# `from <module> import *`
```

Ini adalah cara `import` module

```python
import datetime
print(datetime.datetime.now()) # 2022-07-09 04:21:23.323946


import datetime as date # dengan nama lain
print(date.datetime.now()) # 2022-07-09 04:21:23.323946


# dengan spesifik pada variable/fungsi/class tertentu
from datetime import datetime, date
print(datetime.now()) # 2022-07-09 04:21:23.323946


from datetime import * # dengan spesifik pada seluruh variable/fungsi/class
print(datetime.now()) # 2022-07-09 04:21:23.323946
```

### Membuat module sendiri

Buat file python baru dan isikan dengan variable/fungsi/class.

```python
# operation.py
def div(x, y):
  return x / y

def mul(x, y):
  return x * y

def add(x, y):
  return x + y

def sub(x, y):
  return x - y
```

Kemudian buat file python baru yang lain dan import nama file sebelumnya (operation.py)

```python
# main.py
import operation
print(operation.add(10, 10)) # 20
```