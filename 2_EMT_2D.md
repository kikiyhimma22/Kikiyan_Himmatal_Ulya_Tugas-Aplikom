﻿# Menggambar Grafik 2D dengan EMT
Notebook ini menjelaskan tentang cara menggambar berbagaikurva dan
grafik 2D dengan software EMT. EMT menyediakan fungsi plot2d() untuk
menggambar berbagai kurva dan grafik dua dimensi (2D).


## Basic Plots

Ada fungsi plot yang sangat mendasar. Ada koordinat layar, yang selalu
berkisar dari 0 hingga 1024 di setiap sumbu, tidak peduli apakah
layarnya persegi atau tidak. Semut ada koordinat plot, yang dapat
diatur dengan setplot(). Pemetaan antara koordinat tergantung pada
jendela plot saat ini. Misalnya, shrinkwindow() default menyisakan
ruang untuk label sumbu dan judul plot.


Dalam contoh, kita hanya menggambar beberapa garis acak dalam berbagai
warna. Untuk detail tentang fungsi-fungsi ini, pelajari fungsi inti
EMT.


\>clg; // clear screen


Fungsi utamanya adalah untuk menghilangkan semua tampilan atau
informasi yang sebelumnya muncul di layar agar layar menjadi kosong
kembali.


\>window(0,0,1024,1024); // use all of the window


Fungsi window(0,0,1024,1024) berarti menetapkan atau mengatur ukuran
dan posisi jendela tampilan.


Penjelasan dari fungsi tersebut:


(0,0): Ini adalah koordinat titik awal (x, y) di layar, yang biasanya
merujuk ke pojok kiri atas dari layar atau jendela.


1024,1024: Ini merujuk ke lebar dan tinggi jendela dalam piksel.


\>setplot(0,1,0,1); // set plot coordinates


Fungsi setplot(0,1,0,1) digunakan untuk menetapkan rentang atau skala
koordinat dalam sebuah grafik atau plot.


Penjelasan dari fungsi tersebut:


0, 1 (untuk sumbu x): Ini berarti sumbu x dari grafik akan mulai dari
nilai 0 hingga 1.


0, 1 (untuk sumbu y): Ini berarti sumbu y dari grafik akan mulai dari
nilai 0 hingga 1.


\>hold on; // start overwrite mode


Fungsi hold on; digunakan untuk mempertahankan grafik yang sudah ada,
sehingga grafik baru yang ditambahkan akan ditumpuk atau ditambahkan
di atas grafik yang sudah ada, tanpa menghapus atau menimpa grafik
sebelumnya.


\>n=100; X=random(n,2); Y=random(n,2);  // get random points


Fungsi ini menghasilkan titik acak dalam bentuk koordinat (x, y) untuk
digunakan dalam sebuah grafik atau analisis data.


n=100;: Menetapkan nilai n sebagai 100. Ini berarti Anda ingin
menghasilkan 100 titik acak.


X=random(n,2);: Menghasilkan 100 titik acak untuk koordinat x. Fungsi
random(n,2) berarti bahwa matriks X akan berukuran 100 baris dan 2
kolom. Setiap baris berisi dua angka acak, yang mewakili dua dimensi
dari koordinat acak untuk setiap titik.


Y=random(n,2);: Serupa dengan X, ini menghasilkan 100 titik acak untuk
koordinat y. Fungsi random(n,2) di sini juga menghasilkan matriks 100
baris dan 2 kolom.


\>colors=rgb(random(n),random(n),random(n)); // get random colors


Fungsi colors=rgb(random(n),random(n),random(n)); digunakan untuk
menghasilkan warna acak dengan menggunakan nilai RGB (Red, Green,
Blue).Penjelasan dari fungsi diatas:


random(n): Ini menghasilkan n angka acak (dalam kasus ini, 100 angka
acak, karena sebelumnya n=100).


rgb(random(n),random(n),random(n)): Fungsi rgb menerima tiga
parameter, yaitu nilai acak untuk Red (R), Green (G), dan Blue (B).
Setiap parameter akan berisi daftar angka acak antara 0 dan 1 (atau 0
hingga 255 tergantung pada implementasi), yang mewakili intensitas
dari masing-masing warna.


colors: Variabel ini akan berisi 100 warna acak yang dihasilkan oleh
kombinasi acak dari nilai Red, Green, dan Blue. Setiap warna akan unik
dan dibentuk dari kombinasi acak dari ketiga komponen warna tersebut.


\>loop 1 to n; color(colors[#]); plot(X[#],Y[#]); end; // plot


FUngsi loop 1 to n; color(colors[#]); plot(X[#],Y[#]); end; berarti
melakukan looping atau perulangan dari 1 hingga n (yang dalam hal ini
n = 100) untuk memplot titik acak dengan warna acak yang dihasilkan.


Penjelasan dari fungsi diatas:


loop 1 to n;: Melakukan perulangan dari angka 1 hingga n (dalam hal
ini n = 100). Artinya, ada 100 iterasi.


color(colors[#]);: Pada setiap iterasi, fungsi ini memilih satu warna
acak dari array colors yang telah dihasilkan sebelumnya. Simbol #
adalah indeks yang sesuai dengan iterasi saat ini, jadi pada iterasi
pertama, itu adalah warna pertama, dan seterusnya.


plot(X[#],Y[#]);: Ini memplot titik pada koordinat (X[#], Y[#]), di
mana X[#] dan Y[#] masing-masing adalah nilai x dan y dari titik acak
yang sudah dihasilkan sebelumnya. Simbol # lagi-lagi menunjukkan
indeks iterasi saat ini, sehingga setiap titik memiliki koordinat dan
warna yang unik.


end;: Mengakhiri loop. Setelah semua titik dari 1 hingga n selesai
diplot, loop berhenti.


\>hold off; // end overwrite mode


Fungsi hold off; digunakan untuk mengembalikan ke mode default, di
mana grafik baru menimpa yang lama. Setelah ini, grafik berikutnya
yang diplot akan menggantikan plot yang sebelumnya, bukan
menambahkannya.


\>insimg; // insert to notebook


![images/2_EMT_2D-001.png](images/2_EMT_2D-001.png)

Fungsi insimg; digunakan untuk menyisipkan gambar ke dalam notebook
atau dokumen. Ini memungkinkan pengguna untuk mengintegrasikan grafik,
plot, atau hasil visual lainnya ke dalam catatan mereka, sehingga
dapat dengan mudah dilihat dan dianalisis dalam konteks yang lebih
besar.


\>reset;


Penting untuk menahan grafik, karena perintah plot() akan menghapus
jendela plot.


Untuk menghapus semua yang kami lakukan, kami menggunakan reset().


Untuk menampilkan gambar hasil plot di layar notebook, perintah
plot2d() dapat diakhiri dengan titik dua (:). Cara lain adalah
perintah plot2d() diakhiri dengan titik koma (;), kemudian menggunakan
perintah insimg() untuk menampilkan gambar hasil plot.


Untuk contoh lain, kita menggambar plot sebagai sisipan di plot lain.
Ini dilakukan dengan menentukan jendela plot yang lebih kecil.
Perhatikan bahwa jendela ini tidak menyediakan ruang untuk label sumbu
di luar jendela plot. Kita harus menambahkan beberapa margin untuk ini
sesuai kebutuhan. Perhatikan bahwa kita menyimpan dan memulihkan
jendela penuh, dan menahan plot saat ini sementara kita memplot
sisipan.


\>plot2d("x^3-x");


Fungsi plot2d("x^3-x"); dalam bahasa EMT (Ekspresi Menggunakan
Tindakan) digunakan untuk memplot grafik dua dimensi dari fungsi
matematika yang diberikan, dalam hal ini, fungsi


$$f(x)= x^{3}-x$$\>xw=200; yw=100; ww=300; hw=300;


xw: posisi x (horizontal) dari jendela.


yw: posisi y (vertikal) dari jendela.


ww: lebar jendela.


hw: tinggi jendela.


\>ow=window();


Menyimpan referensi ke jendela saat ini dalam variabel ow. Ini berguna
untuk mengembalikan ke jendela ini nanti.


\>window(xw,yw,xw+ww,yw+hw);


Mengatur jendela baru dengan posisi (xw, yw) sebagai sudut kiri atas
dan (xw+ww, yw+hw) sebagai sudut kanan bawah, berdasarkan nilai yang
telah didefinisikan.


\>hold on;


Mengaktifkan mode penambahan, sehingga grafik berikutnya akan
ditambahkan di atas grafik yang ada tanpa menghapusnya.


\>barclear(xw-50,yw-10,ww+60,ww+60);


Menghapus atau mengosongkan area grafik di sekitar koordinat yang
ditentukan. Ini akan menghapus area berbentuk persegi panjang di
jendela yang ditentukan oleh parameter yang diberikan.


\>plot2d("x^4-x",grid=6):


![images/2_EMT_2D-003.png](images/2_EMT_2D-003.png)

Memplot grafik dua dimensi dari fungsi


$$f(x)=x^{4}-4$$

dengan grid yang diatur pada tingkat 6, yang memberikan tampilan lebih
terstruktur pada grafik.


\>hold off;


Fungsi hold off; digunakan untuk mengakhiri mode penambahan grafik.
Ini berarti bahwa setelah perintah ini, grafik atau plot baru yang
dibuat akan menimpa grafik yang ada sebelumnya, bukan menambahkannya.


\>window(ow);


Plot dengan beberapa angka dicapai dengan cara yang sama. Ada fungsi
utilitas figure() untuk ini.


## Aspek Plot

Plot default menggunakan jendela plot persegi. Anda dapat mengubahnya
dengan fungsi aspect(). Jangan lupa untuk mengatur ulang aspek nanti.
Anda juga dapat mengubah default ini di menu dengan "Set Aspect" ke
rasio aspek tertentu atau ke ukuran jendela grafis saat ini.


Tetapi Anda dapat mengubahnya juga untuk satu plot. Untuk ini, ukuran
area plot saat ini diubah, dan jendela diatur sehingga label memiliki
ruang yang cukup.


\>aspect(2); // rasio panjang dan lebar 2:1


Fungsi ini mengatur rasio aspek dari grafik yang akan dibuat. Dengan
parameter 2, rasio panjang dan lebar grafik akan menjadi 2:1. Ini
berarti lebar grafik akan dua kali lipat dari tingginya, yang dapat
membantu dalam memperjelas visualisasi fungsi yang memiliki rentang
nilai yang lebih lebar.


\>plot2d(["sin(x)","cos(x)"],0,2pi):


![images/2_EMT_2D-005.png](images/2_EMT_2D-005.png)

\>aspect();


Fungsi aspect(); tanpa parameter biasanya digunakan untuk
mengembalikan rasio aspek grafik ke pengaturan default.


\>reset;


Fungsi reset() mengembalikan default plot termasuk rasio aspek.


# Plot 2D di Euler

EMT Math Toolbox memiliki plot dalam 2D, baik untuk data maupun
fungsi. EMT menggunakan fungsi plot2d. Fungsi ini dapat memplot fungsi
dan data.


Dimungkinkan untuk memplot di Maxima menggunakan Gnuplot atau di
Python menggunakan Math Plot Lib.


Euler dapat memplot plot 2D dari


* 
ekspresi

* 
fungsi, variabel, atau kurva parameter,

* 
vektor nilai xy,

* 
awan titik di pesawat,

* 
kurva implisit dengan level atau area level.

* 
Fungsi kompleks


Gaya plot mencakup berbagai gaya untuk garis dan titik, plot batang,
dan plot berarsir.


# Plot Ekspresi atau Variabel

Satu ekspresi dalam "x" (misalnya "4*x^2") atau nama fungsi (misalnya
"f") menghasilkan grafik fungsi.


Berikut adalah contoh paling dasar, yang menggunakan rentang default
dan mengatur y-range yang tepat agar sesuai dengan plot fungsi.


Catatan: Jika Anda mengakhiri baris perintah dengan titik dua ":",
plot akan dimasukkan ke dalam jendela teks. Jika tidak, tekan TAB
untuk melihat plot jika jendela plot tertutup.


\>plot2d("x^2"):


![images/2_EMT_2D-006.png](images/2_EMT_2D-006.png)

\>aspect(1.5); plot2d("x^3-x"):


![images/2_EMT_2D-007.png](images/2_EMT_2D-007.png)

\>a:=5.6; plot2d("exp(-a\*x^2)/a"); insimg(30); // menampilkan gambar hasil plot setinggi 25 baris


![images/2_EMT_2D-008.png](images/2_EMT_2D-008.png)

Dari beberapa contoh sebelumnya Anda dapat melihat bahwa aslinya
gambar plot menggunakan sumbu X dengan rentang nilai dari -2 sampai
dengan 2. Untuk mengubah rentang nilai X dan Y, Anda dapat menambahkan
nilai-nilai batas X (dan Y) di belakang ekspresi yang digambar.


Rentang plot diatur dengan parameter yang ditetapkan berikut


* 
a,b: X-range (default -2,2)

* 
c,d: jrange-y (default: skala dengan nilai)

* 
r: atau jari-jari di sekitar pusat plot

* 
cx,cy: koordinat pusat plot (default 0,0)


\>plot2d("x^3-x",-1,2):


![images/2_EMT_2D-009.png](images/2_EMT_2D-009.png)

\>plot2d("sin(x)",-2\*pi,2\*pi): // plot sin(x) pada interval [-2pi, 2pi]


![images/2_EMT_2D-010.png](images/2_EMT_2D-010.png)

\>plot2d("cos(x)","sin(3\*x)",xmin=0,xmax=2pi):


![images/2_EMT_2D-011.png](images/2_EMT_2D-011.png)

Alternatif untuk titik dua adalah perintah insimg(lines), yang
menyisipkan plot yang menempati sejumlah baris teks tertentu.


Dalam opsi, plot dapat diatur untuk muncul


* 
di jendela terpisah yang dapat diubah ukurannya,

* 
di jendela buku catatan.


Lebih banyak gaya dapat dicapai dengan perintah plot tertentu.


Bagaimanapun, tekan tombol tabulator untuk melihat plotnya, jika
tersembunyi.


Untuk membagi jendela menjadi beberapa plot, gunakan perintah
figure(). Dalam contoh, kita memplot x^1 hingga x^4 menjadi 4 bagian
jendela. Figure(0) mengatur ulang jendela default.


\>reset;

\>figure(2,2); ...  
\>  
Fungsi figure(2,2); digunakan untuk mengatur ukuran jendela grafik
baru menjadi 2 x 2, yang memungkinkan pengguna untuk memvisualisasikan
grafik dengan cara yang terorganisir dan jelas.


\>for n=1 to 4; figure(n); plot2d("x^"+n); end; ...  
\>   figure(0):


![images/2_EMT_2D-012.png](images/2_EMT_2D-012.png)

Di plot2d(), ada gaya alternatif yang tersedia dengan grid=x. Untuk
gambaran umum, kami menunjukkan berbagai gaya kisi dalam satu gambar
(lihat di bawah untuk perintah figure(). Grid gaya grid = 0 tidak
disertakan. Ini tidak menunjukkan kisi dan tidak ada bingkai.


\>figure(3,3); ...  
\>   for k=1:9; figure(k); plot2d("x^3-x",-2,1,grid=k); end; ...  
\>   figure(0):


![images/2_EMT_2D-013.png](images/2_EMT_2D-013.png)

Jika argumen untuk plot2d() adalah ekspresi diikuti oleh empat angka,
angka-angka ini adalah rentang x dan y untuk plot.


Atau, a, b, c, d dapat ditentukan sebagai parameter yang ditetapkan
sebagai a=... dll.


Dalam contoh berikut, kita mengubah gaya kisi, menambahkan label, dan
menggunakan label vertikal untuk sumbu y.


\>aspect(1.5); plot2d("sin(x)",0,2pi,-1.2,1.2,grid=3,xl="x",yl="sin(x)"):


![images/2_EMT_2D-014.png](images/2_EMT_2D-014.png)

\>plot2d("sin(x)+cos(2\*x)",0,4pi):


![images/2_EMT_2D-015.png](images/2_EMT_2D-015.png)

Gambar yang dihasilkan dengan memasukkan plot ke dalam jendela teks
disimpan di direktori yang sama dengan buku catatan, secara default di
subdirektori bernama "images". Mereka juga digunakan oleh ekspor HTML.


Anda cukup menandai gambar apa pun dan menyalinnya ke clipboard dengan
Ctrl-C. Tentu saja, Anda juga dapat mengekspor grafik saat ini dengan
fungsi di menu File.


Fungsi atau ekspresi dalam plot2d dievaluasi secara adaptif. Untuk
kecepatan lebih, matikan plot adaptif dengan &lt;adaptif dan tentukan
jumlah subinterval dengan n=... Ini seharusnya diperlukan dalam kasus
yang jarang terjadi saja.


\>plot2d("sign(x)\*exp(-x^2)",-1,1,<adaptive,n=10000):


![images/2_EMT_2D-016.png](images/2_EMT_2D-016.png)

\>plot2d("x^x",r=1.2,cx=1,cy=1):


![images/2_EMT_2D-017.png](images/2_EMT_2D-017.png)

Perhatikan bahwa x^x tidak didefinisikan untuk x&lt;=0. Fungsi plot2d
menangkap kesalahan ini, dan mulai merencanakan segera setelah fungsi
ditentukan. Ini berfungsi untuk semua fungsi yang mengembalikan NAN di
luar jangkauan definisi mereka.


\>plot2d("log(x)",-0.1,2):


![images/2_EMT_2D-018.png](images/2_EMT_2D-018.png)

Parameter square=true (atau &gt;square) memilih jrange-y secara otomatis
sehingga hasilnya adalah jendela plot persegi. Perhatikan bahwa secara
default, Euler menggunakan ruang persegi di dalam jendela plot.


\>plot2d("x^3-x",\>square):


![images/2_EMT_2D-019.png](images/2_EMT_2D-019.png)

\>plot2d(''integrate("sin(x)\*exp(-x^2)",0,x)'',0,2): // plot integral


![images/2_EMT_2D-020.png](images/2_EMT_2D-020.png)

Jika Anda membutuhkan lebih banyak ruang untuk label-y, panggil
shrinkwindow() dengan parameter yang lebih kecil, atau atur nilai
positif untuk "smaller" di plot2d().


\>plot2d("gamma(x)",1,10,yl="y-values",smaller=6,<vertical):


![images/2_EMT_2D-021.png](images/2_EMT_2D-021.png)

Symbolic expressions can also be used, since they are stored as simple
string expressions.


\>x=linspace(0,2pi,1000); plot2d(sin(5x),cos(7x)):


![images/2_EMT_2D-022.png](images/2_EMT_2D-022.png)

\>a:=5.6; expr &= exp(-a\*x^2)/a; // define expression

\>plot2d(expr,-2,2): // plot from -2 to 2


![images/2_EMT_2D-023.png](images/2_EMT_2D-023.png)

\>plot2d(expr,r=1,thickness=2): // plot in a square around (0,0)


![images/2_EMT_2D-024.png](images/2_EMT_2D-024.png)

\>plot2d(&diff(expr,x),\>add,style="--",color=red): // add another plot


![images/2_EMT_2D-025.png](images/2_EMT_2D-025.png)

\>plot2d(&diff(expr,x,2),a=-2,b=2,c=-2,d=1): // plot in rectangle


![images/2_EMT_2D-026.png](images/2_EMT_2D-026.png)

\>plot2d(&diff(expr,x),a=-2,b=2,\>square): // keep plot square


![images/2_EMT_2D-027.png](images/2_EMT_2D-027.png)

\>plot2d("x^2",0,1,steps=1,color=red,n=10):


![images/2_EMT_2D-028.png](images/2_EMT_2D-028.png)

\>plot2d("x^2",\>add,steps=2,color=blue,n=10):


![images/2_EMT_2D-029.png](images/2_EMT_2D-029.png)

# Fungsi dalam satu Parameter

Fungsi plot yang paling penting untuk plot planar adalah plot2d().
Fungsi ini diimplementasikan dalam bahasa Euler dalam file "plot.e",
yang dimuat di awal program.


Berikut adalah beberapa contoh menggunakan fungsi. Seperti biasa di
EMT, fungsi yang berfungsi untuk fungsi atau ekspresi lain, Anda dapat
meneruskan parameter tambahan (selain x) yang bukan variabel global ke
fungsi dengan parameter titik koma atau dengan koleksi panggilan.


\>function f(x,a) := x^2/a+a\*x^2-x; // define a function

\>a=0.3; plot2d("f",0,1;a): // plot with a=0.3


![images/2_EMT_2D-030.png](images/2_EMT_2D-030.png)

\>plot2d("f",0,1;0.4): // plot with a=0.4


![images/2_EMT_2D-031.png](images/2_EMT_2D-031.png)

\>plot2d({{"f",0.2}},0,1): // plot with a=0.2


![images/2_EMT_2D-032.png](images/2_EMT_2D-032.png)

\>plot2d({{"f(x,b)",b=0.1}},0,1): // plot with 0.1


![images/2_EMT_2D-033.png](images/2_EMT_2D-033.png)

\>function f(x) := x^3-x; ...  
\>   plot2d("f",r=1):


![images/2_EMT_2D-034.png](images/2_EMT_2D-034.png)

Berikut adalah ringkasan fungsi yang diterima


* 
ekspresi atau ekspresi simbolis dalam x

* 
fungsi atau fungsi simbolis dengan nama sebagai "f"

* 
fungsi simbolis hanya dengan nama f


Fungsi plot2d() juga menerima fungsi simbolis. Untuk fungsi simbolis,
nama saja berfungsi.


\>function f(x) &= diff(x^x,x)


    
                                x
                               x  (log(x) + 1)
    

\>plot2d(f,0,2):


![images/2_EMT_2D-035.png](images/2_EMT_2D-035.png)

Tentu saja, untuk ekspresi atau ekspresi simbolis, nama variabel sudah
cukup untuk memplotnya.


\>expr &= sin(x)\*exp(-x)


    
                                  - x
                                 E    sin(x)
    

\>plot2d(expr,0,3pi):


![images/2_EMT_2D-036.png](images/2_EMT_2D-036.png)

\>function f(x) &= x^x;

\>plot2d(f,r=1,cx=1,cy=1,color=blue,thickness=2);

\>plot2d(&diff(f(x),x),\>add,color=red,style="-.-"):


![images/2_EMT_2D-037.png](images/2_EMT_2D-037.png)

Untuk gaya garis ada berbagai opsi.


* 
style="...". Pilih dari "-", "--", "-.", ".", ".-.", "-.-".

* 
color: Lihat di bawah untuk warna.

* 
ketebalan: Defaultnya adalah 1.


Warna dapat dipilih sebagai salah satu warna default, atau sebagai
warna RGB.


* 
0..15: indeks warna default.

* 
Konstanta warna: putih, hitam, merah, hijau, biru, cyan, zaitun,
* abu-abu muda, abu-abu, abu-abu gelap, oranye, hijau muda, pirus, biru
* muda, oranye muda, kuning

* 
RGB(Merah,Hijau,Biru): Parameter adalah real di [0,1].


\>plot2d("exp(-x^2)",r=2,color=red,thickness=3,style="--"):


![images/2_EMT_2D-038.png](images/2_EMT_2D-038.png)

Berikut adalah tampilan warna EMT yang telah ditentukan sebelumnya.


\>aspect(2); columnsplot(ones(1,16),lab=0:15,grid=0,color=0:15):


![images/2_EMT_2D-039.png](images/2_EMT_2D-039.png)

Kode ini mengatur rasio aspek grafik menjadi 2:1 dan kemudian membuat
diagram kolom dengan 16 kolom yang memiliki tinggi sama (1), setiap
kolom diberi label dari 0 hingga 15 dan diwarnai dengan variasi warna.
Grafik ini akan memiliki tampilan yang rapi dan terorganisir tanpa
garis grid di latar belakang.


fungsi aspect(2); mengatur rasio aspek grafik menjadi 2:1, yang
berarti lebar grafik akan dua kali lipat dari tingginya.


columnsplot: Fungsi ini digunakan untuk membuat diagram kolom (bar
chart) dari data yang diberikan.


ones(1,16): Membuat vektor baris yang berisi 16 elemen, semua bernilai
1. Ini berarti semua kolom akan memiliki tinggi yang sama (1).


lab=0:15: Menetapkan label untuk sumbu x dari kolom, mulai dari 0
hingga 15, yang akan menjadi label untuk setiap kolom.


grid=0: Mengatur grid pada plot menjadi tidak ada. Ini berarti tidak
akan ada garis grid yang ditampilkan di latar belakang.


color=0:15: Mengatur warna kolom dengan menggunakan skala warna dari 0
hingga 15, sehingga setiap kolom dapat memiliki warna yang berbeda.


Tapi Anda bisa menggunakan warna apa saja.


\>columnsplot(ones(1,16),grid=0,color=rgb(0,0,linspace(0,1,15))):


![images/2_EMT_2D-040.png](images/2_EMT_2D-040.png)

# Menggambar Beberapa Kurva pada bidang koordinat yang sama

Plot lebih dari satu fungsi (beberapa fungsi) ke dalam satu jendela
dapat dilakukan dengan cara yang berbeda. Salah satu metode adalah
menggunakan &gt;add untuk beberapa panggilan ke plot2d secara
keseluruhan, tetapi panggilan pertama. Kami telah menggunakan fitur
ini dalam contoh di atas.


\>aspect(); plot2d("cos(x)",r=2,grid=6); plot2d("x",style=".",\>add):


![images/2_EMT_2D-041.png](images/2_EMT_2D-041.png)

\>aspect(1.5); plot2d("sin(x)",0,2pi); plot2d("cos(x)",color=blue,style="--",\>add):


![images/2_EMT_2D-042.png](images/2_EMT_2D-042.png)

Salah satu kegunaan &gt;add adalah untuk menambahkan titik pada kurva.


\>plot2d("sin(x)",0,pi); plot2d(2,sin(2),\>points,\>add):


![images/2_EMT_2D-043.png](images/2_EMT_2D-043.png)

Kami menambahkan titik persimpangan dengan label (pada posisi "cl"
untuk kiri tengah), dan memasukkan hasilnya ke dalam buku catatan.
Kami juga menambahkan judul ke plot.


\>plot2d(["cos(x)","x"],r=1.1,cx=0.5,cy=0.5, ...  
\>     color=[black,blue],style=["-","."], ...  
\>     grid=1);

\>x0=solve("cos(x)-x",1);  ...  
\>     plot2d(x0,x0,\>points,\>add,title="Intersection Demo");  ...  
\>     label("cos(x) = x",x0,x0,pos="cl",offset=20):


![images/2_EMT_2D-044.png](images/2_EMT_2D-044.png)

Dalam demo berikut, kita memplot fungsi sinc(x)=sin(x)/x dan ekspansi
Taylor ke-8 dan ke-16. Kami menghitung ekspansi ini menggunakan Maxima
melalui ekspresi simbolik.


Plot ini dilakukan dalam perintah multi-baris berikut dengan tiga
panggilan ke plot2d(). Yang kedua dan ketiga memiliki set bendera
(&gt;add), yang membuat plot menggunakan rentang sebelumnya.


Kami menambahkan kotak label yang menjelaskan fungsinya.


\>$taylor(sin(x)/x,x,0,4)


$$\frac{x^4}{120}-\frac{x^2}{6}+1$$\>plot2d("sinc(x)",0,4pi,color=green,thickness=2); ...  
\>     plot2d(&taylor(sin(x)/x,x,0,8),\>add,color=blue,style="--"); ...  
\>     plot2d(&taylor(sin(x)/x,x,0,16),\>add,color=red,style="-.-"); ...  
\>     labelbox(["sinc","T8","T16"],styles=["-","--","-.-"], ...  
\>       colors=[black,blue,red]):


![images/2_EMT_2D-046.png](images/2_EMT_2D-046.png)

Dalam contoh berikut, kami menghasilkan Bernstein-Polynomial.


$$B_i(x) = \binom{n}{i} x^i (1-x)^{n-i}$$\>plot2d("(1-x)^10",0,1); // plot first function

\>for i=1 to 10; plot2d("bin(10,i)\*x^i\*(1-x)^(10-i)",\>add); end;

\>insimg;


![images/2_EMT_2D-048.png](images/2_EMT_2D-048.png)

Metode kedua adalah menggunakan sepasang matriks nilai-x dan matriks
nilai-y dengan ukuran yang sama.


Kami menghasilkan matriks nilai dengan satu Bernstein-Polynomial di
setiap baris. Untuk ini, kita cukup menggunakan vektor kolom i. Lihat
pengantar tentang bahasa matriks untuk mempelajari lebih detail.


\>x=linspace(0,1,500);


Fungsi ini akan menghasilkan vektor x yang berisi 500 titik yang
terdistribusi secara merata antara 0 dan 1, siap untuk digunakan dalam
analisis atau pemrograman lebih lanjut.


\>n=10; k=(0:n)'; // n is row vector, k is column vector

\>y=bin(n,k)\*x^k\*(1-x)^(n-k); // y is a matrix then

\>plot2d(x,y):


![images/2_EMT_2D-049.png](images/2_EMT_2D-049.png)

Perhatikan bahwa parameter warna dapat berupa vektor. Kemudian setiap
warna digunakan untuk setiap baris matriks.


\>x=linspace(0,1,200); y=x^(1:10)'; plot2d(x,y,color=1:10):


![images/2_EMT_2D-050.png](images/2_EMT_2D-050.png)

Metode lain adalah menggunakan vektor ekspresi (string). Anda kemudian
dapat menggunakan array warna, array gaya, dan array ketebalan dengan
panjang yang sama.


\>plot2d(["sin(x)","cos(x)"],0,2pi,color=4:5): 


![images/2_EMT_2D-051.png](images/2_EMT_2D-051.png)

\>plot2d(["sin(x)","cos(x)"],0,2pi): // plot vector of expressions


![images/2_EMT_2D-052.png](images/2_EMT_2D-052.png)

We can get such a vector from Maxima using makelist() and mxm2str().


\>v &= makelist(binomial(10,i)\*x^i\*(1-x)^(10-i),i,0,10) // make list


    
                   10            9              8  2             7  3
           [(1 - x)  , 10 (1 - x)  x, 45 (1 - x)  x , 120 (1 - x)  x , 
               6  4             5  5             4  6             3  7
    210 (1 - x)  x , 252 (1 - x)  x , 210 (1 - x)  x , 120 (1 - x)  x , 
              2  8              9   10
    45 (1 - x)  x , 10 (1 - x) x , x  ]
    

\>mxm2str(v) // get a vector of strings from the symbolic vector


    (1-x)^10
    10*(1-x)^9*x
    45*(1-x)^8*x^2
    120*(1-x)^7*x^3
    210*(1-x)^6*x^4
    252*(1-x)^5*x^5
    210*(1-x)^4*x^6
    120*(1-x)^3*x^7
    45*(1-x)^2*x^8
    10*(1-x)*x^9
    x^10

\>plot2d(mxm2str(v),0,1): // plot functions


![images/2_EMT_2D-053.png](images/2_EMT_2D-053.png)

Alternatif lain adalah menggunakan bahasa matriks Euler.


Jika sebuah ekspresi menghasilkan matriks fungsi, dengan satu fungsi
di setiap baris, semua fungsi ini akan diplot menjadi satu plot.


Untuk ini, gunakan vektor parameter dalam bentuk vektor kolom. Jika
array warna ditambahkan, itu akan digunakan untuk setiap baris plot.


\>n=(1:10)'; plot2d("x^n",0,1,color=1:10):


![images/2_EMT_2D-054.png](images/2_EMT_2D-054.png)

Ekspresi dan fungsi satu baris dapat melihat variabel global.


Jika Anda tidak dapat menggunakan variabel global, Anda perlu
menggunakan fungsi dengan parameter tambahan, dan meneruskan parameter
ini sebagai parameter titik koma.


Berhati-hatilah, untuk menempatkan semua parameter yang ditetapkan ke
akhir perintah plot2d. Dalam contoh kita meneruskan a=5 ke fungsi f,
yang kita plot dari -10 hingga 10.


\>function f(x,a) := 1/a\*exp(-x^2/a); ...  
\>   plot2d("f",-10,10;5,thickness=2,title="a=5"):


![images/2_EMT_2D-055.png](images/2_EMT_2D-055.png)

Ekspresi dan fungsi satu baris dapat melihat variabel global. Atau,
gunakan koleksi dengan nama fungsi dan semua parameter tambahan.
Daftar khusus ini disebut koleksi panggilan, dan itu adalah cara yang
lebih disukai untuk meneruskan argumen ke fungsi yang dengan
sendirinya diteruskan sebagai argumen ke fungsi lain.


Dalam contoh berikut, kita menggunakan loop untuk memplot beberapa
fungsi (lihat tutorial tentang pemrograman untuk loop).


Jika Anda tidak dapat menggunakan variabel global, Anda perlu
menggunakan fungsi dengan parameter tambahan, dan meneruskan parameter
ini sebagai parameter titik koma.


Berhati-hatilah, untuk menempatkan semua parameter yang ditetapkan ke
akhir perintah plot2d. Dalam contoh kita meneruskan a=5 ke fungsi f,
yang kita plot dari -10 hingga 10.


\>plot2d({{"f",1}},-10,10); ...  
\>   for a=2:10; plot2d({{"f",a}},\>add); end:


![images/2_EMT_2D-056.png](images/2_EMT_2D-056.png)

Kita dapat mencapai hasil yang sama dengan cara berikut menggunakan
bahasa matriks EMT. Setiap baris matriks f(x,a) adalah satu fungsi.
Selain itu, kita dapat mengatur warna untuk setiap baris matriks. Klik
dua kali pada fungsi getspectral() untuk penjelasan.


\>x=-10:0.01:10; a=(1:10)'; plot2d(x,f(x,a),color=getspectral(a/10)):


![images/2_EMT_2D-057.png](images/2_EMT_2D-057.png)

## Label Teks

Dekorasi sederhana bisa


* 
judul dengan title="..."

* 
label x dan y dengan xl="...", yl="..."

* 
label teks lain dengan label("...",x,y)


Perintah label akan memplot ke dalam plot saat ini pada koordinat plot
(x,y). Itu bisa mengambil argumen posisional.


\>plot2d("x^3-x",-1,2,title="y=x^3-x",yl="y",xl="x"):


![images/2_EMT_2D-058.png](images/2_EMT_2D-058.png)

\>expr := "log(x)/x"; ...  
\>     plot2d(expr,0.5,5,title="y="+expr,xl="x",yl="y"); ...  
\>     label("(1,0)",1,0); label("Max",E,expr(E),pos="lc"):


![images/2_EMT_2D-059.png](images/2_EMT_2D-059.png)

Ada juga fungsi labelbox(), yang dapat menampilkan fungsi dan teks.
Dibutuhkan vektor string dan warna, satu item untuk setiap fungsi.


\>function f(x) &= x^2\*exp(-x^2);  ...  
\>   plot2d(&f(x),a=-3,b=3,c=-1,d=1);  ...  
\>   plot2d(&diff(f(x),x),\>add,color=blue,style="--"); ...  
\>   labelbox(["function","derivative"],styles=["-","--"], ...  
\>      colors=[black,blue],w=0.4):


![images/2_EMT_2D-060.png](images/2_EMT_2D-060.png)

Kotak ini ditambatkan di kanan atas secara default, tetapi &gt;kiri
menambatkan di kiri atas. Anda dapat memindahkannya ke tempat mana pun
yang Anda suka. Posisi jangkar adalah sudut kanan atas kotak, dan
angkanya adalah pecahan dari ukuran jendela grafis. Lebarnya otomatis.


Untuk plot titik, kotak label juga berfungsi. Tambahkan parameter
&gt;poin, atau vektor bendera, satu untuk setiap label.


Dalam contoh berikut, hanya ada satu fungsi. Jadi kita bisa
menggunakan string alih-alih vektor string. Kami mengatur warna teks
menjadi hitam untuk contoh ini.


\>n=10; plot2d(0:n,bin(n,0:n),\>addpoints); ...  
\>   labelbox("Binomials",styles="[]",\>points,x=0.1,y=0.1, ...  
\>   tcolor=black,\>left):


![images/2_EMT_2D-061.png](images/2_EMT_2D-061.png)

Gaya plot ini juga tersedia di statplot(). Seperti pada plot2d() warna
dapat diatur untuk setiap baris plot. Ada lebih banyak plot khusus
untuk tujuan statistik (lihat tutorial tentang statistik).


\>statplot(1:10,random(2,10),color=[red,blue]):


![images/2_EMT_2D-062.png](images/2_EMT_2D-062.png)

Fitur serupa adalah fungsi textbox().


Lebar secara default adalah lebar maksimum baris teks. Tapi itu bisa
diatur oleh pengguna juga.


\>function f(x) &= exp(-x)\*sin(2\*pi\*x); ...  
\>   plot2d("f(x)",0,2pi); ...  
\>   textbox(latex("\\text{Example of a damped oscillation}\\ f(x)=e^{-x}sin(2\\pi x)"),w=0.85):


![images/2_EMT_2D-063.png](images/2_EMT_2D-063.png)

Label teks, judul, kotak label, dan teks lainnya dapat berisi string
Unicode (lihat sintaks EMT untuk selengkapnya tentang string Unicode).


\>plot2d("x^3-x",title=u"x &rarr; x&sup3; - x"):


![images/2_EMT_2D-064.png](images/2_EMT_2D-064.png)

Label pada sumbu x dan y dapat vertikal, serta sumbu.


\>plot2d("sinc(x)",0,2pi,xl="x",yl=u"x &rarr; sinc(x)",\>vertical):


![images/2_EMT_2D-065.png](images/2_EMT_2D-065.png)

**Getah


Anda juga dapat memplot rumus LaTeX jika Anda telah menginstal sistem
LaTeX. Saya merekomendasikan MiKTeX. Jalur ke biner "latex" dan
"dvipng" harus berada di jalur sistem, atau Anda harus mengatur LaTeX
di menu opsi.


Perhatikan, penguraian LaTeX itu lambat. Jika Anda ingin menggunakan
LaTeX dalam plot animasi, Anda harus memanggil latex() sebelum loop
sekali dan menggunakan hasilnya (gambar dalam matriks RGB).


Dalam plot berikut, kami menggunakan LaTeX untuk label x dan y, label,
kotak label, dan judul plot.


\>plot2d("exp(-x)\*sin(x)/x",a=0,b=2pi,c=0,d=1,grid=6,color=blue, ...  
\>     title=latex("\\text{Function $\\Phi$}"), ...  
\>     xl=latex("\\phi"),yl=latex("\\Phi(\\phi)")); ...  
\>   textbox( ...  
\>     latex("\\Phi(\\phi) = e^{-\\phi} \\frac{\\sin(\\phi)}{\\phi}"),x=0.8,y=0.5); ...  
\>   label(latex("\\Phi",color=blue),1,0.4):


![images/2_EMT_2D-066.png](images/2_EMT_2D-066.png)

Seringkali, kita menginginkan spasi non-konformal dan label teks pada
sumbu x. Kita dapat menggunakan xaxis() dan yaxis() seperti yang akan
kita tunjukkan nanti.


Cara termudah adalah dengan melakukan plot kosong dengan bingkai
menggunakan grid=4, dan kemudian menambahkan kisi dengan ygrid() dan
xgrid(). Dalam contoh berikut, kita menggunakan tiga string LaTeX
untuk label pada sumbu x dengan xtick().


\>plot2d("sinc(x)",0,2pi,grid=4,<ticks); ...  
\>   ygrid(-2:0.5:2,grid=6); ...  
\>   xgrid([0:2]\*pi,<ticks,grid=6);  ...  
\>   xtick([0,pi,2pi],["0","\\pi","2\\pi"],\>latex):


![images/2_EMT_2D-067.png](images/2_EMT_2D-067.png)

Tentu saja, fungsi juga dapat digunakan.


\>function map f(x) ...


    if x>0 then return x^4
    else return x^2
    endif
    endfunction
</pre>
Parameter "peta" membantu menggunakan fungsi untuk vektor. Untuk


plot, itu tidak perlu. Tetapi untuk menunjukkan bahwa vektorisasi


berguna, kami menambahkan beberapa poin kunci ke plot pada x=-1, x=0
dan x=1.


Pada plot berikut, kami juga memasukkan beberapa kode LaTeX. Kami
menggunakannya untuk


dua label dan kotak teks. Tentu saja, Anda hanya akan dapat
menggunakan


LaTeX jika Anda telah menginstal LaTeX dengan benar.


\>plot2d("f",-1,1,xl="x",yl="f(x)",grid=6);  ...  
\>   plot2d([-1,0,1],f([-1,0,1]),\>points,\>add); ...  
\>   label(latex("x^3"),0.72,f(0.72)); ...  
\>   label(latex("x^2"),-0.52,f(-0.52),pos="ll"); ...  
\>   textbox( ...  
\>     latex("f(x)=\\begin{cases} x^3 & x\>0 \\\\ x^2 & x \\le 0\\end{cases}"), ...  
\>     x=0.7,y=0.2):


![images/2_EMT_2D-068.png](images/2_EMT_2D-068.png)

## Interaksi Pengguna

Saat memplot fungsi atau ekspresi, parameter &gt;user memungkinkan
pengguna untuk memperbesar dan menggeser plot dengan tombol kursor
atau mouse. Pengguna dapat


* 
memperbesar dengan + atau -

* 
Pindahkan plot dengan tombol kursor

* 
Pilih jendela plot dengan mouse

* 
Setel ulang tampilan dengan spasi

* 
keluar dengan pengembalian


Tombol spasi akan mengatur ulang plot ke jendela plot asli.


Saat memplot data, bendera &gt;user hanya akan menunggu penekanan tombol.


\>plot2d({{"x^3-a\*x",a=1}},\>user,title="Press any key!"):


![images/2_EMT_2D-069.png](images/2_EMT_2D-069.png)

\>plot2d("exp(x)\*sin(x)",user=true, ...  
\>     title="+/- or cursor keys (return to exit)"):


![images/2_EMT_2D-070.png](images/2_EMT_2D-070.png)

Berikut ini menunjukkan cara lanjutan interaksi pengguna (lihat
tutorial tentang pemrograman untuk detailnya).


Fungsi bawaan mousedrag() menunggu peristiwa mouse atau keyboard. Ini
melaporkan mouse ke bawah, mouse bergerak atau mouse ke atas, dan
penekanan tombol. Fungsi dragpoints() memanfaatkan ini, dan
memungkinkan pengguna menyeret titik apa pun dalam plot.


Kita membutuhkan fungsi plot terlebih dahulu. Sebagai contoh, kita
melakukan interpolasi dalam 5 titik dengan polinomial. Fungsi harus
diplot ke dalam area plot tetap.


\>function plotf(xp,yp,select) ...


      d=interp(xp,yp);
      plot2d("interpval(xp,d,x)";d,xp,r=2);
      plot2d(xp,yp,>points,>add);
      if select>0 then
        plot2d(xp[select],yp[select],color=red,>points,>add);
      endif;
      title("Drag one point, or press space or return!");
    endfunction
</pre>
Perhatikan parameter titik koma di plot2d (d dan xp), yang diteruskan
ke evaluasi fungsi interp(). Tanpa ini, kita harus menulis fungsi
plotinterp() terlebih dahulu, mengakses nilai-nilai secara global.


Sekarang kita menghasilkan beberapa nilai acak, dan biarkan pengguna
menyeret titik-titiknya.


\>t=-1:0.5:1; dragpoints("plotf",t,random(size(t))-0.5):


![images/2_EMT_2D-071.png](images/2_EMT_2D-071.png)

Ada juga fungsi, yang memplot fungsi lain tergantung pada vektor
parameter, dan memungkinkan pengguna menyesuaikan parameter ini.


Pertama kita membutuhkan fungsi plot.


\>function plotf([a,b]) := plot2d("exp(a\*x)\*cos(2pi\*b\*x)",0,2pi;a,b);


Kemudian kita membutuhkan nama untuk parameter, nilai awal dan matriks
rentang nx2, opsional garis judul.


Ada slider interaktif, yang dapat mengatur nilai oleh pengguna. Fungsi
dragvalues() menyediakan ini.


\>dragvalues("plotf",["a","b"],[-1,2],[[-2,2];[1,10]], ...  
\>     heading="Drag these values:",hcolor=black):


![images/2_EMT_2D-072.png](images/2_EMT_2D-072.png)

Dimungkinkan untuk membatasi nilai yang diseret ke bilangan bulat.
Sebagai contoh, kita menulis fungsi plot, yang memplot polinomial
Taylor derajat n ke fungsi kosinus.


\>function plotf(n) ...


    plot2d("cos(x)",0,2pi,>square,grid=6);
    plot2d(&"taylor(cos(x),x,0,@n)",color=blue,>add);
    textbox("Taylor polynomial of degree "+n,0.1,0.02,style="t",>left);
    endfunction
</pre>
Sekarang kita membiarkan derajat n bervariasi dari 0 hingga 20 dalam
20 pemberhentian. Hasil dari dragvalues() digunakan untuk memplot
sketsa dengan n ini, dan untuk memasukkan plot ke dalam buku catatan.


\>nd=dragvalues("plotf","degree",2,[0,20],20,y=0.8, ...  
\>      heading="Drag the value:"); ...  
\>   plotf(nd):


![images/2_EMT_2D-073.png](images/2_EMT_2D-073.png)

Berikut ini adalah demonstrasi sederhana dari fungsi tersebut.
Pengguna dapat menggambar di atas jendela plot, meninggalkan jejak
titik.


\>function dragtest ...


      plot2d(none,r=1,title="Drag with the mouse, or press any key!");
      start=0;
      repeat
        {flag,m,time}=mousedrag();
        if flag==0 then return; endif;
        if flag==2 then
          hold on; mark(m[1],m[2]); hold off;
        endif;
      end
    endfunction
</pre>
\>dragtest // lihat hasilnya dan cobalah lakukan!


## Gaya Plot 2D

Secara default, EMT menghitung kutu sumbu otomatis dan menambahkan
label ke setiap centang. Ini dapat diubah dengan parameter grid. Gaya
default sumbu dan label dapat dimodifikasi. Selain itu, label dan
judul dapat ditambahkan secara manual. Untuk mengatur ulang ke gaya
default, gunakan reset().


\>aspect();

\>figure(3,4); ...  
\>    figure(1); plot2d("x^3-x",grid=0); ... // no grid, frame or axis 


Tidak ada tampilan bingkai dan sumbu


\> figure(2); plot2d("x^3-x",grid=1); ... // x-y-axis


Terdapat sumbu x-y


\> figure(3); plot2d("x^3-x",grid=2); ... // default ticks

\> figure(4); plot2d("x^3-x",grid=3); ... // x-y- axis with labels inside

\> figure(5); plot2d("x^3-x",grid=4); ... // no ticks, only labels

\> figure(6); plot2d("x^3-x",grid=5); ... // default, but no margin

\> figure(7); plot2d("x^3-x",grid=6); ... // axes only

\> figure(8); plot2d("x^3-x",grid=7); ... // axes only, ticks at axis

\> figure(9); plot2d("x^3-x",grid=8); ... // axes only, finer ticks at axis

\> figure(10); plot2d("x^3-x",grid=9); ... // default, small ticks inside

\> figure(11); plot2d("x^3-x",grid=10); ...// no ticks, axes only

\> figure(0):


![images/2_EMT_2D-074.png](images/2_EMT_2D-074.png)

Parameter &lt;frame mematikan bingkai, dan framecolor=blue mengatur
bingkai ke warna biru.


Jika Anda menginginkan centang Anda sendiri, Anda dapat menggunakan
style=0, dan menambahkan semuanya nanti.


\>aspect(1.5); 

\>plot2d("x^3-x",grid=0); // plot

\>frame; xgrid([-1,0,1]); ygrid(0): // add frame and grid


![images/2_EMT_2D-075.png](images/2_EMT_2D-075.png)

Untuk judul plot dan label sumbu, lihat contoh berikut.


\>plot2d("exp(x)",-1,1);

\>textcolor(black); // set the text color to black

\>title(latex("y=e^x")); // title above the plot

\>xlabel(latex("x")); // "x" for x-axis

\>ylabel(latex("y"),\>vertical); // vertical "y" for y-axis

\>label(latex("(0,1)"),0,1,color=blue): // label a point


![images/2_EMT_2D-076.png](images/2_EMT_2D-076.png)

Sumbu dapat digambar secara terpisah dengan xaxis() dan yaxis().


\>plot2d("x^3-x",<grid,<frame);

\>xaxis(0,xx=-2:1,style="-\>"); yaxis(0,yy=-5:5,style="-\>"):


![images/2_EMT_2D-077.png](images/2_EMT_2D-077.png)

Teks pada plot dapat diatur dengan label(). Dalam contoh berikut, "lc"
berarti pusat bawah. Ini mengatur posisi label relatif terhadap
koordinat plot.


\>function f(x) &= x^3-x


    
                                     3
                                    x  - x
    

\>plot2d(f,-1,1,\>square);

\>x0=fmin(f,0,1); // compute point of minimum

\>label("Rel. Min.",x0,f(x0),pos="lc"): // add a label there


![images/2_EMT_2D-078.png](images/2_EMT_2D-078.png)

Ada juga kotak teks.


\>plot2d(&f(x),-1,1,-2,2); // function

\>plot2d(&diff(f(x),x),\>add,style="--",color=red); // derivative

\>labelbox(["f","f'"],["-","--"],[black,red]): // label box


![images/2_EMT_2D-079.png](images/2_EMT_2D-079.png)

\>plot2d(["exp(x)","1+x"],color=[black,blue],style=["-","-.-"]):


![images/2_EMT_2D-080.png](images/2_EMT_2D-080.png)

\>gridstyle("-\>",color=gray,textcolor=gray,framecolor=gray);  ...  
\>    plot2d("x^3-x",grid=1);   ...  
\>    settitle("y=x^3-x",color=black); ...  
\>    label("x",2,0,pos="bc",color=gray);  ...  
\>    label("y",0,6,pos="cl",color=gray); ...  
\>    reset():


![images/2_EMT_2D-081.png](images/2_EMT_2D-081.png)

Untuk kontrol yang lebih baik, sumbu x dan sumbu y dapat dilakukan
secara manual.


Perintah fullwindow() memperluas jendela plot karena kita tidak lagi
membutuhkan tempat untuk label di luar jendela plot. Gunakan
shrinkwindow() atau reset() untuk mengatur ulang ke default.


\>fullwindow; ...  
\>    gridstyle(color=darkgray,textcolor=darkgray); ...  
\>    plot2d(["2^x","1","2^(-x)"],a=-2,b=2,c=0,d=4,<grid,color=4:6,<frame); ...  
\>    xaxis(0,-2:1,style="-\>"); xaxis(0,2,"x",<axis); ...  
\>    yaxis(0,4,"y",style="-\>"); ...  
\>    yaxis(-2,1:4,\>left); ...  
\>    yaxis(2,2^(-2:2),style=".",<left); ...  
\>    labelbox(["2^x","1","2^-x"],colors=4:6,x=0.8,y=0.2); ...  
\>    reset:


![images/2_EMT_2D-082.png](images/2_EMT_2D-082.png)

Berikut adalah contoh lain, di mana string Unicode digunakan dan sumbu
di luar area plot.


\>aspect(1.5); 

\>plot2d(["sin(x)","cos(x)"],0,2pi,color=[red,green],<grid,<frame); ...  
\>    xaxis(-1.1,(0:2)\*pi,xt=["0",u"&pi;",u"2&pi;"],style="-",\>ticks,\>zero);  ...  
\>    xgrid((0:0.5:2)\*pi,<ticks); ...  
\>    yaxis(-0.1\*pi,-1:0.2:1,style="-",\>zero,\>grid); ...  
\>    labelbox(["sin","cos"],colors=[red,green],x=0.5,y=0.2,\>left); ...  
\>    xlabel(u"&phi;"); ylabel(u"f(&phi;)"):


![images/2_EMT_2D-083.png](images/2_EMT_2D-083.png)

# Memetok Data 2D

Jika x dan y adalah vektor data, data ini akan digunakan sebagai
koordinat x dan y dari kurva. Dalam hal ini, a, b, c, dan d, atau
jari-jari r dapat ditentukan, atau jendela plot akan menyesuaikan
secara otomatis dengan data. Atau, &gt; persegi dapat diatur untuk
mempertahankan rasio aspek persegi.


Memplot ekspresi hanyalah singkatan dari plot data. Untuk plot data,
Anda memerlukan satu atau lebih baris nilai-x, dan satu atau lebih
baris nilai-y. Dari rentang dan nilai-x, fungsi plot2d akan menghitung
data untuk diplot, secara default dengan evaluasi adaptif dari fungsi
tersebut. Untuk plot titik gunakan "&gt;titik", untuk garis campuran dan
titik gunakan "&gt;titik tambahan".


Tetapi Anda dapat memasukkan data secara langsung.


* 
Gunakan vektor baris untuk x dan y untuk satu fungsi.

* 
Matriks untuk x dan y diplot baris demi baris.


Berikut adalah contoh dengan satu baris untuk x dan y.


\>x=-10:0.1:10; y=exp(-x^2)\*x; plot2d(x,y):


![images/2_EMT_2D-084.png](images/2_EMT_2D-084.png)

Data juga dapat diplot sebagai titik. Gunakan points=true untuk ini.
Plotnya bekerja seperti poligon, tetapi hanya menggambar sudutnya.


* 
style="...": Pilih dari "[]", "&lt;&gt;", "o", ".", "..", "+", "*", "[]#",
* "&lt;&gt;#", "o#", ".. #", "#", "|".


Untuk memplot kumpulan titik, gunakan &gt;titik. Jika warna adalah vektor
warna, masing-masing menunjuk


mendapat warna yang berbeda. Untuk matriks koordinat dan vektor kolom,
warna berlaku untuk baris matriks.


Parameter &gt;addpoints menambahkan titik ke segmen garis untuk plot
data.


\>xdata=[1,1.5,2.5,3,4]; ydata=[3,3.1,2.8,2.9,2.7]; // data

\>plot2d(xdata,ydata,a=0.5,b=4.5,c=2.5,d=3.5,style="."); // lines

\>plot2d(xdata,ydata,\>points,\>add,style="o"): // add points


![images/2_EMT_2D-085.png](images/2_EMT_2D-085.png)

\>p=polyfit(xdata,ydata,1); // get regression line

\>plot2d("polyval(p,x)",\>add,color=red): // add plot of line


![images/2_EMT_2D-086.png](images/2_EMT_2D-086.png)

# Menggambar Daerah Yang Dibatasi Kurva

Plot data benar-benar poligon. Kita juga dapat memplot kurva atau
kurva yang diisi.


* 
filled=true mengisi plot.

* 
style="...": Pilih dari "#", "/", "", "/".

* 
fillcolor: Lihat di atas untuk warna yang tersedia.


Warna isian ditentukan oleh argumen "fillcolor", dan pada &lt;outline
opsional mencegah menggambar batas untuk semua gaya kecuali yang
default.


\>t=linspace(0,2pi,1000); // parameter for curve


Perintah ini menghasilkan vektor t yang berisi 1000 titik yang
terdistribusi secara merata dari 0 hingga 2pi


\>x=sin(t)\*exp(t/pi); y=cos(t)\*exp(t/pi); // x(t) and y(t)

\>figure(1,2); aspect(16/9)

\>figure(1); plot2d(x,y,r=10); // plot curve

\>figure(2); plot2d(x,y,r=10,\>filled,style="/",fillcolor=red); // fill curve

\>figure(0):


![images/2_EMT_2D-087.png](images/2_EMT_2D-087.png)

Dalam contoh berikut, kita memplot elips terisi dan dua segi enam
terisi menggunakan kurva tertutup dengan 6 titik dengan gaya isian
yang berbeda.


\>x=linspace(0,2pi,1000); plot2d(sin(x),cos(x)\*0.5,r=1,\>filled,style="/"):


![images/2_EMT_2D-088.png](images/2_EMT_2D-088.png)

\>t=linspace(0,2pi,6); ...  
\>   plot2d(cos(t),sin(t),\>filled,style="/",fillcolor=red,r=1.2):


![images/2_EMT_2D-089.png](images/2_EMT_2D-089.png)

\>t=linspace(0,2pi,6); plot2d(cos(t),sin(t),\>filled,style="#"):


![images/2_EMT_2D-090.png](images/2_EMT_2D-090.png)

Contoh lain adalah septagon, yang kami buat dengan 7 titik pada
lingkaran satuan.


\>t=linspace(0,2pi,7);  ...  
\>    plot2d(cos(t),sin(t),r=1,\>filled,style="/",fillcolor=red):


![images/2_EMT_2D-091.png](images/2_EMT_2D-091.png)

Berikut ini adalah himpunan nilai maksimal dari empat kondisi linier
kurang dari atau sama dengan 3. Ini adalah A[k].v&lt;=3 untuk semua baris
A. Untuk mendapatkan sudut yang bagus, kami menggunakan n yang relatif
besar.


\>A=[2,1;1,2;-1,0;0,-1];

\>function f(x,y) := max([x,y].A');

\>plot2d("f",r=4,level=[0;3],color=green,n=111):


![images/2_EMT_2D-092.png](images/2_EMT_2D-092.png)

Poin utama dari bahasa matriks adalah memungkinkan untuk menghasilkan
tabel fungsi dengan mudah.


\>t=linspace(0,2pi,1000); x=cos(3\*t); y=sin(4\*t);


Kita sekarang memiliki vektor x dan y dari nilai. plot2d() dapat
memplot nilai-nilai ini


sebagai kurva yang menghubungkan titik-titik. Plot bisa diisi. Dalam
hal ini


Ini menghasilkan hasil yang bagus karena aturan penggulitan, yang
digunakan untuk


isi.


\>plot2d(x,y,<grid,<frame,\>filled):


![images/2_EMT_2D-093.png](images/2_EMT_2D-093.png)

Vektor interval diplot terhadap nilai x sebagai wilayah yang diisi


antara nilai interval yang lebih rendah dan atas.


Ini dapat berguna untuk memplot kesalahan perhitungan. Tapi itu bisa


juga digunakan untuk memplot kesalahan statistik.


\>t=0:0.1:1; ...  
\>    plot2d(t,interval(t-random(size(t)),t+random(size(t))),style="|");  ...  
\>    plot2d(t,t,add=true):


![images/2_EMT_2D-094.png](images/2_EMT_2D-094.png)

Jika x adalah vektor yang diurutkan, dan y adalah vektor interval,
maka plot2d akan memplot rentang interval yang terisi dalam bidang.
Gaya isian sama dengan gaya poligon.


\>t=-1:0.01:1; x=~t-0.01,t+0.01~; y=x^3-x;

\>plot2d(t,y):


![images/2_EMT_2D-095.png](images/2_EMT_2D-095.png)

Dimungkinkan untuk mengisi wilayah nilai untuk fungsi tertentu. Bagi


ini, level harus matriks 2xn. Baris pertama adalah batas bawah


dan baris kedua berisi batas atas.


\>expr := "2\*x^2+x\*y+3\*y^4+y"; // define an expression f(x,y)

\>plot2d(expr,level=[0;1],style="-",color=blue): // 0 <= f(x,y) <= 1


![images/2_EMT_2D-096.png](images/2_EMT_2D-096.png)

We can also fill ranges of values like


$$-1 \le (x^2+y^2)^2-x^2+y^2 \le 0.$$\>plot2d("(x^2+y^2)^2-x^2+y^2",r=1.2,level=[-1;0],style="/"):


![images/2_EMT_2D-098.png](images/2_EMT_2D-098.png)

\>plot2d("cos(x)","sin(x)^3",xmin=0,xmax=2pi,\>filled,style="/"):


![images/2_EMT_2D-099.png](images/2_EMT_2D-099.png)

# Grafik Fungsi Parametrik

Nilai x tidak perlu diurutkan. (x,y) hanya menggambarkan kurva. Jika x
diurutkan, kurva adalah grafik dari suatu fungsi.


Dalam contoh berikut, kita memplot spiral


lateks: gamma(t) = t cdot (cos(2pi t),sin(2pi t))


Kita perlu menggunakan sangat banyak titik untuk tampilan yang halus
atau fungsi adaptive() untuk mengevaluasi ekspresi (lihat fungsi
adaptive() untuk lebih jelasnya).


\>t=linspace(0,1,1000); ...  
\>   plot2d(t\*cos(2\*pi\*t),t\*sin(2\*pi\*t),r=1):


![images/2_EMT_2D-100.png](images/2_EMT_2D-100.png)

Atau, dimungkinkan untuk menggunakan dua ekspresi untuk kurva. Berikut
ini memplot kurva yang sama seperti di atas.


\>plot2d("x\*cos(2\*pi\*x)","x\*sin(2\*pi\*x)",xmin=0,xmax=1,r=1):


![images/2_EMT_2D-101.png](images/2_EMT_2D-101.png)

\>t=linspace(0,1,1000); r=exp(-t); x=r\*cos(2pi\*t); y=r\*sin(2pi\*t);

\>plot2d(x,y,r=1):


![images/2_EMT_2D-102.png](images/2_EMT_2D-102.png)

Pada contoh berikutnya, kita memplot kurva


$$\gamma(t) = (r(t) \cos(t), r(t) \sin(t))$$dengan


$$r(t) = 1 + \dfrac{\sin(3t)}{2}.$$\>t=linspace(0,2pi,1000); r=1+sin(3\*t)/2; x=r\*cos(t); y=r\*sin(t); ...  
\>   plot2d(x,y,\>filled,fillcolor=red,style="/",r=1.5):


![images/2_EMT_2D-105.png](images/2_EMT_2D-105.png)

# Menggambar Grafik Bilangan Kompleks

Array bilangan kompleks juga dapat diplot. Kemudian titik jaringan
akan terhubung. Jika sejumlah garis kisi ditentukan (atau vektor garis
kisi 1x2) dalam argumen cgrid hanya garis kisi yang terlihat.


Matriks bilangan kompleks akan secara otomatis diplot sebagai kisi
dalam bidang kompleks.


Dalam contoh berikut, kita memplot gambar lingkaran satuan di bawah
fungsi eksponensial. Parameter cgrid menyembunyikan beberapa kurva
grid.


\>aspect(); r=linspace(0,1,50); a=linspace(0,2pi,80)'; z=r\*exp(I\*a);...  
\>   plot2d(z,a=-1.25,b=1.25,c=-1.25,d=1.25,cgrid=10):


![images/2_EMT_2D-106.png](images/2_EMT_2D-106.png)

\>aspect(1.25); r=linspace(0,1,50); a=linspace(0,2pi,200)'; z=r\*exp(I\*a);

\>plot2d(exp(z),cgrid=[40,10]):


![images/2_EMT_2D-107.png](images/2_EMT_2D-107.png)

\>r=linspace(0,1,10); a=linspace(0,2pi,40)'; z=r\*exp(I\*a);

\>plot2d(exp(z),\>points,\>add):


![images/2_EMT_2D-108.png](images/2_EMT_2D-108.png)

Vektor bilangan kompleks secara otomatis diplot sebagai kurva dalam
bidang kompleks dengan bagian real dan bagian imajiner.


Dalam contoh, kita memplot lingkaran satuan dengan


$$\gamma(t) = e^{it}$$\>t=linspace(0,2pi,1000); ...  
\>   plot2d(exp(I\*t)+exp(4\*I\*t),r=2):


![images/2_EMT_2D-110.png](images/2_EMT_2D-110.png)

# Plot Statistik

Ada banyak fungsi yang mengkhususkan diri pada plot statistik. Salah
satu plot yang sering digunakan adalah plot kolom.


Jumlah kumulatif dari nilai terdistribusi 0-1-normal menghasilkan
jalan acak.


\>plot2d(cumsum(randnormal(1,1000))):


![images/2_EMT_2D-111.png](images/2_EMT_2D-111.png)

Menggunakan dua baris menunjukkan jalan dalam dua dimensi.


\>X=cumsum(randnormal(2,1000)); plot2d(X[1],X[2]):


![images/2_EMT_2D-112.png](images/2_EMT_2D-112.png)

\>columnsplot(cumsum(random(10)),style="/",color=blue):


![images/2_EMT_2D-113.png](images/2_EMT_2D-113.png)

Ini juga dapat menampilkan string sebagai label.


\>months=["Jan","Feb","Mar","Apr","May","Jun", ...  
\>     "Jul","Aug","Sep","Oct","Nov","Dec"];

\>values=[10,12,12,18,22,28,30,26,22,18,12,8];

\>columnsplot(values,lab=months,color=red,style="-");

\>title("Temperature"):


![images/2_EMT_2D-114.png](images/2_EMT_2D-114.png)

\>k=0:10;

\>plot2d(k,bin(10,k),\>bar):


![images/2_EMT_2D-115.png](images/2_EMT_2D-115.png)

\>plot2d(k,bin(10,k)); plot2d(k,bin(10,k),\>points,\>add):


![images/2_EMT_2D-116.png](images/2_EMT_2D-116.png)

\>plot2d(normal(1000),normal(1000),\>points,grid=6,style=".."):


![images/2_EMT_2D-117.png](images/2_EMT_2D-117.png)

\>plot2d(normal(1,1000),\>distribution,style="O"):


![images/2_EMT_2D-118.png](images/2_EMT_2D-118.png)

\>plot2d("qnormal",0,5;2.5,0.5,\>filled):


![images/2_EMT_2D-119.png](images/2_EMT_2D-119.png)

Untuk memplot distribusi statistik eksperimental, Anda dapat
menggunakan distribution=n dengan plot2d.


\>w=randexponential(1,1000); // exponential distribution

\>plot2d(w,\>distribution): // or distribution=n with n intervals


![images/2_EMT_2D-120.png](images/2_EMT_2D-120.png)

Atau Anda dapat menghitung distribusi dari data dan memplot hasilnya
dengan &gt;bar di plot3d, atau dengan plot kolom.


\>w=normal(1000); // 0-1-normal distribution

\>{x,y}=histo(w,10,v=[-6,-4,-2,-1,0,1,2,4,6]); // interval bounds v

\>plot2d(x,y,\>bar):


![images/2_EMT_2D-121.png](images/2_EMT_2D-121.png)

Fungsi statplot() mengatur gaya dengan string sederhana.


\>statplot(1:10,cumsum(random(10)),"b"):


![images/2_EMT_2D-122.png](images/2_EMT_2D-122.png)

\>n=10; i=0:n; ...  
\>   plot2d(i,bin(n,i)/2^n,a=0,b=10,c=0,d=0.3); ...  
\>   plot2d(i,bin(n,i)/2^n,points=true,style="ow",add=true,color=blue):


![images/2_EMT_2D-123.png](images/2_EMT_2D-123.png)

Selain itu, data dapat diplot sebagai batang. Dalam hal ini, x harus
diurutkan dan satu elemen lebih panjang dari y. Bilah akan memanjang
dari x[i] ke x[i+1] dengan nilai y[i]. Jika x memiliki ukuran yang
sama dengan y, itu akan diperpanjang oleh satu elemen dengan spasi
terakhir.


Gaya isian dapat digunakan seperti di atas.


\>n=10; k=bin(n,0:n); ...  
\>   plot2d(-0.5:n+0.5,k,bar=true,fillcolor=lightgray):


![images/2_EMT_2D-124.png](images/2_EMT_2D-124.png)

Data untuk plot batang (bar=1) dan histogram (histogram=1) dapat
diberikan secara eksplisit dalam xv dan yv, atau dapat dihitung dari
distribusi empiris dalam xv dengan &gt;distribusi (atau distribusi=n).
Histogram nilai xv akan dihitung secara otomatis dengan &gt;histogram.
Jika &gt;genap ditentukan, nilai xv akan dihitung dalam interval bilangan
bulat.


\>plot2d(normal(10000),distribution=50):


![images/2_EMT_2D-125.png](images/2_EMT_2D-125.png)

\>k=0:10; m=bin(10,k); x=(0:11)-0.5; plot2d(x,m,\>bar):


![images/2_EMT_2D-126.png](images/2_EMT_2D-126.png)

\>columnsplot(m,k):


![images/2_EMT_2D-127.png](images/2_EMT_2D-127.png)

\>plot2d(random(600)\*6,histogram=6):


![images/2_EMT_2D-128.png](images/2_EMT_2D-128.png)

Untuk distribusi, ada parameter distribution=n, yang menghitung nilai
secara otomatis dan mencetak distribusi relatif dengan n sub-interval.


\>plot2d(normal(1,1000),distribution=10,style="\\/"):


![images/2_EMT_2D-129.png](images/2_EMT_2D-129.png)

Dengan parameter even=true, ini akan menggunakan interval bilangan
bulat.


\>plot2d(intrandom(1,1000,10),distribution=10,even=true):


![images/2_EMT_2D-130.png](images/2_EMT_2D-130.png)

Perhatikan bahwa ada banyak plot statistik, yang mungkin berguna.
Lihatlah tutorial tentang statistik.


\>columnsplot(getmultiplicities(1:6,intrandom(1,6000,6))):


![images/2_EMT_2D-131.png](images/2_EMT_2D-131.png)

\>plot2d(normal(1,1000),\>distribution); ...  
\>     plot2d("qnormal(x)",color=red,thickness=2,\>add):


![images/2_EMT_2D-132.png](images/2_EMT_2D-132.png)

Ada juga banyak plot khusus untuk statistik. Boxplot menunjukkan
kuartil distribusi ini dan banyak outlier. Menurut definisi, outlier
dalam boxplot adalah data yang melebihi 1,5 kali rentang 50% tengah
plot.


\>M=normal(5,1000); boxplot(quartiles(M)):


![images/2_EMT_2D-133.png](images/2_EMT_2D-133.png)

# Fungsi Implisit

Plot implisit menunjukkan garis level yang menyelesaikan f(x,y)=level,
di mana "level" dapat berupa nilai tunggal atau vektor nilai. Jika
level="auto", akan ada garis level nc, yang akan menyebar antara
minimum dan maksimum fungsi secara merata. Warna yang lebih gelap atau
lebih terang dapat ditambahkan dengan &gt;hue untuk menunjukkan nilai
fungsi. Untuk fungsi implisit, xv harus berupa fungsi atau ekspresi
dari parameter x dan y, atau, sebagai alternatif, xv dapat berupa
matriks nilai.


Euler dapat menandai garis level


lateks: f(x,y) = c


dari fungsi apa pun.


Untuk menggambar himpunan f(x,y)=c untuk satu atau lebih konstanta c,
Anda dapat menggunakan plot2d() dengan plot implisitnya di bidang.
Parameter untuk c adalah level=c, di mana c dapat berupa vektor garis
level. Selain itu, skema warna dapat digambar di latar belakang untuk
menunjukkan nilai fungsi untuk setiap titik dalam plot. Parameter "n"
menentukan kehalusan plot.


\>aspect(1.5); 

\>plot2d("x^2+y^2-x\*y-x",r=1.5,level=0,contourcolor=red):


![images/2_EMT_2D-134.png](images/2_EMT_2D-134.png)

\>expr := "2\*x^2+x\*y+3\*y^4+y"; // define an expression f(x,y)

\>plot2d(expr,level=0): // Solutions of f(x,y)=0


![images/2_EMT_2D-135.png](images/2_EMT_2D-135.png)

\>plot2d(expr,level=0:0.5:20,\>hue,contourcolor=white,n=200): // nice


![images/2_EMT_2D-136.png](images/2_EMT_2D-136.png)

\>plot2d(expr,level=0:0.5:20,\>hue,\>spectral,n=200,grid=4): // nicer


![images/2_EMT_2D-137.png](images/2_EMT_2D-137.png)

Ini juga berfungsi untuk plot data. Tetapi Anda harus menentukan
rentang


untuk label sumbu.


\>x=-2:0.05:1; y=x'; z=expr(x,y);

\>plot2d(z,level=0,a=-1,b=2,c=-2,d=1,\>hue):


![images/2_EMT_2D-138.png](images/2_EMT_2D-138.png)

\>plot2d("x^3-y^2",\>contour,\>hue,\>spectral):


![images/2_EMT_2D-139.png](images/2_EMT_2D-139.png)

\>plot2d("x^3-y^2",level=0,contourwidth=3,\>add,contourcolor=red):


![images/2_EMT_2D-140.png](images/2_EMT_2D-140.png)

\>z=z+normal(size(z))\*0.2;

\>plot2d(z,level=0.5,a=-1,b=2,c=-2,d=1):


![images/2_EMT_2D-141.png](images/2_EMT_2D-141.png)

\>plot2d(expr,level=[0:0.2:5;0.05:0.2:5.05],color=lightgray):


![images/2_EMT_2D-142.png](images/2_EMT_2D-142.png)

\>plot2d("x^2+y^3+x\*y",level=1,r=4,n=100):


![images/2_EMT_2D-143.png](images/2_EMT_2D-143.png)

\>plot2d("x^2+2\*y^2-x\*y",level=0:0.1:10,n=100,contourcolor=white,\>hue):


![images/2_EMT_2D-144.png](images/2_EMT_2D-144.png)

Dimungkinkan juga untuk mengisi set


$$a \le f(x,y) \le b$$

dengan rentang level.


Dimungkinkan untuk mengisi wilayah nilai untuk fungsi tertentu. Untuk
ini, level harus berupa matriks 2xn. Baris pertama adalah batas bawah
dan baris kedua berisi batas atas.


\>plot2d(expr,level=[0;1],style="-",color=blue): // 0 <= f(x,y) <= 1


![images/2_EMT_2D-146.png](images/2_EMT_2D-146.png)

Plot implisit juga dapat menunjukkan rentang level. Kemudian level
harus berupa matriks 2xn dari interval level, di mana baris pertama
berisi awal dan baris kedua akhir dari setiap interval. Atau, vektor
baris sederhana dapat digunakan untuk level, dan parameter dl
memperluas nilai level ke interval.


\>plot2d("x^4+y^4",r=1.5,level=[0;1],color=blue,style="/"):


![images/2_EMT_2D-147.png](images/2_EMT_2D-147.png)

\>plot2d("x^2+y^3+x\*y",level=[0,2,4;1,3,5],style="/",r=2,n=100):


![images/2_EMT_2D-148.png](images/2_EMT_2D-148.png)

\>plot2d("x^2+y^3+x\*y",level=-10:20,r=2,style="-",dl=0.1,n=100):


![images/2_EMT_2D-149.png](images/2_EMT_2D-149.png)

\>plot2d("sin(x)\*cos(y)",r=pi,\>hue,\>levels,n=100):


![images/2_EMT_2D-150.png](images/2_EMT_2D-150.png)

Dimungkinkan juga untuk menandai suatu wilayah


$$a \le f(x,y) \le b.$$Ini dilakukan dengan menambahkan level dengan dua baris.


\>plot2d("(x^2+y^2-1)^3-x^2\*y^3",r=1.3, ...  
\>     style="#",color=red,<outline, ...  
\>     level=[-2;0],n=100):


![images/2_EMT_2D-152.png](images/2_EMT_2D-152.png)

Dimungkinkan untuk menentukan tingkat tertentu. Misalnya, kita dapat
memplot solusi dari persamaan seperti


$$x^3-xy+x^2y^2=6$$\>plot2d("x^3-x\*y+x^2\*y^2",r=6,level=1,n=100):


![images/2_EMT_2D-154.png](images/2_EMT_2D-154.png)

\>function starplot1 (v, style="/", color=green, lab=none) ...


      if !holding() then clg; endif;
      w=window(); window(0,0,1024,1024);
      h=holding(1);
      r=max(abs(v))*1.2;
      setplot(-r,r,-r,r);
      n=cols(v); t=linspace(0,2pi,n);
      v=v|v[1]; c=v*cos(t); s=v*sin(t);
      cl=barcolor(color); st=barstyle(style);
      loop 1 to n
        polygon([0,c[#],c[#+1]],[0,s[#],s[#+1]],1);
        if lab!=none then
          rlab=v[#]+r*0.1;
          {col,row}=toscreen(cos(t[#])*rlab,sin(t[#])*rlab);
          ctext(""+lab[#],col,row-textheight()/2);
        endif;
      end;
      barcolor(cl); barstyle(st);
      holding(h);
      window(w);
    endfunction
</pre>
Tidak ada kutu kisi atau sumbu di sini. Selain itu, kami menggunakan
jendela penuh untuk plot.


Kami memanggil reset sebelum kami menguji plot ini untuk mengembalikan
default grafis. Ini tidak perlu, jika Anda yakin bahwa plot Anda
berhasil.


\>reset; starplot1(normal(1,10)+5,color=red,lab=1:10):


![images/2_EMT_2D-155.png](images/2_EMT_2D-155.png)

Terkadang, Anda mungkin ingin merencanakan sesuatu yang tidak dapat
dilakukan plot2d, tetapi hampir.


Dalam fungsi berikut, kita melakukan plot impuls logaritma. Plot2d
dapat melakukan plot logaritma, tetapi tidak untuk bilah impuls.


\>function logimpulseplot1 (x,y) ...


      {x0,y0}=makeimpulse(x,log(y)/log(10));
      plot2d(x0,y0,>bar,grid=0);
      h=holding(1);
      frame();
      xgrid(ticks(x));
      p=plot();
      for i=-10 to 10;
        if i<=p[4] and i>=p[3] then
           ygrid(i,yt="10^"+i);
        endif;
      end;
      holding(h);
    endfunction
</pre>
Mari kita ujinya dengan nilai yang didistribusikan secara
eksponensial.


\>aspect(1.5); x=1:10; y=-log(random(size(x)))\*200; ...  
\>   logimpulseplot1(x,y):


![images/2_EMT_2D-156.png](images/2_EMT_2D-156.png)

Mari kita animasikan kurva 2D menggunakan plot langsung. Perintah
plot(x,y) hanya memplot kurva ke jendela plot. setplot(a,b,c,d)
mengatur jendela ini.


Fungsi wait(0) memaksa plot muncul di jendela grafis. Jika tidak,
penggambaran ulang terjadi dalam interval waktu yang jarang.


\>function animliss (n,m) ...


    t=linspace(0,2pi,500);
    f=0;
    c=framecolor(0);
    l=linewidth(2);
    setplot(-1,1,-1,1);
    repeat
      clg;
      plot(sin(n*t),cos(m*t+f));
      wait(0);
      if testkey() then break; endif;
      f=f+0.02;
    end;
    framecolor(c);
    linewidth(l);
    endfunction
</pre>
Tekan tombol apa saja untuk menghentikan animasi ini.


\>animliss(2,3); // lihat hasilnya, jika sudah puas, tekan ENTER


# Plot Logaritma

EMT menggunakan parameter "logplot" untuk skala logaritma.


Plot logaritma dapat diplot baik menggunakan skala logaritma di y
dengan logplot=1, atau menggunakan skala logaritma di x dan y dengan
logplot=2, atau di x dengan logplot=3.


* 
logplot=1: logaritma y

* 
logplot=2: x-y-logaritma

* 
logplot=3: x-logaritma


\>plot2d("exp(x^3-x)\*x^2",1,5,logplot=1):


![images/2_EMT_2D-157.png](images/2_EMT_2D-157.png)

\>plot2d("exp(x+sin(x))",0,100,logplot=1):


![images/2_EMT_2D-158.png](images/2_EMT_2D-158.png)

\>plot2d("exp(x+sin(x))",10,100,logplot=2):


![images/2_EMT_2D-159.png](images/2_EMT_2D-159.png)

\>plot2d("gamma(x)",1,10,logplot=1):


![images/2_EMT_2D-160.png](images/2_EMT_2D-160.png)

\>plot2d("log(x\*(2+sin(x/100)))",10,1000,logplot=3):


![images/2_EMT_2D-161.png](images/2_EMT_2D-161.png)

Ini juga berfungsi dengan plot data.


\>x=10^(1:20); y=x^2-x;

\>plot2d(x,y,logplot=2):


![images/2_EMT_2D-162.png](images/2_EMT_2D-162.png)

\>function f(x):= (1/3)x^3-x^2-3\*x+4

\>plot2d("f",-4,5):


![images/2_EMT_2D-163.png](images/2_EMT_2D-163.png)

# Contoh lain dan soal:

\>plot2d("x^7+y^9+x\*y",level=1,r=5,n=200):


![images/2_EMT_2D-164.png](images/2_EMT_2D-164.png)

\>plot2d(normal(1,1000),\>distribution); ...  
\>     plot2d("qnormal(x)",color=black,thickness=7,\>add):


![images/2_EMT_2D-165.png](images/2_EMT_2D-165.png)

\>plot2d("x^3-y^9",\>contour,\>hue,\>spectral):


![images/2_EMT_2D-166.png](images/2_EMT_2D-166.png)

\>reset;...  
\>  
Buatlah kurva dengan k dari 1 sampai 10, dengan fungsi


$$x^5-3x$$\>figure(5,2);...  
\>   for k=1:10; figure(k); plot2d("x^5-3x",-3,2,grid=k); end;...  
\>   figure(0):


![images/2_EMT_2D-168.png](images/2_EMT_2D-168.png)

Gambar plot fungsi berikut:


$$x^{1+n},1 <= n <=5$$Penyelesaian:


\>reset;...  
\>   figure(2,2);...  
\>   for n=1 to 5; figure(n); plot2d("x^1"+n); end;... 

\>figure(0):


![images/2_EMT_2D-170.png](images/2_EMT_2D-170.png)

Gambarkan grafik fungsi berikut:


$$x^5+x+4$$$$4x^2+2x^2+4$$$$x^2+9x$$\>reset;...  
\>   aspect(3,1);...  
\>   figure(1,3); figure(1); plot2d("x^5+x+4", grid=2);...  
\>   figure(2); plot2d("4x^2x^2+4", grid=5);...  
\>   figure(3); plot2d("x^2+9x", grid=4);...  
\>   figure(0):


![images/2_EMT_2D-174.png](images/2_EMT_2D-174.png)

\>plot2d("x^3+y^3",r=1.5,level=[0;1],color=blue,style="/"):


![images/2_EMT_2D-175.png](images/2_EMT_2D-175.png)

\>plot2d("(x^3+y^3-2)^3-x^2\*y^3",r=1.3, ...  
\>     style="#",color=red,<outline, ...  
\>     level=[-2;0],n=100):


![images/2_EMT_2D-176.png](images/2_EMT_2D-176.png)

\>plot2d("sin(x)\*cos(y)",r=2pi,\>hue,\>levels,n=100):


![images/2_EMT_2D-177.png](images/2_EMT_2D-177.png)

\>plot2d("x^3+2\*y^3-x\*y",level=0:0.1:10,n=100,contourcolor=white,\>hue):


![images/2_EMT_2D-178.png](images/2_EMT_2D-178.png)

\>plot2d(normal(1,1000),\>distribution); ...  
\>     plot2d("qnormal(x)",color=red,thickness=3,\>add):


![images/2_EMT_2D-179.png](images/2_EMT_2D-179.png)

\>M=normal(5,1000); boxplot(quartiles(M)):


![images/2_EMT_2D-180.png](images/2_EMT_2D-180.png)

\>plot2d(random(500)\*5,histogram=5):


![images/2_EMT_2D-181.png](images/2_EMT_2D-181.png)

# Rujukan Lengkap Fungsi plot2d()

  function plot2d (xv, yv, btest, a, b, c, d, xmin, xmax, r, n,  ..  
  logplot, grid, frame, framecolor, square, color, thickness, style, ..  
  auto, add, user, delta, points, addpoints, pointstyle, bar, histogram,  ..  
  distribution, even, steps, own, adaptive, hue, level, contour,  ..  
  nc, filled, fillcolor, outline, title, xl, yl, maps, contourcolor, ..  
  contourwidth, ticks, margin, clipping, cx, cy, insimg, spectral,  ..  
  cgrid, vertical, smaller, dl, niveau, levels)  

Multipurpose plot function for plots in the plane (2D plots). This function can do
plots of functions of one variables, data plots, curves in the plane, bar plots, grids
of complex numbers, and implicit plots of functions of two variables.


Parameters




x,y       : equations, functions or data vectors


a,b,c,d   : Plot area (default a=-2,b=2)


r         : if r is set, then a=cx-r, b=cx+r, c=cy-r, d=cy+r


            r can be a vector [rx,ry] or a vector [rx1,rx2,ry1,ry2].


xmin,xmax : range of the parameter for curves


auto      : Determine y-range automatically (default)


square    : if true, try to keep square x-y-ranges


n         : number of intervals (default is adaptive)


grid      : 0 = no grid and labels,


            1 = axis only,


            2 = normal grid (see below for the number of grid lines)


            3 = inside axis


            4 = no grid


            5 = full grid including margin


            6 = ticks at the frame


            7 = axis only


            8 = axis only, sub-ticks


frame     : 0 = no frame


framecolor: color of the frame and the grid


margin    : number between 0 and 0.4 for the margin around the plot


color     : Color of curves. If this is a vector of colors,


            it will be used for each row of a matrix of plots. In the case of


            point plots, it should be a column vector. If a row vector or a


            full matrix of colors is used for point plots, it will be used for


            each data point.


thickness : line thickness for curves


            This value can be smaller than 1 for very thin lines.


style     : Plot style for lines, markers, and fills.


            For points use


            "[]", "&lt;&gt;", ".", "..", "...",


            "*", "+", "|", "-", "o"


            "[]#", "&lt;&gt;#", "o#" (filled shapes)


            "[]w", "&lt;&gt;w", "ow" (non-transparent)


            For lines use


            "-", "--", "-.", ".", ".-.", "-.-", "-&gt;"


            For filled polygons or bar plots use


            "#", "#O", "O", "/", "\", "\/",


            "+", "|", "-", "t"


points    : plot single points instead of line segments


addpoints : if true, plots line segments and points


add       : add the plot to the existing plot


user      : enable user interaction for functions


delta     : step size for user interaction


bar       : bar plot (x are the interval bounds, y the interval values)


histogram : plots the frequencies of x in n subintervals


distribution=n : plots the distribution of x with n subintervals


even      : use inter values for automatic histograms.


steps     : plots the function as a step function (steps=1,2)


adaptive  : use adaptive plots (n is the minimal number of steps)


level     : plot level lines of an implicit function of two variables


outline   : draws boundary of level ranges.




If the level value is a 2xn matrix, ranges of levels will be drawn


in the color using the given fill style. If outline is true, it


will be drawn in the contour color. Using this feature, regions of


f(x,y) between limits can be marked.




hue       : add hue color to the level plot to indicate the function


            value


contour   : Use level plot with automatic levels


nc        : number of automatic level lines


title     : plot title (default "")


xl, yl    : labels for the x- and y-axis


smaller   : if &gt;0, there will be more space to the left for labels.


vertical  :


  Turns vertical labels on or off. This changes the global variable


  verticallabels locally for one plot. The value 1 sets only vertical


  text, the value 2 uses vertical numerical labels on the y axis.


filled    : fill the plot of a curve


fillcolor : fill color for bar and filled curves


outline   : boundary for filled polygons


logplot   : set logarithmic plots


            1 = logplot in y,


            2 = logplot in xy,


            3 = logplot in x


own       :


  A string, which points to an own plot routine. With &gt;user, you get


  the same user interaction as in plot2d. The range will be set


  before each call to your function.


maps      : map expressions (0 is faster), functions are always mapped.


contourcolor : color of contour lines


contourwidth : width of contour lines


clipping  : toggles the clipping (default is true)


title     :


  This can be used to describe the plot. The title will appear above


  the plot. Moreover, a label for the x and y axis can be added with


  xl="string" or yl="string". Other labels can be added with the


  functions label() or labelbox(). The title can be a unicode


  string or an image of a Latex formula.


cgrid     :


  Determines the number of grid lines for plots of complex grids.


  Should be a divisor of the the matrix size minus 1 (number of


  subintervals). cgrid can be a vector [cx,cy].


Overview


The function can plot


* 
expressions, call collections or functions of one variable,

* 
parametric curves,

* 
x data against y data,

* 
implicit functions,

* 
bar plots,

* 
complex grids,

* 
polygons.


If a function or expression for xv is given, plot2d() will compute


values in the given range using the function or expression. The


expression must be an expression in the variable x. The range must


be defined in the parameters a and b unless the default range


[-2,2] should be used. The y-range will be computed automatically,


unless c and d are specified, or a radius r, which yields the range


[-r,r] for x and y. For plots of functions, plot2d will use an


adaptive evaluation of the function by default. To speed up the


plot for complicated functions, switch this off with &lt;adaptive, and


optionally decrease the number of intervals n. Moreover, plot2d()


will by default use mapping. I.e., it will compute the plot element


for element. If your expression or your functions can handle a


vector x, you can switch that off with &lt;maps for faster evaluation.


Note that adaptive plots are always computed element for element. 


If functions or expressions for both xv and for yv are specified,


plot2d() will compute a curve with the xv values as x-coordinates


and the yv values as y-coordinates. In this case, a range should be


defined for the parameter using xmin, xmax. Expressions contained


in strings must always be expressions in the parameter variable x.


