 # Praktikum 9 
 
## Exception and Handling

#### Contoh Assert Statement

- Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

```
def KelvinTo Fahrenheit (Temperature):
    assert (Temperature >= 0), "Colder than absolute zero!"
    return ((Temperature-273)*1.8)+32
print (KelvinToFahrenheit (273))
print (int (KelvinToFahrenheit (505.78)))
print (KelvinToFahrenheit (-5))
```

- Output yang di hasilkan

![gambar](gambar/1.png)

- Jika pernyataan gagal, Python menggunakan ArgumentExpression ArgumentExpression sebagai argumen argumen untuk AssertionError AssertionError. Pengecualian AssertionError Pengecualian AssertionError dapat ditangkap dan ditangani ditangani seperti pengecualian lainnya menggunakan try- kecuali pernyataan, tetapi jika dibiarkan, mereka akan menghentikan program dan menghasilkan backtrace.

#### ContohHandling an Exception

- Contoh-contoh ini membuka file, menulis konten file, dan keluar dengan aman karena ada tidak masalah
- Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

```
try:
    fh= open("testfile", "w")
    fh.write("This is my test ile for exception handling!!")
except IOError:
    print("Error: cant\'t find file or read data")
else:
    print("Written content in the file successfully")
    fh.close()
```

- Output yang di hasilkan

![gambar](gambar/2.png)

- Contoh ini mencoba membuka file yang Anda tidak memiliki izin menulis, sehingga membuat file pengecualian
- Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

```
try:
    fh= open("testfile", "r")
    fh.write("This is my test ile for exception handling!!")
except IOError:
    print("Error: cant\'t find file or read data")
else:
    print("Written content in the file successfully")
    fh.close()
```

- Output yang di hasilkan

![gambar](gambar/3.png)

#### Contoh The try-finally Clause

- Ketika exception dilempar ke dalam blok try, eksekusi segera dilanjutkan ke akhir memblok. Setelah semua pernyataan di blok akhirnya dieksekusi, pengecualian dimunculkan lagi dan ditangani dalam pernyataan kecuali jika ada di lapisan berikutnya yang lebih tinggi dari percobaan-kecuali penyataan.
- Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:
- Jika Anda tidak memiliki izin untuk membuka file dalam mode tulis yang dapat ditulis, maka ini akan menghasilkan hasil berikut:

```
try:
    fh = open("testfile", "w")
    fh.write("This is my test file for exception handling!!")
finally:
    print("Error: can\'t find file or read data")
```

- Output yang di hasilkan

![gambar](gambar/4.png)

- Contoh yang sama dapat ditulis lebih bersih sebagai berikut:

```
try:
    fh= open("testfile", "r")
    try:
        fh.write("This is my test ile for exception handling!!")
    finally:
        print ("Going to close the file")
        fh.close()
except IOError:
    print("Error cant\'t find file or read data")
```

- Output yang di hasilkan

![gambar](gambar/5.png)

#### Contoh Argument of an Exception

- Berikut adalah contoh untuk satu pengecualian
- Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

```
#Define a function here.

def temp_convert (var):
    try:
        return int (var)
    except ValueError (Argument):
        print("The argument Call above function here. does not contain numbers\n", Argument)
# Call above funcition here.

temp_convert("xyz")
```

- Output yang di hasilkan

![gambar](gambar/6.png)

#### Contoh Raising an Exception

- Pengecualian dapat berupa string, kelas, atau objek. Sebagian besar pengecualian adalah pengecualian dari inti Python menimbulkan adalah kelas, dengan argumen=argumen yang merupakan turunan dari kelas. Mendefinisikan pengecualian barucukup mudah dan dapat dilakukan sebagai berikut:

```
def functionName ( level):
    if level < 1:
        raise ("Invalid level!", level)
        # The code below to this would not be executed
        # if we raise the exception
```

- Output yang di hasilkan

![gambar](gambar/7.png)

#### Contoh User-Defined Exception

- Python juga memungkinkan Anda membuat pengecualian sendiri dengan menurunkan kelas-kelas dari yang standar pengecualian bawaan.
- Berikut adalah contoh-contoh yang terkait dengan RuntimeError. Di sini, kelas dibuat yang merupakan subkelas dari subkelas RuntimeError. Ini berguna saat Anda perlumenampilkan tampilan informasi yang lebih spesifik saat e pengecualian tertangkap.
- Di blok coba, pengecualian yang ditentukan pengguna dimunculkan dan ditangkap di blok kecuali. Itu variabel e digunakan untuk membuat instance dari kelas Networkerror.
- Ketika kode di bawah dijalankan, menghasilkan hasil sebagai berikut:

```
class Networkerror (RuntimeError):
    def _init_(self, arg):
        self, arg = arg
try:
    raise Networkerror ("Bad hostname")
except Networkerror(e):
    print (e.args)
```

- Output yang di hasilkan

![gambar](gambar/8.png)



