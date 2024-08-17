# Proyek Pengembangan dan Pengoperasian Sistem Machine Learning Pipeline

![dataset-cover sms](https://github.com/user-attachments/assets/3b403244-2cc5-49d6-9e0d-5f0006412725)


| | Deskripsi |
| ----------- | ----------- |
| Dataset | [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) |
| Masalah | Masalah yang dihadapi dalam dataset ini adalah bagaimana membedakan pesan SMS yang merupakan spam atau bukan spam. Seiring dengan bertambanhnya jumlah penduduk dari waktu kewaktu, penggunaan sms sebagai media bertukar informasi juga turut berkembang. Pertukaran informasi dapat dilakukan secara instan. Namun disisi lain, penggunaan sms juga rentan dengan spam. Spam menjadi gangguan yang cukup mengganggu bagi pengguna. Oleh karena itu, diperlukan sebuah model yang bisa dengan tepat mengenali dan membedakan mana pesan berupa spam dan mana pesan yang bukan spam. Adapun tantangan dalam pengembangan ini adalah pesan SMS biasanya pendek dan sering menggunakan bahasa sehari-hari, singkatan, atau bahkan slang, yang membuat proses ini menjadi lebih sulit. |
| Solusi machine learning | Solusi yang akan dibangun adalah model klasifikasi menggunakan neural network yang dapat membantu pengguna untuk mengetahui apakah suatu pesan adalah spam atau bukan. |
| Metode pengolahan | Proses pemrosesan data dimulai dengan mengubah teks pesan SMS menjadi huruf kecil menggunakan fungsi tf.strings.lower untuk memastikan konsistensi. Selain itu, tanda baca dihapus dengan metode lower_and_strip_punctuation dari TextVectorization. Label juga diubah menjadi format numerik, di mana pesan ham diberi label 0 dan pesan spam diberi label 1 dengan tf.cast. Metode ini memastikan bahwa data yang digunakan untuk pelatihan dan inferensi konsisten dan siap untuk pemrosesan lebih lanjut. |
| Arsitektur model | Model ini dirancang dengan beberapa lapisan utama. Pertama, lapisan input menerima data teks yang telah diproses. Teks tersebut kemudian diubah menjadi token numerik menggunakan TextVectorization. Selanjutnya, token tersebut diubah menjadi representasi vektor dengan lapisan embedding. Untuk mereduksi dimensi dari vektor embedding, digunakan lapisan GlobalAveragePooling1D. Model ini melanjutkan dengan beberapa lapisan Dense dengan fungsi aktivasi ReLU, diakhiri dengan lapisan Dense terakhir yang menggunakan fungsi aktivasi sigmoid untuk menghasilkan probabilitas klasifikasi biner. Model ini kemudian dikompilasi dengan optimizer Adam dan metrik akurasi biner, siap untuk pelatihan dengan data yang telah diproses. |
| Metrik evaluasi | Metrik yang digunakan meliputi Area Under Curve (AUC) untuk menilai area di bawah kurva ROC, False Positive untuk menghitung kesalahan klasifikasi data negatif sebagai positif, False Negative untuk menghitung kesalahan klasifikasi data positif sebagai negatif, True Positive untuk mengukur klasifikasi positif yang benar, True Negative untuk mengukur klasifikasi negatif yang benar, dan Binary Accuracy untuk mengukur proporsi prediksi yang benar dalam masalah klasifikasi biner. |
| Performa model | Model menunjukkan kinerja yang sangat baik dengan metrik berikut: AUC sebesar 0.96755, Binary Accuracy sebesar 0.98225, dan jumlah contoh sebanyak 1.127. Model mencatat 16 False Negatives, 4 False Positives, dan nilai Loss sebesar 0.10437. Selain itu, model berhasil mengidentifikasi 977 True Negatives dan 130 True Positives. Hasil ini menunjukkan bahwa model memiliki akurasi dan kemampuan prediksi yang sangat tinggi dalam membedakan antara pesan spam dan non-spam. |

# Sekilas Mengenai TensorFlow Extended (TFX)

Sebuah pipeline machine learning biasanya dimulai dengan pengumpulan data pelatihan baru dan diakhiri dengan pengumpulan umpan balik mengenai kinerja model. Pipeline ini mencakup beberapa langkah tambahan, seperti preprocessing data, pelatihan model, analisis model, dan penerapan model.

Pipeline machine learning terdiri dari beberapa tahapan yang saling terkait, sehingga harus dilakukan dalam urutan yang tepat. Untuk mengatur keseluruhan proses ini, diperlukan alat yang dikenal sebagai Pipeline orchestration. Pipeline orchestration akan mengatur alur kerja berdasarkan dependensi tugas dalam grafik pipeline.

![tfx pipelines](https://github.com/user-attachments/assets/bbd40174-a75b-4391-a8b8-d26d0440ed3b)

TensorFlow Extended (TFX) adalah alat yang memungkinkan Anda untuk membangun pipeline machine learning secara menyeluruh. TFX menyediakan berbagai pustaka dan komponen (TFXComponents) yang mendukung pembangunan pipeline machine learning. Pipeline yang dibangun dengan TFX sering disebut sebagai pipeline TFX.


# Pengembangan Proyek Menggunakan TensorFlow Extended (TFX) untuk Membuat Machine Learning Pipeline
Machine learning pipeline yang memuat seluruh komponen sebagai berikut:
- ExampleGen
- StatisticGen
- SchemaGen
- ExampleValidator
- Transform
- Trainer
- Resolver
- Evaluator
- Pusher

# Menjalankan dengan docker

Membuat docker image 

```bash
docker build -t spam-detection-tf-serving .
```

Menjelankan docker image dan menentukan port. Ingat bahwa di dalam docker container TF Serving menggunakan port 8501.

```bash
docker run -p 8080:8501 spam-detection-tf-serving
```
