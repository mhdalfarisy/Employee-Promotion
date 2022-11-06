

## PROJECT : # PREDICT EMPLOYEE PROMOTION

![a1](https://github.com/mhdalfarisy/mhdalfarisy/blob/main/advance-career.jpg)

## Table of Contents

- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Metric](#metric)
- [Analytical Approach](#analytical-approach)
- [Definisi Kolom](#definisi-kolom)
- [Data Analyst dan Machine Learning](#data-analyst-dan-machine-learning)
  - [Kesimpulan Data Analyst dan Machine Learning](#kesimpulan-data-analyst-dan-machine-learning)
  - [Saran Data Analyst dan Machine Learning](#saran-data-analyst-dan-machine-learning)
- [OTHERS PROJECT](#others-project)

### **Problem Statement**

Sebuah perusahaan level multinasional yang memiliki jumlah pegawai dalam skala besar, ingin melebarkan usaha bisnisnya dengan membuka cabang di beberapa lokasi yang baru. Oleh karena itu, perusahaan yang melihat pegawainya sebagai aset (*talent*) ingin melakukan proses promosi kepada seluruh pegawainya yang nantinya akan menduduki jabatan satu tingkat di atas jabatan sebelumnya sesuai dengan departmennya masing-masing. Proses penentuan promosi jabatan akan diumumkan setelah pegawai melewati periode pelatihan dan evaluasi. Program pelatihan dan evaluasi ini bertujuan untuk pengembangan kemampuan pegawai. Dan apabila pegawai pada akhirnya dipromosikan, budaya perusahaan tetap terjaga di tempat yang baru.

Proses pemilihan kandidat pegawai yang akan dipromosi:
1. Perusahaan mengidentifikasi data pegawai berdasarkan rekomendasi dan kinerja.
2. Pegawai yang terpilih akan menjalani program pelatihan dan evaluasi secara terpisah untuk masing-masing departmennya. Program ini berlandaskan pada kemampuan yang dibutuhkan dari setiap departemen.
3. Di akhir program, berdasarkan berbagai faktor seperti kinerja pelatihan, dll., seorang pegawai akan menjadi kandidat untuk dipromosikan.

### **Objectives**

Maka berdasarkan permasalahan tersebut, perusahaan ingin memiliki kemampuan untuk memprediksi kemungkinan seorang pegawai yang akan dipromosikan pada perusahaan tersebut atau tidak, sehingga perusahaan dapat memfokuskan untuk mempersiapkan test assesment untuk kandidat pegawai yang direkomendasi oleh model dan proses promosi pegawai yang akan diumumkan pada tahap akhir. Limitasi model yang akan digunakan untuk memprediksi promosi pegawai (di bawah C-Level).
Dan juga, perusahaan ingin mengetahui faktor apa yang membuat seorang pegawai dipromosi atau tidak, sehingga perusahaan dapat membuat rencana/program yang lebih baik dalam mempromosikan pegawai potensial.

### **Metric**

0 : Tidak Promosi Jabatan

1 : Promosi Jabatan

Type 1 error : False Positive  
Konsekuensi : Sia-sianya biaya, waktu dan tenaga test assesment dikarenakan karyawan yang mendapatkan promosi bukan dari karyawan yang sangat berpotensi.

Type 2 error : False Negative  
Konsekuensi: Karyawan yang berpotensi di prediksi tidak mendapatkan promosi.

Berdasarkan konsekuensinya, maka sebisa mungkin yang akan kita lakukan adalah membuat model yang efisien yang dapat mengurangi waktu dan tenaga. Namun juga membuat model tanpa membuat hilangnya pegawai potensial yang akan memegang tanggung jawab lebih besar dari sebelumnya. Maka dari itu, nilai recall dan precision berdasarkan kelas positivenya perlu untuk diseimbangkan. Sehingga metric utama yang akan digunakan adalah `f1-score`.

### **Analytical Approach**

Kami akan menggunakan pendekatan berbasis data (*data-driven*) untuk memprediksi apakah pegawai akan direkomendasi untuk promosi atau tidak. Prediksi kami berdasarkan pada informasi terkait demografi, pendidikan terakhir, kinerja, dan fitur lainnya yang ada pada pegawai.

Selanjutnya, kami akan melakukan analisis data untuk menemukan pola yang membedakan pegawai yang akan dipromosikan dan tidak dipromosikan jabatannya.

Kemudian, kami akan mengembangkan model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas seorang pegawai yang akan dipromosikan di perusahaan tersebut atau tidak.

### **Definisi Kolom**
| **Nama Kolom** |**Keterangan Kolom** |
| --- | --- |
|CustomerID| ID unik yang mengidentifikasi setiap pelanggan|
|Employee_id | Unique ID for employee|
|Department | Department of employee|
|Region | Regio R of employment (unordered)|
|Education | Edu cationELevel|
|Gender | Gender of Employee|
|Recruitment_channel | Channel of recruitment for employee
|No_ of_ trainings | No of other trainings completed in previous year on soft skills, technical skills etc|
|Age | Age of Employee
|Previous_ year_ rating | Employee Rating for the previous year|
|Length_ of_ service | Length of service in years|
|Awards_ won? | If awards won during previous year then 1 else 0|
|Avg_ training_ score | Average score in current training evaluations|
|Is_promoted|(Target) Recommended for promotion|

## Data Analyst dan Machine Learning

### **Kesimpulan Data Analyst dan Machine Learning**

1. 1. Total karyawan yang akan di promosikan berjumlah 4.232 atau setara dengan 9% dari total keseluruhan karyawan.
2. Karyawan paling banyak berasal dari departement sales dan marketing serta dari departement ini banyak karyawan yang mendapatkan promosi.
3. Banyak karyawan yang dipromosikan dari rating terbaik yaitu rating 5 yang paling banyak berasal dari departement Operations dan department Sales & marketing.
4. Karyawan yang mendapatkan promosi berasal dari gelar sarjana / Bachelor's
5. Paling banyak karyawan laki-laki yang mendapatkan promosi sebanyak 6% dari total keseluruhan karyawan yang di promosi dan yang tidak dapat promosi.
6. Umur paling banyak karyawan yang mendapatkan promosi berasal dari umur 29 tahun sampai dengan 34 tahun.
7. Karyawan yang dapat promosi paling banyak yang tidak pernah mendapatkan penghargaan sebanyak 8% dari pada karyawan yang mendapatkan penghargaan hanya 1%.
8. Karyawan yang memiliki skor training `exellent` paling banyak mendapatkan promosi dari keseluruhan karyawan yang di promosikan.
9. Dengan menggunakan model Machine Learning kita dapat melakukan penghematan waktu dengan menyaring terlebih dahulu pegawai yang akan direkomendasikan untuk dipromosi. hal ini dapat dilihat dari classification report dengan nilai precision sebesar 0.90 pada class positive. yang berarti model memiliki ketepatan sebesar 81% dalam menyaring pegawai yang sebenarnya akan dipromosi. Dengan nilai recall sebesar 0.99 pada kelas negative, artinya model dapat dapat memprediksi hingga 99% untuk pegawai yang tidak akan dipromosi dari keseluruhan pegawai yang tebakannnya benar, dengan ketepatan (precision) prediksinya sebesar 0.94. Ini berarti model dapat menebak pegawai mana yang tidak untuk dipromosikan dengan ketepatan mencapai 94%. Artinya dari 100 pegawai yang tidak dipromosikan, model dapat menebak 94 pegawai. Dengan nilai recall pada kelas positive yang hanya sebesar 0.36. Model hanya dapat menebak sebesar 36% dari keseluruhan pegawai yang benar tebakannya. Ini mengakibatkan konsekuensi semakin sedikitnya pegawai potensial yang akan direkomendasikan.
10. Tanpa menggunakan model, dengan asumsi pengecekan dokumen seorang pegawai berkisar 5 menit. Maka apabila terdapat 1000 pegawai yang akan diperiksa secara keseluruhan dengan cara manual, dibutuhkan waktu selama 5000 menit. Sedangkan dengan menggunakan model, kita dapat menyaring dari 1000 pegawai. Kita akan mendapatkan, ketepatan rata-rata hingga 92% (macro avg precision) dalam menyaring pegawai. Artinya model dapat menghemat waktu hingga 92% (4.600 menit) dari total keseluruhan. Dengan menggunakan model, setidaknya model dapat mengklasifikasikan hingga 36% (recall positive) pegawai akan rekomendasikan untuk promosi dari total pegawai yang telah diprediksi secara benar. 

## **Saran Data Analyst dan Machine Learning**

- **Proses Identifikasi** : Proses identifikasi untuk karyawan yang akan di lakukan training untuk promosi jabatan dapat dilakukan pada semua department yang ada di perusahaan dengan persyaratan rating KPI Karyawan masuk dalam skor 3 / Good.
-  **Proses Latihan dan Evaluasi** : Saat proses training perusahaan dapat memfokuskan / menyaring karyawan yang mendapatkan skor training di atas 60 atau masuk dalam kategori excellent.
-  **Prediksi Karyawan DiPromosi** : Setelah karyawan dilakukan identifikasi dan latihan serta evaluasi terhadap skor karyawan maka Perusahaan dapat menggunakan mesin learning untuk melakukan prediksi karyawan mana saja yang akan di promosikan dan karyawan yang belum bisa di promosikan. Pada hal ini yang menjadi fokus penilaian dan pertimbangan pada saat menggunakan mechine learning ada pada Skor `KPI Karyawan` **,** `Karyawan dipromosikan sesuai dengan Departement bekerja` **,** `Pendidikan minimal sarjana / bachelor` dan `Skor Training`..

<br>

# **OTHERS PROJECT**

<table>
<tbody>
 <tr>

<h1 align="left">Data Analyst</h1>
  
<td align="left" width="50%">
<span><b><Left>E-Commers Pakistan</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/EDA---Pakistan-s-Larges-Ecommers" target="_blank">
<img height=250px src="https://github.com/mhdalfarisy/EDA---Pakistan-s-Larges-Ecommers/blob/main/Images/62253a402fccf.jpg"> 
</td>
<!-- <tr> -->
<td align="left" width="50%">
<span><b><Left>Employee Attrition</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/Employee-Analysis-Attrition-Report" target="_blank">
<img height=250px src="https://github.com/mhdalfarisy/Employee-Analysis-Attrition-Report/blob/main/Aset/Reasons-Attrition1_large%20(1).jpg"> 
</td>
</tbody>
</table>
 <tr>
<br>
<table>
<tbody>
 <tr>
 
<h1 align="left">Machine Learning - Supervised</h1>

<td align="left" width="20%">
<span><b><left>California House Price</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/California-House-Price-Prediction-Using-Machine-Learning" target="_blank">
<img height=150px src="https://github.com/mhdalfarisy/California-House-Price-Prediction-Using-Machine-Learning/blob/main/gambar/CA-Sales-Home-Volume.png"> 
</td>

<td align="left" width="20%">
<span><b><left>Credit Card Fraud</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/Credit-Card-Fraud-Prediction" target="_blank">
<img height=150px src="https://github.com/mhdalfarisy/Credit-Card-Fraud-Prediction/blob/main/68747470733a2f2f65787465726e616c2d636f6e74656e742e6475636b6475636b676f2e636f6d2f69752f3f753d687474707325334125324625324661692d6a6f75726e65792e636f6d25324677702d636f6e74656e7425324675706c6f61647325324632303139253246.jfif"> 
</td>

<!-- <tr> -->
<td align="left" width="20%">
<span><b><left>Telco Customer Churn</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/Employee-Promotion" target="_blank">
<img height=150px src="https://github.com/mhdalfarisy/mhdalfarisy/blob/main/7-Strategies-To-Reduce-Customer-Churn-Rate.png"> 
</td>

<!-- <tr> -->
<td align="left" width="20%">
<span><b><left>Employee Promotion</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/Telco-Customer-Churn-Predict" target="_blank">
<img height=150px src="https://github.com/mhdalfarisy/mhdalfarisy/blob/main/advance-career.jpg"> 
</td>

</tbody>
</table>
 <tr>
  
<h1 align="left">Machine Learning - Unsupervised</h1>  

<table>
<tbody>
 <tr>  
  
<!-- <tr> -->
<td align="left" width="25%">
<span><b><left>Segmentation Customer Mall</center></b></span> 
<code><a href="https://github.com/mhdalfarisy/Segmentation-Customer-Mall" target="_blank">
<img height=200px src="https://github.com/mhdalfarisy/Segmentation-Customer-Mall/blob/main/2.-Customer-Segmentation.jpg"> 
</td>
 
</tbody>
</table>
 <tr>
  
<br>

<table>
<tbody>
 <tr>

<h1 align="left">Data Visualization</h1>
  
<td align="left" width="30%">
<span><b><Left>E-Commers Pakistan</center></b></span> 
<code><a href="https://public.tableau.com/app/profile/muhammad.al.farisy6147/viz/ProjectE-CommersPakistanDashboard/Dashboard1" target="_blank">
<img height=200px src="https://github.com/mhdalfarisy/mhdalfarisy/blob/main/Pakistan%20Visualisasi.png"> 
</td>
 
<!-- <tr> -->
<td align="left" width="30%">
<span><b><left>Employee Attrition Report</center></b></span> 
<code><a href="https://public.tableau.com/app/profile/muhammad.al.farisy6147/viz/ProjectHumanResourceAttritionAnalysisDashboard/Dashboard1" target="_blank">
<img height=200px src="https://github.com/mhdalfarisy/mhdalfarisy/blob/main/HRD%20VIsualisasi.png"> 
</td>
 
<!-- <tr> -->
<td align="left" width="25%">
<span><b><left>Telco Customer Churn</center></b></span> 
<code><a href="https://public.tableau.com/app/profile/muhammad.al.farisy6147/viz/CustomerChunVisualization/Dashboard2?publish=yes" target="_blank">
<img height=200px src="https://github.com/mhdalfarisy/mhdalfarisy/blob/main/Telco%20Customer%20%2022.png"> 
</td>
 
</tbody>
</table>
 <tr>



<br>
<!-- <h1 align="center">Others Data Visualization Report</h1> -->
<td align="left" width="30%">
<span><b><left>Others Data Visualization Report (Click Picture) :   </left></b></span> 
<code><a href="https://public.tableau.com/app/profile/muhammad.al.farisy6147" target="_blank"><img height="100" src="https://github.com/mhdalfarisy/mhdalfarisy/blob/main/tol_devices_optimized.png"></a></code>
<br>
<br>
<br>
 
**💬 Ask me about anything, I'll be happy to help!** <br>
**💬 My inbox is always open, Contact me**
<br>
<br> 
  </a>
  <a href="mailto:m.alfarisy797@gmail.com">
    <img align="left" alt="Muhammad Al-farisy | Gmail" width="26px" src="https://cdn.worldvectorlogo.com/logos/official-gmail-icon-2020-.svg" />
  </a>
  <a href="https://www.linkedin.com/in/m-alfarisy97/">
    <img align="left" alt="Muhammad Al-farisy | LinkedIN" width="26px" src="https://cdn.worldvectorlogo.com/logos/linkedin-icon-2.svg" />    
  </a>
<br>
<br>


| <a href="https://github.com/mhdalfarisy"><img align="center" src="https://github-readme-stats.vercel.app/api?username=mhdalfarisy&show_icons=true&include_all_commits=true&theme=buefy&hide_border=true" alt="Anurag's github stats" /></a> | <a href="https://github.com/mhdalfarisy/github-readme-stats"><img align="center" src="https://github-readme-stats.vercel.app/api/top-langs/?username=mhdalfarisy&layout=compact&theme=buefy&hide_border=true" /></a> |
| ------------- | ------------- |
 
<table>
<tbody>
 <tr>
 
<h1 align="left">THANKS YOU !!! </h1>

<td align="center" width="30%">
<img height=300px src="https://media.giphy.com/media/dyzew7Py7bnW9DiJJj/giphy.gif"> 
</td>  
  
<!-- <td align="center" width="30%">
<img height=300px src="https://media.giphy.com/media/7c8QeB0VMddFOuu4iR/giphy.gif"> 
</td>
  
<td align="right" width="30%">
<img height=300px src="https://media.giphy.com/media/gutZ5Pm6Xl62eIf5RZ/giphy.gif"> 
</td>    -->

⭐️ From [Muhammad Al-farisy](https://github.com/mhdalfarisy)
