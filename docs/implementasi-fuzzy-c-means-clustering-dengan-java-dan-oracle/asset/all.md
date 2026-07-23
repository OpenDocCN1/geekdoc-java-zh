![](images/00128.jpeg)

# Cover

IMPLEMENTASI FUZZY C-MEANS CLUSTERING DENGAN JAVA DAN ORACLE

oleh Eko Heryanto

![](images/00001.jpeg)

Created with the Personal Edition of HelpNDoc: [Generate EPub eBooks with ease](http://www.helpndoc.com/create-epub-ebooks)

# Abstrak

# Abstrak

       Benchmarking, yaitu proses memberi batasan yang jelas antara poin Indeks Harga Saham Gabungan Bursa Efek Jakarta (IHSG BEJ), adalah suatu hal yang penting untuk menentukan dan mengetahui poin indeks mana yang termasuk  di dalam kelompok yang bisa dikatakan tinggi, rendah atau rata-rata. Hal ini  diperlukan sebagai suatu standar bahwa poin indeks tertentu akan masuk ke dalam kelompok yang mana. Tanpa benchmarking, permasalahan akan timbul seiring dengan adanya pelbagai persepsi manusia yang tentu saja berbeda dalam memberikan penilaian terhadap poin indeks (berdasarkan perkiraan dari masing-masing individu), apakah poin indeks tertentu masuk dalam kategori tinggi, rendah atau rata-rata?. Tidak ada batasan yang jelas antara poin indeks satu dengan yang lainnya. Fuzzy C-Means, yaitu suatu metode untuk mengklaster set data menjadi beberapa kelompok data dengan membagi rata set data, menjadi salah satu metode untuk melakukan benchmarking terhadap IHSG BEJ. Fuzzy C-Means -yang didasari dengan logika fuzzy- mengelompokkan data berdasarkan jarak antara centroid dengan data. Setiap data memiliki derajat keanggotaan terhadap tiap klaster. Data dengan derajat keanggotaan paling tinggilah yang akan menjadi anggota dari klaster dimana derajat keanggotaan tersebut tertuju.

Dalam Buku ini, akan diimplementasikan Fuzzy C-Means Clustering yang melakukan benchmarking terhadap IHSG BEJ tahun 2005 sehingga memudahkan pengguna untuk melakukan analisis data teknikal historis dari data tersebut.

Dari hasil ujicoba terhadap beberapa jenis IHSG BEJ, didapatkan suatu kesimpulan bahwa benchmarking bisa dilakukan terhadap pelbagai jenis IHSG BEJ dan bisa didapatkan beberapa informasi yang berguna bila pola IHSG BEJ dianalisis lebih dalam dan menghubungkannya dengan variabel waktu.

Kata Kunci: Benchmarking, Fuzzy C-Means Clustering, IHSG, IHSG BEJ.

Created with the Personal Edition of HelpNDoc: [Free Web Help generator](http://www.helpndoc.com)

# Kata Pengantar

# Kata Pengantar

Buku ini bukanlah hasil karya yang sempurna, meskipun begitu penyusun berharap semoga masih bisa bermanfaat bagi pembaca. Segala tegur sapa dari para pembaca akan penyusun sambut dengan baik demi kemajuan ilmu pengetahuan khususnya di bidang informatika.

Penyusun mengucapkan selamat membaca, semoga bermanfaat bagi seluruh umat manusia.

Sidoarjo,13 September 2016

                                Eko Heryanto

Created with the Personal Edition of HelpNDoc: [Full-featured EPub generator](http://www.helpndoc.com/create-epub-ebooks)

# Teori Penunjang

Created with the Personal Edition of HelpNDoc: [Produce online help for Qt applications](http://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework)

# Benchmarking

## Benchmarking

Sebelum melangkah lebih jauh dalam pengerjaan buku ini, mari pertajam konsep yang ada dengan mengetahui definisi dari benchmarking, kebenaran benchmark sebagai suatu standar?. Berikut ini adalah definisi dari benchmark dari pelbagai sumber:

*   [www.askoxford.com](http://www.askoxford.com)

Benchmark adalah (1) a standar or point of reference, (2) a surveyor’s mark cut in a wall and used as a reference point in measuring altitudes.

Dari sumber diatas dapat diperoleh bahwa benchmark adalah (1) sebuah standar atau batas referansi (2) Sebuah tanda potongan pada tembok sebagai batas referansi dalam pengukuran ketinggian.

*   [www.encarta.msn.com](http://www.encarta.msn.com)

Benchmark adalah (1) standard: a standard against which something can be measured and assessed,

(2) test of computer performance: a standard test to measure the performance of computer hardware or software.

Sumber diatas menyatakan definisi dari benchmark, yakni (1) standar: sebuah standar pada sesuatu yang dapat diukur dan dinilai, (2) tes dari kinerja komputer: sebuah standar pengujian untuk mengukur kinerja perangkat keras dan perangkat lunak komputer.

*   [http://www.investorwords.com](http://www.investorwords.com)

Benchmark adalah a standard, used for comparison. For example, the Nasdaq may be used as a benchmark against which the performance of a technology stock is compared.

Pengertian benchmark menurut [http://www.investorwords.com](http://www.investorwords.com) adalah sebuah standar, digunakan untuk perbandingan. Contohnya, Nasdaq bisa digunakan sebagai benchmark terhadap kinerja saham yang dibandingkan.

       Dari definisi diatas didapatkan beberapa poin penting dari benchmark, yakni standar, sesuatu yang bisa diukur dan dinilai, digunakan untuk perbandingan. Bila digabungkan poin-poin tersebut maka definisi benchmark adalah sebuah standar/baku dari sesuatu yang bisa diukur dan dinilai yang digunakan untuk perbandingan dengan sesuatu. Sedangkan benchmarking sendiri adalah suatu proses untuk melakukan benchmark.

       Dari penjelasan diatas, maka pengertian benchmarking IHSG BEJ adalah suatu proses untuk melakukan standarisasi yang digunakan sebagai penilaian terhadap suatu poin sehingga dapat membandingkan nilai dari poin IHSG BEJ satu dengan yang lainnya.

Created with the Personal Edition of HelpNDoc: [Single source CHM, PDF, DOC and HTML Help creation](http://www.helpndoc.com/help-authoring-tool)

# Clustering

## Clustering atau Pengklasteran

Pengklasteran adalah proses mengelompokkan data ke dalam beberapa kelas atau klaster sehingga objek dan sebuah klaster memiliki similaritas/persamaan yang tinggi jika dibandingkan dengan yang lainnya, namun berbeda (dissimilar) dengan objek di lain klaster. Umumnya, distance measure (ukuran jarak) yang digunakan dalam pengklasteran. Pengklasteran  bisa digunakan dalam pelbagai bidang, misalnya data mining, statistik, biologi, dan machine learning.

Klaster  adalah sebuah kumpulan dari objek data yang memiliki persamaan (similaritas) dengan yang lainnya dalam klaster  yang sama dan tidak/kurang memiliki persamaan (dissimilaritas) kepada objek yang ada di klaster lain.

Analisis dalam pengklasteran adalah sebuah hal penting dalam aktivitas manusia. Semasa muda, manusia belajar tentang perbedaan karakter antara kucing dan anjing, atau antara hewan dan tumbuhan, yang secara berulang-ulang sehingga akan timbul suatu skema pengklasteran  dibawah sadar. Analisis klaster  telah digunakan secara luas dalam banyak aplikasi

Ada beberapa aplikasi dari pengklasteran, berikut ini adalah contohnya dalam pelbagai bidang:

*   Bisnis, pengklasteran  bisa membantu pemasar mendapatkan grup yang berbeda dalam basis pelanggan mereka dan mengkarakteristikkan grup pelanggan berdasarkan pada pola pembelian.
*   Biologi, bisa digunakan untuk memperoleh taksonomi dari tanaman dan hewan, kategori gen dengan fungsionalitas yang sama, dan memperoleh informasi struktur yang ada di dalam suatu populasi.
*   Pengklasteran  juga bisa membantu dalam mengidentifikasi daerah yang sama untuk pertanian yang dapat dimasukkan kedalam database observasi bumi.
*   Mengidentifikasi kumpulan dari rumah-rumah dalam sebuah kota berdasarkan tipe rumahnya, harga dan lokasi geografis.
*   Membantu dalam mengklasifikasikan dokumen-dokumen pada web untuk pencarian informasi.

Created with the Personal Edition of HelpNDoc: [Write eBooks for the Kindle](http://www.helpndoc.com/feature-tour/create-ebooks-for-amazon-kindle)

# Fuzzy C-Means Clustering

## Fuzzy C-Means Clustering

Fuzzy C-Means (FCM) adalah sebuah metode untuk mengklaster data, membuat satu data menjadi anggota dua klaster atau lebih. Metode ini dibuat oleh Dunn pada 1973 dan dikembangkan oleh Bezdek pada tahun 1981\. FCM dibuat berdasarkan minimisasi dari fungsi objektif dibawah ini:

 ![](images/00002.gif) ,![](images/00003.gif)   (2.1)

 Gambar 2.1 Rumus Metode Minimisasi

Dimana:

*   *   m adalah sembarang bilangan real lebih besar daripada 1,
    *   uij adalah derajat keanggotaan dari xi pada klaster j,
    *   xi adalah data terukur ke i,
    *   cj adalah pusat dari klaster, dan
    *   ||*|| adalah sembarang bentuk normal yang menyatakan persamaan antara sembarang data terukur dan pusat klaster.

Partisi Fuzzy dibawah ini melalui sebuah optimisasi iterasi dari sebuah fungsi objektif yang ada diatas. Simbol cj  adalah  pusat klaster dan uij adalah update dari derajat keanggotaan data.

   ![](images/00004.gif) (2.2)

 ![](images/00005.gif)            (2.3)

Gambar 2.3 Rumus Centroid dan Update Derajat Keanggotaan

Iterasi ini akan berhenti saat ![](images/00006.gif), dimana ![](images/00007.gif) adalah sebuah standar penghentian yang nilainya adalah antara 0 dan 1 dank adalah langkah-langkah iterasi yang ditempuh selama keadaan penghentiannya terpenuhi.
             Data diikat pada masing-masing klaster dengan fungsi keanggotaan. Fungsi keanggotaan yang merepresentasikan karakter dari algoritme fuzzy. Untuk pemahaman yang lebih baik, bisa diasumsikan contoh mono-dimensional di bawah ini. Ada sebuah data set tertentu yang direpresentasikan dalam sebuah sumbu x seperti gambar 2.4 di bawah ini:

![](images/00008.jpeg)

                                              Gambar 2\. 4 Sumbu X

Dengan melihat gambar 2.5, bisa diidentifikasikan dua klaster yang berdekatan dari dua data terkonsentrasi. Klaster tersebut diberi nama klaster ‘A’ dan klaster ‘B’. Dalam pendekatan pertama –algoritme K-Means-, masing-masing data terhubung hanya pada sebuah centroid. Fungsi keanggotaannya akan menjadi seperti pada Gambar 2.5 berikut ini:

![](images/00009.jpeg)

                            Gambar 2.5 Grafik Derajat Keanggotaan K-Mean

Pada pendekatan Fuzzy C-Means, data yang sama tidak menjadi sebuah klaster secara eklusif lagi, tapi datanya bisa ditempatkan di tengah. Pada kasus ini, fungsi keanggotaan mengikuti sebuah jalur khusus untuk mengindikasikan bahwa setiap data bisa terdapat dalam beberapa klaster dengan derajat keanggotaan yang berbeda.

![](images/00010.jpeg)

                  Gambar 2.6 Grafik Derajat Keanggotaan Fuzzy C-Means

Pada Gambar 2.6 data ditunjukkan dalam tanda merah letaknya lebih ke dalam klaster B daripada ke dalam klaster A. Nilai  0.2 dari  ‘m’ mengindikasikan derajat keanggotaan dari A pada data.

Sekarang, dengan menggunakan representasi grafik, dapat dibangun sebuah matrix U yang faktor-faktornya adalah yang diambil dari fungsi keanggotaan. Matrik U tesebut seperti pada Gambar 2.7 berikut ini.

![](images/00011.gif)  ![](images/00012.gif)

                                                            Gambar 2.7 Matrik U                

Jumlah dari baris dan kolom bergantung pada banyaknya data dan klaster. Lebih tepatnya jika ada sebuah kolom C = 2 dan baris N, maka C adalah jumlah dari klaster dan N adalah jumlah data yang diindikasikan dengan uij.

Pada contoh di atas menggunakan kasus K-Means  dan FCM. Bisa diperhatikan bahwa pada kasus pertama (K-means), koefisiennya selalu satu (unitary). Hal ini mengindikasikan bahwa masing-masing data hanya pada satu klaster. Sedangkan FCM koefisiennya bisa selalu lebih dari satu. Hal ini berarti data bisa menjadi anggota lebih dari satu klaster dengan derajat keanggotaan yang berbeda pula. Derajat keanggotaan yang paling tinggi nilainya akan diambil sebagai suatu acuan dimanakah suatu data masuk menjadi anggota klaster.

FCM lebih baik daripada K-Means dalam hal fleksibilitas. FCM lebih fleksibel karena memiliki toleransi keanggotaan data terhadap tiap klaster. Hal ini tidak terjadi pada algoritme K-Means.

Tabel 2.1 Data Contoh

| Data |
| xi | 1 | 2 | 3 | 4 | 5 | 6 |
| yi | 7 | 8 | 9 | 10 | 11 | 12 |

Tabel 2.2 Derajat Keanggotaan Fuzzy dan Crisp untuk dua klaster

| Data | Keanggotaan Crisp | Derajat Keanggotaan Fuzzy |
| xi | yi |
| 1 | 7 | 1 | 0 | 0,8737 | 0.1262 |
| 2 | 8 | 1 | 0 | 0,9292 | 0,0707 |
| 3 | 9 | 1 | 0 | 0,7047 | 0,2952 |
| 4 | 10 | 0 | 1 | 0,2952 | 0,7047 |
| 5 | 11 | 0 | 1 | 0,0707 | 0,9292 |
| 6 | 12 | 0 | 1 | 0,1262 | 0,8737 |

       Contoh fleksibilitas dari FCM adalah sebagai berikut, ada sebuah data set seperti pada Tabel 2.1\.  Data tersebut dikelompokkan menjadi 2 klaster dengan menggunakan 2 metode yakni FCM dan K-Means. Tabel 2.2 adalah hasil dari proses klasterisasi. Metode crisp (pada K-Mean) memberikan derajat keanggotaan 1 atau 0, artinya, metode ini menempatkan tiap data tepat pada satu klaster. Namun, pada FCM, tiap data menjadi anggota pada kedua klaster dengan derajat keanggotaan masing-masing.

       Pada himpunan tegas (crisp), nilai keanggotaan suatu item x dalam suatu himpunan A, yang sering ditulis dengan μA[x], memiliki 2 kemungkinan, yaitu:

*   *   satu (1), yang berarti bahwa suatu item menjadi anggota dalam suatu himpunan, atau
    *   nol (0), yang berarti bahwa suatu item tidak menjadi anggota dalam suatu himpunan.

Contoh 1 metode crisp: diketahui: S = {1,2,3,4,5,6} adalah semesta pembicaraan.

A = {1,2,3}; B = {3,4,5}; bisa dikatakan bahwa:

*   *   Nilai keanggotaan 2 pada himpunan A, μA[2] = 1, karena 2 є A.
    *   Nilai keanggotaan 3 pada himpunan A, μA[3] = 1, karena 3 є A.
    *   Nilai keanggotaan 4 pada himpunan A, μA[4] = 0, karena 4 ![](images/00013.gif) A.
    *   Nilai keanggotaan 2 pada himpunan B, μB[2] = 0, karena 2 ![](images/00014.gif)B.
    *   Nilai keanggotaan 3 pada himpunan B, μB[3] = 1, karena 3 є B.

Contoh 2 metode crisp: misalkan variabel umur dibagi menjadi 3 kategori, yaitu:

Muda : 0 ≤ umur < 35 tahun;  Parobaya   : 35 ≤ umur ≤ 55;    Tua  : umur > 55 tahun

Nilai keanggotaan secara grafis, himpunan Muda, Parobaya, dan Tua ini dapat dilihat pada Gambar 2.8 berikut ini:

![](images/00015.jpeg)![](images/00016.jpeg)![](images/00017.jpeg)

Gambar 2.8 Himpunan Crisp: Muda, Parobaya, dan Tua

Pada Gambar 2.8, dapat dijelaskan bahwa:

*   Jika seseorang berusia 34  tahun, maka ia dikatakan Muda (μMUDA[34] = 1);
*   Jika seseorang berusia 35 tahun, maka ia dikatakan Tidak Muda (μMUDA[35] = 0);
*   Jika seseorang berusia 35 tahun kurang 1 hari, maka ia dikatakan Tidak Parobaya ( μPAROBAYA[35 tahun – 1 hari] = 0 );
*   Jika seseorang berusia 35 tahun, maka ia dikatakan Parobaya (μPAROBAYA[35] = 1);
*   Jika seseorang berusia 55 tahun, maka ia dikatakan Parobaya (μPAROBAYA[55] = 1);
*   Jika seseorang berusia 55 tahun kurang 1 hari, maka ia dikatakan Parobaya (μPAROBAYA[ 55 tahun – 1 hari ] = 1);
*   Jika seseorang berusia 55 tahun kurang 1 jam, maka ia dikatakan Parobaya (μPAROBAYA[ 55 tahun – 1 jam ] = 1);
*   Jika seseorang berusia 55 tahun lebih 1 hari, maka ia dikatakan Tua  (μTUA[ 55 tahun + 1 hari ] = 1);

*   Jika seseorang berusia 55 tahun lebih dari 1 jam, maka ia dikatakan Tua (μTUA[ 55 tahun + 1 jam ] = 1);

Dari sini bisa dikatakan bahwa pemakaian himpunan crisp untuk menyatakan umur sangat tidak adil, adanya perubahan kecil saja pada suatu nilai mengakibatkan perbedaan kategori yang cukup signifikan.

       Himpunan fuzzy digunakan untuk mengantisipasi hal tersebut. Seseorang dapat masuk dalam 2 himpunan yang berbeda, Muda dan Parobaya, Parobaya dan Tua, dsb. Seberapa besar eksistensinya dalam himpunan tersebut dapat dilihat pada derajat keanggotaannya. Gambar 2.9 berikut ini menunjukkan himpunan fuzzy untuk variabel umur.

![](images/00018.jpeg)

Gambar 2.9 Fungsi Derajat Keanggotaan Fuzzy Variabel Umur

Pada Gambar 2.9, dapat dilihat bahwa: 

*   Seseorang yang berumur 40 tahun, termasuk dalam himpunan Muda dengan μMUDA[40] = 0,25; namun dia juga termasuk dalam himpunan Parobaya dengan μPAROBAYA[40] = 0,5.
*   Seseorang yang berumur 50 tahun, termasuk dalam himpunan Tua dengan μTUA[50] = 0,25; namun dia juga termasuk dalam himpunan Parobaya dengan μPAROBAYA[50] = 0,5.

Kalau pada himpunan crisp, derajat keanggotaan hanya ada 2 kemungkinan, yaitu 0 atau 1, pada himpunan fuzzy derajat keanggotannnya terletak pada rentang 0 dan 1\. Apabila x memiliki derajat keanggotaan fuzzy μA[x] = 0 berarti x tidak menjadi anggota himpunan A, demikian pula apabila x memiliki derajat keanggotaan fuzzy μA[x] = 1 berarti x menjadi anggota penuh pada himpunan A.

Satu contoh lagi bila himpunan ini diaplikasikan dengan poin indeks, misalkan ada variabel tingkat indeks yang dibagi menjadi 3 kategori, yaitu:

Rendah : 0 ≤ indeks < 1050;      Normal : 1050≤ umur ≤ 1250;      Tinggi : indeks > 1250

![](images/00019.jpeg)

Gambar 2.10 Himpunan Crisp: Rendah, Normal dan Tinggi

Pada Gambar 2.10, dapat dijelaskan bahwa:

*   Jika indeks bernilai 1049 maka dikatakan Rendah (μRENDAH[1049] = 1);
*   Jika indeks bernilai 1050, maka dikatakan Tidak Rendah (μRENDAH[1050]=0);
*   Jika indeks bernilai 1050 kurang 0,001 poin, maka dikatakan Tidak Normal            ( μNORMAL[ 1050 – 0,001 ] = 0 );
*   Jika indeks bernilai 1050 maka dikatakan Normal (μNORMAL[1050] = 1);
*   Jika indeks bernilai 1250 maka dikatakan Normal (μNORMAL[1250] = 1);
*   Jika indeks bernilai 1250 kurang 0,001 poin, maka dikatakan Tidak Tinggi (μTINGGI[ 1250 – 0,001 ] = 0);

Dari sini bisa dikatakan bahwa pemakaian himpunan crisp untuk menyatakan indeks sangat tidak adil, adanya perubahan kecil saja pada suatu nilai mengakibatkan perbedaan kategori yang cukup signifikan.

![](images/00020.jpeg)

Gambar 2.11 Fungsi Derajat Keanggotaan Fuzzy : Tingkat Indeks

Pada Gambar 2.11, dapat dilihat bahwa:

*   Indeks yang bernilai 1100, termasuk himpunan Rendah dengan μRENDAH[1100] = 0,25; namun juga termasuk dalam himpunan Normal dengan μNORMAL[1100] = 0,5.
*   Indeks yang bernilai 1200, termasuk  himpunan Tinggi dengan μTINGGI[1200] = 0,25; namun dia juga termasuk dalam himpunan Normal dengan μPAROBAYA[1200] = 0,5.

Created with the Personal Edition of HelpNDoc: [Easily create CHM Help documents](http://www.helpndoc.com/feature-tour)

# IHSG

## Indeks Harga Saham Gabungan

Pengetahuan tentang Indeks Harga Saham (IHS) diibaratkan pintu masuk ke dalam rumah. Kalau ingin masuk rumah, tentu harus melewati pintu. Untuk itu, investor harus tahu dimana letak pintu itu dan bagaimana cara membukanya. Jadi, bila ingin melakukan investasi di pasar modal, investor harus mengetahui terlebih dahulu IHS. Setelah berhasil membuka pintu, investor harus menentukan posisi, apakah harus datang ke ruang tamu, ke ruang makan, atau ke kamar tidur. Untuk menentukan posisi, investor perlu mengetahui kondisi pasar. Dalam pasar modal, terutama pasar saham, kondisi pasar ditunjukkan oleh siklus pasar yang terdiri dari pasar bullish, normal dan bearish. Jadi bila ingin melakukan investasi di pasar modal, investor harus mengetahui terlebih dahulu indikator yang dapat digunakan untuk menganalisis kondisi pasar modal tersebut. [[Wid96]](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX).

Berikut ini akan diberikan beberapa pengetahuan tentang Indeks Harga Saham dan Indeks Harga Saham Gabungan.

### 2.4.1 Definisi

IHS sebenarnya merupakan angka indeks harga saham yang telah disusun dan dihitung sedemikian rupa sehingga menghasilkan trend (kecenderungan). Angka indeks adalah angka yang diolah sedemikian rupa sehingga dapat dipergunakan untuk membandingkan kegiatan atau peristiwa, yang bisa berupa perubahan harga saham dari waktu ke waktu.

Dalam perhitungan angka indeks ini digunakan dua dasar waktu, yaitu waktu dasar (base period) dan waktu yang berlaku/berjalan (current period). Waktu dasar adalah waktu dimana suatu peristiwa dipergunakan sebagai dasar perbandingan dengan waktu berjalan. Sedangkan waktu berjalan adalah waktu berlakunya suatu kegiatan atau peristiwa yang nantinya akan dibandingkan dengan waktu dasarnya.

Indeks Harga Saham Gabungan (IHSG) adalah suatu indikator yang digunakan untuk mengukur dan melaporkan perubahan seluruh nilai saham yang terdaftar (listing) dibandingkan dengan total nilai harga dasarnya. Jadi untuk menentukan angka indeks harus tersedia data lebih dari satu, sebab harus ditentukan harga dasar dan  harga saham yang berlaku di bursa [[Wid96]](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX)[.](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX)

Manfaat dari IHSG menurut Jack Clark Francis, antara lain:

1.  Untuk mengetahui secara cepat pergerakan harga pasar (IHSG) dalam mempengaruhi nilai pasar investasi di pasar modal.
2.  IHS ini juga berguna untuk analisis historis. Dengan menganalisis indeks pasar (IHSG) dan indikator ekonomi yang lain, seorang analis bisa mendeteksi hubungan antara indeks dan sektor-sektor ekonomi. Jenis hubungan ini akan sangat berguna jika indeks tersebut merupakan dependable indicator (indikator terikat), ini akan berguna untuk membuat ramalan [[Fra93].](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX)

### 2.4.2  Metode Perhitungan Indeks Harga Saham Gabungan

       Pada prinsipnya, perhitungan IHSG tidak berbeda dengan perhitungan IHS individu. IHS individu adalah IHS yang digunakan untuk saham perusahaan tunggal. Tiap saham perusahaan memiliki IHS individu. IHS individu bermanfaat untuk menilai keadaan saham suatu perusahaan yang tercatat pada bursa saham.

IHS individu menggunakan rumus sebagai berikut:

![](images/00021.gif)            (2.4)

      Dimana:

*   IHS : Indeks Harga Saham.
*   Ht    : harga pada waktu berlaku (current period).
*   Ho   : harga pada waktu dasar (base period).

      Dengan kriteria sebagai berikut:

*   Jika nilai IHS = 100, menunjukkan bursa dalam kondisi normal.
*   Jika nilai IHS > 100, menunjukkan bursa dalam kondisi bergairah.
*   Jika nilai IHS < 100, menunjukkan bursa dalam kondisi lesu.

Perhitungan IHSG ada tiga metode yang lazim digunakan, berikutnya adalah masing-masing pembahasan dari pelbagai metode tersebut.

#### 2.4.2.1 Metode Perhitungan Indeks Harga Saham Gabungan Sederhana

Metode perhitungan ini menggunakan data seluruh harga saham yang listing (tercatat)  di bursa saat itu. Asumsinya bahwa seluruh saham memiliki peran yang sama dalam mempengaruhi pasar.

Berdasarkan rumus dasar IHS, dapat ditemukan rumus umum menghitung IHSG, yaitu:

IHSG = ![](images/00022.gif)               (2.5)

Dimana:

*   ![](images/00023.gif)Ht : total harga seluruh saham pada waktu yang berlaku.

*   ![](images/00024.gif)Ho : total harga seluruh saham pada waktu dasar.

Dengan kriteria sebagai berikut:

*   Jika nilai IHSG =100, menunjukkan bursa saham dalam kondisi normal.
*   Jika nilai IHSG >100, menunjukkan bursa saham dalam kondisi bergairah.
*   Jika nilai IHSG < 100, menunjukkan bursa dalam kondisi lesu.

#### 2.4.2.2 Metode Perhitungan Indeks Harga Saham Gabungan Tertimbang

Berbeda dengan metode sebelumnya, metode ini mempertimbangkan kekuatan suatu saham dalam mempengaruhi pasar, artinya jika terjadi perubahan terhadap harga saham tertentu maka seluruh harga saham akan terpengaruh. Atas dasar bobot kekuatan mempengaruhi pasar inilah perhitungan IHSG tertimbang. Penentuan bobot kekuatan suatu saham adalah besarnya kecilnya jumlah saham yang didaftarkan.  Semakin banyak jumlah saham didaftarkan, semakin kuat kemampuan suatu saham dalam membentuk IHSG. Metode tertimbang terdiri dari empat model perhitungan IHSG yaitu Laspeyres, Paasche, Irving Fisher, dan Drobisch. Masing-masing model tertimbang akan dijelaskan lebih lanjut yang disertai dengan rumusnya.

2.4.2.2.1 Model Perhitungan Laspeyres

Dalam model perhitungan ini, kriteria jumlah saham yang digunakan adalah jumlah saham saat penawaran perdana atau waktu dasar. Jika menggunakan jumlah saham yang beredar pada waktu dasar sebagai kriteria maka digunakan rumus yang dikemukakan Laspeyres. Rumus umum dari Laspeyres adalah sebagai berikut:

IHSG = ![](images/00025.gif)      (2.6)

        Dimana:

*   Ht: harga saham pada waktu yang berlaku.
*   Ho: harga saham pada waktu dasar.
*   Ko: jumlah seluruh saham yang beredar pada waktu dasar.

2.4.2.2.2 Model Perhitungan Paasche

Dalam model perhitungan ini, kriteria jumlah saham yang digunakan adalah jumlah saham pada waktu berlaku sebagai pertimbangan. Jika menggunakan jumlah saham yang beredar pada waktu berlaku sebagai kriteria maka digunakan rumus yang dikemukakan Paasche. Rumus umum dari Paasche adalah sebagai berikut :

IHSG = ![](images/00026.gif)      (2.7)

Dimana:

*   Ht: harga saham pada waktu yang berlaku.
*   Ho: harga saham pada waktu dasar.
*   Kt: jumlah seluruh saham yang beredar pada waktu yang

berlaku.

2.4.2.2.3 Model Perhitungan Irving Fisher

Model perhitungan yang dikemukakan oleh Irving Fisher ini merupakan gabungan antara model perhitungan Laspeyres dan Paasche. Perhitungannya dapat diperoleh dengan mengalikan IHSG hasil metode Laspeyres dan metode Paasche kemudian keduanya diakar kuadratkan. Rumusnya adalah sebagai berikut :

IHSG = ![](images/00027.gif)      (2.8)

Dimana:

*   IHSGL: IHSG model perhitungan Laspeyres.
*   IHSGP: IHSG model perhitungan Paasche.

2.4.2.2.4 Model Perhitungan Drobisch

Seperti halnya metode perhitungan yang dikemukakan oleh Irving Fisher, Drobisch juga menemukan metode yang lebih sederhana dibanding dua metode sebelumnya (Laspeyres dan Paasche). Metode ini menjumlah dua metode yakni metode Laspeyres dan metode Paasche, kemudian hasil dari penjumlahan tersebut dibagi menjadi dua dan dijadikan dalam bentuk persen dengan mengalikannya dengan 100%. Metode Drobisch bermaksud untuk membagi rata dua metode Laspeyres dan Paasche.

   Rumus dari metode Drobisch adalah sebagai berikut :

IHSG = ![](images/00028.gif)     (2.9)

Dimana:

*   IHSGL: IHSG model perhitungan Laspeyres.
*   IHSGP: IHSG model perhitungan Paasche.

#### 2.4.2.3 Metode Perhitungan Indeks Harga Saham Gabungan Sampling

Perhitungan IHSG kurang efisien apabila memasukkan seluruh saham yang listing di bursa. Hal ini karena jika jumlah saham yang listing sudah mencapai puluhan ribu, maka sangat rumit untuk menghitung IHSG.

Beberapa pasar modal dunia seperti Dow Jones (the Dow Jones Industrial Average), hanya menggunakan 30 saham sektor industri sebagai sampel. Demikian pula indeks harga saham yang dipakai oleh Standard & Poor’s 500 (the Standard & Poor’s 500 Composite), indeks sahamnya menggunakan 500 saham, terdiri dari 400 saham perusahaan industri, 40 saham perusahaan utilitas, 20 saham perusahaan transportasi dan 40 saham perusahaan keuangan.

### 2.4.3  Beberapa Istilah dalam Pergerakan IHSG

Ada banyak sekali istilah-istilah yang berhubungan dengan pasar modal, akan tetapi dalam buku ini akan dibahas beberapa saja  yang tentu saja berhubungan dengan buku ini. Berikut ini adalah pembahasannya.

#### 2.4.3.1 Pasar Bullish

       Ciri-ciri kondisi pasar bullish jika didasarkan pergerakan nilai indikator IHSG adalah sebagai berikut:

*   Terjadi trend kenaikan pada nilai IHSG dari waktu ke waktu
*   Nilai tertinggi yang baru selalu lebih tinggi dari nilai tertinggi sebelumnya hingga pada akhir fase ketiga.
*   Dalam pergerakan nilai IHSG baru yang terendah selalu lebih tinggi dari nilai indeks terendah sebelumnya.

#### 2.4.3.2 Pasar Bearish

Pasar bearish merupakan kebalikan dari pasar bullish dengan ciri-ciri sebagai berikut:

*   Terjadi trend penurunan pada nilai IHSG dari waktu ke waktu.
*   Nilai indeks tertinggi yang baru selalu lebih rendah dari nilai tertinggi sebelumnya sampai pada akhir fase ketiga.
*   Dalam pergerakan nilai IHSG baru yang terendah selalu lebih rendah dari nilai indeks terendah sebelumnya.
*   Pada pasar bearish  investor yang melakukan transaksi bukan merupakan real  investor, melainkan sebagian besar merupakan spekulan yang hanya mengharapkan keuntungan dari fluktuasi harga dari waktu ke waktu dalam jangka pendek.
*   Pada pasar bearish biasanya timbul anggapan bahwa : ”Good news is no news and bad news is nightmare” (berita baik adalah tidak ada berita dan berita buruk adalah mimpi buruk), yang artinya kebanyakan investor lebih bersikap pesimis.
*   Pada pasar bearish frekuensi perdagangan cenderung kecil, akibat kecilnya profit yang mungkin diperoleh dengan risiko yang tinggi.
*   Pada pasar bearish jatuhnya harga saham terjadi pada hampir seluruh saham dengan nilai yang tinggi[[Wid96]](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX).

## 2.5 Indeks Harga Saham Gabungan Bursa Efek Jakarta

Dalam rangka memberikan informasi yang lebih lengkap tentang perkembangan bursa kepada publik, BEJ telah menyebarkan data pergerakan harga saham melalui media cetak dan elektronik. Indikator pergerakan harga saham tersebut adalah IHS.

Saat ini, BEJ mempunyai 4 macam indeks saham:

1\. IHSG, menggunakan semua saham tercatat sebagai komponen kalkulasi

   indeks.

2\. Indeks Sektoral, menggunakan semua saham yang masuk dalam setiap

   sektor.

3\. Indeks LQ45, menggunakan 45 saham terpilih setelah melalui beberapa

   tahapan seleksi.

4.Indeks Individual, yang merupakan indeks untuk masing-masing saham

  didasarkan Harga Dasar.

IHSG, Indeks Sektoral dan Indeks LQ45 menggunakan metode perhitungan yang sama, yang membedakannya hanya jumlah saham yang digunakan sebagai komponen dalam perhitungannya.

       Pada tanggal 1 April 1983, IHSG diperkenalkan untuk pertama kalinya sebagai indikator pergerakan harga saham di BEJ. Indeks ini mencakup pergerakan harga seluruh saham biasa dan saham preferen yang tercatat di BEJ. Hari Dasar untuk perhitungan IHSG adalah tanggal 10 Agustus 1982\. Pada tanggal tersebut, indeks ditetapkan dengan nilai dasar 100 dan saham tercatat pada saat itu berjumlah 13 saham.

Metode perhitungan IHSG adalah jumlah Nilai Pasar dari total saham yang tercatat pada tanggal 10 Agustus 1982\. Jumlah Nilai Pasar adalah total perkalian setiap saham tercatat (kecuali untuk perusahaan yang berada dalam program restrukturisasi) dengan harga di BEJ pada hari tesebut.

Formula perhitungannya adalah sebagai berikut:

![](images/00029.gif) (2.10)

Perhitungan indeks merepresentasikan pergerakan harga saham di pasar/bursa yang terjadi melalui sistem perdagangan lelang. Nilai Dasar akan disesuaikan secara cepat bila terjadi perubahan modal emiten atau terdapat faktor lain yang tidak terkait dengan harga saham.penyesuaian akan dilakukan bila ada tambahan emiten baru, HMETD (right issue), partial/company listing, waran, dan obligasi konversi demikian juga delisting. Dalam hal terjadi stock split, dividen saham atau saham bonus, Nilai Dasar tidak disesuaikan karena Nilai Pasar tidak terpengaruh. Harga saham yang digunakan dalam menghitung IHSG adalah harga saham di pasar reguler yang didasarkan pada harga yang terjadi berdasarkan sistem lelang.

Formula untuk menghitung Nilai Dasar adalah:

![](images/00030.gif) (2.11)

### 2.5.1 Indeks Sektoral

Indeks Sektoral merupakan bagian dari IHSG. Semua perusahaan yang tercatat di BEJ diklasifikasikan dalam 9 sektor yang didasarkan pada klasifikasi industri yang ditetapkan oleh BEJ yang di sebut JASICA (Jakarta Stock Exchange Industrial Classification). Kesembilan sektor tersebut adalah:

A. Sektor Utama (industri yang menghasilkan bahan-bahan baku)

       1\. Sektor 1, Pertanian.

       2\. Sektor 2, Pertambangan.

B. Sektor Kedua (industri pengolahan/manufaktur)

       3\. Sektor 3, Industri Dasar dan Kimia.

       4\. Sektor 4, Aneka Industri.

       5\. Sektor 5, Industri Barang Konsumsi.

C. Sektor ketiga (jasa)

       6\. Sektor 6, Properti dan Real Estate.

       7\. Sektor 7, Transportasi dan Infrastruktur.

       8\. Sektor 8, Keuangan.

       9\. Sektor 9, Perdagangan, Jasa dan Investasi.

Indeks Sektoral diperkenalkan pada tanggal 2 Januari 1996 dengan Nilai Dasar 100 untuk setiap sektor dan menggunakan Hari Dasar 28 Desember 1995\. Disamping kesembilan sektor tersebut, BEJ menghitung indeks industri manufaktur/pengolahan yang merepresentasikan kumpulan saham yang diklasifikasikan kedalam sektor 3, sektor 4, dan sektor 5.

### 2.5.2 Indeks LQ45

Indeks ini terdiri dari 45 saham yang dipilih setelah melalui beberapa kriteria sehingga indeks ini terdiri dari saham-saham yang mempunyai likuiditas yang tinggi dan juga mempertimbangkan kapitalisasi pasar dari saham-saham.

#### 2.5.2.1 Kriteria Pemilihan Saham Indeks LQ45

Untuk masuk dalam pemilihan tersebut, sebuah saham harus memenuhi kriteria tertentu dan lolos dari seleksi utama sebagai berikut:

1\. Masuk dalam top 60 dari total transaksi saham di pasar regular (rata-rata nilai    transaksi selama 12 bulan terakhir).

2\.  Masuk dalam ranking yang didasarkan pada nilai kapitalisasi pasar (rata-rata kapitalisasi pasar selama 12 bulan terakhir).

3\.   Telah tercatat di BEJ sekurang-kurangnya 3 bulan.

4\.  Kondisi keuangan perusahaan, prospek pertumbuhan perusahaan, frekuensi

        dan jumlah transaksi di pasar regular.

### 2.5.3 Evaluasi Indeks dan Pergantian Saham

BEJ secara terus menerus memantau perkembangan komponen saham yang masuk dalam perhitungan LQ45\. Setiap 3 bulan, di-review pergerakan ranking saham yang masuk dalam perhitungan Indeks LQ45\. Penggantian saham akan dilakukan setiap 6 bulan sekali, yakni pada setiap awal bulan Februari dan Agustus.

Bila ada satu saham yang tidak memenuhi kriteria, saham tersebut akan dikeluarkan dari perhitungan indeks dan digantikan dengan saham yang

memenuhi kriteria.

Saham-saham yang masuk dalam kriteria rangking 1-35 dikalkulasikan dengan cepat dalam perhitungan indeks. Sedangkan saham yang masuk pada rangking 36-45 tidak perlu dimasukkan dalam perhitungan indeks.

Hari Dasar Indeks LQ45 dan Awal Perhitungan (13 Juli 1994 - 1996) Indeks LQ45 dihitung mundur hingga tanggal 13 Juli 1994 sebagai Hari Dasar, dengan Nilai Dasar 100\. Untuk seleksi awal digunakan data pasar Juli 1993-Juni 1994\. Hasilnya, ke-45 saham tersebut meliputi 72% total market kapitalisasi pasar dan 72,5% nilai transaksi di pasar regular.

### 2.5.5 Jakarta Islamic Index (JII)

Dalam rangka mengakomodasi investor yang tertarik untuk berinvestasi, BEJ dan Danareksa Investment Management (DIM) meluncurkan sebuah indeks yang didasarkan pada Syariah Islam, dikenal dengan nama Jakarta Islamic Index (JII).

JII diluncurkan pada tanggal 3 Juli 2000\. JII dihitung mundur hingga tanggal 1 Januari 1995 sebagai Hari Dasar dengan Nilai Dasar 100.

JII terdiri dari 30 saham yang sesuai dengan Syariah Islam. Dewan Pengawas Syariah PT DIM terlibat dalam menetapkan kriteria saham-saham yang masuk dalam JII.

#### 2.5.5.1 Kriteria Saham-Saham yang Tidak Masuk dalam JII

Berdasarkan arahan Dewan Pengawas Syariah PT DIM, jenis kegiatan utama emiten yang bertentangan dengan Syariah adalah:

*   Usaha perjudian dan permainan yang tergolong judi atau perdagangan yang dilarang.
*   Usaha lembaga keuangan konvensional (ribawi) termasuk perbankan dan asuransi konvensional.
*   Usaha yang memproduksi, mendistribusi serta merperdagangkan makanan dan minuman yang tergolong haram.
*   Usaha yang memproduksi, mendistribusi dan/atau menyediakan barang-barang ataupun jasa yang merusak moral dan bersifat mudarat.

#### 2.5.5.2 Penetapan Saham-Saham yang Masuk JII

Untuk menetapkan saham-saham yang masuk dalam perhitungan indeks JII dilakukan dengan urutan seleksi sebagai berikut:

1.  Memilih kumpulan saham dengan jenis usaha utama yang tidak bertentangan dengan prinsip Syariah dan sudah tercatat lebih dari 3  bulan (kecuali termasuk dalam 10 kapitalisasi besar).
2.  Memilih saham berdasarkan laporan keuangan tahunan atau tengah tahunan terakhir yang memiliki rasio kewajiban terhadap aktiva maksimal sebesar 90%.
3.  Memilih 60 saham dari susunan saham diatas berdasarkan urutan rata-rata kapitalisasi pasar (market capitalization) terbesar selama satu tahun terakhir.
4.  Memilih 30 saham dengan urutan berdasarkan tingkat likuiditas rata-rata nilai perdagangan selama satu tahun terakhir.

Saham-saham yang masuk ke dalam JII memiliki daya tarik yang tinggi bagi masyarakat yang memiliki niat untuk melakukan investasi hanya pada perusahaan yang bersifat halal. Banyak investor baik dari dalam maupun dari luar negeri yang beragama Islam yang berinvestasi pada saham-saham tersebut.

### 2.5.6 Indeks Papan Utama (Main Board Index/MBX) dan Indeks Papan Pengembangan (Development Board Index)

Pada tanggal 13 Juli 2000, BEJ meluncurkan peraturan baru di bidang pencatatan, yaitu Sistem Pencatatan 2 Papan. Sistem ini diimplementasikan untuk mendorong bursa Indonesia.

Klasifikasi Papan Pencatatan terdiri dari :

*   Papan Utama untuk perusahaan besar dengan track record yang baik.
*   Papan Pengembangan, untuk mengakomodasi perusahaan-perusahaan yang belum bisa memenuhi persyaratan Papan Utama, tetapi masuk pada kategori perusahaan berprospek. Disamping itu, Papan Pengembangan diperuntukkan bagi perusahaan yang mengalami restrukturisasi atau pemulihan kinerja.

Dalam rangka menyediakan indikator untuk mengawasi saham-saham yang masuk dalam kategori setiap papan, pada tanggal 8 April 2002, BEJ telah meluncurkan 2 indeks baru: Indeks Papan Utama dan Indeks Papan Pengembangan. Kedua Indeks tersebut menggunakan metode perhitungan seperti indeks lainnya, contohnya menggunakan pembobotan berdasarkan kapitalisasi pasar. Hari Dasar untuk perhitungan indeks papan utama dan papan pengembangan adalah tanggal 28 desember 2001 dengan Nilai Dasar 100\. Pada tanggal tersebut 24 saham tercatat di Papan Utama dan 287 saham tercatat di Papan Pengembangan dengan komposisi kapitalisasi pasar untuk kedua indeks tersebut adalah 62 % dan 38% berturut-turut.

Created with the Personal Edition of HelpNDoc: [Single source CHM, PDF, DOC and HTML Help creation](http://www.helpndoc.com/help-authoring-tool)

# Perancangan Perangkat Lunak

# P erancangan Perangkat Lunak

Bab ini merupakan uraian mengenai inti penerapan teori dan algoritme yang dikembangkan dalam bentuk perangkat lunak. Ada tiga hal yang harus diperhatikan dalam perancangan perangkat lunak ini yaitu perancangan data, perancangan proses dan perancangan antarmuka. Untuk menjadikannya lebih sederhana, maka perancangan perangkat lunak ini dibagi ke dalam beberapa tahapan meliputi:

1.  Perancangan Data
2.  Perancangan Proses
3.  Perancangan Antarmuka

Created with the Personal Edition of HelpNDoc: [Free Qt Help documentation generator](http://www.helpndoc.com)

# Perancangan Data

## Perancangan Data

Data-data yang digunakan dalam perangkat lunak ini dapat dibedakan menjadi tiga yaitu data masukan, data proses dan data keluaran. Beberapa jenis data tersebut akan dijelaskan pada sub bab berikutnya. Alur dari informasi diprosesnya suatu data sehingga menjadi suatu informasi memang perlu diketahui. Adapun  alur dari aliran informasi dari data-data tersebut dapat dilihat pada diagram berikut ini:

![](images/00031.gif)

                             Gambar 3.1 Alur informasi dari data

### 3.1.1 Data Masukan

Data masukan adalah data-data yang diperlukan agar perangkat lunak dapat bekerja. Data mentah yang dapat diolah dalam aplikasi ini terdiri dari data input yaitu data IHSG BEJ dengan jenis yang sesuai dengan yang diinputkan pengguna. Sebelum menjadi data input  yang sesuai, data melewati beberapa proses yaitu:

#### 3.1.1.1\. Pemilihan data yang diperlukan dan konversi ke dalam bentuk CSV.

Data masukan yang diperlukan dalam buku ini adalah data IHSG BEJ pada periode 2005\. Data tersebut berupa file yang berekstensi txt, dengan format pada Gambar 3.2 sebagai berikut:

![](images/00032.jpeg)

                                      Gambar 3.2 Bentuk data asli IHSG BEJ

Jumlah dari file teks yang didapat adalah 238 file yang berarti dalam waktu satu tahun (tahun 2005) terjadi sekitar 238 trading time (waktu perdagangan saham).

Kolom indeks adalah nama dari jenis indeks, tertera dalam tabel bahwa terdapat 15 indeks. Masing-masing indeks memiliki karakteristik sendiri-sendiri, dibagi menurut karakternya dan sektoral.

Namun sesuai dengan batasan masalah, bahwa yang diklaster adalah data IHSG pada tahun 2005, berarti data yang dibutuhkan adalah data dari seluruh jenis IHSG dan yang berada pada kolom ‘today’. Setelah pemilihan data selesai, data kemudian dikonversi ke bentuk CSV (Comma Separated Value). Hal tersebut untuk memudahkan konversi ke dalam database.

#### 3.1.1.2 Konversi ke Database Oracle

       Data masukan yang masih dalam bentuk CSV perlu untuk dikonversi dan simpan ke dalam database. Hal ini untuk memudahkan dalam pembuatan aplikasi karena aplikasi dapat mengakses data melalui database. DBMS (Database Management System) yang dipakai adalah Oracle Database 10G.

#### 3.1.1.3 Pemilahan Data Sesuai dengan Jenis Indeks  

       Data masukan yang masuk ke dalam database masih belum tersaring dengan baik, masih campur antara jenis indeks satu dengan jenis indeks lainnya. Oleh karena itu diperlukan pemilahan data yang sesuai dengan jenis indeks masing-masing. Hal ini dapat dilakukan dengan membuat view untuk masing-masing jenis indeks.

### 3.1.2 Data Proses

Data proses adalah data-data yang digunakan selama proses klasterisasi yaitu proses pencarian pusat klaster dengan algoritme pengklasteran FCM dan proses pencarian derajat keanggotaan optimal. Data ini diolah dari data masukan dan digunakan untuk menghasilkan data keluaran. Data masukan diproses dengan dua tahap, yakni:

1.  1.  1.  1.  Pencarian  pusat klaster

Pada tahap ini data mentah masukan diolah untuk menghasil pusat klaster dari masing-masing klaster. Penghitungan pusat klaster sesuai dengan rumus penghitungan pencarian pusat klaster pada pengklasteran Fuzzy C-Means (rumus 2.2).

1.  1.  1.  1.  Pencarian derajat keanggotaan optimal

Pada tahap ini terdiri atas fase pencarian derajat keanggotaan tiap data mentah pada tiap klaster dan fase pencarian data derajat keanggotaan optimal.

*   Fase pencarian derajat keanggotaan

Pada tahap ini, data proses hasil proses pencarian pusat klaster diolah dengan data mentah masukan. Penghitungan derajat keanggotaan masing-masing klaster dihitung dengan rumus update derajat keanggotaan pada metode pengklasteran Fuzzy C-means (rumus 2.3).

*   Fase pencarian derajat keanggotaan optimal

Pada tahap ini, data hasil pada fase pencarian derajat keanggotaan optimal dicari dan disimpan dalam sebuah matriks. Dilakukan algoritme perbandingan untuk mendapatkan yang optimal.

### 3.1.3 Data Keluaran

Data keluaran adalah informasi yang dihasilkan oleh perangkat lunak untuk pengguna setelah melalui proses penampilan data hasil klasterisasi. Informasi didapat dari proses pengklasteran data mentah dengan  metode pengklasteran FCM. Pada tahap ini, data dapat dilihat oleh pengguna dengan jelas karena ada perbedaan warna untuk masing-masing klaster dan data keluaran didalamnya. Pada tahap ini data yang telah diproses diberikan warna pada grafik, sehingga pengguna lebih mudah membedakan daerah klaster.

Created with the Personal Edition of HelpNDoc: [Free EPub producer](http://www.helpndoc.com/create-epub-ebooks)

# Perancangan Proses

## Perancangan Proses

Perangkat lunak ini didesain dengan penyesuaian terhadap tahapan-tahapan yang dilalui oleh pengklasteran FCM. Berikut ini adalah alurnya:

![](images/00033.gif)

                                        Gambar 3.3  Diagram Alur Proses

### 3.2.1 Fase Preprocessing

       Pada tahap ini, data masukan diolah sesuai dengan keinginan pengguna. Data masukan diproses sesuai dengan parameter yang di-input-kan pengguna. Parameter yang di-input-kan pengguna yakni,  jenis indeks, jumlah klaster, batas ketelitian, dan fuzziness. Semua input tersebut merupakan syarat parameter metode pengklasteran Fuzzy C-Means kecuali jenis indeks. Jenis indeks mempengaruhi data masukan yang akan diolah. Tiap masukkan nantinya akan diberi persyaratan masukan sehingga masukan yang masuk ke aplikasi adalah masukan yang benar dan sesuai dengan masukan yang disyaratkan oleh algoritme FCM. Diagram dibawah ini akan menjelaskan proses tersebut.

       ![](images/00034.gif)

Gambar 3.4 Diagram Preprocessing

### 3.2.2 Fase Proses Klasterisasi

        Proses klasterisasi adalah proses inti dari aplikasi yang nantinya akan dibuat. Proses ini memiliki alur seperti Gambar 3.5 berikut ini.

![](images/00035.gif)

                            Gambar 3.5 Diagram Alir Proses Klasterisasi

#### 3.2.2.1 Proses Generate Data Input

Proses ini merupakan proses untuk inisialisasi derajat keanggotaan tiap data. Inisialisasi dari proses ini didapatkan dari bilangan generate random (bilangan acak).

#### 3.2.2.2 Komputasi Pusat Klaster

Disini data masukan diolah sehingga menjadi beberapa pusat klaster  yang jumlahnya sesuai dengan jumlah klaster yang diinputkan oleh pengguna. Fase ini melalui tahap rumus berikut ini:

![](images/00036.gif)             (3.1)

#### 3.2.2.3 Komputasi Derajat Keanggotaan

Disini data hasil proses pada fase pencarian pusat klaster diolah dengan data masukan berupa data mentah indeks. Melakukan komputasi untuk menghitung derajat keanggotaan masing-masing data terhadap klaster, dengan rumus sebagai berikut:

![](images/00037.gif)             (3.2)

#### 3.2.2.4 Fase Pemberhentian

Melakukan pengambilan keputusan, yakni bila terdapat nilai selisih derajat keanggotaan data yang lebih kecil dari batas ketelitian (dari fase preprocessing) maka proses akan berhenti, bila tidak maka akan dilanjutkan ke tahap komputasi pusat klaster.

       Hal tersebut sesuai dengan rumus sebagai berikut:

![](images/00038.gif)             (3.3)

### 3.2.5 Fase Pencarian Derajat Keanggotaan Optimal

Disini data hasil proses pada fase update derajat keanggotaan diolah dengan algoritme perbandingan untuk mendapatkan derajat keanggotaan optimal untuk masing-masing klaster. Kemudian diambil derajat keanggotaan dari data yang paling tinggi nilainya.

### 3.2.6 Fase Pengelompokkan Berdasarkan Klaster

       Pada fase ini data hasil dari fase pencarian derajat keanggotaan optimal akan dikelompokkan sesuai dengan persamaan klasternya. Data akan dikelompokkan sesuai dengan data yang lainnya yang memiliki kemiripan klaster. Pengelompokkan nanti menggunakan algoritme sorting.

### 3.2.7 Fase Pembuatan Grafik Data Terklaster

       Data yang sudah mengelompok berdasarkan kemiripan klaster dibuatkan sebuah grafik yang merupakan representasi dari data pada klaster tertentu. Grafik ini nantinya akan dibuat dengan berwarna. Hal ini untuk memudahkan pengguna dalam membedakan daerah klaster dan memudahkan mendapatkan informasi.

Created with the Personal Edition of HelpNDoc: [Free Qt Help documentation generator](http://www.helpndoc.com)

# Perancangan Antarmuka

## Perancangan Antarmuka

       Perancangan antarmuka dimaksudkan untuk memudahkan pengguna dalam menjalankan perangkat lunak. Interaksi antar pengguna dengan perangkat lunak menggunakan mouse dan keyboard. Pengguna bisa memilih jenis IHSG yang diinginkan, memasukkan data input serta menekan tombol untuk memulai proses baik untuk melakukan generate maupun untuk melakukan run proses serta juga untuk melakukan proses secara step by step (proses perlangkah) . Selain input untuk proses klasterisasi, juga terdapat input untuk melihat grafik hasil dari pengklasteran data. Input tersebut berupa radio button yang bisa di klik sesuai dengan keinginan pengguna. Radio button tersebut bisa dipilih bila pengguna bermaksud melihat data dan grafik, pilihan-pilihannya adalah sebagai berikut:

*   Grafik IHSG, yakni pengguna bisa melihat grafik poin indeks terhadap waktu sebelum data indeks diklaster.
*   Derajat keanggotaan, pengguna bisa melihat nilai keanggotaan data indeks terhadap masing-masing klaster beserta grafiknya.
*   Data terklaster, pengguna bisa melihat grafik poin indeks terhadap waktu setelah data indeks diklaster.
*   Detail data tersortir, pengguna bisa melihat data indeks terklaster secara detail yang sudah tersortir secara ascending.

Berikut adalah perancangan antarmuka dengan penjelasan dari tiap komponen yang ada pada form. Semuanya ada pada Gambar 3.6.

![](images/00039.gif)

                                  Gambar 3.6 Rancangan Antarmuka

Created with the Personal Edition of HelpNDoc: [Produce Kindle eBooks easily](http://www.helpndoc.com/feature-tour/create-ebooks-for-amazon-kindle)

# Implementasi Perangkat Lunak

# Implementasi Perangkat Lunak

Bab ini akan menguraikan tentang implementasi dari rancangan perangkat lunak yang telah dibuat. Pembahasan meliputi lingkungan implementasi perangkat lunak, implementasi proses, dan implementasi kelas.

## 4.1 Lingkungan Aplikasi

Lingkungan implementasi meliputi perangkat keras dan perangkat lunak yang digunakan. Spesifikasi perangkat keras dan perangkat lunak yang digunakan dalam implementasi dapat dilihat pada tabel 4.1:

Tabel 4.1 Lingkungan Implementasi Perangkat Lunak

| Perangkat Keras | Prosesor : Intel(R) Pentium(R) 4 CPU 2.8 GHzMemori  : 1024 MB RAM |
| Perangkat Lunak | Sistem Operasi                      : Microsoft Windows Server 2003Perangkat Lunak IDE           : NetBeans 5Komponen java                     : JFreeChartDriver                                    :  JDBC Oracle 10G |

Created with the Personal Edition of HelpNDoc: [Free Qt Help documentation generator](http://www.helpndoc.com)

# Implementasi Data

## Implementasi Data

Implementasi data merupakan bab yang menjelaskan tentang implementasi dari perancangan data yang ada pada bab 3\. Seperti pada perancangan data, implementasi data dibagi menjadi 3 yaitu data masukan, data proses dan data keluaran.  

### 4.2.1 Data Masukan

Data masukan yang dalam bentuk teks, diproses dengan melakukan konversi ke dalam bentuk file CSV (Comma Separated Value). Data yang dikonversi adalah data yang diperlukan saja. Konversi ini dilakukan agar data dapat lebih mudah untuk dimasukkan ke dalam suatu database. Pemilihan ke dalam bentuk CSV karena data dalam bentuk seperti itu bisa dikonversi ke dalam beberapa database, artinya beberapa database mendukung bentuk tersebut dalam proses import ke database tersebut.

Data masukan yang dibutuhkan dipindahkan ke dalam database (Oracle Database  10G), dengan beberapa atribut berikut ini:

![](images/00040.gif)

Gambar 4.1 Atribut Tabel IHSG BEJ

DDL (Data Definition Language) dari tabel yang akan dibuat adalah sebagai berikut:

![](images/00041.gif)

Gambar 4.2 Create Table IHSG BEJ

Berikut ini adalah beberapa data setelah dilakukan pemindahan ke dalam database Oracle.

![](images/00042.gif)

          Gambar 4.3 Data IHSG BEJ Oracle

Agar efisien dalam menggunakan waktu dalam pem-filter-an data yang benar pada master data saham maka dibuat beberapa view yang hasilnya adalah data yang dibutuhkan yakni IHSG yang sesuai dengan jenis masing-masing indeks. View adalah tabel secara virtual/bayangan atau query yang tersimpan dan tidak menyimpan data secara fisik View merupakan bagian dari DDL(Data Definition Language).

View dari masing-masing jenis indeks memiliki beberapa atribut sebagai berikut:

![](images/00043.gif)

Gambar 4.4 Atribut-atribut View

Berikut ini adalah beberapa jenis view yang digunakan untuk masing –masing IHSG:

*   VIEW_COMP2

View ini digunakan untuk mendapatkan IHSG BEJ yang berjenis composite index

![](images/00044.gif)

Gambar 4.5 View Composite Index

*   VIEW_AGRI

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor pertanian.

![](images/00045.gif)

                Gambar 4.6 View Agriculture Index

*   VIEW_MINING

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor pertambangan.

![](images/00046.gif)

             Gambar 4.7 View Mining Index

*   VIEW_BASIC

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor industri dasar dan kimia.

![](images/00047.gif)

                Gambar 4.8 View Basic Industry Index

*   VIEW_MISCELL

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam aneka industri.

![](images/00048.gif)

         Gambar 4.9 View Miscellanous Index

*   VIEW_CONSUME

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor industri barang konsumsi.

![](images/00049.gif)

          Gambar 4.10 View Consumer Good Index

*   VIEW_FINANCE

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor keuangan.

![](images/00050.gif)

           Gambar 4.11 View Finance Index

*   VIEW_INFRA

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor transportasi dan infrastruktur.

![](images/00051.gif)

             Gambar 4.12 View Infrastructure Index

*   VIEW_PROPERTY

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor properti dan real estate.

![](images/00052.gif)

                Gambar 4.13 View Property Index

*   VIEW_TRADE

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks sektoral yakni sektor perdagangan, jasa dan investasi.

![](images/00053.gif)

           Gambar 4.14 View Trade Index

*   VIEW_LQ

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam LQ45.

![](images/00054.gif)

             Gambar 4.15 View LQ45 Index

*   VIEW_MAIN

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks papan utama.

![](images/00055.gif)

           Gambar 4.16 View Main Board Index

*   VIEW_ISLAM

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam JII.

![](images/00056.gif)

                     Gambar 4.17 View Jakarta Islamic Index

*   VIEW_DEVELOP

View ini digunakan untuk mendapatkan IHSG BEJ yang termasuk dalam indeks papan pengembangan.

![](images/00057.gif)

                    Gambar 4.18 View Development Board Index

### 4.2.2 Data Proses

Implementasi dari perancangan data proses adalah membuat suatu matriks untuk menampung isi dari dari data masukan setelah di proses. Data masukan diproses dengan dua tahap, yakni:

1\.  Pencarian  pusat klaster

Pusat klaster disimpan dalam sebuah matriks satu dimensi setelah proses pencarian matriks dilakukan. Matriks ini jumlah barisnya sesuai dengan jumlah klaster yang diinputkan oleh pengguna. Matriks ini dinamakan dengan clustercentroid.

2\.   Pencarian derajat keanggotaan optimal

Pada tahap ini terdiri atas fase pencarian derajat keanggotaan tiap data masukan pada tiap klaster dan fase pencarian data derajat keanggotaan optimal.

          a. Fase pencarian derajat keanggotaan

Pada tahap ini, data proses hasil proses pencarian pusat klaster diolah dengan data masukan. Hasil dari proses ini dimasukkan kedalam matriks dua dimensi yang masing-masing indeksnya menunjukkan indeks dari data dan indeks dari klaster. Matriks ini berisi derajat keanggotaan tiap data pada klaster tertentu. Matriks ini diberi nama dengan matriks u1.

1.  Fase pencarian derajat keanggotaan optimal

Pada tahap ini, data hasil pada fase pencarian derajat keanggotaan optimal dicari dan disimpan dalam sebuah matriks. Matriks ini merupakan matriks satu dimensi yang isinya adalah indeks dari klaster yang derajatnya optimal.

### 4.2.3 Data Keluaran

Data keluaran adalah informasi yang dihasilkan oleh perangkat lunak untuk pengguna. Data yang sudah terproses sehingga mendapatkan keanggotaan pada klaster tertertentu dibuat tampilan grafiknya dengan warna yang berbeda untuk tiap klaster. Hal ini ada pada metode createDataset yang menampung data hasil proses klasterisasi.

Created with the Personal Edition of HelpNDoc: [Benefits of a Help Authoring Tool](http://www.helpauthoringsoftware.com)

# Implementasi Proses

## Implementasi Proses

       Sub bab ini menjelaskan tentang implementasi dari perancangan proses yang ada pada bab 3.

### 4.3.1 Fase Preprocessing  

        Fase ini merupakan fase dimana pengguna melakukan input ke aplikasi. Input dari pengguna perlu dilakukan suatu filter  sesuai dengan yang disyaratkan oleh algoritme pengklasteran Fuzzy C-Means. Berikut ini adalah kode program dari persyaratan input:

![](images/00058.gif)

       Fase ini juga melakukan proses pengambilan data masukan dari database sesuai dengan jenis indeks. Pengambilan melalui database dengan menggunakan koneksi langsung dengan komponen yang disediakan oleh Oracle yakni Oracle Data Source. ConnectDbFix adalah kelas yang berisi koneksi dan pengambilan data dari database. Kode program pengaksesan dari proses ini adalah sebagai berikut:

![](images/00059.gif)

![](images/00060.gif)

### 4.3.2 Fase Proses Klasterisasi

       Pada fase proses klasterisasi terdapat beberapa tahap yang sudah dijelaskan pada bab perancangan perangkat lunak. Berikut ini adalah beberapa kode program yang mencerminkan tahap perancangan tersebut.

#### 4.3.2.1 Proses Generate Data Input

       Berikut ini adalah kode program untuk mendapatkan nilai random yang dipersyaratkan oleh metode pengklasteran Fuzzy C-Means. Kode program ini menggunakan kelas random yang sudah tersedia.

![](images/00061.gif)

#### 4.3.2.2 Komputasi Pusat Klaster

       Berikut ini adalah kode program untuk mendapatkan pusat klaster seperti pada rumus pengklasteran dengan Fuzzy C-Means.

![](images/00062.gif)

#### 4.3.2.3 Komputasi Derajat Keanggotaan

       Derajat keanggotaan tiap data perlu untuk dihitung nilainya untuk masing-masing klaster. Tiap data selalu melakukan update derajat keanggotaan hingga kondisi pemberhentian terpenuhi. Berikut ini adalah kode program dari rumus mendapatkan derajat keanggotaan data pada masing-masing klaster.

![](images/00063.gif)

#### 4.3.2.4 Fase Pemberhentian

       Berikut ini adalah kode program dari fase pemberhentian seperti yang dijelaskan pada bab 3.

![](images/00064.gif)

### 4.3.3 Fase Pencarian Derajat Keanggotaan Optimal

       Fase ini adalah fase untuk mendapatkan data dengan derajat keanggotaan optimal. Berikut ini adalah kode program dari fase ini. Pada fase ini dilakukan sebuah algoritme perbandingan. Algoritme ini melakukan seleksi terhadap data pada suatu matriks yang memiliki derajat keanggotaan paling tinggi. Jikalau derajat keanggotaan paling tinggi didapatkan maka indeks matriks dari klaster akan disimpan sebagai nilai pengembaliannya. Nilai pengembalian ini yang berguna untuk proses selanjutnya.

![](images/00065.gif)

### 4.3.4 Fase Pengelompokkan Berdasarkan Klaster

       Kode program untuk mengelompokkan data berdasarkan klasternya adalah sebagai berikut:

![](images/00066.gif)

### 4.3.5 Fase Pembuatan Grafik Data Terklaster

       Ada beberapa grafik dalam aplikasi pada buku ini. Masing-masing akan dijelaskan berikut ini.

#### 4.3.5.1 Kelas hariFrame

       Kelas hariFrame berfungsi untuk menampilkan data hasil dari klasterisasi. Kelas ini akan menampilkan derajat keangotaan masing-masing data yang sudah terklaster beserta tanggal.

![](images/00067.gif)

#### 4.3.5.2 Kelas chartFrame

Kelas chartFrame berfungsi untuk menampilkan grafik dari data IHSG BEJ yang masih belum terklaster. Kelas ini terdiri dari 3 hal utama, yakni:

*   createDataSet: untuk menampung data yang akan digunakan.
*   createChart: untuk membuat grafik dari data yang tertampung dalam DataSet.
*   createDemoPanel: sebagai tempat dari grafiknya.

![](images/00068.gif)

#### 4.3.5.3 Kelas markerFrame

       Kelas markerFrame berfungsi untuk menampilkan grafik dari data-data IHSG BEJ yang telah terklaster. Kelas ini memiliki 3 hal utama yang sama dengan kelas chartFrame. Hanya bedanya adalah terletak pada marker. Marker ini digunakan sebagai pembeda antara klaster satu dengan yang lainnya. Hal ini untuk memudahkan pengguna agar bisa melihat informasi secara jelas. Berikut ini adalah implementasi dari kelas markerFrame dalam Java.

![](images/00069.gif)

#### 4.3.5.4 Kelas MbfFrame

       Kelas MbfFrame ini berfungsi untuk menampilkan derajat keanggotaan masing-masing IHSG BEJ secara detil dan menyeluruh. Kelas ini sekilas sama dengan hariFrame, akan tetapi sebenarnya berbeda. Bedanya terletak pada jumlah derajat keanggotaan masing-masing IHSG BEJ. Kelas ini akan menampilkan derajat keanggotaan dari IHSG BEJ dari masing-masing klaster, sedangkan hariFrame hanya menampilkan derajat keanggotaan yang paling besar saja.

![](images/00070.gif)

#### 4.3.5.5 Kelas degreeFrame

       Kelas degreeFrame digunakan untuk menampilkan grafik dari data-data derajat keanggotaan dari masing-masing IHSG BEJ pada tiap-tiap klaster. Dengan menggunakan kelas ini, bisa dilihat derajat keanggotaan masing-masing IHSG BEJ.

![](images/00071.gif)

Created with the Personal Edition of HelpNDoc: [Easily create CHM Help documents](http://www.helpndoc.com/feature-tour)

# Implementasi Antar Muka

## 4 Implementasi Antarmuka

Berikut ini adalah implementasi dari perancangan antarmuka dengan penjelasan dari tiap komponen yang ada pada form. Semuanya ada pada Gambar 4.19.

ecara umum implementasi antarmuka adalah sebagai berikut:

![](images/00072.jpeg)

Gambar 4.19 Implementasi Antarmuka

Untuk keterangan input  pada gambar 4.19 diatas adalah sebagai berikut:

*   *   Input 1:

Berupa nilai bilangan positif lebih dari 1, yang menyatakan jumlah dari klaster yang diinginkan oleh pengguna.

*   *   Input 2:

Berupa bilangan positif lebih dari 1, yang menyatakan nilai fuzziness dari FCM.

*   *   Input 3 :

Berupa bilangan desimal antara 0 dan 1, yang menyatakan batas ketelitian dari derajat keanggotaan masing-masing data terhadap klaster.

Contoh:

| input 1 | input 2 | input 3 |
| 3 | 2 | 0.03 |

Ada beberapa tombol yang bisa digunakan pengguna untuk menggunakan aplikasi tersebut, yakni:

*   *   Tombol Generate, tombol ini berfungsi untuk melakukan generate data secara random.
    *   Tombol Step by Step, tombol ini berfungsi untuk melakukan proses pengklasteran secara bertahap hingga kondisi pemberhentiannya terpenuhi.

*   Tombol Run, tombol ini berfungsi untuk melakukan proses pengklasteran secara langsung hingga kondisi pemberhentian iterasi terpenuhi.
*   Tombol Open, tombol ini berfungsi untuk membuka frame baru sesuai dengan pilihan pengguna pada radio button.

Created with the Personal Edition of HelpNDoc: [Full-featured multi-format Help generator](http://www.helpndoc.com/help-authoring-tool)

# Uji coba dan Evaluasi

# Uji Coba dan Evaluasi

Bab ini menjelaskan tentang lingkungan uji coba, skenario serta analisis dari aplikasi  yang telah dibuat.

## 5.1 Lingkungan Uji Coba

Uji coba aplikasi dilakukan dengan menggunakan spesifikasi sebagai berikut:

Tabel 5.1 Lingkungan Uji Coba

| Perangkat Keras | Prosesor : Intel(R) Pentium(R) 4 CPU 2.8 GHzMemori  : 1024 MB RAM |
| Perangkat Lunak | Sistem Operasi                      : Microsoft Windows Server 2003Perangkat Lunak IDE           : NetBeans 5DBMS                                   : Oracle 10G Database Server |

Created with the Personal Edition of HelpNDoc: [Full-featured Kindle eBooks generator](http://www.helpndoc.com/feature-tour/create-ebooks-for-amazon-kindle)

# Skenario 1

## Skenario Uji Coba 1

Pada uji coba ini diberikan suatu skenario yang ditujukan untuk mengetahui fungsionalitas aplikasi yang dibuat.

1.  1.  1.  Garis Besar Skenario 1

Suatu studi kasus dilakukan pada sudut pandang pengguna yang akan melakukan benchmarking sebagai alat bantu dalam pengambilan keputusan dan atau untuk melakukan suatu laporan terhadap nilai IHSG BEJ jenis Composite Index pada tahun 2005\. IHSG BEJ jenis Composite Index dibagi ke dalam kelompok-kelompok berikut ini:

Tabel 5.2 Kelompok Skenario 1

| Kelompok /Kelas | Keterangan |
| Kelas A | Kelas ini berarti terdapat nilai-nilai IHSG dengan poin yang sangat tinggi yang berarti pasar dalam keadaan Bullish. |
| Kelas AB | Kelas ini berarti terdapat nilai-nilai IHSG yang masih sangat baik, perdagangan masih dalam keadaan rata-rata atas. |
| Kelas B | Kelas ini berarti terdapat nilai-nilai IHSG yang masih dalam keadaan baik, perdagangan masih dalam keadaan rata-rata. |
| Kelas BC | Kelas ini berarti terdapat nilai-nilai IHSG yang masih dalam keadaan cukup baik, perdagangan masih dalam keadaan rata-rata bawah. |
| Kelas C | Kelas ini berarti terdapat nilai-nilai IHSG yang masih dalam keadaan cukup, dan cenderung untuk terpuruk, dan akan ke dalam kondisi pasar Bearish. |
| Kelas D | Kelas ini berarti terdapat nilai-nilai IHSG dengan poin yang sangat rendah dan terpuruk, kondisi berarti pasar dalam keadaan Bearish. |

1.  1.  1.  Pelaksanaan Skenario 1

Uji coba dilaksanakan dengan melakukan apa yang telah dituliskan dalam skenario diatas. Pelaksanaan Skenario ini akan melalui beberapa tahap, yakni tahap input parameter, proses benchmarking, melihat output dari benchmarking dan melakukan analisis dari output.

#### 5.2.2.1 Input Parameter

       Sesuai dengan skenario diatas, harus di-input-kan beberapa parameternya.

Input parameter yang  harus dimasukkan adalah:

Jumlah Cluster = 6 ; Fuzziness (m)     = 2; Batas ketelitian   = 0.03

![](images/00073.gif)

Gambar 5.1 Input Skenario 1

Kemudian pilihlah ”Composite Index” pada combo box disamping label Nama Index. Hal ini karena dilakukan sebuah benchmarking terhadap IHSG BEJ yang “Composite Index”.

![](images/00074.gif)

Gambar 5.2 Input Jenis Indeks Skenario 1

#### 5.2.2.2 Proses Benchmarking

       Ada beberapa proses yang harus dilalui dalam melakukan benchmarking. Proses ini merupakan tahap-tahap dari Fuzzy C-Mean Clustering. Pertama, inisialisasi derajat keanggotaan dengan melakukan klik kepada tombol Generate, yang nantinya akan melakukan inisialisasi pada variabel derajat keanggotaan dengan nilai random.

![](images/00075.gif)

Gambar 5.3 Generate Data Random

Kemudian klik tombol Run untuk melakukan proses selanjutnya, yakni mencari centroid dan mencari derajat keanggotaan masing-masing data terhadap masing-masing klaster serta melakukan update derajat keanggotaan secara terus menerus hingga batas ketelitiannya tercapai.

![](images/00076.gif)

Gambar 5.4 Run Proses Benchmarking

1.  1.  1.  1.  Output Benchmarking

Setelah terjadi beberapa tahapan dalam proses benchmarking, dapat dilihat hasilnya dengan representasi grafik-grafik pada Gambar 5.5 dan 5.6 berikut ini:

![](images/00001.jpeg)

                                  Gambar 5.5 Derajat Keanggotaan Skenario 1

Gambar 5.5 adalah grafik data IHSG BEJ terhadap derajat keanggotaannya pada tiap klaster. Beberapa daerah warna yang ada merepresentasikan masing-masing klaster. Pada grafik terdapat 6 warna yang berarti ada 6 klaster. Tiap data bisa menjadi anggota lebih dari satu klaster. Hal ini bila direpresentasikan dengan grafik, tiap data bisa masuk ke dalam lebih dari satu daerah warna.

Sedangkan grafik dibawah adalah sebuah grafik yang merepresentasikan masing-masing data yang  terklaster yang dihubungkan dengan variable waktu (saat terjadinya indeks berlangsung). Juga terlihat centroid dari masing-masing klaster.

![](images/00077.jpeg)

                                Gambar 5.6 Grafik Data Terklaster Skenario 1

Dibawah ini adalah sebuah tabel data berisi data IHSG BEJ Composite terklaster beserta derajat keanggotaan data pada masing-masing klaster berikut ini:

![](images/00078.jpeg)

Gambar 5.7 Output Derajat Keanggotaan Skenario 1

Apa yang bisa dilihat pada Gambar 5.7 ?. Gambar tersebut memberikan informasi derajat keanggotaan tiap data pada tiap klaster. Ini merupakan ciri khas dari FCM yang memiliki sifat fleksibilitas. Dari derajat keanggotaan tersebut bisa didapatkan suatu kecenderungan dari poin indeks tertentu. Contohnya pada data 1000,877\. Data tersebut memiliki derajat keanggotaan maksimalnya ada pada klaster 4 yang bernilai 0,716 sedangkan derajat keanggotaan tertinggi kedua ada pada klaster 3 yang bernilai 0,147\. Bila melihat pada Gambar 5.6 klaster 4 yang berwarna coklat sedangkan klaster 3 yang berwarna kuning maka diberikan informasi bahwa poin indeks 1000,877 masuk ke dalam klaster 4 dan cenderung ke dalam klaster 3\.

Hasil tabel data berupa data IHSG BEJ Composite terklaster yang sudah tersortir ascending beserta derajat keanggotaan paling maksimum masing-masing data dengan variabel waktu pada Gambar 5.8 berikut ini:

![](images/00079.jpeg)

Gambar 5.8 Output Data Terkorelasi Waktu Skenario 1

1.  1.  1.  1.  Analisis Output

Pada Gambar 5.9 bisa terlihat bahwa poin IHSG BEJ yang bernilai 1.041,628 masih belum diketahui masuk dalam kelompok yang mana. Gambar tersebut termasuk ke dalam grafik buta. Hal ini karena grafik tersebut masih belum bisa memberikan informasi secara lebih jelas. Contohnya adalah data yang ditunjuk pada grafik tersebut masuk ke dalam kelompok yang mana, apakah masuk dalam kelompok A, AB, B, BC, C atau D ?. Tiap manusia akan memiliki beberapa penilaian berbeda satu dengan yang lainnya.

![](images/00080.gif)

                                         Gambar 5.9 Grafik Buta Skenario 1

Namun melalui grafik yang ada dibawah ini bisa dilihat dengan jelas bahwa data tersebut berada pada kelompok C, karena termasuk ke dalam klaster kedua dari bawah.  Dari Gambar 5.10 dengan sangat jelas bisa dibedakan data mana termasuk ke dalam kelompok yang mana.

![](images/00081.jpeg)

Gambar 5.10 Grafik Benchmarking Skenario 1

Sekarang, mari mencari informasi yang terdapat dalam grafik Gambar 5.10 dari data terklaster tersebut. Lihatlah pada kelompok A (yang berwarna merah), yang merupakan kasta tertinggi dari kelompok data. Jika dilihat lebih jeli, bisa didapatkan bahwa indeks akan tinggi (berada pada kelompok A) pada bulan Agustus dan Desember. Berdasarkan informasi tersebut bisa dibuat suatu pijakan bahwa bursa saham dalam keadaan tinggi pada bulan-bulan tersebut. Hal tersebut bisa sebagai informasi dan pelajaran dari pengalaman untuk tahun berikutnya apa yang harus dilakukan pelaku pasar modal (khususnya investor) untuk menyikapi hal tersebut.

Benchmark didapatkan lebih rincinya adalah sebagai berikut:

![](images/00082.gif)

Gambar 5.11 Range Benchmark Skenario 1

Created with the Personal Edition of HelpNDoc: [Free help authoring environment](http://www.helpndoc.com/help-authoring-tool)

# Skenario 2

## Skenario Uji Coba 2

Pada uji coba ini diberikan suatu skenario yang ditujukan untuk mengetahui fungsionalitas aplikasi yang dibuat.

### 5.3.1 Garis Besar Skenario 2

Suatu studi kasus dilakukan pada sudut pandang pengguna yang akan melakukan benchmarking nilai IHSG BEJ jenis LQ45 pada tahun 2005\.

Penyusun memilih LQ45 karena terdapat suatu produk pasar modal dari PT. Bursa Efek Surabaya yang menjual poin dari indeks LQ45\. Tiap poin dari indeks tersebut diberikan harga tertentu oleh pihak yang mengeluarkan produk tersebut (dalam hal ini adalah PT Bursa Efek Surabaya). Investor melakukan aksi jual dan beli dari poin indeks tersebut. Investor mendapatkan keuntungan dari selisih jual beli poin indeks tersebut. Namanya adalah LQ Futures dan Mini LQ Futures. LQ Future diluncurkan pada tanggal 13 Agustus 2001 dan menjadi pelopor dari produk derivative khususnya untuk indeks future di Bursa Efek Surabaya. LQ Futures menggunakan IHSG BEJ yang berjenis LQ45 sebagai underlying (dasar/barang). LQ45 terkenal sebagai suatu benchmark pada saham yang tergolong blue chip pada bursa saham Indonesia. Pada pasar modal Indonesia yang cepat perkembangannya, indeks LQ45 menjadi sangat efektif untuk melakukan track pada bursa saham Indonesia pada umumnya. Hal ini karena ada korelasi yang sangat dekat antara indeks LQ45 dan IHSG BEJ yang berjenis composite index.

IHSG BEJ jenis LQ45 dibagi ke dalam kelompok-kelompok/kelas-kelas berikut ini:

Tabel 5.3 Kelompok Skenario 2

| Kelompok /Kelas | Keterangan |
| Kelas A | Kelas ini berarti terdapat nilai-nilai IHSG BEJ LQ45 dengan poin yang sangat tinggi yang berarti pasar dalam keadaan Bullish.  |
| Kelas B | Kelas ini berarti terdapat nilai-nilai IHSG BEJ LQ45 yang masih dalam keadaan baik, perdagangan masih dalam keadaan rata-rata. |
| Kelas C | Kelas ini berarti terdapat nilai-nilai IHSG BEJ LQ45 dengan poin yang sangat rendah dan terpuruk, kondisi berarti pasar dalam keadaan Bearish. |

1.  1.  1.  Pelaksanaan Skenario 2

Uji coba dilaksanakan dengan melakukan apa yang telah dituliskan dalam skenario diatas.

Pelaksanaan skenario ini akan melalui beberapa tahapan, yakni tahap input parameter, proses benchmarking, melihat output dari benchmarking dan melakukan analisis dari output.

#### 5.3.2.1  Input Parameter

       Sesuai dengan skenario diatas, harus di-input-kan beberapa parameternya.

Input parameter yang harus dimasukkan adalah:

Jumlah Cluster = 3; Fuzziness (m)     = 2; Batas ketelitian   = 0.03

![](images/00083.gif)

Gambar 5.12 Input Parameter Skenario 2

Pilihlah ”LQ45” pada combo box disamping label Nama Index. Hal ini karena akan dilakukan benchmarking terhadap IHSG BEJ jenis “LQ45”. Hal itu bisa dilihat pada Gambar 5.13 berikut ini.

![](images/00084.gif)

Gambar 5.13 Input Jenis Index Skenario 2

#### 5.3.2.2  Proses Benchmarking

       Ada beberapa proses yang harus dilalui untuk melakukan benchmarking. Proses ini merupakan tahap-tahap dari Fuzzy C-Means Clustering. Pertama, inisialisasi derajat keanggotaan dengan melakukan klik pada tombol Generate, yang nantinya akan melakukan inisialisasi pada variabel derajat keanggotaan dengan nilai random.

![](images/00085.gif)

Gambar 5.14 Generate Data Skenario 2

Kemudian klik tombol Run untuk melakukan proses selanjutnya, yakni mencari pusat klaster dan mencari derajat keanggotaan masing-masing data terhadap masing-masing klaster serta melakukan update derajat keanggotaan secara terus menerus hingga batas ketelitiannya tercapai.

![](images/00086.gif)

Gambar 5.15 Run Proses Skenario 2

1.  1.  1.  1.  Output Benchmarking

Setelah beberapa tahapan dilalui dalam proses benchmarking, dapat dilihat hasilnya dari representasi grafik pada Gambar 5.16 berikut ini. Grafik tersebut adalah grafik data IHSG BEJ LQ45 terhadap derajat keanggotaannya kepada masing-masing klaster. Beberapa warna yang ada adalah merepresentasikan masing-masing klaster. Didalam grafik terdapat 3 warna yang berarti ada 3 klaster. Ada  data yang masuk pada lebih dari dua klaster. Hal itu bisa dilihat dengan melihat daerah klaster yang berwarna. Pada grafik terlihat bahwa ada beberapa warna yang saling tumpang tindih. Daerah klaster yang berwarna biru sebagian tertutupi oleh daerah klaster yang berwarna merah begitu juga sebaliknya. Bahkan ada data yang masuk pada 3 daerah klaster.

![](images/00087.jpeg)

 Gambar 5.16 Derajat Keanggotaan Skenario 2

Sedangkan grafik Gambar 5.17 adalah sebuah grafik yang merepresentasikan tiap data yang  terklaster yang dihubungkan dengan variabel waktu (saat terjadinya indeks berlangsung). Juga terlihat centroid dari masing-masing klaster.

![](images/00088.jpeg)

                                Gambar 5.17 Grafik Data Terklaster Skenario 2

Berikut adalah tabel data berisi data IHSG BEJ LQ45 terklaster beserta derajat keanggotaan data pada masing-masing klaster:

![](images/00089.jpeg)

Gambar 5.18 Output Derajat Keanggotaan Skenario 2

Apa yang bisa dilihat pada Gambar 5.18 ?. Gambar itu memberikan informasi derajat keanggotaan tiap data pada klaster tertentu. Dari derajat keanggotaan tersebut bisa didapatkan suatu kecenderungan dari poin indeks tertentu. Contohnya pada data 218,568\. Data tersebut memiliki derajat keanggotaan tertinggi ada pada klaster 1 yang bernilai 0,835 sedangkan derajat keanggotaan tertinggi kedua ada pada klaster 0 yang bernilai 0,123\. Bila melihat pada Gambar 5.17 klaster 1 yang berwarna biru sedangkan klaster 0 yang berwarna merah maka diberikan informasi bahwa poin indeks 218,568 masuk ke dalam klaster 1dan cenderung ke dalam klaster 0.

Hasil tabel data berupa data IHSG BEJ LQ45 terklaster yang sudah tersortir ascending beserta derajat keanggotaan maksimum masing-masing data dengan variabel waktu ada Gambar 5.19 berikut ini:

![](images/00090.jpeg)

Gambar 5.19 Output Data Terkorelasi Waktu Skenario 2

1.  1.  1.  1.  Analisis Output

Berikut ini adalah grafik buta, data yang ditunjuk dalam grafik tersebut masuk ke dalam kelompok yang mana, apakah masuk dalam kelompok A, B, atau C.

![](images/00091.jpeg)

                                      Gambar 5.20 Grafik Buta Skenario 2

Melalui grafik pada Gambar 5.21, bisa dilihat dengan jelas bahwa data tersebut berada pada kelompok B. Data dapat dibedakan masuk dalam kelompok mana.

![](images/00092.jpeg)

Gambar 5.21 Grafik Benchmarking Skenario 2

Berikut ini adalah benchmark lebih detail :

![](images/00093.jpeg)

 Gambar 5.22 Range Benchmark Skenario 2

Informasi bisa diperoleh dengan melihat beberapa grafik yang ada. Indeks akan tinggi (berada pada kelompok A) pada bulan Juli, Agustus dan Desember. Berdasarkan informasi tersebut bisa dibuat suatu pijakan bahwa bursa saham LQ45 dalam keadaan tinggi pada bulan-bulan tersebut. Hal tersebut bisa sebagai informasi dan pelajaran dari pengalaman untuk tahun berikutnya apa yang harus dilakukan pelaku pasar modal (khususnya investor) untuk menyikapi hal tersebut.

Created with the Personal Edition of HelpNDoc: [Produce electronic books easily](http://www.helpndoc.com/create-epub-ebooks)

# Skenario 3

## Skenario Uji Coba 3

Uji coba ini diberikan suatu skenarioyang diujikan pada aplikasi ini. Skenario yang diujikan adalah skenario jenis IHSG BEJ yang termasuk ke dalam sektor industri.

### 5.4.1  Garis Besar Skenario 3

Terdapat suatu studi kasus dalam sudut pandang pengguna yang akan melakukan benchmarking terhadap nilai IHSG BEJ yang sektoral untuk mengetahui keadaan bursa saham pada sektor tertentu. Kali ini yang di ujicoba adalah IHSG BEJ dibidang Agriculture (pertanian).

Perusahaan yang tercatat di BEJ diklasifikasikan dalam 9 sektor yang didasarkan pada klasifikasi industri yang ditetapkan oleh BEJ yang disebut JASICA (Jakarta Stock Exchange Industrial Classification). Tiap sektor memiliki karakter sesuai dengan bidang perusahaan yang masuk dalam sektor tersebut. Dalam skenario ini, dipilih Agriculture sebagai perwakilan dari beberapa sektor tersebut. IHSG BEJ yang jenisnya Agriculture terdiri dari beberapa saham perusahaan yang bergerak dibidang pertanian. Salah satu contoh dari perusahaan tersebut adalah PT. Astra Agro Lestari Tbk (nama-nama perusahaan yang masuk dalam sektor industri bisa dilihat pada lampiran F).

IHSG BEJ Agriculture dibagi  ke dalam kelompok/kelas berikut ini:

Tabel 5.4 Kelompok Skenario 3

| Kelompok /Kelas | Keterangan |
| Kelas A | Kelas ini berarti terdapat nilai-nilai IHSG BEJ Agriculture  dengan poin yang sangat tinggi yang berarti pasar dalam keadaan Bullish. |
| Kelas B | Kelas ini berarti terdapat nilai-nilai IHSG BEJ Agriculture yang masih dalam keadaan baik, perdagangan masih dalam keadaan rata-rata. |
| Kelas C | Kelas ini berarti terdapat nilai-nilai IHSG BEJ Agriculture dengan poin yang sangat rendah dan terpuruk, kondisi berarti pasar dalam keadaan Bearish. |

### 5.4.2 Pelaksanaan Skenario

Uji coba dilaksanakan dengan melakukan apa yang telah dituliskan dalam skenario diatas. Pelaksanaan skenario ini akan melalui beberapa tahapan, yakni tahap input parameter, proses benchmarking, melihat output dari benchmarking dan melakukan analisis dari output. Masing-masing tahapan tersebut akan dijelaskan lebih lanjut pada sub bahasan yang ada dibawah ini.

#### 5.4.2.1  Input Parameter

       Sesuai dengan skenario diatas, harus di-input-kan beberapa parameternya.

Input parameter yang harus dimasukkan adalah:

Jumlah Cluster  = 3; Fuzziness (m)     = 2; Batas ketelitian   = 0.03

![](images/00094.gif)

Gambar 5.23 Input Parameter Skenario 3

Kemudian pilih ”Agriculture” pada combo box disamping label Nama Index. Hal ini karena akan dilakukan benchmarking terhadap IHSG BEJ yang berjenis “Agriculture”.

![](images/00095.gif)

Gambar 5.24 Input Jenis Indeks Skenario 3

#### 5.4.2.2  Proses Benchmarking.

       Ada beberapa proses yang harus dilalui untuk melakukan benchmarking. Proses ini merupakan tahap-tahap dari Fuzzy C-Mean Clustering. Pertama, inisialisasi derajat keanggotaan dengan melakukan klik kepada tombol Generate, yang nantinya akan melakukan inisialisasi pada variabel derajat keanggotaan dengan nilai random.

![](images/00096.gif)

Gambar 5.25 Generate Data Skenario 3

Kemudian klik tombol Run untuk melakukan proses selanjutnya, yakni mencari centroid dan mencari derajat keanggotaan masing-masing data terhadap masing-masing klaster serta melakukan update derajat keanggotaan secara terus menerus hingga batas ketelitiannya tercapai.

![](images/00097.gif)

        Gambar 5.26 Run Proses Skenario 3

1.  1.  1.  1.  Output Benchmarking

Setelah terjadi beberapa tahap dalam proses benchmarking, dapat dilihat hasilnya dengan representasi grafik pada Gambar 5.27\. Grafik tersebut adalah grafik data IHSG BEJ Agriculture terhadap derajat keanggotaannya pada masing-masing klaster. Beberapa warna yang ada merepresentasikan masing-masing klaster. Pada grafik terdapat 3 warna yang berarti ada 3 klaster.

![](images/00098.jpeg)

Gambar 5.27 Grafik Derajat Keanggotaan Skenario 3

Sedangkan grafik pada Gambar 5.28 adalah grafik yang merepresentasikan masing-masing data yang  terklaster yang dihubungkan dengan variable waktu (saat terjadinya indeks berlangsung). Tiap klaster dibedakan dengan warna. Pada grafik tersebut juga terlihat centroid dari masing-masing klaster. Gugusan titik yang berwarna merah adalah klaster C, biru adalah klaster B, sedangkan hijau adalah klaster C.

![](images/00099.jpeg)

                                   Gambar 5.28 Grafik Data Terklaster Skenario 3

Gambar 5.29 adalah hasil dari klasterisasi dengan derajat keanggotaan data di tiap klaster.

![](images/00100.jpeg)

                    Gambar 5.29 Output Derajat Keanggotaan Maksimum Skenario 3

Apa yang bisa dilihat pada Gambar 5.29 ?. Gambar itu memberikan informasi derajat keanggotaan tiap data pada klaster tertentu. Dari derajat keanggotaan tersebut bisa didapatkan suatu kecenderungan dari poin indeks tertentu. Contohnya pada data 303,318\. Data tersebut memiliki derajat keanggotaan tertinggi ada pada klaster 0 yang bernilai 0,994 sedangkan derajat keanggotaan tertinggi kedua ada pada klaster 1 yang bernilai 0,004\. Bila melihat pada Gambar 5.28 klaster 0 yang berwarna merah sedangkan klaster 1 yang berwarna biru maka diberikan informasi bahwa poin indeks 303,318 masuk ke dalam klaster 0 dan cenderung ke dalam klaster 1.

Gambar 5.30 adalah hasil dari klasterisasi yang sudah tersortir ascending beserta derajat keanggotaan maksimum tiap data dengan variabel waktu:

![](images/00101.jpeg)

                     Gambar 5.30  Output Data Terkorelasi dengan Waktu Skenario 3

1.  1.  1.  1.  Analisis Output

Berikut ini adalah grafik buta, data yang ditunjuk dalam grafik tersebut masuk ke dalam kelompok yang mana, apakah masuk dalam kelompok A, B, atau C?.

![](images/00102.gif)

                                    Gambar 5.31 Grafik Buta Skenario 3

Akan tetapi melalui grafik yang ada pada Gambar 5.32 bisa dilihat dengan jelas bahwa data tersebut berada pada kelompok A, karena termasuk di dalam klaster pertama dari atas. Data bisa dilihat dengan jelas masuk ke dalam kelompok yang mana.

![](images/00103.jpeg)

  Gambar 5.32 Grafik Benchmarking Skenario 3

Informasi bisa diperoleh dengan melihat beberapa grafik yang ada. Indeks akan tinggi (berada pada kelompok A) pada bulan Oktober, Nopember dan Desember. Berdasarkan informasi tersebut bisa dibuat suatu pijakan bahwa bursa saham Agriculture dalam keadaan tinggi pada bulan-bulan tersebut. Hal tersebut bisa sebagai informasi dan pelajaran dari pengalaman untuk tahun berikutnya apa yang harus dilakukan pelaku pasar modal (khususnya investor) untuk menyikapi hal tersebut.

Gambar 5.33 berikut ini adalah benchmark dari IHSG BEJ agriculture :

![](images/00104.jpeg)

Gambar 5.33 Range Benchmark Skenario 3

Created with the Personal Edition of HelpNDoc: [Create help files for the Qt Help Framework](http://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework)

# Skenario 4

## Skenario Uji Coba 4

Pada uji coba ini diberikan suatu skenario yang ditujukan untuk mengetahui fungsionalitas aplikasi yang dibuat.

### 5.5.1 Garis Besar Skenario 4

Terdapat suatu studi kasus dalam sudut pandang pengguna yang akan melakukan benchmarking terhadap nilai IHSG BEJ. Kali ini yang di ujicoba adalah IHSG BEJ yang jenisnya JII (Jakarta Islamic Index). Saham-saham yang masuk ke dalam JII memiliki daya tarik yang tinggi bagi masyarakat yang memiliki niat untuk melakukan investasi hanya pada perusahaan yang bersifat halal. Banyak investor baik dari dalam maupun dari luar negeri yang beragama Islam yang berinvestasi pada saham-saham tersebut. Perusahaan yang sahamnya termasuk dalam JII ada pada lampiran E.

Tabel 5.5 Kelompok Skenario 4

| Kelompok /Kelas | Keterangan |
| Kelas A | Kelas ini berarti terdapat nilai-nilai IHSG JII dengan poin yang sangat tinggi yang berarti pasar dalam keadaan Bullish. |
| Kelas AB | Kelas ini berarti terdapat nilai-nilai IHSG JII yang masih sangat baik, perdagangan masih dalam keadaan rata-rata atas. |
| Kelas B | Kelas ini berarti terdapat nilai-nilai IHSG JII yang masih dalam keadaan baik, perdagangan masih dalam keadaan rata-rata. |
| Kelas BC | Kelas ini berarti terdapat nilai-nilai IHSG JII yang masih dalam keadaan cukup baik, perdagangan masih dalam keadaan rata-rata bawah. |
| Kelas C | Kelas ini berarti terdapat nilai-nilai IHSG JII yang masih dalam keadaan cukup, dan cenderung untuk terpuruk, dana kan ke dalam kondisi pasar Bearish. |
| Kelas D | Kelas ini berarti terdapat nilai-nilai IHSG JII dengan poin yang sangat rendah dan terpuruk, kondisi berarti pasar dalam keadaan Bearish. |

### 5.5.2  Pelaksanaan Skenario

Uji coba dilaksanakan dengan melakukan apa yang telah dituliskan dalam skenario diatas. Pelaksanaan skenario ini akan melalui beberapa tahap, yakni tahap input parameter, proses benchmarking, melihat output dari benchmarking dan melakukan analisis dari output. Masing-masing tahapan tersebut akan dijelaskan lebih lanjut pada sub bahasan yang ada dibawah ini.

#### 5.5.2.1  Input Parameter

       Sesuai dengan skenario diatas, harus di-input-kan beberapa parameternya.

Input parameter yang harus dimasukkan adalah:

Jumlah Cluster  = 6; Fuzziness (m)     = 2; Batas ketelitian   = 0.03

![](images/00105.jpeg)

Gambar 5.34 Input Parameter Skenario 4

Kemudian pilih ”Jakarta Islamic Index” pada combo box disamping label Nama Index. Hal ini karena akan dilakukan benchmarking terhadap IHSG BEJ yang berjenis “Jakarta Islamic Index”.

![](images/00106.jpeg)

     Gambar 5.35 Jenis Indeks Skenario 4

#### 5.5.2.2  Proses Benchmarking.

       Ada beberapa proses yang harus dilalui untuk melakukan benchmarking. Proses ini merupakan tahap dari FCM. Pertama, inisialisasi derajat keanggotaan dengan melakukan klik kepada tombol Generate, yang nantinya akan melakukan inisialisasi pada variabel derajat keanggotaan dengan nilai random.

![](images/00107.jpeg)

Gambar 5.36 Generate Data Skenario 4

Kemudian klik tombol Run untuk melakukan proses selanjutnya, yakni mencari centroid dan mencari derajat keanggotaan masing-masing data terhadap masing-masing klaster serta melakukan update derajat keanggotaan secara terus menerus hingga batas ketelitiannya tercapai.

![](images/00108.jpeg)

Gambar 5.37 Run Proses Skenario 4

1.  1.  1.  1.  Output Benchmarking

Setelah terjadi beberapa tahap dalam proses benchmarking, dapat dilihat hasilnya dengan representasi grafik pada Gambar 5.38\. Grafik tersebut adalah grafik data IHSG BEJ JII terhadap derajat keanggotaannya pada masing-masing klaster. Beberapa warna yang ada merepresentasikan masing-masing klaster

![](images/00109.jpeg)

Gambar 5.38 Grafik Derajat Keanggotaan Skenario 4

Sedangkan grafik pada Gambar 5.39 adalah grafik yang merepresentasikan masing-masing data yang  terklaster yang dihubungkan dengan variable waktu (saat terjadinya indeks berlangsung). Tiap klaster dibedakan dengan warna. Pada grafik tersebut juga terlihat centroid dari masing-masing klaster.

![](images/00110.jpeg)

                                Gambar 5.39 Grafik Data Terklaster Skenario 4

Hasil dari data IHSG BEJ JII terklaster beserta derajat keanggotaan data pada masing-masing klaster ada pada Gambar 5.40:

![](images/00111.jpeg)

Gambar 5.40 Output Derajat Keanggotaan Skenario 4

Apa yang bisa dilihat pada Gambar 5.40 ?. Gambar itu memberikan informasi derajat keanggotaan tiap data pada klaster tertentu. Contohnya pada data 166,605\. Data tersebut memiliki derajat keanggotaan tertinggi ada pada klaster 4 yang bernilai 0,562 sedangkan derajat keanggotaan tertinggi kedua ada pada klaster 5 yang bernilai 0,338\. Bila melihat pada Gambar 5.39 klaster 4 yang berwarna coklat sedangkan klaster 5 yang berwarna ungu maka diberikan informasi bahwa poin indeks 166,605 masuk ke dalam klaster 4 dan cenderung ke dalam klaster 5.

Gambar 5.41 adalah hasil data IHSG BEJ JII terklaster yang sudah tersortir ascending berdasarkan klaster beserta derajat keanggotaan maksimum masing-masing data dengan variabel waktu:

![](images/00112.jpeg)

 Gambar 5.41 Output Data Terkorelasi dengan Waktu Skenario 4

1.  1.  1.  1.  Analisis Output

Berikut ini adalah grafik buta, data yang ditunjuk dalam grafik tersebut masuk ke dalam kelompok yang mana, apakah masuk dalam kelompok A, B, atau C?.

![](images/00113.jpeg)

                                      Gambar 5.42 Grafik Buta Skenario 4

Akan tetapi melalui grafik yang ada pada Gambar 5.43 bisa dilihat dengan jelas bahwa data tersebut berada pada kelompok AB, karena termasuk di dalam klaster kedua dari atas.

![](images/00114.jpeg)

                                Gambar 5.43 Grafik Benchmarking Skenario 4

Informasi bisa diperoleh dengan melihat beberapa grafik yang ada. Indeks akan tinggi (berada pada kelompok A) pada bulan Agustus dan Desember. Berdasarkan informasi tersebut bisa dibuat suatu pijakan bahwa bursa saham JII dalam keadaan tinggi pada bulan-bulan tersebut. Hal tersebut bisa sebagai informasi dan pelajaran dari pengalaman untuk tahun berikutnya apa yang harus dilakukan pelaku pasar modal (khususnya investor) untuk menyikapi hal tersebut.

        Detail dari benchmark dari IHSG BEJ JII adalah sebagai berikut:

![](images/00115.gif)

Gambar 5.44 Range Benchmark Skenario 4

Created with the Personal Edition of HelpNDoc: [Create help files for the Qt Help Framework](http://www.helpndoc.com/feature-tour/create-help-files-for-the-qt-help-framework)

# Skenario 5

## Skenario Uji Coba 5

Pada uji coba ini diberikan suatu skenario yang ditujukan untuk mengetahui fungsionalitas aplikasi yang dibuat. Terdapat sebuah skenario yang diujikan pada aplikasi ini.

### 5.6.1 Garis Besar Skenario 5

Suatu studi kasus dilakukan pada sudut pandang pengguna yang akan melakukan benchmarking sebagai alat bantu dalam pengambilan keputusan dan atau untuk melakukan suatu laporan terhadap nilai IHSG BEJ jenis Main Board pada tahun 2005\.

IHSG BEJ jenis Main Board dibagi ke dalam kelompok-kelompok/kelas-kelas berikut ini:

Tabel 5.6 Kelompok Skenario 5

| Kelompok /Kelas | Keterangan |
| Kelas A | Kelas ini berarti terdapat nilai-nilai IHSG BEJ Main Board dengan poin yang sangat tinggi yang berarti pasar dalam keadaan Bullish.  |
| Kelas B | Kelas ini berarti terdapat nilai-nilai IHSG BEJ Main Board yang masih dalam keadaan baik, perdagangan masih dalam keadaan rata-rata. |
| Kelas C | Kelas ini berarti terdapat nilai-nilai IHSG BEJ Main Board dengan poin yang sangat rendah dan terpuruk, kondisi berarti pasar dalam keadaan Bearish. |

1.  1.  1.  Pelaksanaan Skenario 5

Uji coba dilaksanakan dengan melakukan apa yang telah dituliskan dalam skenario diatas.

Pelaksanaan skenario ini akan melalui beberapa tahapan, yakni tahap input parameter, proses benchmarking, melihat output dari benchmarking dan melakukan analisis dari output.

#### 5.6.2.1  Input Parameter

       Sesuai dengan skenario diatas, harus di-input-kan beberapa parameternya.

Input parameter yang harus dimasukkan adalah:

Jumlah Cluster = 3; Fuzziness (m)     = 2; Batas ketelitian   = 0.03

![](images/00116.gif)

Gambar 5.45 Input Parameter Skenario 5

Pilihlah ”Main Board” pada combo box disamping label Nama Index. Hal ini karena akan dilakukan benchmarking terhadap IHSG BEJ jenis ”Main Board” Hal itu bisa dilihat pada Gambar 5.46 berikut ini.

![](images/00117.jpeg)

Gambar 5.46 Input Jenis Index Skenario 5

#### 5.6.2.2  Proses Benchmarking

       Ada beberapa proses yang harus dilalui untuk melakukan benchmarking. Proses ini merupakan tahap-tahap dari FCM. Pertama, inisialisasi derajat keanggotaan dengan melakukan klik pada tombol Generate, yang nantinya akan melakukan inisialisasi pada variabel derajat keanggotaan dengan nilai random.

![](images/00118.jpeg)

Gambar 5.47 Generate Data Skenario 5

Kemudian klik tombol Run untuk melakukan proses selanjutnya, yakni mencari pusat klaster dan mencari derajat keanggotaan masing-masing data terhadap masing-masing klaster serta melakukan update derajat keanggotaan secara terus menerus hingga batas ketelitiannya tercapai.

![](images/00119.jpeg)

Gambar 5.48 Run Proses Skenario 5

1.  1.  1.  1.  Output Benchmarking

Setelah beberapa tahapan dilalui dalam proses benchmarking, dapat dilihat hasilnya dari representasi grafik pada Gambar 5.49 berikut ini.

![](images/00120.jpeg)

 Gambar 5.49 Derajat Keanggotaan Skenario 5

Grafik tersebut adalah grafik data IHSG BEJ Main Board terhadap derajat keanggotaannya kepada tiap klaster. Beberapa warna yang ada merepresentasikan tiap klaster. Didalam grafik terdapat 3 warna yang berarti ada 3 klaster. Ada  data yang masuk pada lebih dari dua klaster. Hal itu bisa dilihat dengan melihat daerah klaster yang berwarna. Pada grafik terlihat bahwa ada beberapa warna yang saling tumpang tindih. Daerah klaster yang berwarna biru sebagian tertutupi oleh daerah klaster yang berwarna hijau begitu juga sebaliknya. Bahkan ada data yang masuk pada 3 daerah klaster, ketiga daerah klaster tersebut saling tumpang tindih.

Sedangkan grafik Gambar 5.50 adalah sebuah grafik yang merepresentasikan tiap data yang  terklaster yang dihubungkan dengan variabel waktu (saat terjadinya indeks berlangsung). Juga terlihat centroid dari masing-masing klaster.

![](images/00121.jpeg)

 Gambar 5.50 Grafik Data Terklaster Skenario 5

Gambar 5.51 adalah sebuah tabel data berisi data terklaster beserta derajat keanggotaan data pada tiap klaster:

![](images/00122.jpeg)

Gambar 5.51 Output Derajat Keanggotaan Skenario 5

Apa yang bisa dilihat pada Gambar 5.51 ?. Gambar itu memberikan informasi derajat keanggotaan tiap data pada klaster tertentu. Ini merupakan ciri khas dari FCM yang memiliki sifat fleksibilitas. Dari derajat keanggotaan tersebut bisa didapatkan suatu kecenderungan dari poin indeks tertentu. Contohnya pada data 269,281\. Data tersebut memiliki derajat keanggotaan tertinggi ada pada klaster 1 yang bernilai 0,837 sedangkan derajat keanggotaan tertinggi kedua ada pada klaster 2 yang bernilai 0,123\. Bila melihat pada Gambar 5.50 klaster 1 yang berwarna biru sedangkan klaster 2 yang berwarna merah maka diberikan informasi bahwa poin indeks 269,281 masuk ke dalam klaster 1 dan cenderung ke dalam klaster 2.

Hasil tabel data berupa data terklaster yang sudah tersortir ascending beserta derajat keanggotaan maksimum dengan variabel waktu ada Gambar 5.52 berikut ini:

![](images/00123.jpeg)

Gambar 5.52 Output Data Terkorelasi Waktu Skenario 5

1.  1.  1.  1.  Analisis Output

Berikut ini adalah grafik buta, data yang ditunjuk dalam grafik tersebut masuk ke dalam kelompok yang mana, apakah masuk dalam kelompok A, B, atau C ?.

![](images/00124.jpeg)

                                     Gambar 5.53 Grafik Buta Skenario 5

Melalui grafik pada Gambar 5.54, bisa dilihat dengan jelas bahwa data tersebut berada pada kelompok B. Data dapat dibedakan masuk dalam kelompok mana.

![](images/00125.jpeg)

Gambar 5.54 Grafik Benchmarking Skenario 5

Informasi bisa diperoleh dengan melihat beberapa grafik yang ada. Indeks akan tinggi (berada pada kelompok A) pada Agustus dan Desember. Berdasarkan informasi tersebut bisa dibuat suatu pijakan bahwa bursa saham Main Board dalam keadaan tinggi pada bulan-bulan tersebut. Hal tersebut bisa sebagai informasi dan pelajaran dari pengalaman untuk tahun berikutnya apa yang harus dilakukan pelaku pasar modal (khususnya investor) untuk menyikapi hal tersebut.

Berikut ini adalah benchmark lebih detail :

![](images/00126.jpeg)

   Gambar 5.55 Range Benchmark Skenario 5

Created with the Personal Edition of HelpNDoc: [Easy to use tool to create HTML Help files and Help web sites](http://www.helpndoc.com/help-authoring-tool)

# Kesimpulan dan Saran

# Kesimpulan dan Saran

Bab ini menjelaskan tentang kesimpulan dari ujicoba yang telah dilakukan serta saran untuk perbaikan dari buku ini.

## 6.1 Kesimpulan

Pada bab 5 telah diujicobakan 5 skenario dengan jenis IHSG yang berbeda. IHSG jenis Composite Index, LQ45, Agriculture Sector,  JII dan Main Board Index adalah IHSG yang diujicobakan. Setelah melihat hasil dari ujicoba dari bab 5 diatas, maka bisa dibuat suatu kesimpulan dari ujicoba. Kesimpulan yang dinyatakan berikut ini telah disetujui oleh praktisi pasar modal.

Kesimpulan yang bisa diambil dari buku ini adalah:

*   Implementasi Fuzzy C-Means Clustering untuk pengklasteran IHSG BEJ bisa dilakukan untuk proses benchmarking yakni proses memberi batasan yang jelas antar poin IHSG BEJ.
*   Analisis data historis dari IHSG BEJ dapat dilakukan setelah proses benchmarking dilakukan yang kemudian dikorelasikan dengan variabel waktu terjadinya indeks.

## 6.2 Saran

Saran adalah suatu hal yang wajib sebagai usaha untuk mencapai kesempurnaan dari hasil karya setiap manusia. Oleh karena itu dibutuhkan sekali saran untuk buku ini. Saran dari buku ini merupakan saran dari praktisi pasar modal. Berikut ini adalah saran-saran untuk buku ini :

*   Implementasi dari Fuzzy C-Means Clustering sebaiknya tidak terbatas satu dimensi saja (dimensi indeks), namun bisa dihubungkan dengan variabel-variabel lainnya yang nantinya bisa mendukung  proses benchmarking.
*   Data yang digunakan tidak hanya terbatas pada tahun 2005 saja, tetapi untuk rentang tahun yang lebih lama.

Created with the Personal Edition of HelpNDoc: [Free CHM Help documentation generator](http://www.helpndoc.com)

# Daftar Pustaka

# Daftar Pustaka

| [Agr04] | Ashish Kumar Agrawal, Mini Project Report: Design and approaches implementation of a classification system based on soft computing and statistical approaches, 2004, IIIT Deemed University. |
| [Bez81] | J. C. Bezdek,  Pattern Recognition with Fuzzy Objective Function  Algoritms, Plenum Press, New York., 1981. |
| [Dun73] | J. C. Dunn, A Fuzzy Relative of the ISODATA Process and Its Use in  Detecting Compact Well-Separated Clusters,  Journal of Cybernetics 3: 32-57, 1973. |
| [Fra93] | Jack Clark Francis, (trans) Handoyo, Prasetyo, Management of Investment,3rd ed.McGraw Hill International Editions,New York, 1993. |
| [Han01] | Jiawei Han, and Micheline  Kamber, Data Mining : Concepts and Techiques,  Morgan Kaufmann Publisher.San Francisco, 2001. |
| [Huang90] | Stanley S.C. Huang, (trans) Lamarto Yohannes, Timing The Stock USA, Market For Maximum Profit, Probus Publishing Company,Chichago, Illinois, 1990. |
| [Jang97] | Jyh-Shing Roger Jang, Chuen-Tsai Sun, dan Eiji Mizutani, Neuro-Fuzzy and Soft Computing : A Computational Approach to Learning and Machine Intelligence, New Jersey : Prentice-Hall International Inc, 1997. |
| [Jak05] | Jakarta Stock Exchange Research and Development Division, JSX Monthly Statistics Volume 14 No 11, November 2005. |
| [Kann] | S R Kannan, Segmentation of MRI Using New Unsupervised Fuzzy C-Mean Algorithm, ICTP, DISI, Universitaa di Genova Italy. |
|  |  |
| [Mic06] | Microsoft,  http://[www.encarta.msn.com](http://www.encarta.msn.com), 2006. |
| [Muc] | Hans-Joachim Mucha and Hizir Sofyan, : Nonhierarchical Clustering. [http://www.quantlet.com/mdstat/scripts/xag/html/xaghtmlframe149.html](http://www.quantlet.com/mdstat/scripts/xag/html/xaghtmlframe149.html). |
| [Oxf06] | Oxford University Press, [http://www.askoxford.com](http://www.askoxford.com), 2006. |
| [Pring91] | Martin J. Pring, (trans) Tirok Junius, Investment :Analysis Explained,3rd ed, McGraw Hill International Editions, New York, 1991. |
| [Ras] | Tariq Rashid,  Clustering [http://www.cs.bris.ac.uk/home/tr1690/documentation/fuzzy_clustering_ini](http://www.cs.bris.ac.uk/home/tr1690/documentation/fuzzy_clustering_initial_report/node11.html)tial_report/node11.html. |
| [Web97] | WebFinance, Inc,  [http://www.investorwords.com](http://www.investorwords.com), 1997-2006. |
|  |  |

Created with the Personal Edition of HelpNDoc: [Free help authoring tool](http://www.helpndoc.com/help-authoring-tool)

# Table of Contents

[Cover](#part0000.html_0-808d8ed5263047b2a3c1b548b3675a4b)[Abstrak](#part0001_split_000.html_UGI0-808d8ed5263047b2a3c1b548b3675a4b)[Kata Pengantar](#part0002_split_000.html_1T140-808d8ed5263047b2a3c1b548b3675a4b)[Teori Penunjang](#part0003.html_2RHM0-808d8ed5263047b2a3c1b548b3675a4b)[Benchmarking](#part0004_split_000.html_3Q280-808d8ed5263047b2a3c1b548b3675a4b)[Clustering](#part0005_split_000.html_4OIQ0-808d8ed5263047b2a3c1b548b3675a4b)[Fuzzy C-Means Clustering](#part0006_split_000.html_5N3C0-808d8ed5263047b2a3c1b548b3675a4b)[IHSG](#part0007_split_000.html_6LJU0-808d8ed5263047b2a3c1b548b3675a4b)[Perancangan Perangkat Lunak](#part0008_split_000.html_7K4G0-808d8ed5263047b2a3c1b548b3675a4b)[Perancangan Data](#part0009_split_000.html_8IL20-808d8ed5263047b2a3c1b548b3675a4b)[Perancangan Proses](#part0010_split_000.html_9H5K0-808d8ed5263047b2a3c1b548b3675a4b)[Perancangan Antarmuka](#part0011_split_000.html_AFM60-808d8ed5263047b2a3c1b548b3675a4b)[Implementasi Perangkat Lunak](#part0012_split_000.html_BE6O0-808d8ed5263047b2a3c1b548b3675a4b)[Implementasi Data](#part0013_split_000.html_CCNA0-808d8ed5263047b2a3c1b548b3675a4b)[Implementasi Proses](#part0014_split_000.html_DB7S0-808d8ed5263047b2a3c1b548b3675a4b)[Implementasi Antar Muka](#part0015_split_000.html_E9OE0-808d8ed5263047b2a3c1b548b3675a4b)[Uji coba dan Evaluasi](#part0016_split_000.html_F8900-808d8ed5263047b2a3c1b548b3675a4b)[Skenario 1](#part0017_split_000.html_G6PI0-808d8ed5263047b2a3c1b548b3675a4b)[Skenario 2](#part0018_split_000.html_H5A40-808d8ed5263047b2a3c1b548b3675a4b)[Skenario 3](#part0019_split_000.html_I3QM0-808d8ed5263047b2a3c1b548b3675a4b)[Skenario 4](#part0020_split_000.html_J2B80-808d8ed5263047b2a3c1b548b3675a4b)[Skenario 5](#part0021_split_000.html_K0RQ0-808d8ed5263047b2a3c1b548b3675a4b)[Kesimpulan dan Saran](#part0022_split_000.html_KVCC0-808d8ed5263047b2a3c1b548b3675a4b)[Daftar Pustaka](#part0023_split_000.html_LTSU0-808d8ed5263047b2a3c1b548b3675a4b)