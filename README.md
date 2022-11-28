# House-Price-Prediction

# Businesss Problem Understanding
## Context
Bank ABC merupakan bank dengan fokus kredit pada kredit multiguna dengan pinjaman dengan agunan properti atau rumah tinggal. Dimana rasio dari pinjaman yang diberikan oleh bank 80% dari nilai agunan atau bangunan ini. Untuk menilai properti atau bangunan yang akan dijaminkan ke bank perlu dilakukan penilaian baik dari eksternal maupun internal. Penilaian ini memakan waktu yang tidak sebentar, karena harus dilakukan secara hati-hati dan detail. Meskipun tim penilai di sisi eksternal ditunjuk langsung oleh bank pemberi kredit, namun tidak menutup kemungkinan hasil yang dihasilkan bisa bias atau tidak sesuai dengan taksiran. Dari penilai internal juga sangat memungkinkan lamanya waktu penilaian jika jaminan atau agunan yang diajukan sangat banyak. Jika penilaian yang dilakukan terlalu tinggi maka ini akan merugikan pihak perbankan dikemudian hari jika terjadi kredit macet. Sebaliknya jika penilaian terlalu murah maka nasabah enggan mengambil kredit pada bank kami. 

## Problem Statement 
Salah satu yang menjadi masalah dalam pemberian kredit adalah efisiensi dan efektifitas dalam penilaian atau penaksiran nilai agunan berupa rumah sebagai ukuran pemberian kredit yang bisa diberikan kepada nasabah. Pemecahan masalah ini merupakan menjadi masalah yang harus diselesaikan oleh departemen kredit guna meningkatkan efisiensi dan efektifitas dalam operasinal bisnis, hal ini ingin dicapai guna memberikan customer satisfaction terkait pelayanan pemberian kredit kepada nasabah. 

Banyaknya jenis, spesifikasi maupun lokasi rumah tinggal yang diajukan oleh nasabah, membuat harga taksiran juga sangat bervariatif. Dengan banyaknya perbedaan dari masing-masing agunan, sangat penting bagi bank untuk menilai berapa harga pasaran atau taksiran yang diajukan sebagai agunan, mengingat pemberian kredit atau plafond sangat bergantung dengan nilai agunan yang diberikan. Kecepatan dalam penaksiran inilah yang ingin dicapai oleh departement kredit untuk meningkatkan efisiensi dan efektifitas dalam pelayanan. Semakin cepat kredit diberikan kepada nasabah maka semakin cepat juga perusahaan mendapatkan profit dari bunga pinjaman tersebut. 

## Goals
Goals yang ingin dicapai dengan dibuatnya predicting tools ini jelas ingin mempercepat waktu pemberian kredit serta mengurangi bias pada tim penilai internal. Prediksi harga yang dibuat akan mengikuti standar yang telah ditetapkan oleh bank. Hal ini bertujuan untuk memudahkan tim internal dalam pengambilan keputusan. 

## Analytics Approach

Hal yang perlu dilakukan adalah dengan melakukan pendekatan dalam membuat model yang dapat memprediksi harga secara akurat dengan memerhatikan faktor-faktor(fitur) yang dapat memengaruhi harga rumah. Penentuan fitur juga memerhatikan korelasi dari fitur itu sendiri kita bisa memlihat fitur atau faktor apa saja yang dapat memengaruhi harga rumah tersebut. Model inilah yang dapat digunakan untuk membantu mempercepat waktu pemberian kredit pada Bank ABC.   

## Metric Evaluation
Pada model yang dibuat nantinya akan menggunakan beberapa metrik evaluasi antara lain RMSE, MAE dan MAPE. 

**RMSE** adalah  metode pengukuran dengan mengukur perbedaan nilai dari prediksi sebuah model sebagai estimasi atas nilai yang diobservasi. Nilai RMSE didapat dari akar kuadrat Mean Square Error. 

**MAE** adalah rata-rata nilai absolut dari error, sedangkan 

**MAPE** adalah rata-rata persentase error yang dihasilkan oleh model. 

Ketiganya digunakan untuk melihat seberapa baik model dapat memprediksi data yang belum pernah dilihat atau data test. Semakin kecil nilai ketiganya, artinya model semakin akurat dalam memprediksi target atau dependent variable sesuai dengan feature yang telah digunakan.

Penggunaan **RMSE** untuk menilai akurasi model prediksi, apakah model prediksi tersebut sesuai atau tidak.

Penggunaan **MAE** dan **MAPE** lebih mudah untuk di interpretasi, dimana hasil erorr hanya akan dimutlakan untuk MAE dan untuk MAPE akan dibagi dengan data aktual. Untuk MAPE sendiri lebih fair digunakan dalam nominal rupiah karena yang dihitung nantinya adalah prosentase.


# Conclusion
Kesimpulan dari pemodelan yang telah dilakukan, feature yang paling berpengaruh adalah `ocean_proximity(INLAND)` dan `median_income`. Hal ini juga bisa di lihat dari EDA ada corelation matrix bahwa median income punya korelasi yang tinggi terharap median_house_value. 
Metrik yang digunakan dalam model untuk melihat seberapa akurat model dalam memprediksi harga adalah dengan RMSE, MAE & MAPE. Ketika kita melihat nilai MAPE yang sudah dilakukan tuning, dihasilkan angka sebesar 16,8% persen. Berarti ketika kita memprediksi harga sebuah rumah pada rentang data yang telah ditentukan, maka prediksi harga akan meleset lebih atau kurang dari 16,8%. Nilai ini dianggap wajar ketika kita akan memprediksi harga rumah dengan nilai tinggi, penggunaan MAPE juga lebih fair karena menghitung presentase bukan nilai mutlak. 

Namun, tidak menutup kemungkinan kemungkinan ketika model akan memprediksi dengan tidak akurat dan meleset jauh dari nilai aktual, karena bisa terjadi bisa pada model karena terbatasnya fitur yang digunakan. Melakukan prediksi diluar limitasi yang telah ditentukan juga memungkinkan model akan memprediksi dengan tidak akurat. 

#  Recommendation 

Untuk mengukur seberapa efektif pengaplikasian model pada masalah bisnis, kita perlu melakukan A/B testing pada kasus ini, untuk melihat bagaimana kinerja divisi kredit atau seberapa cepat pemberian kredit diberikan pada waktu tertentu sebelum menggunakan model dengan sesudah menggunakan model.

Rekomendasi yang dapat diberikan dalam pembuatan model kedepannya adalah:
1. Dapat menambah fitur-fitur yang memiliki hubungan atau korelasi yang kuat dengan harga rumah. Seperti Akses jalan(lebar jalan), luas tanah, luas bangunan, nilai pajak tanah dan bangunan, daya listrik. 
2. Perhatikan juga fitur-fitur yang memiliki hubungan dengan lingkungan seperti seberapa dekat dengan sekolah, pasar, pelayanan kesehatan, taman kota, dan lain-lain. Karena rumah dengan akses yang lebih mudah serta dekat dengan tempat-tempat strategis akan memiliki nilai yang lebih tinggi. 
3. Membedakan rumah-rumah yang masuk dalam cluster(perumahan) dengan yang tidak. 
4. Update dan tambah dengan data-data yang baru dan relevan dengan daerah tempat kantor melakukan operasional, penambahan data baru juga bisa diikuti dengan percobaan pada model-model lain yang lebih bisa mengeneralisasi data. 
5. Mungkin jika diperlukan bisa dibuat model lanjutan yang berkaitan dengan berapa jumlah plafond atau kredit yang dapat diterima oleh nasabah. 
