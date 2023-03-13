# Capstone-Project-Module-3

# Business Problem Understanding
Sebuah perusahaan yang bergerak di bidang Konsultan Data diminta oleh perusahaan telekomunikasi untuk menganalisa data mereka. Perusahaan telekomunikasi tersebut ingin mengetahui pelanggan mana saja yang akan berpindah ke telekomunikasi pesaing / perusahaan lain (Churn). Tujuan mereka adalah agar perusahaan dapat mengurangi tingkat pelanggan berpindah ke perusahaan lain serta mempertahankan pelanggan dengan membuat pelanggan loyal dan juga mengurangi cost dimana mencari pelanggan baru membutuhkan biaya yang lebih besar dibandingkan memberikan promo (Retention).

Target :

0 : Pelanggan tidak berhenti menggunakan layanan

1 : Pelanggan berhenti menggunakan layanan

Pada dataset yang diberikan perusahaan, berisikan data yang mewakili profil pelanggan yang telah meninggalkan perusahaan telekomunikasi. Churn di telekomunikasi dan layanan berbasis langganan lainnya berarti situasi ketika pelanggan meninggalkan penyedia layanan.

## Problem Statement :

Proses untuk mendapatkan pelanggan baru 5 kali lebih mahal daripada mempertahankan pelanggan yang sudah ada, dan membuat pelanggan baru menjadi loyal juga 16 kali lebih mahal. Perusahaan memerlukan strategi untuk mengurangi atau bahkan menghentikan churn (kehilangan pelanggan) dan meretensi pelanggan yang sudah ada, karena pelanggan merupakan sumber utama revenue perusahaan.

berdasarkan informasi yang didapatkan, rata-rata biaya customer acquisition cost untuk industri telekomunikasi adalah sekitar $315 per pelanggan baru.(sumber : https://www.revechat.com/blog/customer-acquisition-cost/)

Perusahaan dapat memberikan insentif seperti diskon atau promo seperti paket yang menarik kepada pelanggan mereka untuk mempertahankan pelanggan. Namun hal ini akan sia sia jika kita memberikan insentif ini kepada pelanggan yang akan churn. sama halnya jika insentif juga diberikan secara merata maka perusahaan juga akan mengeluarkan banyak cost yang tidak efektif dan mengurangi pendapatan mereka.

Jika perusahaan sudah mengeluarkan biaya besar untuk marketing mereka untuk mendapatkan pelanggan baru namun ternyata pelanggan baru itu churn maka perusahaan juga akan mengeluarkan lebih banyak uang dibandingkan memberikan insentif ke pelanggan mereka.

## Goals :

Maka berdasarkan permasalahan tersebut, perusahaan ingin memiliki kemampuan untuk memprediksi kemungkinan seorang pelanggan akan/ingin berhenti dan meninggalkan layanan mereka atau tidak, sehingga dapat fokus pada pelanggan yang bersedia untuk tetap menggunakan layanan perusahaan tersebut.

Dan juga, perusahaan ingin mengetahui faktor atau variabel apa yang membuat seorang pelanggan tetap setia dengan mereka atau tidak, sehingga mereka dapat membuat rencana yang lebih baik dalam mendekati kandidat pelanggan potensial.

## Analytic Approach :

Jadi yang akan kita lakukan adalah menganalisis data untuk menemukan pola yang membedakan pelanggan yang akan tetap menggunakan layanan perusahaan dan yang akan meninggalkan / berhenti.

Kemudian kita akan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas seorang pelanggan akan/ingin tetap berlangganan dengan perusahaan tersebut atau meninggalkannya.

## Metric Evaluation

Type 1 error : False Positive  
Konsekuensi: kehilangan pelanggan potensial dan juga insentif yang dikeluarkan.

Type 2 error : False Negative  
Konsekuensi: kehilangan pelanggan dan juga kerugian akan segala biaya yang baik yang diterima ataupun yang dikeluarkan untuk pelanggan, selain itu juga perusahaan harus mengeluarkan biaya lagi untuk mencari pelanggan baru. 

biaya untuk mencari pelanggan baru = $315
biaya untuk memberikan retensi = 1/5 * $315 = $63

sumber : https://www.outboundengine.com/blog/customer-retention-marketing-vs-customer-acquisition-marketing/

Berdasarkan konsekuensinya, maka sebisa mungkin yang akan kita lakukan adalah membuat model yang dapat mengurangi cost untuk pelanggan yang tidak setia dari perusahaan tersebut, tetapi tanpa membuat menjadi kurangnya pelanggan setia perusahaan. Jadi kita ingin sebanyak mungkin prediksi kelas negatif yang benar, dengan sesedikit mungkin prediksi false positive. Jadi nanti metric utama yang akan kita gunakan adalah F2 Score karena recall kita anggap dua kali lebih penting daripada precision.

## Conclusion

Berdasarkan nilai recall pada classification report dari model yang kita pilih, kita dapat menyimpulkan /mengambil konklusi bahwa dengan menggunakan model yang dibuat, perusahaan dapat mengurangi 64% pelanggan yang tidak churn untuk tidak kita berikan insentif sebagai bagian untuk mempertahankan pelanggan. Selain itu, perusahaan bisa mendapatkan 89% pelanggan yang akan churn untuk lebih kita maksimalkan dalam memberikan insentif untuk mencegah terjadinya churn.

Model kita ini memiliki ketepatan prediksi pelanggan yang akan churn sebesar 47%, jadi setiap model kita memprediksi bahwa seorang pelanggan yang akan churn adalah 47%. Sehingga masih akan ada pelanggan yang sebetulnya tidak akan churn namun diprediksi akan churn sebesar 39% (berdasarkan nilai recall - nilai precision) dari keseluruhan pelanggan yang tidak churn.

## Recommendation

ada beberapa rekomendasi yang dapat dilakukan untuk mengembangkan model agar lebih baik, seperti:
1. membuat kebijakan baru yang mendorong pelanggan untuk tetap loyal dengan perusahaan seperti memberikan insentif atau reward yang menarik bagi pelanggan untuk beralih dari Contract Month - to - Month ke contract satu tahun atau dua tahun.
2. Menambahkan fitur atau atribut baru yang kemungkinan bisa berhubungan dengan ketertarikan pelanggan, seperti menambahkan layanan tv kabel, bonus tambahan seperti jika sudah berlangganan Fiber Optik maka secara gratis mendapatkan device protection, pelayanan Tech support kepada seluruh pelanggan, dll.
3. Mencoba algorithm ML yang lain dan juga mencoba hyperparameter tuning kembali, dapat dicoba seperti menggunakan teknik oversampling yang berbeda juga selain Random Over Sampling, seperti SMOTENC, dll. 
4. Menganalisa data-data yang model kita masih salah tebak untuk mengetahui alasannya dan karakteristiknya bagaimana.
