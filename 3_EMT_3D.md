# 3. Menggambar Plot 3D dengan EMT
Ini adalah pengenalan plot 3D di Euler. Kita membutuhkan plot 3D untuk
memvisualisasikan fungsi dari dua variabel.


Euler menggambar fungsi tersebut menggunakan algoritma pengurutan
untuk menyembunyikan bagian di latar belakang. Secara umum, Euler
menggunakan proyeksi pusat. Standarnya adalah dari kuadran x-y positif
menuju titik asal x=y=z=0, tetapi sudut=0° terlihat dari arah sumbu y.
Sudut pandang dan tinggi dapat diubah.


Euler dapat merencanakan


* 
permukaan dengan bayangan dan garis level atau rentang level,

* 
awan poin,

* 
kurva parametrik,

* 
permukaan implisit.


Plot 3D dari suatu fungsi menggunakan plot3d. Cara termudah adalah
dengan memplot ekspresi dalam x dan y. Parameter r mengatur kisaran
plot di sekitar (0,0).


\>aspect(1.5); plot3d("x^2+sin(y)",r=2\*pi): 


![images/3_EMT_3D-001.png](images/3_EMT_3D-001.png)

## 1) Menggambar Grafik Fungsi Dua Variabel dalam Bentuk

## Ekspresi Langsung

Grafik fungsi dua variabel dalam bentuk ekspresi langsung adalah
representasi visual dari hubungan matematis antara dua variabel
independen yang dinyatakan dalam bentuk persamaan atau ekspresi
matematis. Biasanya, grafik ini digunakan untuk menggambarkan hubungan
antara dua variabel dalam bidang dua dimensi dan tiga dimensi. Dalam
konteks ini, variabel independen (x dan y) adalah variabel input,
sedangkan variabel dependen (z) adalah variabel output yang dihasilkan
oleh ekspresi matematis.


Rumus umum untuk menggambar grafik fungsi dua variabel dalam bentuk
ekspresi langsung adalah:


$$z = f(x, y)$$Dalam rumus ini:


- z adalah variabel dependen yang ingin kita gambar dalam grafik.


- f(x, y) adalah ekspresi matematis yang menghubungkan variabel z
dengan variabel independen x dan y. Ekspresi ini dapat berupa fungsi
linear, fungsi kuadrat, fungsi akar kuadrat, eksponensial, logaritma,
trigonometri, nilai mutlak, atau jenis fungsi matematis lainnya,
tergantung pada hubungan yang ingin diilustrasikan.


## 1. Grafik Fungsi Linear



Fungsi linear dua variabel biasanya dinyatakan dalam bentuk


$$f(x,y)=ax+by+c$$

dimana a,b, dan c adalah konstanta.  Grafik fungsi linear ini adalah
sebuah bidang datar, dan bentuknya akan bervariasi tergantung pada
nilai a dan b.


Contoh:


$$f(x,y)=7x+3y+9$$\>plot3d("7\*x+3\*y+9"):


![images/3_EMT_3D-005.png](images/3_EMT_3D-005.png)

$$f(x,y)=-9x-3y-12$$\>plot3d("-9\*x-3\*y-12"):


![images/3_EMT_3D-007.png](images/3_EMT_3D-007.png)

## 2. Grafik Fungsi Kuadrat



Fungsi kuadrat dua variabel biasanya dinyatakan dalam bentuk


$$f(x,y)=ax^2+by^2+cxy+dx+ey+f$$

dimana a, b, c, d, e, dan f adalah konstanta. Grafik fungsi kuadrat
ini adalah sebuah permukaan yang dapat memiliki berbagai bentuk
tergantung pada nilai-nilai konstantanya.


Contoh:


$$f(x,y)= 4x^2+y^2+4xy+8x+3y+12$$\>plot3d("4\*x^2+y^2+4\*x\*y+8\*x+3\*y+12"):


![images/3_EMT_3D-010.png](images/3_EMT_3D-010.png)

## 3. Grafik Fungsi Akar Kuadrat



Grafik fungsi akar kuadrat dua variabel


$$f(x,y)=\sqrt{x^2+y^2}$$

adalah grafik permukaan yang menggambarkan jarak titik (x, y) dari
titik asal (0, 0) dalam ruang tiga dimensi.


Contoh:


$$f(x,y)=\sqrt{x^2+y^2}$$\>plot3d("sqrt(x^2+y^2)"):


![images/3_EMT_3D-013.png](images/3_EMT_3D-013.png)

$$f(x,y)=\sqrt{6x^2+9y^2}$$\>plot3d("sqrt(36\*x^2+9\*y^2)"):


![images/3_EMT_3D-015.png](images/3_EMT_3D-015.png)

## 4. Grafik Fungsi Eksponensial



Fungsi eksponensial dua variabel bisa dinyatakan


$$f(x,y)=a.b^{xy}$$

dimana a dan b adalah konstanta, x dan y adalah variabel. Fungsi ini
menggambarkan pertumbuhan eksponensial yang bergantung pada nilai x
dan y.


Contoh:


$$f(x,y)= 12.3^{xy}$$\>plot3d("12\*3^(x\*y)"):


![images/3_EMT_3D-018.png](images/3_EMT_3D-018.png)

$$f(x,y)= 5.-8^{xy}$$\>plot3d("5\*-8^(x\*y)"):


![images/3_EMT_3D-020.png](images/3_EMT_3D-020.png)

## 5. Grafik Fungsi Logaritma



Grafik fungsi logaritma dua variabel adalah grafik yang menggambarkan
nilai logaritma dari suatu ekspresi yang melibatkan dua variabel
(biasanya x dan y). Fungsi logaritma dua variabel ini dinyatakan
sebagai


$$f(x,y)=log_b(xy)$$

dimana b adalah basis logaritma. Basis logaritma ini dapat
berbeda-beda.


Contoh:


$$f(x,y)=log(xy), basis 10$$\>plot3d("log(x\*y)"):


![images/3_EMT_3D-023.png](images/3_EMT_3D-023.png)

$$f(x,y)=log(4x.9y), basis 10$$\>plot3d("log(4x\*9\*y)"):


![images/3_EMT_3D-025.png](images/3_EMT_3D-025.png)

## 6. Grafik Fungsi Trigonometri



Fungsi trigonometri dua variabel adalah fungsi matematika yang
melibatkan operasi trigonometri (seperti sin, cos, tan) pada kedua
variabel x dan y.


Contoh:


$$f(x,y)=sin(45x).cos(y)$$\>plot3d("sin(45x)\*cos(y)"):


![images/3_EMT_3D-027.png](images/3_EMT_3D-027.png)

$$f(x,y)=sin(2x).cos(4y)$$\>plot3d("sin(2x)\*cos(4y)"):


![images/3_EMT_3D-029.png](images/3_EMT_3D-029.png)

$$f(x,y)=sin(15x).tan(60y)$$\>plot3d("sin(15x)\*tan(60y)"):


![images/3_EMT_3D-031.png](images/3_EMT_3D-031.png)

$$f(x,y)=cos(x).tan(2y)$$\>plot3d("cos(x)\*tan(2y)"):


![images/3_EMT_3D-033.png](images/3_EMT_3D-033.png)

$$f(x,y)=cosec(6x).sec(2y)$$\>plot3d("cosec(6x)\*sec(2y)"):


![images/3_EMT_3D-035.png](images/3_EMT_3D-035.png)

## 7. Grafik Fungsi Nilai Mutlak



Fungsi nilai mutlak dua variabel, juga dikenal sebagai fungsi modul
dua variabel, dinyatakan sebagai


$$f(x,y)=|g(x,y)|$$

dimana g(x,y) adalah fungsi dua variabel.


Contoh:


$$f(x,y)=|x^2 - y^2|$$\>plot3d("abs(x^2 - y^2)"):


![images/3_EMT_3D-038.png](images/3_EMT_3D-038.png)

$$f(x,y)=|5x^2 + 3y^2|$$\>plot3d("abs(5\*x^2 + 3\*y^2)"):


![images/3_EMT_3D-040.png](images/3_EMT_3D-040.png)

$$f(x,y)=|-2x^2 - 5y^2|$$\>plot3d("abs(-2x^2 - 5y^2)"):


![images/3_EMT_3D-042.png](images/3_EMT_3D-042.png)

## Latihan soal



Buatkan grafik dari fungsi berikut:


1.


$$f(x,y)=16x-4y+6$$\>plot3d("16\*x - 4\*y +6"):


![images/3_EMT_3D-044.png](images/3_EMT_3D-044.png)

2.


$$f(x,y)=cos(45x).sin(15y)$$\>plot3d("cos(45\*x)\*sin(15\*y)"):


![images/3_EMT_3D-046.png](images/3_EMT_3D-046.png)

3.


$$f(x,y)=\sqrt{x^2+20y^2}$$\>plot3d("sqrt(x^2+20\*y^2)"):


![images/3_EMT_3D-048.png](images/3_EMT_3D-048.png)

## 2) Menggambar Grafik Fungsi Dua Variabel yang Rumusnya Disimpan

## dalam Variabel Ekspresi

## Apa yang dimaksud dengan Grafik Fungsi Dua Variabel?

Grafik fungsi dua variabel adalah representasi visual dari hubungan
antara sebuah fungsi matematika dengan dua variabel independen
(biasanya disebut sebagai "x" dan "y") dan variabel dependen (biasanya
disebut sebagai "z" atau "f(x, y)").


Dalam grafik ini, sumbu x dan sumbu y digunakan untuk menggambarkan
nilai-nilai dua variabel independen, sementara permukaan atau grafik
3D digunakan untuk menggambarkan nilai-nilai variabel dependen yang
dihasilkan oleh fungsi tersebut.


Grafik fungsi dua variabel membantu memvisualisasikan bagaimana nilai
variabel dependen (z) berubah seiring perubahan kedua variabel
independen (x dan y) sesuai dengan aturan fungsi tersebut.


## Fungsi matematika yg terlibat dalam Menggambar Grafik

## Fungsi Dua Variabel

1. Fungsi Linear


Bentuk umum :


$$f(x, y) = ax + by + c$$

di mana a, b, dan c adalah konstanta. Grafiknya adalah bidang datar.


2. Fungsi Kuadratik


Bentuk umum :


$$f(x, y) = ax^2 + by^2 + cxy + dx + ey + f.$$

Grafiknya dapat berupa permukaan yang berbentuk paraboloid, baik
terbuka ke atas atau ke bawah.


3.Fungsi Trigonometri


Bentuk umum sinus dan cosinus :


$$(x, y) = sin(x) + cos(y)$$

akan menghasilkan permukaan yang berulang-ulang naik dan turun.


4.Fungsi Pecahan


Bentuk umum :


$$f(x, y) = g(x, y) / h(x, y)$$

di mana g(x, y) dan h(x, y) adalah fungsi-fungsi lain.


grafiknya dapat menghasilkan berbagai pola yang tergantung pada sifat
fungsi g dan h.


## Menggambar Grafik Fungsi



Perintah yang digunakan untuk menggambar grafik fungsi dalam EMT yaitu
dengan menggunakan plot3d.


Untuk menampilkan grafik, akhiri perintah plot3d dengan tanda (:).


Tanda (:) akan menampilkan grafik di layar yang berbeda.


\>plot3d("6\*x^2+3\*y^2"):


![images/3_EMT_3D-053.png](images/3_EMT_3D-053.png)

\>plot3d("6\*x^2+3\*x\*sin(y)",-5,5,0,6\*pi):


![images/3_EMT_3D-054.png](images/3_EMT_3D-054.png)

## Menyimpan Variabel Ekspresi



Untuk menyimpan sebuah fungsi, dapat dilakukan dengan menggunakan
perintah function. Lalu, ketika ingin memanggil atau membuat grafik
dari fungsi tersebut, cukup dengan memanggil nama fungsi tersebut.


\>function a(x,y):= x^2+y^3

\>plot3d("a"):


![images/3_EMT_3D-055.png](images/3_EMT_3D-055.png)

\>function f(x,y):= x^3-y^2

\>plot3d("f"):


![images/3_EMT_3D-056.png](images/3_EMT_3D-056.png)

## Contoh Latihan Soal

$$f(x,y)= 14x^3+y^4$$\>function f(x,y):= 14\*x^3+y^4

\>plot3d("f"):


![images/3_EMT_3D-058.png](images/3_EMT_3D-058.png)

\>plot3d("a",\>user, ...  
\>   title="Turn with the vector keys (press return to finish)"):


![images/3_EMT_3D-059.png](images/3_EMT_3D-059.png)

Perintah ini mengizinkan pengguna untuk menggambar grafik 3D dari
fungsi yang mereka masukkan sendiri, serta memberikan petunjuk
interaktif tentang cara berinteraksi dengan grafik. Pengguna dapat
memutar tampilan grafik menggunakan tombol arah pada keyboard, dan
menekan "return" untuk menyelesaikan interaksi.


\>plot3d("a",r=5,n=80,fscale=4,scale=1.2,frame=3):


![images/3_EMT_3D-060.png](images/3_EMT_3D-060.png)

perintah ini akan menggambar grafik tiga dimensi dari fungsi "a" dalam
rentang x dan y dari -5 hingga 5, dengan 80 titik untuk detail yang
lebih halus. Nilai fungsi akan diperbesar 4 kali, dan grafik akan
ditampilkan dengan skala 1.2 untuk tampilan yang lebih jelas. Bingkai
grafis akan ditentukan oleh parameter frame=3.


\>view


    [5,  2.6,  2,  0.4]

\>plot3d("a",distance=3,zoom=2,angle=0,height=0):


![images/3_EMT_3D-061.png](images/3_EMT_3D-061.png)

\>plot3d("x^4+y^2",a=0,b=1,c=-1,d=1,angle=-20°,height=20°, ...  
\>   center=[0.4,0,0],zoom=5):


![images/3_EMT_3D-062.png](images/3_EMT_3D-062.png)

\>plot3d("a",r=2,<fscale,<scale,distance=13,height=50°, ...  
\>    center=[0,0,-2],frame=3):


![images/3_EMT_3D-063.png](images/3_EMT_3D-063.png)

\>plot3d("a",r=5,\>polar, ...  
\>   fscale=2,\>hue,n=100,zoom=4,\>contour,color=orange):


![images/3_EMT_3D-064.png](images/3_EMT_3D-064.png)

\>plot3d("x","a","y",r=2,zoom=3.5,frame=3):


![images/3_EMT_3D-065.png](images/3_EMT_3D-065.png)

FUNGSI LINEAR


---

\>function e(x,y):= 25x+15y-5

\>plot3d("e"):


![images/3_EMT_3D-066.png](images/3_EMT_3D-066.png)

\>plot3d("e",\>user, ...  
\>   title="Turn with the vector keys (press return to finish)"):


![images/3_EMT_3D-067.png](images/3_EMT_3D-067.png)

\>plot3d("e",r=10,n=80,fscale=4,scale=1.2,frame=3):


![images/3_EMT_3D-068.png](images/3_EMT_3D-068.png)

\>view


    [5,  2.6,  2,  0.4]

\>plot3d("e",distance=3,zoom=2,angle=0,height=0):


![images/3_EMT_3D-069.png](images/3_EMT_3D-069.png)

\>plot3d("e",a=0,b=1,c=-1,d=1,angle=-20°,height=20°, ...  
\>   center=[0.4,0,0],zoom=5):


![images/3_EMT_3D-070.png](images/3_EMT_3D-070.png)

\>plot3d("e",r=2,<fscale,<scale,distance=13,height=50°, ...  
\>   center=[0,0,-2],frame=3):


![images/3_EMT_3D-071.png](images/3_EMT_3D-071.png)

\>plot3d("e",r=5,\>polar, ...  
\>   fscale=2,\>hue,n=100,zoom=4,\>contour,color=gray):


![images/3_EMT_3D-072.png](images/3_EMT_3D-072.png)

\>plot3d("x","e","y",r=2,zoom=3.5,frame=3):


![images/3_EMT_3D-073.png](images/3_EMT_3D-073.png)

FUNGSI TRIGONOMETRI


---

\>function f(x,y):= cos(x+y)

\>plot3d("f")

\>plot3d("f",\>user, ...  
\>   title="Turn with the vector keys (press return to finish)"):


![images/3_EMT_3D-074.png](images/3_EMT_3D-074.png)

\>plot3d("f",r=10,n=80,fscale=4,scale=1.2,frame=3):


![images/3_EMT_3D-075.png](images/3_EMT_3D-075.png)

\>view


    [5,  2.6,  2,  0.4]

\>plot3d("f",distance=3,zoom=2,angle=0,height=0):


![images/3_EMT_3D-076.png](images/3_EMT_3D-076.png)

\>plot3d("f",a=0,b=1,c=-1,d=1,angle=-20°,height=20°, ...  
\>   center=[0.4,0,0],zoom=5):


![images/3_EMT_3D-077.png](images/3_EMT_3D-077.png)

\>plot3d("f",r=5,\>polar, ...  
\>   fscale=2,\>hue,n=100,zoom=4,\>contour,color=gray):


![images/3_EMT_3D-078.png](images/3_EMT_3D-078.png)

## 3) Menggambar Grafik Fungsi Dua Variabel yang Fungsinya

## Didefinisikan sebagai Fungsi Numerik

Sebelum masuk ke cara memvisualisasikan grafik, perlu diketahui apa
itu fungsi dua variabel dan apa itu fungsi numerik.


## Fungsi Dua Variabel

Fungsi dua variabel adalah jenis fungsi di mana ada dua variabel bebas
(biasanya dinotasikan sebagai x dan y) yang menentukan nilai dari
fungsi tersebut. Dengan kata lain, untuk setiap kombinasi nilai dari x
dan y, fungsi ini akan menghasilkan satu nilai output tertentu. Fungsi
dari dua variabel yang mana setiap kombinasi nilai dari kedua variabel
tersebut menghasilkan sebuah nilai tunggal.


## Fungsi Numerik

Fungsi dimana setiap pasangan variabel independen adalah angka atau
bilangan nyata. Secara sederhana, ketika memasukkan angka atau
bilangan nyata ke variabel-variabel dalam fungsi maka hasil akhir yang
dihasilkan juga angka atau bilangan nyata, bukan simbol atau ekspresi
yang belum dihitung.


Contoh:


ada fungsi


$$f(x,y)=2x+y$$Ketika kita memasukkan bilangan nyata ke x dan y maka akan dihasilkan
suatu bilangan nyata juga. Misal masukkan x=1 dan y=1. Akan diperoleh


$$2(1)+1=3$$## Visualisasi Grafik

Untuk memvisualisaikan fungsi dua variabel dengan fungsinya
didefinisikan sebagai fungsi numerik, akan dibuat grafik 3D dengan
sintaks plot3d. Untuk membedakan fungsi numerik dengan simbolik, pada
kali ini untuk setiap fungsi numerik dua variabel hanya akan memuat
variabel x dan y. Namun, dalam pemakaian secara umum, bisa digunakan
variabel apapun.


Penulisan Sintaks:


1) definisikan fungsi numerik


function f(x,y):= ax+by dengan a dan b adalah suatu konstanta dan
fungsi tidak selalu direpresentastikan dengan f tetapi bisa dengan
huruf apapun. Contoh : g(x,y)


2) sintaks plot3d


plot3d("f"):


Contoh Visualisasi Grafik:


1. Visualisasi grafik fungsi linear dua variabel


$$f(x,y) = 9x+2y$$\>function f(x,y):= 9\*x+2\*y

\>plot3d("f"):


![images/3_EMT_3D-082.png](images/3_EMT_3D-082.png)

2. Visualisasi grafik fungsi kuadrat dua variabel


$$f(x,y)=x^2+2xy+y^2$$\>function f(x,y):= x^2+2\*x\*y+y^2 

\>plot3d("f"):


![images/3_EMT_3D-084.png](images/3_EMT_3D-084.png)

3. Visualisasi Grafik Fungsi Eksponen Dua Variabel


$$g(x,y) = 6x^{2y+8}$$\>function g(x,y):= 6\*x^(2y+8)

\>plot3d("g"):


![images/3_EMT_3D-086.png](images/3_EMT_3D-086.png)

4. Grafik Fungsi Logaritma Dua Variabel


$$f(x,y)=\log(xy)$$\>function f(x,y):= log(x\*y)

\>plot3d("f"):


![images/3_EMT_3D-088.png](images/3_EMT_3D-088.png)

5. Grafik Fungsi Trigonometri Dua Variabel


$$h(x,y)=sin(xy)cos(y)$$\>function h(x,y):= sin(x\*y)\*cos(y)

\>plot3d("h"): 


![images/3_EMT_3D-090.png](images/3_EMT_3D-090.png)

6. Grafik Fungsi Nilai Mutlak Dua Variabel


$$i(x,y)=|(2x+y)|$$\>function i(x,y):= abs(2x+y)

\>plot3d("i"):


![images/3_EMT_3D-092.png](images/3_EMT_3D-092.png)

# Latihan Soal

Buatlah visualisasi grafik dari fungsi berikut ini!


$$f(x,y)=8^x+3y$$\>function f(x,y):=8^x+3\*y

\>plot3d ("f"):


![images/3_EMT_3D-094.png](images/3_EMT_3D-094.png)

$$g(x,y)=sin(7x^2y+1)$$\>function g(x,y):= sin(7\*x^2\*y+1)

\>plot3d("g"):


![images/3_EMT_3D-096.png](images/3_EMT_3D-096.png)

$$h(x,y)=|16x+sin(y^3+1)|$$\>function h(x,y):=abs(16\*x + sin(y^3+1))

\>plot3d("h"):


![images/3_EMT_3D-098.png](images/3_EMT_3D-098.png)

## 4) Menggambar Grafik Fungsi Dua Variabel yang Fungsinya

## Didefinisikan sebagai Fungsi Simbolik

Grafik Fungsi dua variabel yang fungsinya didefinisikan sebagai fungsi
simbolik adalah suatu grafik yang memvisualisasikan Persamaan Linear
Dua Variabel (PLDV) dalam koordinat kartesius dengan fungsinya
merupakan fungsi simbolik.


Proses visualisasi ini memungkinkan Kita untuk melihat dan memahami
bagaimana fungsi tersebut berperilaku dalam tiga dimensi.


Sedangkan yang dimaksud dengan fungsi simbolik yaitu fungsi yang
didefinisikan dalam bentuk matematika simbolik, artinya kita memiliki
ekspresi matematika yang menggambarkan hubungan antara dua variabel.
misalnya, jika kita memiliki fungsi


$$f(x, y) = x^2 + y^2$$

kita dapat menggambar grafiknya untuk melihat bentuk permukaan yang
dihasilkan oleh fungsi ini dalam tiga dimensi. Grafik ini mungkin akan
berupa tumpukan parabola yang membentuk kerucut.


Karakteristik fungsi simbolik adalah dengan mengganti tanda := menjadi
&amp;=


Perbedaan utama antara fungsi numerik dan fungsi simbolik adalah bahwa
fungsi numerik memberikan hasil numerik secara langsung (menghasilkan
angka), sementara fungsi simbolik memungkinkan kita untuk bekerja
dengan simbol matematika sebelum menghitung nilai numeriknya. Pilihan
antara keduanya tergantung pada kebutuhan analisis matematika yang
kita lakukan.


Tujuan menggambar grafik fungsi dua variabel adalah untuk memahami
pola, sifat, dan hubungan antara dua variabel tersebut secara visual,
yang dapat membantu dalam analisis dan pemahaman masalah matematika
atau ilmu pengetahuan yang melibatkan fungsi ini.


## Langkah-langkah Membuat Grafik

1) Definisikan fungsinya terlebih dahulu. Tentukan fungsi dua variabel
yang akan divisualisasikan dalam bentuk simbolik.


Misal diambil fungsi


$$f(x,y)=4x^2+y^2$$

Maka perintah yang dapat dituliskan yaitu:


\>function f(x,y)&= 4\*x^2+y^2;


2) Panggil fungsinya


\>plot3d("f(x,y)"):


![images/3_EMT_3D-101.png](images/3_EMT_3D-101.png)

3) Tentukan rentang variabelnya


\>plot3d("f(x,y)",-5,5,0,6\*pi):


![images/3_EMT_3D-102.png](images/3_EMT_3D-102.png)

## Membuat Grafik Fungsi Linear

$$g(x,y)=8x+4y$$\>function g(x,y) &= 8\*x+4\*y;

\>plot3d("g(x,y)"):


![images/3_EMT_3D-104.png](images/3_EMT_3D-104.png)

$$M(x,y)=-12x+7y$$\>function M(x,y) &= -12\*x+7\*y;

\>plot3d("M(x,y)"):


![images/3_EMT_3D-106.png](images/3_EMT_3D-106.png)

Rentang variabel:


\>plot3d("M(x,y)",-2,2,0,6\*pi):


![images/3_EMT_3D-107.png](images/3_EMT_3D-107.png)

## Membuat Grafik Fungsi Kuadrat

$$Q(x,y)=5x^2-7y^2$$\>function Q(x,y) &= 5\*x^2 - 7\*y^2;

\>plot3d("Q(x,y)"):


![images/3_EMT_3D-109.png](images/3_EMT_3D-109.png)

$$P(x,y)=8x^2-2xy+6y^2$$\>function P(x,y) &= 8\*x^2-2\*x\*y+6\*y^2;

\>plot3d("P(x,y)"):


![images/3_EMT_3D-111.png](images/3_EMT_3D-111.png)

Rentang variabel:


\>plot3d("P(x,y)",-10,10,0,9\*pi):


![images/3_EMT_3D-112.png](images/3_EMT_3D-112.png)

## Membuat Grafik Fungsi Akar Kuadrat

$$A(x,y)= \sqrt{49x^2+16y^2}$$\>function A(x,y) &= sqrt(49\*x^2+16\*y^2);

\>plot3d("A"):


![images/3_EMT_3D-114.png](images/3_EMT_3D-114.png)

$$W(x,y)= \sqrt{6x^2-2y^2}$$\>function W(x,y) &= sqrt(6\*x^2-2\*y^2);

\>plot3d("W"):


![images/3_EMT_3D-116.png](images/3_EMT_3D-116.png)

Rentang Variabel:


\>plot3d("W(x,y)",-20,100,0,5\*pi):


![images/3_EMT_3D-117.png](images/3_EMT_3D-117.png)

## Membuat Grafik Fungsi Eksponensial

$$F(x,y)= 27.12^{xy}$$\>function F(x,y) &= 27\*12^(x\*y);

\>plot3d("F"):


![images/3_EMT_3D-119.png](images/3_EMT_3D-119.png)

$$H(x,y)=25.(-20)^{xy}$$\>function H(x,y) &= 25\*-12^(x\*y);

\>plot3d("H"):


![images/3_EMT_3D-121.png](images/3_EMT_3D-121.png)

$$T(x,y)=(-21).8^{xy}$$\>function T(x,y) &= -21\*8^(x\*y);

\>plot3d("T"):


![images/3_EMT_3D-123.png](images/3_EMT_3D-123.png)

## Membuat Grafik Fungsi Logaritma

$$B(x,y)=log(x.2y), Basis 10$$\>function B(x,y) &= log(x\*2\*y);

\>plot3d("B"):


![images/3_EMT_3D-125.png](images/3_EMT_3D-125.png)

$$C(x,y)=log(30x.45y), basis 10$$\>function C(x,y) &= log(30\*x\*45\*y);

\>plot3d("C"):


![images/3_EMT_3D-127.png](images/3_EMT_3D-127.png)

## Membuat Grafik Fungsi Trigonometri

$$D(x,y)=sin(6x).cos(16y)$$\>function D(x,y) &= sin(6\*x)\*cos(16\*y);

\>plot3d("D"):


![images/3_EMT_3D-129.png](images/3_EMT_3D-129.png)

$$J(x,y)=sin(2x).tan(y)$$\>function J(x,y) &= sin(2\*x)\*tan(y);

\>plot3d("J"):


![images/3_EMT_3D-131.png](images/3_EMT_3D-131.png)

## Membuat Grafik Fungsi Nilai Mutlak

$$T(x,y)=|2x^2-y^2|$$\>function T(x,y) &= abs(2\*x^2 - y^2);

\>plot3d("T"):


![images/3_EMT_3D-133.png](images/3_EMT_3D-133.png)

## Latihan

Buatlah grafik dari fungsi berikut:


$$A(x,y)=x^2y+3y^2$$\>function A(x,y) &= x^2\*y+3\*y^2;

\>plot3d ("A"):


![images/3_EMT_3D-135.png](images/3_EMT_3D-135.png)

$$B(x,y)=4y^2-2x^2y+4x^3+24x^2$$\>function B(x,y)&= 4\*y^2-2\*x^2\*y+4\*x^3+24\*x^2;

\>plot3d("B"):


![images/3_EMT_3D-137.png](images/3_EMT_3D-137.png)

$$C(x,y)=cosec(9x)-tan(2y)$$\>function C(x,y)&= cosec(9\*x)-tan(2\*y);

\>plot3d ("C"):


![images/3_EMT_3D-139.png](images/3_EMT_3D-139.png)

Beri rentang variabel untuk fungsi C(x,y):


-100,50,0,2*pi


\>plot3d("C(x,y)",-100,50,0,2\*pi): 


![images/3_EMT_3D-140.png](images/3_EMT_3D-140.png)

## 5) Menggambar Data $x$, $y$, $z$ pada ruang Tiga Dimensi (3D)

  Menggambar data pada ruang tiga dimensi (3D) adalah proses  

visualisasi data yang mengubah informasi dalam tiga dimensi, yaitu
panjang, lebar, dan tinggi, menjadi representasi visual yang dapat
dipahami dan dianalisis.


  Tujuan dari menggambar data 3D adalah untuk membantu pemahaman dan  

interpretasi data yang lebih baik, terutama ketika data tersebut
memiliki komponen yang tidak dapat direpresentasikan dengan baik dalam
dua dimensi.


Sama seperti plot2d, plot3d menerima data. Untuk objek 3D, kita perlu
menyediakan matriks nilai x-, y- dan z, atau tiga fungsi atau ekspresi
fx(x,y), fy(x,y), fz(x,y).


$$\gamma(t,s) = (x(t,s),y(t,s),z(t,s))$$Karena x,y,z adalah matriks, kita asumsikan bahwa (t,s) melalui sebuah
kotak persegi. Hasilnya, kita dapat memplot gambar persegi panjang di
ruang angkasa.


Kita dapat menggunakan bahasa matriks Euler untuk menghasilkan
koordinat secara efektif.


Dalam contoh berikut, kami menggunakan vektor nilai t dan vektor kolom
nilai s untuk membuat parameter permukaan bola. Dalam gambar kita
dapat menandai daerah, dalam kasus kita daerah kutub.


## Contoh 1 grafik fungsi

\>t=-1:0.1:1; s=(-1:0.1:1)'; plot3d(t,s,t\*s):


![images/3_EMT_3D-142.png](images/3_EMT_3D-142.png)

Penjelasan sintaks dari plot


- plot3d = membawa euler untuk mengetahui perintah apa yang harus
dilakukan


- ( ...) = tempat kita untuk memasukkan perintah yang kita inginkan


## Contoh 2

kita akan memebentuk plot dengan fungsi dibawah ini


$$5x^2 + y^2$$\>plot3d("5\*x^2+y^2"):


![images/3_EMT_3D-144.png](images/3_EMT_3D-144.png)

Selanjutnya kita akan menggambar garis pada plot dengan menggunakan
grid


\>plot3d("5\*x^2+y^2",grid=2):


![images/3_EMT_3D-145.png](images/3_EMT_3D-145.png)

Jika kita ingin memodifikasi plot dengan menambahkan warna pada plot,
bisa menggunakan fillcolor.


Fillcolor dapat diisi dengan 1 warna yang sama atau 2 warna yang
berbeda


\>plot3d("5\*x^2+y^2",grid= 2,fillcolor=[red,blue]):


![images/3_EMT_3D-146.png](images/3_EMT_3D-146.png)

## Contoh 3

Jika kita ingin membuat plot 3d pada fungsi


$$12x^2+y^3$$kita bisa menggunakan perintah seperti dibawah ini


\>plot3d("12x^2+y^3",grid=10,\>hue, color=red);

\>insimg()


![images/3_EMT_3D-148.png](images/3_EMT_3D-148.png)

Jika kita mau menebalkan warna pada gambar diatas makam bisa
menggunakan perintah


\>plot3d("12x^2+y^3",grid=10,fillcolor=[red,yellow]);

\>insimg()


![images/3_EMT_3D-149.png](images/3_EMT_3D-149.png)

## Contoh 4

Tentu saja, titik cloud juga dimungkinkan. Untuk memplot data titik
dalam ruang, kita membutuhkan tiga vektor untuk koordinat titik-titik
tersebut.


Gayanya sama seperti di plot2d dengan points=true;


\>n=500;...  
\>   plot3d(normal(1,n),normal(1,n),normal(1,n),points=true,style="."):


![images/3_EMT_3D-150.png](images/3_EMT_3D-150.png)

## 6) Membuat Gambar Grafik Tiga Dimensi (3D) yang

## Bersifat Interaktif dan animasi grafik 3D

Membuat gambar grafik tiga dimensi (3D) yang bersifat interaktif
adalah proses menciptakan visualisasi tiga dimensi yang memungkinkan
pengguna berinteraksi dengan objek-objek 3D. Interaktivitas dalam
gambar 3D memungkinkan pengguna untuk melakukan tindakan seperti
mengubah sudut pandang, memindahkan objek, atau berinteraksi dengan
elemen-elemen dalam adegan 3D. Sedangkan animasi grafik 3D dapat
mencakup pergerakan, tetapi juga dapat berarti perubahan dalam
tampilan atau atribut objek tanpa pergerakan fisik yang mencolok.


Interaksi user dimungkinkan dengan parameter &gt;user. dengan perintah
&gt;user kita dapat menekan tombol berikut.


* 
kiri, kanan, atas, bawah: memutar sudut pandang

* 
+,-: memperbesar atau memperkecil

* 
a: menghasilkan anaglyph (lihat di bawah)

* 
l : tombol nyalakan sumber cahaya (lihat dibawah)

* 
spasi: reset ke default

* 
kembali: akhiri interaksi


\>plot3d("exp(-x^2+y^2)",\>user,...  
\>   title="Coba gerakkan"): 


![images/3_EMT_3D-151.png](images/3_EMT_3D-151.png)

\>plot3d("exp(x^2+y^2)",\>user,...  
\>   title="Coba gerakkan)"):


![images/3_EMT_3D-152.png](images/3_EMT_3D-152.png)

## Animasi 3D

\>function testplot () := plot3d("x^2+y^3");...  
\>   rotate("testplot"); testplot():


![images/3_EMT_3D-153.png](images/3_EMT_3D-153.png)

Fungsi rotate yaitu untuk memutar plot.


Fungsi ini akan membuat animasi plot 3D dari fungsi


$$4x^2 + y^3$$

yang berputar di sekitar sumbu z dari sudut 0 hingga 360 derajat


\>plot3d("exp(-(4\*x^2+y^2)/5)",r=10,n=80,fscale=8,scale=1.2,frame=3,\>user):


![images/3_EMT_3D-155.png](images/3_EMT_3D-155.png)

Ada beberapa parameter untuk menskalakan fungsi atau mengubah tampilan
grafik.


fscale: menskalakan ke nilai fungsi (defaultnya adalah &lt;fscale).


scale: angka atau vektor 1x2 untuk diskalakan ke arah x dan y.


frame: jenis bingkai (default 1).


\>plot3d("4\*x^2+y^2",distance=10,zoom=5,angle=0,height=5):


![images/3_EMT_3D-156.png](images/3_EMT_3D-156.png)

Tampilan dapat diubah dengan berbagai cara.


* 
distance: jarak pandang ke plot.

* 
zoom: nilai zoom.

* 
angle: sudut terhadap sumbu y negatif dalam radian.

* 
height: ketinggian tampilan dalam radian.


\>plot3d("x^4+y^2",a=0,b=1,c=-1,d=1,angle=-20°,height=20°,...  
\>   center=[0,0,1],zoom=5):


![images/3_EMT_3D-157.png](images/3_EMT_3D-157.png)

Plot selalu terlihat berada di tengah kubus plot. Kita dapat
memindahkan bagian tengah dengan center parameter.


\>plot3d("x^2+1",a=-1,b=1,rotate=true,grid=5):


![images/3_EMT_3D-158.png](images/3_EMT_3D-158.png)

Parameter memutar memutar fungsi dalam x di sekitar sumbu x.


* 
rotate=1: Menggunakan sumbu x

* 
rotate=2: Menggunakan sumbu z


## 7) Menggambar Fungsi Parametrik Tiga Dimensi (3D)

## Pengertian

Fungsi parametrik adalah jenis fungsi matematika yang menggambarkan
hubungan antara dua atau lebih variabel, di mana setiap variabel
dinyatakan sebagai fungsi dari satu atau lebih parameter. Fungsi
parametrik digunakan untuk menggambarkan kurva, lintasan, atau
hubungan antara berbagai variabel yang bergantung pada
parameter-parameter tertentu.


Fungsi parametrik merupakan salah satu cara mendefinisikan kurva atau
permukaan dalam ruang 2D atau 3D menggunakan satu atau lebih parameter
independen.


* 
Dalam 2D, kurva dinyatakan sebagai x(t) dan y(t), di mana adalah t
* adalah parameter yang mengontrol posisi sepanjang kurva.

* 
Dalam 3D, kita menggunakan tiga persamaan parametrik untuk
* mendeskripsikan posisi x,y,z sebagai fungsi dari parameter t.Fungsi
* ini ditulis sebagai:
* x=f(t),
* y=g(t),
* z=h(t),


## Contoh Soal

\>plot3d("cos(x)\*cos(y)","sin(x)\*cos(y)","sin(y)", a=0,b=2\*pi,c=pi/2,d=-pi/2,...  
\>   \>hue,color=yellow,light=[0,1,0],<frame,...  
\>   n=90,grid=[25,50],wirecolor=black,zoom=4):


![images/3_EMT_3D-159.png](images/3_EMT_3D-159.png)

\>aspect(16/9); allwindow; ...  
\>   x:=linspace(0,2\*pi,100); y:=(-1:0.1:1)'; ...  
\>   plot3d(sin(x)\*(y/2\*sin(x/2)),cos(x)\*(y/2\*sin(x/2)),y/2\*cos(x/2), ...  
\>   <frame,hue=2,max=0.5,scale=1.5):


![images/3_EMT_3D-160.png](images/3_EMT_3D-160.png)

\>aspect(16/9); allwindow;...  
\>   x:=linspace(0,2\*pi,100); y:=(-1:0.1:1)';...  
\>   plot3d(sin(x)\*(y/2\*sin(x/2)),cos(x)\*(y/2\*sin(x/2)),y/2\*cos(x/2),...  
\>   \>lines,<frame,xmin=0,xmax=10,n=10,\>user):


![images/3_EMT_3D-161.png](images/3_EMT_3D-161.png)

\>reset;...  
\>   S:=normal(10,1250); plot3d(S[3],S[6],S[9],\>points,style="."):


![images/3_EMT_3D-162.png](images/3_EMT_3D-162.png)

\>S:=normal(10,1250); T:=cumsum(normal(10,1250));...  
\>   plot3d(T[2],T[5],T[8],\>wire,...  
\>   linewidth=2,\>anaglyph,zoom=3):


![images/3_EMT_3D-163.png](images/3_EMT_3D-163.png)

\>P=cumsum(normal(5,75));...  
\>   plot3d(P[3],P[4],P[5],\>anaglyph,\>wire):


![images/3_EMT_3D-164.png](images/3_EMT_3D-164.png)

## 8) Menggambar Fungsi Implisit Tiga Dimensi (3D)

Fungsi implisit (implicit function) adalah fungsi yang memuat lebih
dari satu variabel, berjenis variabel bebas dan variabel terikat yang
berada dalam satu ruas sehingga tidak bisa dipisahkan pada ruas yang
berbeda.


$$F(x,y,z)=0$$

(1 persamaan dan 3 variabel), terdiri dari 2 variabel bebas dan 1
terikat


Misalnya, F(x, y, z) = x^2 + y^2 + z^2 - 1 = 0 adalah persamaan
implisit yang menggambarkan bola dengan jari-jari 1 dan pusat di
(0,0,0).


Plot Implisit


Ada juga plot implisit dalam tiga dimensi. Euler menghasilkan
pemotongan melalui objek. Fitur plot3d mencakup plot implisit. Plot
ini menunjukkan himpunan nol suatu fungsi dalam tiga variabel.


Solusi dari


$$f(x,y,z) = 0$$dapat divisualisasikan dalam potongan yang sejajar dengan bidang x-y,
x-z, z-x dan y-z.


* 
implisit=1: dipotong sejajar bidang y-z

* 
implisit=2: dipotong sejajar dengan bidang x-z

* 
implisit=3: dipotong sejajar dengan bidang z-x (yang berarti
* pemotongan dilakukan dengan mempertahankan nilai y konstan)

* 
implisit=4: dipotong sejajar bidang x-y


Tambahkan nilai-nilai ini, jika Anda mau. Dalam contoh kita memplot


$$M = \{ (x,y,z) : x^2+y^3+zy=1 \}$$---

## Contoh Fungsi Implisit

\>plot3d("4\*x^2+y^3+z\*y-1",r=7,implicit=2):


![images/3_EMT_3D-168.png](images/3_EMT_3D-168.png)

\>plot3d("12\*x^2 + 9\*y^2 + 4\*z^2 - 25",r=8,implicit=4):


![images/3_EMT_3D-169.png](images/3_EMT_3D-169.png)

\>c=1; d=1;

\>plot3d("((x^2+y^2-c^2)^2+(z^2-1)^2)\*((y^2+z^2-c^2)^2+(x^2-1)^2)\*((z^2+x^2-c^2)^2+(y^2-1)^2)-d",r=2,<frame,\>implicit,\>user):


![images/3_EMT_3D-170.png](images/3_EMT_3D-170.png)

## Latihan soal

Gambarlah Fungsi implisit berikut dalam 3D


$$f(x,y,z)=5x^2+y^2-6z^2-12$$\>plot3d("5\*x^2+y^2-6\*z^2-12",r=8,implicit=3):


![images/3_EMT_3D-172.png](images/3_EMT_3D-172.png)

Gambarlah fungsi 3D dari fungsi implisit berikut ini


$$f(x,y,z)=xy+x^3y^2+xz^3-12=0$$

dengan r=4


\>plot3d("x\*y+x^3\*y^2+x\*z^3-12", r=4, implicit=3):


![images/3_EMT_3D-174.png](images/3_EMT_3D-174.png)

## 9) Mengatur tampilan, warna dan sudut pandang gambar permukaan

## Tiga Dimensi (3D) Dan Menampilkan kontur dan bidang kontur

## permukaan Tiga Dimensi(3D)

Untuk plot, Euler menambahkan garis grid. Sebagai gantinya
dimungkinkan untuk menggunakan garis level dan rona satu warna atau
rona berwarna spektral. Euler dapat menggambar tinggi fungsi pada plot
dengan bayangan. Di semua plot 3D, Euler dapat menghasilkan anaglyph
merah/sian.


-&gt; hue: Menyalakan bayangan cahaya alih-alih kabel.


-&gt; kontur: Memplot garis kontur otomatis pada plot.


- level=... (atau level): Sebuah vektor nilai untuk garis kontur.


Standarnya adalah level="auto", yang menghitung beberapa garis level
secara otomatis. Seperti yang Anda lihat di plot, level sebenarnya
adalah rentang level.


Gaya default dapat diubah. Untuk plot kontur berikut, kami menggunakan
grid yang lebih halus untuk 100x100 poin, skala fungsi dan plot, dan
menggunakan sudut pandang yang berbeda.


\>plot3d("exp(-x^2-y^2)",r=2,n=100,level="thin", ...  
\>    \>contour,\>spectral,fscale=1,scale=1.1,angle=45°,height=20°):


![images/3_EMT_3D-175.png](images/3_EMT_3D-175.png)

\>plot3d("exp(x\*y)",angle=100°,\>contour,color=yellow):


![images/3_EMT_3D-176.png](images/3_EMT_3D-176.png)

Bayangan default menggunakan warna abu-abu. Tetapi rentang warna
spektral juga tersedia.


-&gt; spektral: Menggunakan skema spektral default


- color=...: Menggunakan warna khusus atau skema spektral


Untuk plot berikut, kami menggunakan skema spektral default dan
menambah jumlah titik untuk mendapatkan tampilan yang sangat halus.


\>plot3d("x^2+y^2",\>spectral,\>contour,n=100):


![images/3_EMT_3D-177.png](images/3_EMT_3D-177.png)

Alih-alih garis level otomatis, kita juga dapat mengatur nilai garis
level. Ini akan menghasilkan garis level tipis alih-alih rentang
level.


\>plot3d("x^2-y^2",0,1,0,1,angle=220°,level=-1:0.2:1,color=redgreen):


![images/3_EMT_3D-178.png](images/3_EMT_3D-178.png)

Dalam plot berikut, kami menggunakan dua pita level yang sangat luas
dari -0,1 hingga 1, dan dari 0,9 hingga 1. Ini dimasukkan sebagai
matriks dengan batas level sebagai kolom.


Selain itu, kami melapisi kisi dengan 10 interval di setiap arah.


\>plot3d("x^2+y^3",level=[-0.1,0.9;0,1], ...  
\>     \>spectral,angle=30°,grid=10,contourcolor=blue):


![images/3_EMT_3D-179.png](images/3_EMT_3D-179.png)

Dalam contoh berikut, kami memplot himpunan, di mana


$$f(x,y) = x^y-y^x = 0$$Kami menggunakan satu garis tipis untuk garis level.


\>plot3d("x^y-y^x",level=0,a=0,b=6,c=0,d=6,contourcolor=red,n=100):


![images/3_EMT_3D-181.png](images/3_EMT_3D-181.png)

Dimungkinkan untuk menunjukkan bidang kontur di bawah plot. Warna dan
jarak ke plot dapat ditentukan.


\>plot3d("x^2+y^4",\>cp,cpcolor=green,cpdelta=0.2):


![images/3_EMT_3D-182.png](images/3_EMT_3D-182.png)

Berikut adalah beberapa gaya lagi. Kami selalu mematikan frame, dan
menggunakan berbagai skema warna untuk plot dan grid.


\>figure(2,2); ...  
\>   expr="y^3-x^2"; ...  
\>   figure(1);  ...  
\>     plot3d(expr,<frame,\>cp,cpcolor=spectral); ...  
\>   figure(2);  ...  
\>     plot3d(expr,<frame,\>spectral,grid=10,cp=2); ...  
\>   figure(3);  ...  
\>     plot3d(expr,<frame,\>contour,color=gray,nc=5,cp=3,cpcolor=greenred); ...  
\>   figure(4);  ...  
\>     plot3d(expr,<frame,\>hue,grid=10,\>transparent,\>cp,cpcolor=gray); ...  
\>   figure(0):


![images/3_EMT_3D-183.png](images/3_EMT_3D-183.png)

Ada beberapa skema spektral lainnya, bernomor dari 1 hingga 9. Tetapi
Anda juga dapat menggunakan warna=nilai, di mana nilai


* 
spektral: untuk rentang dari biru ke merah

* 
putih: untuk rentang yang lebih redup

* 
kuningbiru,ungu hijau,birukuning,hijaumerah

* 
birukuning, hijau ungu, kuning biru, merah hijau


\>figure(3,3); ...  
\>   for i=1:9;  ...  
\>     figure(i); plot3d("x^2+y^2",spectral=i,\>contour,\>cp,<frame,zoom=4);  ...  
\>   end; ...  
\>   figure(0):


![images/3_EMT_3D-184.png](images/3_EMT_3D-184.png)

Sumber cahaya dapat diubah dengan l dan tombol kursor selama interaksi
pengguna. Itu juga dapat diatur dengan parameter.


* 
cahaya: arah untuk cahaya

* 
amb: cahaya sekitar antara 0 dan 1


Perhatikan bahwa program tidak membuat perbedaan antara sisi plot.
Tidak ada bayangan. Untuk ini, Anda perlu Povray.


\>plot3d("-x^2-y^2", ...  
\>     hue=true,light=[0,1,1],amb=0,user=true, ...  
\>     title="Press l and cursor keys (return to exit)"):


![images/3_EMT_3D-185.png](images/3_EMT_3D-185.png)

Parameter warna mengubah warna permukaan. Warna garis level juga dapat
diubah.


\>plot3d("-x^2-y^2",color=rgb(0.2,0.2,0),hue=true,frame=false, ...  
\>     zoom=3,contourcolor=red,level=-2:0.1:1,dl=0.01):


![images/3_EMT_3D-186.png](images/3_EMT_3D-186.png)

Warna 0 memberikan efek pelangi khusus.


\>plot3d("x^2/(x^2+y^2+1)",color=0,hue=true,grid=10):


![images/3_EMT_3D-187.png](images/3_EMT_3D-187.png)

Permukaannya juga bisa transparan.


\>plot3d("x^2+y^2",\>transparent,grid=10,wirecolor=red):


![images/3_EMT_3D-188.png](images/3_EMT_3D-188.png)

## 10) Menggambar Diagram Batang Tiga Dimensi

Bar plots/plot batang juga dimungkinkan. Untuk itu, kita harus
menyediakannya


* 
x: vektor baris dengan n+1 elemen

* 
y: vektor kolom dengan n+1 elemen

* 
z: matriks nilai nxn.


z bisa lebih besar, tetapi hanya nilai nxn yang akan digunakan.


Dalam contoh ini, pertama-tama kita menghitung nilainya. Kemudian kita
sesuaikan x dan y, sehingga vektor-vektornya berpusat pada nilai yang
digunakan.


\>x=-1:0.1:1; y=x'; z=x^2+y^2; ...  
\>   xa=(x|1.1)-0.05; ya=(y\_1.1)-0.05; ...  
\>   plot3d(xa,ya,z,bar=true):


![images/3_EMT_3D-189.png](images/3_EMT_3D-189.png)

\>x=-0.01:0.1:1; y=x'; z=x+2/3\*y; ...  
\>   xa=(x|1.1)-0.05; ya=(y\_1.1)-0.05; ...  
\>   plot3d(xa,ya,z,bar=true):


![images/3_EMT_3D-190.png](images/3_EMT_3D-190.png)

\>x=-0.01:0.1:1; y=x'; z=1/2\*x+1/2\*y; ...  
\>   xa=(x|1.1); ya=(y\_1.1); ...  
\>   plot3d(xa,ya,z,bar=true):


![images/3_EMT_3D-191.png](images/3_EMT_3D-191.png)

Dimungkinkan untuk membagi plot suatu permukaan menjadi dua bagian
atau lebih.


\>x=-1:0.1:1; y=x'; z=1/10\*x+1/10\*y; d=zeros(size(x)); ...  
\>   plot3d(x,y,z,disconnect=2:2:5):


![images/3_EMT_3D-192.png](images/3_EMT_3D-192.png)

\>x=-1:0.1:1; y=x'; z=x+y; d=zeros(size(x)); ...  
\>   plot3d(x,y,z,disconnect=2:2:20):


![images/3_EMT_3D-193.png](images/3_EMT_3D-193.png)

Jika memuat atau menghasilkan matriks data M dari file dan perlu
memplotnya dalam 3D, Anda dapat menskalakan matriks ke [-1,1] dengan
skala(M), atau menskalakan matriks dengan &gt;zscale. Hal ini dapat
dikombinasikan dengan faktor penskalaan individual yang diterapkan
sebagai tambahan.


\>i=1:20; j=i'; ...  
\>   plot3d(i\*j^2+100\*normal(20,20),\>zscale,scale=[1,1,1.5],angle=-40°,zoom=1.8):


![images/3_EMT_3D-194.png](images/3_EMT_3D-194.png)

\>Z=intrandom(5,100,6); v=zeros(5,6); ...  
\>   loop 1 to 5; v[#]=getmultiplicities(1:6,Z[#]); end; ...  
\>   columnsplot3d(v',scols=1:5,ccols=[1:5]):


![images/3_EMT_3D-195.png](images/3_EMT_3D-195.png)

\>Z=intrandom(6,100,6); v=zeros(6,2); ...  
\>   loop 1 to 6; v[#]=getmultiplicities(1:2,Z[#]); end; ...  
\>   columnsplot3d(v',scols=1:6,ccols=[1:6]):


![images/3_EMT_3D-196.png](images/3_EMT_3D-196.png)

\>Z=intrandom(7,1000,6); v=zeros(7,1); ...  
\>   loop 1 to 7; v[#]=getmultiplicities(1:1,Z[#]); end; ...  
\>   columnsplot3d(v',scols=1:7,ccols=[1:7]):


![images/3_EMT_3D-197.png](images/3_EMT_3D-197.png)

## 11) Menggambar Permukaan Benda Putar

\>plot2d("(x^2+y^2-1)^3-x^2\*y^3",r=1.3, ...  
\>   style="#",color=blue,<outline, ...  
\>   level=[-2;0],n=100):


![images/3_EMT_3D-198.png](images/3_EMT_3D-198.png)

\>ekspresi &= (x^2+y^2-1)^3-x^2\*y^3; $ekspresi


$$\left(y^2+x^2-1\right)^3-x^2\,y^3$$Kami ingin memutar kurva jantung di sekitar sumbu y. Berikut adalah
ungkapan, yang mendefinisikan hati:


$$f(x,y)=(x^2+y^2-1)^3-x^2.y^3.$$Selanjutnya kita atur


$$x=r.cos(a),\quad y=r.sin(a).$$\>function fr(r,a) &= ekspresi with [x=r\*cos(a),y=r\*sin(a)] | trigreduce; $fr(r,a)


$$\left(r^2-1\right)^3+\frac{\left(\sin \left(5\,a\right)-\sin \left(  3\,a\right)-2\,\sin a\right)\,r^5}{16}$$Hal ini memungkinkan untuk mendefinisikan fungsi numerik, yang
memecahkan r, jika a diberikan. Dengan fungsi itu kita dapat memplot
jantung yang diputar sebagai permukaan parametrik.


\>function map f(a) := bisect("fr",0,2;a); ...  
\>   t=linspace(-pi/2,pi/2,100); r=f(t);  ...  
\>   s=linspace(pi,2pi,100)'; ...  
\>   plot3d(r\*cos(t)\*sin(s),r\*cos(t)\*cos(s),r\*sin(t), ...  
\>   \>hue,<frame,color=yellow,zoom=4,amb=0,max=0.7,grid=12,height=50°):


![images/3_EMT_3D-203.png](images/3_EMT_3D-203.png)

Berikut ini adalah plot 3D dari gambar di atas yang diputar di sekitar
sumbu z. Kami mendefinisikan fungsi, yang menggambarkan objek.


\>function f(x,y,z) ...


    r=x^2+y^2;
    return (r+z^2-1)^3-r*z^3;
     endfunction
</pre>
\>plot3d("f(x,y,z)", ...  
\>   xmin=0,xmax=1.2,ymin=-1.2,ymax=1.2,zmin=-1.2,zmax=1.4, ...  
\>   implicit=1,angle=-30°,zoom=2.5,n=[10,60,60],\>anaglyph):


![images/3_EMT_3D-204.png](images/3_EMT_3D-204.png)

## 12) Menggambar Grafik 3D dengan Povray di EMT

Menggambar Povray Dengan bantuan file Euler povray.e, Euler dapat
menghasilkan file Povray. Hasilnya sangat bagus untuk dilihat.


Untuk dapat menjalankan sintaks dalam povray perlu menginstal Povray
(32bit atau 64bit) dari http://www.povray.org/, dan meletakkan
sub-direktori "bin" dari Povray ke pathway, atau mengatur variabel
"defaultpovray" dengan path lengkap yang menunjuk ke "pvengine.exe".


Interface Povray dari Euler menghasilkan file Povray di direktori home
pengguna, dan memanggil Povray untuk mengurai file-file ini. Nama file
default adalah current.pov, dan direktori default adalah eulerhome(),
biasanya c:\Users\Username\Euler. Povray menghasilkan file PNG, yang
dapat dimuat oleh Euler ke dalam buku catatan. Untuk membersihkan
file-file ini, gunakan povclear().


Sintaks yang digunakan untuk menjalankan povray adalah pov3d. Fungsi
pov3d memiliki komponen yang sama dengan plot3d. Ini dapat
menghasilkan grafik fungsi f(x,y), atau permukaan dengan koordinat
X,Y,Z dalam matriks, termasuk garis level opsional. Fungsi ini memulai
raytracer secara otomatis, dan memuat gambar ke dalam notebook Euler.


Selain pov3d(), ada banyak fungsi yang menghasilkan objek Povray.
Fungsi-fungsi ini mengembalikan string, yang berisi kode Povray untuk
objek. Untuk menggunakan fungsi ini, mulai file Povray dengan
povstart(). Kemudian gunakan writeln(...) untuk menulis objek ke file
gambar. Terakhir, akhiri file dengan povend(). Secara default,
raytracer akan dimulai, dan PNG akan dimasukkan ke dalam notebook
Euler.


Fungsi objek memiliki parameter yang disebut "look", yang membutuhkan
string dengan kode Povray untuk tekstur dan hasil akhir objek. Fungsi
povlook() dapat digunakan untuk menghasilkan string ini. Ini memiliki
parameter untuk warna, transparansi, Phong Shading dll.


Lingkup Povray memiliki sistem koordinat lain. Interface ini
menerjemahkan semua koordinat ke sistem Povray. Jadi Anda dapat terus
berpikir dalam sistem koordinat Euler dengan z menunjuk vertikal ke
atas, dan x,y,z sumbu dalam arti tangan kanan.


Anda perlu memuat file povray.


\>load povray;


Pastikan, direktori bin Povray ada di path. Jika tidak, edit variabel
berikut sehingga berisi path ke povray yang dapat dieksekusi.


\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

## Contoh Penggunaan



Akan diberikan contoh sederhana penggunaan povray pada EMT


Perintah berikut menghasilkan file povray di direktori pengguna dan
menjalankan Povray untuk ray tracing file ini.


Jika memulai perintah berikut, GUI Povray akan terbuka, menjalankan
file, dan menutup secara otomatis. Karena alasan keamanan, akan
ditanya, apakah ingin mengizinkan file exe untuk dijalankan. Agar
pertanyaan tersebut tidak muncul lagi bisa dipilih batal.


\>pov3d("3\*x^2+4\*y^2",zoom=4);


![images/3_EMT_3D-205.png](images/3_EMT_3D-205.png)

hasil visualisasi fungsi dapat dibuat menjadi transparan dan
menambahkan hasil akhir lainnya.


\> pov3d("(x^2+y^3)",axiscolor=blue,angle=30°, ...  
\>     look=povlook(yellow,0.2),level=-1:0.5:1,zoom=3);


![images/3_EMT_3D-206.png](images/3_EMT_3D-206.png)

\>pov3d("((x-1)^2+(y+1)^2)\*((x+1)^2+y^2)/40",r=1.5, ...  
\>     angle=120°,level=1/40,dlevel=0.005,light=[-1,1,1],height=45°,n=50, ...  
\>     <fscale,zoom=3.8);


![images/3_EMT_3D-207.png](images/3_EMT_3D-207.png)

## Object Povray



Contoh-contoh di atas tadi merupakan visualisasi permukaan fungsi
dengan menggunakan sintaks pov3d. Untuk menghasilkan objek dalam
povray perlu ditulis menjadi file povray.


Untuk menghasilkan output dimulai dengan povstart()


\>load povray; ...  
\>   defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

\>povstart(zoom=3.5)

\>c1=povcylinder(-povx,povx,1,povlook(orange)); ...  
\>   c2=povcylinder(-povy,povy,1,povlook(yellow)); ...  
\>   c3=povcylinder(-povz,povz,1,povlook(lightblue));


Di atas telah didefinisikan tiga silinder yang disimpan dalam string


di Euler. Fungsi povx(), povy(), dll. hanya mengembalikan vektor


[1,0,0] yang dapat digunakan sebagai gantinya.


\>c1


    cylinder { &lt;-1,0,0&gt;, &lt;1,0,0&gt;, 1
     texture { pigment { color rgb &lt;0.941176,0.509804,0.392157&gt; }  } 
     finish { ambient 0.2 } 
     }

Akan ditambahkan tekstur ke objek dengan tiga warna berbeda yaitu
orange, yellow, dan lightblue.


Untuk menamahkan tekstur ini dapat digunakan sintaks povlook(), yang
mengembalikan string dengan kode Povray yang relevan. Selain
menambahkan warna, ditambahkan juga transparansi dan cahaya.


\>povlook(rgb(0.1,0.2,0.3),0.1,0.5)


     texture { pigment { color rgbf &lt;0.101961,0.2,0.301961,0.1&gt; }  } 
     finish { ambient 0.5 } 
    

\>writeln(povintersection([c1,c2,c3]));

\>povend;


![images/3_EMT_3D-208.png](images/3_EMT_3D-208.png)

## Contoh Lain

Akan ditampilkan fungsi untuk membuat sebuah donat


\>povstart(angle=0,height=45°); //height untuk menampilkan fungsi dengan suatiu derajat tertentu 

\>function povdonat (r1,r2,look="") := "torus {"+r1+","+r2+look+"}"; //fungsi untuk menampilkan sebuah donat

\>writeln(povobject(povdonat(1,0.5),povlook(lightblue,\>phong),xrotate(90°)));

\>povend();


![images/3_EMT_3D-209.png](images/3_EMT_3D-209.png)

## 13) Menggambar Grafik Tiga Dimensi alam modus anaglif

Untuk menghasilkan anaglyph untuk kacamata merah/sian, Povray harus
berjalan dua kali dari posisi kamera yang berbeda. Ini menghasilkan
dua file Povray dan dua file PNG, yang dimuat dengan fungsi
loadanaglyph().


Tentu saja, Anda memerlukan kacamata merah/sian untuk melihat contoh
berikut dengan benar.


Fungsi pov3d() memiliki sakelar sederhana untuk menghasilkan
anaglyphs.


\>pov3d("-exp(-x^2-y^2)/2",r=2,height=45°,\>anaglyph, ...  
\>     center=[0,0,0.5],zoom=3.5);


![images/3_EMT_3D-210.png](images/3_EMT_3D-210.png)

Jika Anda membuat adegan dengan objek, Anda perlu menempatkan generasi
adegan ke dalam fungsi, dan menjalankannya dua kali dengan nilai yang
berbeda untuk parameter anaglyph.


\>function myscene ...


      s=povsphere(povc,1);
      cl=povcylinder(-povz,povz,0.5);
      clx=povobject(cl,rotate=xrotate(90°));
      cly=povobject(cl,rotate=yrotate(90°));
      c=povbox([-1,-1,0],1);
      un=povunion([cl,clx,cly,c]);
      obj=povdifference(s,un,povlook(red));
      writeln(obj);
      writeAxes();
    endfunction
</pre>
Fungsi povanaglyph() melakukan semua ini. Parameternya seperti di
povstart() dan povend() digabungkan.


\>povanaglyph("myscene",zoom=4.5);


![images/3_EMT_3D-211.png](images/3_EMT_3D-211.png)

## 14) Fungsi Implisit menggunakan Povray

Povray dapat memplot himpunan di mana f(x,y,z)=0, seperti parameter
implisit di plot3d. Namun hasilnya terlihat jauh lebih baik.


Sintaks untuk fungsinya sedikit berbeda. Anda tidak dapat menggunakan
keluaran ekspresi Maxima atau Euler.


$$((x^2+y^2-c^2)^2+(z^2-1)^2)*((y^2+z^2-c^2)^2+(x^2-1)^2)*((z^2+x^2-c^2)^2+(y^2-1)^2)=d$$\>load povray;

\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

\>povstart(angle=25°,height=10°);

\>writeln(povsurface("pow(x,2)+pow(y,2)\*pow(z,2)-1",povlook(blue),povbox(-2,2,"")));

\>povend();


![images/3_EMT_3D-213.png](images/3_EMT_3D-213.png)

\>load povray;

\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

\>povstart(angle=70°,height=50°,zoom=4);

\>writeln(povsurface("pow(x,2)\*y-pow(y,3)-pow(z,2)",povlook(green))); ...  
\>   writeAxes(); ...  
\>   povend();


![images/3_EMT_3D-214.png](images/3_EMT_3D-214.png)

\>load povray;

\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

\>povstart(angle=70°,height=30°);

\>writeln(povsurface("pow(x,2)+pow(y,2)\*pow(z,2)-1",povlook(red),povbox(-2,2,"")));

\>povend();


![images/3_EMT_3D-215.png](images/3_EMT_3D-215.png)

## Contoh lain

\>povstart(angle=45, height=100);

\>defaultpovray="C:\\Program Files\\POV-Ray\\v3.7\\bin\\pvengine.exe"


    C:\Program Files\POV-Ray\v3.7\bin\pvengine.exe

\>writeln(povsurface("pow(x,2)+pow(y,3)\*pow(z,2)-1", povlook(blue),povbox(-25,4,""))); 

\>povend(); 


![images/3_EMT_3D-216.png](images/3_EMT_3D-216.png)

## 15) Menggambar Titik pada ruang Tiga Dimensi (3D)

Alih-alih fungsi, kita dapat memplot dengan koordinat. Seperti pada
plot3d, kita membutuhkan tiga matriks untuk mendefinisikan objek.


Dalam contoh kita memutar fungsi di sekitar sumbu z.


\>function f(x) := x^3-x+1; ...  
\>   x=-1:0.01:1; t=linspace(0,2pi,8)'; ...  
\>   Z=x; X=cos(t)\*f(x); Y=sin(t)\*f(x); ...  
\>   pov3d(X,Y,Z,angle=40°,height=20°,axis=0,zoom=4,light=[10,-5,5]);


![images/3_EMT_3D-217.png](images/3_EMT_3D-217.png)

Dalam contoh berikut, kami memplot gelombang teredam. Kami
menghasilkan gelombang dengan bahasa matriks Euler.


Kami juga menunjukkan, bagaimana objek tambahan dapat ditambahkan ke
adegan pov3d. Untuk pembuatan objek, lihat contoh berikut. Perhatikan
bahwa plot3d menskalakan plot, sehingga cocok dengan kubus satuan.


\>r=linspace(0,1,80); phi=linspace(0,2pi,80)'; ...  
\>   x=r\*cos(phi); y=r\*sin(phi); z=exp(-5\*r)\*cos(8\*pi\*r)/3;  ...  
\>   pov3d(x,y,z,zoom=5,axis=0,add=povsphere([0,0,0.5],0.1,povlook(green)), ...  
\>     w=500,h=300);


![images/3_EMT_3D-218.png](images/3_EMT_3D-218.png)

Dengan metode bayangan canggih dari Povray, sangat sedikit titik yang
dapat menghasilkan permukaan yang sangat halus. Hanya di perbatasan
dan dalam bayang-bayang triknya mungkin menjadi jelas.


Untuk ini, kita perlu menambahkan vektor normal di setiap titik
matriks.


\>Z &= 4\*x^2\*y^3


    
                                      2  3
                                   4 x  y
    

Persamaan permukaannya adalah [x,y,Z]. Kami menghitung dua turunan ke
x dan y ini dan mengambil produk silang sebagai normal.


\>dx &= diff([x,y,Z],x); dy &= diff([x,y,Z],y);


Kami mendefinisikan normal sebagai produk silang dari turunan ini, dan
mendefinisikan fungsi koordinat.


\>N &= crossproduct(dx,dy); NX &= N[1]; NY &= N[2]; NZ &= N[3]; N,


    
                                  3        2  2
                          [- 8 x y , - 12 x  y , 1]
    

Kami hanya menggunakan 25 poin.


\>x=-1:0.5:1; y=x';

\>pov3d(x,y,Z(x,y),angle=10°, ...  
\>     xv=NX(x,y),yv=NY(x,y),zv=NZ(x,y),<shadow);


![images/3_EMT_3D-219.png](images/3_EMT_3D-219.png)

Berikut ini adalah simpul Trefoil yang dilakukan oleh A. Busser di
Povray. Ada versi yang ditingkatkan dari ini dalam contoh.


  <a href="Contoh\Trefoil Simpul.html">Simpul trefoil</a>  

Untuk tampilan yang bagus dengan tidak terlalu banyak titik, kami
menambahkan vektor normal di sini. Kami menggunakan Maxima untuk
menghitung normal bagi kami. Pertama, ketiga fungsi koordinat sebagai
ekspresi simbolik.


\>X &= ((4+sin(3\*y))+cos(x))\*cos(2\*y); ...  
\>   Y &= ((4+sin(3\*y))+cos(x))\*sin(2\*y); ...  
\>   Z &= sin(x)+2\*cos(3\*y);


Kemudian kedua vektor turunan ke x dan y.


\>dx &= diff([X,Y,Z],x); dy &= diff([X,Y,Z],y);


Sekarang normal, yang merupakan produk silang dari dua turunan.


\>dn &= crossproduct(dx,dy);


Kami sekarang mengevaluasi semua ini secara numerik.


\>x:=linspace(-%pi,%pi,40); y:=linspace(-%pi,%pi,100)';


Vektor normal adalah evaluasi dari ekspresi simbolik dn[i] untuk
i=1,2,3. Sintaks untuk ini adalah &amp;"expression"(parameters). Ini
adalah alternatif dari metode pada contoh sebelumnya, di mana kita
mendefinisikan ekspresi simbolik NX, NY, NZ terlebih dahulu.


\>pov3d(X(x,y),Y(x,y),Z(x,y),axis=0,zoom=5,w=450,h=350, ...  
\>     <shadow,look=povlook(gray), ...  
\>     xv=&"dn[1]"(x,y), yv=&"dn[2]"(x,y), zv=&"dn[3]"(x,y));


![images/3_EMT_3D-220.png](images/3_EMT_3D-220.png)

Kami juga dapat menghasilkan grid dalam 3D.


\>povstart(zoom=4); ...  
\>   x=-1:0.5:1; r=1-(x+1)^2/6; ...  
\>   t=(0°:30°:360°)'; y=r\*cos(t); z=r\*sin(t); ...  
\>   writeln(povgrid(x,y,z,d=0.02,dballs=0.05)); ...  
\>   povend();


![images/3_EMT_3D-221.png](images/3_EMT_3D-221.png)

With povgrid(), curves are possible.


\>povstart(center=[0,0,1],zoom=3.6); ...  
\>   t=linspace(0,2,1000); r=exp(-t); ...  
\>   x=cos(2\*pi\*10\*t)\*r; y=sin(2\*pi\*10\*t)\*r; z=t; ...  
\>   writeln(povgrid(x,y,z,povlook(red))); ...  
\>   writeAxis(0,2,axis=3); ...  
\>   povend();


![images/3_EMT_3D-222.png](images/3_EMT_3D-222.png)

# Latihan Soal

1. Buatlah plot 3D dari fungsi


$$f(x,y)=x^3+3y^2$$

dengan zoom 3 dan angle 55 derajat menggunakan povray


\>pov3d("x^3+3\*y^2",zoom=3,angle=55°);


![images/3_EMT_3D-224.png](images/3_EMT_3D-224.png)

2. Buatlah gabungan 2 silinder dengan fungsi povx() berwarna merah dan
povz() berwarna kuning dan zoom 4


\>povstart(zoom=4)

\>c1 = povcylinder (-povx,povx,1,povlook(red));

\>c2 = povcylinder (-povz,povz,1,povlook(yellow));

\>writeln(povintersection([c1,c2]));

\>povend();


![images/3_EMT_3D-225.png](images/3_EMT_3D-225.png)

\> 


3. Buatlah grafik 3D dari fungsi kuadrat berikut ini dengan parameter
tambahan:


$$z=4x^2-2y^2$$

Tampilkan grafik tersebut dengan transparent, dan menggunakan grid
dengan resolusi 50, dengan warna biru pada garis di plot tersebut


\>plot3d("4\*x^2-2\*y^2",\>transparent,grid=50,wirecolor=blue):


![images/3_EMT_3D-227.png](images/3_EMT_3D-227.png)

