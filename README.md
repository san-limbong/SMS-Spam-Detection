# Submission 1: SMS Spam Detection
Nama: San Antonio Limbong

Username dicoding: san-limbong

| | Deskripsi |
| ----------- | ----------- |
| Dataset | [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) |
| Masalah | Deskripsi masalah yang di angkat |
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
