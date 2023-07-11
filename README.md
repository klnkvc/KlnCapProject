# Capstone Project
## Pembuatan Jupyter Notebook Klasifikasi Kualitas Wine dengan IBM Watson AutoAI

Project ini adalah salah satu persyaratan untuk lulus dari program IBM AI dan Cybersecurity.
Tujuan dari project ini yaitu untuk membuat model machine learning yang membantu dalam melakukan klasifikasi kualitas wine berdasarkan beberapa parameter tertentu.
</br>Salah satu kebutuhan agar dapat menjalankan project ini maka anda harus memilki akun aktif [**IBM CLOUD**](cloud.ibm.com), akun **IBM CLOUD** dapat dimiliki secara gratis 

#### Service yang dibutuhkan
* [Watson Studio](https://cloud.ibm.com/catalog/services/watson-studio)
* [Watson Machine Learning](https://cloud.ibm.com/catalog/services/watson-machine-learning)
* [Cloud Object Storage](https://cloud.ibm.com/objectstorage/create)

#### Hal yang harus dilakukan sebelumnya
* Mendaftar akun [IBM CLOUD](cloud.ibm.com)
* Mengaktifkan service Cloud Object Storage
* Mengaktifkan service Watson Machine Learning
* Mengaktifkan service Watson Studio
* Membuat project Watson Studio dan memasukkan dataset WineQT.csv

### Langkah-Langkah Project
#### 1. Mendapatkan API Key
1. Pada halaman utama IBM Cloud, Klik `Manage` pada kanan atas halaman dan pilih `Access (IAM)`
2. Pada bagian kiri pilih `API Keys` dan pilh `Create`
3. Berikan nama kepada API Key dan simpan API Keys yang diberikan
#### 2. Mendapatkan Target Space Id
1. Buka `Watson Studio` dan pilih project yang dibuat
2. Tekan icon Burger di pojok kiri atas dan pilih `Deployments`
3. Pilih `New Deployment Space`
4. Berikan nama Deployment Space
5. Pada bagian kanan, pilih `Cloud Object Storage` dan `Watson Machine Learning`
6. Pilih `Create`
7. Pada halaman Deployment, Pilih tab `Manage` dan Target Space Id ada pada bagian `Space GUID`
#### 3. Menjalankan Eksperimen AutoAI
1. Pada halaman project di Watson Studio, tekan `New Asset` dan pilih `AutoAI`
2. Berikan nama dan pilih `Create`
3. Pada halaman `Add Data Source`, upload file `WineQT.csv`
4. Tekan `No` pada bagian **Create a time series analysis**
5. Pada bagian **Select Prediction Column**, pilih `Quality`
6. Buka `Experiment Settings`
7. Pada bagian **Optimized algorithm selection** pilih `Score only`
8. Pada bagian **Algorithm to use**, pilih `4`
9. Pilih `Save Settings` dan klik `Run Experiment`
#### 4. Membuat Notebook Eksperimen
1. Setelah selesai menjalankan Eksperimen, pilihlah icon `Save` berbentuk disket pada bagian kanan atas
2. Pilih `Create`
3. Kembali ke halaman Project dan buka Notebook yang telah di simpan
4. Pilih `Edit` pada bagian kanan atas halaman
#### 5. Pengaturan Awal Notebook
1. Pada bagian `Watson Machine Learning Connection`, masukkan API Keys yang telah disimpan ke dalam `api_key = 'INSERT API KEY'`
2. Pada bagian `Deployment Creation`, masukkan Target Space Id yang telah disimpan ke dalam `target_space_id = "INSERT TARGET SPACE ID"`
#### 6. Menjalankan Notebook
Jalankan seluruh bagian Notebook mulai dari bagian paling atas, Gunakan kombinasi `Shift+Enter` atau tekan tombol `Run` pada setiap baris</br>
Setelah menjalankan seluruh bagian dari Notebook, maka sebuah model machine learning akan dibuat di dalam Deployment Space.</br>
#### 7. Pengujian 
1. Buka Halaman `Deployment Space`, masuk ke tab `Deployment`, dan pilih `Best_pipeline_webservice`
2. Buka tab `Test`, Masukkan file `Best_pipeline_webservice_test_input.csv`, dan tekan `Predict`
3. Bandingkan hasil prediksi model klasifikasi yang telah dibuat dengan file `winequality-red.csv`

## License

This code pattern is licensed under the Apache License, Version 2. Separate third-party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1](https://developercertificate.org/) and the [Apache License, Version 2](https://www.apache.org/licenses/LICENSE-2.0.txt).

[Apache License FAQ](https://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN)
