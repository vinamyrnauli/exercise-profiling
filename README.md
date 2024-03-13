## TUTORIAL 5

**Nama: Vina Myrnauli Abigail Siallagan** <br>
**NPM: 2206825776** <br>
**Kelas: Pemrograman Lanjut - A** <br>

### Berikut adalah hasil dari uji JMeter dengan GUI
* **HTTP Request untuk `/all-student`:**
<p align="center">
    <img src="src\main\resources\images\gui-1-jm.jpg" />
</p>

* **HTTP Request untuk `/all-student-name`:**
<p align="center">
    <img src="src\main\resources\images\gui-2-jm.jpg" />
</p>

* **HTTP Request untuk `/highest-gpa`:**
<p align="center">
    <img src="src\main\resources\images\gui-3-jm.jpg" />
</p>

### Berikut adalah hasil uji JMeter dengan CLI
* **HTTP Request untuk `/all-student`:**
<p align="center">
    <img src="src\main\resources\images\cli-1-jm.jpg" />
</p>

* **HTTP Request untuk `/all-student-name`:**
<p align="center">
    <img src="src\main\resources\images\cli-2-jm.jpg" />
</p>

* **HTTP Request untuk `/highest-gpa`:**
<p align="center">
    <img src="src\main\resources\images\cli-3-jm.jpg" />
</p>

### Berikut adalah proses pengoptimalan performa 
**HTTP Request untuk `/all-student`:** <br>
1. Sebelum Optimisasi:
    <p align="center">
        <img src="src\main\resources\images\preprof-1.jpg" />
    </p> 

2. Setelah Optimisasi:
- Profiling
    <p align="center">
        <img src="src\main\resources\images\posprof-1.jpg" />
    </p> 
- JMeter
    <p align="center">
        <img src="src\main\resources\images\cli-1-after.jpg" />
    </p> 

**HTTP Request untuk `/all-student-name`:** <br>
1. Sebelum Optimisasi:
    <p align="center">
        <img src="src\main\resources\images\preprof-2.jpg" />
    </p> 

2. Setelah Optimisasi:
- Profiling
    <p align="center">
        <img src="src\main\resources\images\posprof-2.jpg" />
    </p> 
- JMeter
    <p align="center">
        <img src="src\main\resources\images\cli-2-after.jpg" />
    </p> 

**HTTP Request untuk `/highest-gpa`:** <br>
1. Sebelum Optimisasi:
    <p align="center">
        <img src="src\main\resources\images\preprof-3.jpg" />
    </p> 

2. Setelah Optimisasi:
- Profiling
    <p align="center">
        <img src="src\main\resources\images\posprof-3.jpg" />
    </p> 
- JMeter
    <p align="center">
        <img src="src\main\resources\images\cli-3-after.jpg" />
    </p> 

### Penjelasan pengurangan waktu eksekusi
- Terdapat pengurangan waktu eksekusi saat mengakses `/all-student` dari rata-rata 13021ms menjadi 3019ms di *Profiling Intellij* dan dari rata-rata 95000ms menjadi 85500ms di JMeter.
- Terdapat pengurangan waktu eksekusi saat mengakses `/all-student-name` dari rata-rata 1022ms menjadi 312ms di *Profiling Intellij* dan dari rata-rata 6747ms menjadi 4720,5ms di JMeter.
- Terdapat pengurangan waktu eksekusi saat mengakses `/highest-gpa` dari rata-rata 325ms menjadi 325ms di *Profiling Intellij* dan dari rata-rata 81,85ms menjadi 80,8ms di JMeter.

Proses pengoptimalan ini menghasilkan peningkatan yang lumayan signifikan dalam waktu eksekusi *endpoint* yang diuji. Baik untuk *Profiling Intellij* atau JMeter sudah menunjukkan pengurangan waktu eksekusi sehingga menghasilkan waktu respons yang lebih cepat untuk tiap *endpoint*.

### Pertanyaan refleksi
**1. What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?** <br>
Tes menggunakan JMeter melibatkan simulasi tindakan pengguna untuk menilai respons aplikasi, fokus pada aspek seperti waktu respons, throughput, dan penggunaan sumber daya. Ini membantu mengidentifikasi area yang perlu perbaikan, meskipun hanya memperhatikan respons secara umum tanpa memahami detail operasi aplikasi. Di sisi lain, dengan IntelliJ Profiler, profil aplikasi secara rinci dianalisis, memungkinkan identifikasi bagian kode yang memakan waktu dan pemahaman lebih mendalam tentang kinerja aplikasi, termasuk pola penggunaan memori dan beban kerja CPU. Informasi yang diperoleh dari profiling memungkinkan optimisasi pada bagian kode yang berdampak signifikan terhadap kinerja aplikasi.

**2. How does the profiling process help you in identifying and understanding the weak points in your application?** <br>
Profiling dapat membantu dalam memahami dan mengenali cara kode beroperasi dalam aplikasi dengan memonitor perilaku saat aplikasi berjalan, termasuk penggunaan CPU, alokasi memori, panggilan fungsi, dan aktivitas thread. Dengan menganalisis data ini, kita bisa menemukan ketidakoptimalan, titik-titik tersendat (bottlenecks), atau penggunaan sumber daya yang berlebihan. Alat-alat profiling memberikan visualisasi dari jalannya aplikasi saat berjalan, yang mempermudah untuk mengidentifikasi bagian kode yang bermasalah serta memungkinkan upaya optimisasi yang terarah.

**3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?** <br>
Benar, IntelliJ Profiler dapat memberikan bantuan yang sangat efektif kepada pengembang dalam menganalisis dan mengenali masalah kinerja dalam kode aplikasi mereka. Sebagai contoh, dalam tutorial dan latihan pada modul 5 ini, kita dapat memperhatikan bahwa beberapa metode memiliki kinerja yang lebih lambat. Dengan kemampuan Profiler untuk menampilkan durasi setiap baris kode, kita dapat dengan mudah mengidentifikasi bagian program yang menjadi penyebab kemacetan atau bottlenecks.

**4. What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?** <br>
Salah satu tantangan utama dalam melakukan pengujian performance testing and profiling adalah interpretasi hasil output dan perbandingannya dengan output sebelumnya. Dalam proses profiling, banyak informasi yang dihasilkan, sehingga diperlukan pencarian yang cermat dan teliti. Selain itu, kita perlu merekam output sebelumnya, misalnya dengan mengambil screenshot, atau merujuk kembali ke profiling sebelumnya. Namun, yang diharapkan adalah kemungkinan untuk membandingkan secara langsung hasil sebelum dan sesudah melakukan optimisasi. Untuk mengatasi tantangan ini, diperlukan kebiasaan dalam menggunakan alat tersebut dan kehati-hatian dalam memperoleh data yang diinginkan.

**5. What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?** <br>
Adanya IntelliJ Profiller ini, kita tidak perlu mengandalkan aplikasi pihak ketiga, dan proses profiling sudah terintegrasi langsung dengan keseluruhan lingkungan pengembangan (IDE). Ini membuat kita lebih mudah dalam mengidentifikasi bagian kode yang menjadi penyebab bottlenecks.

**6. How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?** <br>

Saat menemukan perbedaan hasil antara pengujian kinerja menggunakan JMeter dan profiling dengan IntelliJ Profiler, langkah awalnya adalah memeriksa kembali metode pengujian dan skenario yang digunakan dalam kedua alat tersebut. Perlu juga untuk membandingkan metrik yang diukur oleh keduanya guna mengidentifikasi perbedaan fokus atau ruang lingkup, seperti perbedaan dalam perangkat keras/perangkat lunak yang digunakan.

**7. What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?** <br>
Setelah meninjau hasil dari pengujian kinerja dan pembuatan profil, ada beberapa strategi yang dapat diterapkan untuk meningkatkan kualitas kode aplikasi. Saya akan memulai dengan memeriksa durasi program menggunakan JMeter. Jika saya menemukan waktu eksekusi yang berlebihan, saya akan mengidentifikasi bagian kode yang bertanggung jawab dan melakukan optimalisasi. Penting bagi saya untuk memastikan bahwa perubahan yang saya lakukan tidak mengganggu fungsionalitas aplikasi dengan melakukan perbandingan antara output sebelum dan setelah modifikasi.



