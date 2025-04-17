# Laporan Submission 1 Proyek Machine Learning - Adin Rama Ariyanto Putra

## Domain Proyek

Biaya medis merupakan salah satu aspek penting dalam sistem pelayanan kesehatan yang berdampak langsung pada kesejahteraan masyarakat. Dalam beberapa tahun terakhir, tren biaya medis menunjukkan peningkatan yang signifikan seiring dengan kemajuan teknologi medis, peningkatan harapan hidup, serta perubahan pola hidup masyarakat. Pemahaman mendalam mengenai faktor-faktor yang memengaruhi biaya medis menjadi krusial untuk membantu perencanaan keuangan, pengambilan kebijakan kesehatan, dan pengembangan sistem asuransi yang efisien.

Salah satu pendekatan yang dapat digunakan untuk menganalisis biaya medis adalah melalui pemanfaatan data dan teknik analisis prediktif. Dengan mengkaji faktor-faktor seperti usia, jenis kelamin, kebiasaan merokok, indeks massa tubuh (BMI), dan wilayah geografis, kita dapat mengidentifikasi pola-pola yang berkontribusi terhadap tingginya biaya pengobatan. Analisis ini tidak hanya berguna bagi penyedia layanan kesehatan dan perusahaan asuransi, tetapi juga bagi individu untuk lebih memahami risiko finansial yang mungkin mereka hadapi terkait dengan kondisi kesehatan mereka. Oleh karena itu, penting untuk mengembangkan model prediksi biaya medis yang akurat guna mendukung sistem kesehatan yang lebih terjangkau dan berkelanjutan.

**Penelitian yang membahas topik ini antara lain**:
- Penelitian pertama dilakukan oleh Dewanti Wardhani, seorang mahasiswa Universitas Airlangga. Penelitian berjudul [Analisis Biaya Medis Langsung Pasien BPJS Bronkopneumonia Balita di Rumah Sakit](https://unair.ac.id/analisis-biaya-medis-langsung-pasien-bpjs-bronkopneumonia-balita-di-rumah-sakit) menganalisis biaya medis langsung untuk pasien balita dengan bronkopneumonia yang menggunakan BPJS di sebuah rumah sakit di Surabaya selama periode Januari hingga Maret 2023. Hasilnya menunjukkan bahwa total biaya penanganan mencapai Rp463.267.781, dengan rata-rata biaya per pasien sebesar Rp2.693.417. Komponen biaya terbesar berasal dari penggunaan fasilitas rumah sakit, yang menyumbang 34,87% dari total biaya. Temuan ini menyoroti pentingnya efisiensi dalam penggunaan fasilitas untuk mengendalikan biaya medis.​
- Penelitian kedua dilakukan oleh Mutiara Nurtandhee, seorang mahasiswa Institut Teknologi Sumatera. Penelitian berjudul [Estimasi Biaya Pelayanan Kesehatan sebagai Upaya Pencegahan Defisit Dana Jaminan Sosial untuk Penyakit Gagal Ginjal](https://jurnal-jkn.bpjs-kesehatan.go.id/index.php/jjkn/article/view/104) memproyeksikan peningkatan signifikan dalam biaya pengobatan penyakit gagal ginjal di Indonesia, diperkirakan mencapai antara 7 hingga 10 triliun rupiah pada tahun 2023–2025. Kenaikan ini disebabkan oleh meningkatnya jumlah pasien, terutama yang menjalani hemodialisis. Penulis menyarankan implementasi skema cost-sharing, seperti yang diterapkan di Amerika Serikat, untuk mengendalikan pengeluaran dan mencegah defisit Dana Jaminan Sosial (DJS) BPJS Kesehatan.
- Penelitian ketiga dilakukan oleh mahasiswa Universitas Gadjah Mada, yakni Raymon Simanullang, Tri Murti Andayani, dan Chairun Wiedyaningsih. Penelitian berjudul [Estimasi Biaya Penyakit COVID-19 Rawat Inap di RSUP Dr. Sardjito Yogyakarta: Direct Medical Cost](https://jurnal.ugm.ac.id/majalahfarmaseutik/article/view/83529/38031) menganalisis biaya medis langsung untuk pasien COVID-19 yang dirawat inap di RSUP Dr. Sardjito Yogyakarta selama Juli–September 2021. Dengan sampel 99 pasien, total biaya mencapai sekitar Rp1,9 miliar, dengan rata-rata biaya per pasien sebesar Rp19,36 juta. Komponen biaya terbesar adalah jasa pelayanan medis (53%) dan obat serta bahan medis habis pakai (31,43%). Faktor seperti jenis kelamin, lama rawat inap, dan kelas perawatan memengaruhi total biaya yang dikeluarkan.

## Business Understanding

### Problem Statements

- Dari serangkaian fitur yang ada, fitur apa yang paling berpengaruh terhadap biaya medis perorangan?
- Apakah biaya medis bagi pasien perokok lebih besar daripada pasien yang tidak merokok?
- Berapa biaya medis perorangan yang nantinya ditanggung oleh asuransi kesehatan berdasarkan karakteristik atau fitur tertentu?

### Goals (Tujuan)

- Mengetahui fitur yang paling berkorelasi dengan biaya medis perorangan.
- Mengetahui perbandingan biaya medis bagi pasien perokok dengan yang tidak merokok.
- Membuat model machine learning yang dapat memprediksi biaya medis perorangan seakurat mungkin berdasarkan fitur-fitur yang ada.

### Metodologi

- Dalam studi kasus ini akan melakukan prediksi terhadap biaya medis perorangan yang ditanggung oleh asuransi kesehatan. Seperti yang diketahui bahwasanya biaya merupakan variabel kontinu, sehingga dalam hal ini akan menggunakan teknik regresi. Oleh karena itu, metodologi pada proyek ini adalah: **membangun model regresi dengan biaya medis perorangan sebagai target**.

## Data Understanding

Data yang digunakan pada studi kasus ini adalah [Medical Cost Personal](https://raw.githubusercontent.com/stedy/Machine-Learning-with-R-datasets/master/insurance.csv) yang berasal dari GitHub pembelajaran ML. Pada satudi kasus ini, hanya akan menggunakan dataset ini sehingga tidak perlu menambahkan data lain atau melakukan penggabungan dataset lagi. Selain itu, dataset ini juga cukup bersih sehingga tidak terlalu banyak memerlukan proses data cleaning.

Dataset memiliki 1.338 baris dan 7 buah kolom. Kolom disini terdiri dari fitur numerik dan non-numerik. Fitur numerik terdiri dari *age, bmi,* dan *children*. Sedangkan fitur non-numerik terdiri dari *sex, smoker,* dan *region*. Untuk fitur biaya *(charges)* sendiri merupakan label/target dalam format dollar Amerika.

### Variabel-variabel pada Medical Cost Personal dataset adalah sebagai berikut:
- age : usia seseorang yang ditanggung biaya medisnya oleh asuransi kesehatan.
- sex : jenis kelamin (female, male).
- bmi : Body-Mass-Index.
- children : jumlah anak yang menjadi tanggungan.
- smoker : menunjukkan apakah seorang tersebut merokok atau tidak (yes, no)
- region : asal daerah di US (northeast, southeast, southwest, northwest).
- charges : biaya medis yang perlu dikeluarkan (label/target).

**Tahapan yang dilakukan pada tahap eksplorasi data (EDA)**:
- Mengecek informasi dan deskripsi statistik data.
- Mengecek dan menangani outlier (jika ada).
- Melakukan analisis univariate dan multivariate.
- Melakukan visualisasi selama tahap EDA.

## Data Preparation

- Melakukan one-hot-encoding untuk fitur kategori. Hal ini bertujuan untuk mengubah fitur menjadi numerik agar dapat diproses oleh model machine learning.
- Membagi data menjadi set pelatihan dan pengujian sebelum dilakukan standarisasi. Selain berfungsi untuk proses evaluasi, hal ini juga bertujuan agar tidak terjadi kebocoran data ketika melakukan proses pemodelan.
- Melakukan standarisasi data menggunakan fungsi MinMaxScaler() dari sklearn, agar semua data memiliki rentang yang sama.

## Modeling
Pada bagian ini penulis menggunakan 3 algoritma dan melakukan perbandingan untuk mengetahui algoritma mana yang memberikan performa paling baik. Algoritma yang digunakan antara lain K-Nearest Neighbor, Decision Tree, dan Random Forest.

**Alasan memilih K-Nearest Neighbor**: 
- KNN adalah metode non-parametrik yang sangat baik untuk mendeteksi pola lokal dalam data.
- Cocok untuk dataset yang tidak terlalu besar dan memiliki fitur numerik yang beragam.
- KNN memprediksi nilai target dengan menghitung rata-rata dari nilai k tetangga terdekat, sehingga tidak membuat asumsi tentang distribusi data.
- Dalam konteks prediksi biaya medis, KNN bisa bermanfaat karena memperhitungkan kemiripan pasien (usia, BMI, kebiasaan merokok, dll.) terhadap pasien lain yang sudah diketahui biayanya.

**Alasan memilih Decision Tree**:
- Decision Tree sangat bagus dalam menangani data dengan hubungan non-linear dan kompleks antar fitur.
- Dapat menangani baik fitur numerik maupun kategori secara langsung tanpa perlu encoding yang rumit.
- Mudah diinterpretasikan, sehingga berguna untuk menjelaskan pengaruh setiap fitur terhadap prediksi biaya medis.
- Mampu memodelkan interaksi antar fitur, misalnya kombinasi "smoker = yes" dan "age > 50" mungkin menghasilkan biaya yang sangat tinggi.

**Alasan memilih Random Forest**:
- Random Forest adalah ensemble method yang menggabungkan banyak decision tree, sehingga mengurangi risiko overfitting.
- Memberikan prediksi yang stabil dan akurat dengan memanfaatkan kekuatan dari banyak pohon acak.
- Sangat efektif untuk menangani dataset dengan banyak fitur dan mengurangi noise pada data.
- Dapat memberikan feature importance, yaitu sejauh mana setiap fitur memengaruhi prediksi — berguna untuk analisis biaya medis lebih dalam.

## Evaluation
Pada bagian ini menggunakan 2 metrik evaluasi, yakni Mean Squared Error (MSE) dan Root Mean Squared Error (RMSE). Kedua metrik ini berfungsi untuk menilai seberapa baik model dapat memprediksi data latih berdasarkan nilai error.

**Mean Squared Error (MSE)**: Digunakan untuk menghitung rata-rata kesalahan kuadrat dalam prediksi.

**Root Mean Squared Error (RMSE)**: Digunakan untuk menghitung akar kuadrat dari MSE.
