# Submission 1: SMS Spam Detection
Nama: San Antonio Limbong

Username dicoding: san-limbong

| | Deskripsi |
| ----------- | ----------- |
| Dataset | [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) |
| Masalah | Masalah yang dihadapi dalam dataset ini adalah bagaimana membedakan pesan SMS yang merupakan spam atau bukan spam. Seiring dengan bertambanhnya jumlah penduduk dari waktu kewaktu, penggunaan sms sebagai media bertukar informasi juga turut berkembang. Pertukaran informasi dapat dilakukan secara instan. Namun disisi lain, penggunaan sms juga rentan dengan spam. Spam menjadi gangguan yang cukup mengganggu bagi pengguna. Oleh karena itu, diperlukan sebuah model yang bisa dengan tepat mengenali dan membedakan mana pesan berupa spam dan mana pesan yang bukan spam. Adapun tantangan dalam pengembangan ini adalah pesan SMS biasanya pendek dan sering menggunakan bahasa sehari-hari, singkatan, atau bahkan slang, yang membuat proses ini menjadi lebih sulit. |
| Solusi machine learning | Deskripsi solusi machine learning yang akan dibuat |
| Metode pengolahan | Deskripsi metode pengolahan data yang digunakan |
| Arsitektur model | Deskripsi arsitektur model yang diguanakan |
| Metrik evaluasi | Deksripsi metrik yang digunakan untuk mengevaluasi performa model |
| Performa model | Deksripsi performa model yang dibuat |



# Menjalankan dengan docker

Membuat docker image 

```bash
docker build -t spam-detection-tf-serving .
```

Menjelankan docker image dan menentukan port. Ingat bahwa di dalam docker container TF Serving menggunakan port 8501.

```bash
docker run -p 8080:8501 spam-detection-tf-serving
```
