# FarmingAI

## DESKRIPSI PRODUK

 <p align="justify">&nbsp;&nbsp;&nbsp;Farming.AI merupakan sebuah alat yang dapat melakukan irigasi pada lahan pertanian
secara otomatis dengan menggunakan mikrokontroler ESP32 berbasis Internet of
Things. Farming.AI juga terintegrasi dengan aplikasi android sehingga petani dapat
dengan mudah melakukan monitoring dan controlling pengairan lahan hanya
menggunakan android. Melalui aplikasi android yang dibuat, petani dapat mengatur
kapan waktu irigasi, berapa lama durasi irigasi dan berapa jumlah debit irigasi yang
diperlukan. Pengembangan dalam inovasi ini adalah penggunaan teknologi Artifficial
Intelligence yaitu Machine Learning sehingga Farming.AI dapat mengetahu kondisi
ideal dari kelembapan tanah yang cocok untuk tumbuhan. Apbila tanah sudah mulai
kering, maka Farming.AI akan melakukan pengairan secara otomatis. Dengan adanya
Farming.AI, kami yakin mampu meningkatkan efisiensi faktor produksi sehingga
Berjalan secara signifikan, meningkatkan produksi dan produktifitas pertanian, dan
mampu meningkatan daya saing produk pertanian.</p>
<p align="justify">&#9733;Keunggulan dari Farming.AI adalah sebagai berikut.
  <ol>
    <li>Monitoring dan Contolling irigasi dapat dilakukan dari jarak jauh secara realtime</li>
    <li>Menggunakan teknologi AI yaitu Machine Learning.</li>
    <li>Harga yang ditawarkan cukup terjangkau</li>
    <li>Pembuatan alat yang mudah dan mudah diterapkan</li>
    <li>Biaya listrik yang rendah</li>
    <li>Merupakan inovasi pertanian modern pertama di Indonesia yang berbasis AI</li>
  </ol>
</p>

### Perancangan Hardware (Mekanik)

![Screenshot 2024-01-19 000515](https://github.com/Bigbozz47/FarmingAI/assets/116621615/37d6832b-af44-4219-a3bd-49dba6290312)

 <p align="justify">&nbsp;&nbsp;&nbsp;Gambar 1 merupakan ilustrasi kondisi lingkungan pada pertanian sayur
kangkung. Berdasarkan kondisi lingkungan, tidak ada
sumur di daerah tersebut. Biasanya petani mengambil air dari rumah yang mengalir
dari PDAM. Hal ini tentunya meningkatkan biaya listirk. Oleh karena itu, sumber air
diambil dari sungai yang mengalir di samping jalan raya. Air ditarik menggunakan
pompa shimizu 220VAC dengan tekanan 150 Bar lalu dialirkan ke lahan untuk
pengairan. Air mengalir dari pipa dengan diameter ¾ inch. Disamping pompa
diletakkan box rangkaian yang berisi rangkain kelistrikan alat.</p>

![Screenshot 2024-01-19 000758](https://github.com/Bigbozz47/FarmingAI/assets/116621615/ab5e49b6-70bf-4125-9eed-502f61863a8f)

<p align="justify">&nbsp;&nbsp;&nbsp;Berdasarkan gambar 2, fungsi dari masing-masing komponen dijelaskan
sebagai berikut.
  <ol>
    <li>Box Rangkaian (Ukuran 250x250 mm)
        Kotak rangkaian berfungsi sebagai tempat komponen rangkaian. Box rangkaian terbuat dari bahan akrilik 3mm.</li>
    <li>ESP 32
Mikrokontroler ESP 32 berbasis Internet of Things (IoT) berfungsi sebagai otak
sistem. Menerima data dari sensor dan memberikan instruksi ke relay untuk
mengontrol perangkat lainnya.</li>
    <li>Relay 2 Channel
Relay digunakan sebagai saklar elektrik untuk mengontrol berbagai perangkat
elektrik dalam sistem, seperti Motor Pump dan ESP 32.</li>
    <li>Auto Buckboost DC-DC Converter
Berfungsi sebgai penurun tegangan dari 12 Volt ke 5 V karena ESP32 memiliki
tegangan input dengan rentang 3,3 – 5V DC.</li>
    <li>Power Supply
Menyediakan daya listrik untuk seluruh sistem, termasuk mikrokontroler, relay,
dan perangkat lainnya.
</li>
  </ol>
</p>

### Perancangan Hardware (Elektrik)

![Screenshot 2024-01-19 001518](https://github.com/Bigbozz47/FarmingAI/assets/116621615/2fa22d8a-33b3-4bdf-9dc3-053d46cdab04)

 <p align="justify">&nbsp;&nbsp;&nbsp;Berdasarkan gambar 3, dapat dijelaskan cara kerja rangkaian sebgai berikut.
Dimulai dari Power Supply atau trafo 3A berkekuatan 12V, aliran daya dialirkan
melalui auto buck boost untuk menjaga tegangan yang stabil. Mesin pompa air,
sebagai komponen vital dalam penyiraman lahan pertanian, terhubung ke relay 2
channel yang dapat diatur oleh mikrokontroler ESP32. Auto buck boost juga
terkoneksi dengan ESP32, menjadi jantung sistem yang mengatur operasi seluruh
rangkaian.</p>

<p align="justify">&nbsp;&nbsp;&nbsp;ESP32 berperan sebagai otak cerdas, menerima informasi dari sensor DHT11
yang memantau suhu dan kelembaban udara sekitar. Relay 2 channel berfungsi
sebagai penghubung antara ESP32 dan sensor soil moisture hygrometer yang
memantau kelembaban tanah. Melalui kerjasama yang terkoordinasi, ESP32
mengambil keputusan berdasarkan data yang diterima dari kedua sensor tersebut.
Ketika diperlukan, ESP32 memberikan instruksi kepada relay untuk mengaktifkan
atau menonaktifkan pompa air sesuai dengan kondisi lingkungan, memastikan bahwa
tanaman menerima pasokan air yang optimal. Rangkaian ini menciptakan sistem
irigasi yang cerdas, menggabungkan teknologi sensorik dan kontrol mikrokontroler
untuk meningkatkan efisiensi dalam pertanian.</p>

### Perancangan Software (Aplikasi Farming.AI)
<p align="justify">&nbsp;&nbsp;&nbsp;Perancangan apliasi dilakukan menggunakan MIT App Inventor dan
menggunakan firebase sebagai realtime database.</p>

![WhatsApp Image 2024-01-12 at 21 37 55](https://github.com/Bigbozz47/FarmingAI/assets/116621615/93c9b7fb-807f-412c-9795-64314428134f)

<p align="justify">&nbsp;&nbsp;&nbsp;Berdasarkan gambar 4, Aplikasi Farming AI memiliki desain antarmuka yang
terdiri dari beberapa fitur penting untuk memberikan kendali dan pemantauan yang
efektif kepada petani:
  <ol>
    <li>Pertama, terdapat menu login (Gambar 4(a)) yang memastikan akses yang aman
dengan mengharuskan pengguna memasukkan username dan password.</li>
    <li>Setelah masuk, pengguna diarahkan ke dashboard (Gambar 4(b)) yang
menawarkan dua opsi utama yaitu controlling dan monitoring.</li>
    <li>Di dalam menu "Controlling" (Gambar 4(c)), pengguna dapat memilih antara
mode manual dan mode off. Mode manual memungkinkan petani untuk secara
langsung mengontrol operasi Farming AI dengan kemampuan untuk memeriksa
kondisi air, ketersediaan pestisida, durasi irigasi, dan volume air yang digunakan.
Sementara itu, opsi "Off" mematikan sistem secara keseluruhan. Fitur ini
memberikan kontrol langsung kepada petani untuk menyesuaikan operasi sesuai
kebutuhan dan kondisi lapangan. Apabila menggunakan mode auto, maka sistem
akan menyiram lahan pertanian berdasarkan data kelembaban yang diterima dari
sensor kelembaban tanah dan sensor suhu menggunakan machine learning.
Apabila kelembapan tanah maupun udara lebih kecil atau lebih besar dari data
kondisi ideal, maka sistem akan hidup atau mati.
</li>
    <li>Selanjutnya, pada menu "Monitoring" (Gambar 4(d)), terdapat tiga fitur utama
yang memberikan informasi kritis untuk pertanian. Fitur pertama adalah
temperatur, yang memberikan pemantauan real-time terhadap suhu udara di
sekitar lahan pertanian. Fitur kedua adalah kelembapan udara, memberikan
informasi tentang tingkat kelembaban di lingkungan sekitar tanaman. Fitur
terakhir adalah kelembaban tanah, yang memantau tingkat kelembaban di tanah
untuk membantu dalam menentukan waktu yang tepat untuk irigasi. Dengan
kombinasi fitur ini, aplikasi Farming AI memberikan solusi terpadu untuk kontrol
dan pemantauan, meningkatkan efisiensi dan hasil pertanian.</li>
  </ol>
</p>

### Perancangan Sistem

![Screenshot 2024-01-19 002454](https://github.com/Bigbozz47/FarmingAI/assets/116621615/79581999-b3a7-4456-91f6-9bf80d84ff21)

<p align="justify">&nbsp;&nbsp;&nbsp;Berdasarkan gambar 5, cara kinerja sistem faming.AI yaitu data kelembapan
tanah dan udara diperoleh dari sensor kelembapan tanah dan sensor DHT11. Data
tersebut dikirim ke ESP32 sebagai pusat control. ESP32 mengirim data ke firebase
cloud untuk disimpan secara realtime. Data dari firebase cloud tersebut dapat dilihat
secara interaktif dari aplikasi farming.AI pada menu monitoing.</p>

<p align="justify">&nbsp;&nbsp;&nbsp;Apabila pengguna melakukan aksi pada menu controlling, maka data dari
aplikasi dikirm ke firebase. Data kemudian diteruskan ke mikrokontroller.
Mikrokontroler akan mengirimkan sinyal PWM berupa lebar pulsa (duty cicle) ke
relay untuk menghidupkan relay. Apabila relay yang tadinya NO berubah menjadi
NC, maka pompa akan hidup dan melakukan penyiraman lahan pertanian.</p>
