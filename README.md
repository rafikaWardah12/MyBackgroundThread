# MyBackgroundThread
Project ini memuat simulasi dari background thread yang dapat mempengaruhi processing data di android. Teknologi yang digunakan yaitu bahasa kotlin yang merupakan deklaratif function dan XML sebagai interfacenya.
# Implementasi
1. Membuat countdown
2. Menjalankan aplikasi dan mengalami freeze
3. Menambahkan Executor Service
4. Menjalankan aplikasi kembali dan tidak terjadi freeze
5. Menambahkan Coroutine sebagai alternative Executor Service di Kotlin
# What I Learn
1. **Aturan dalam membuat Thread Baru :**
* Tidak memblokir UI Thread
* Tidak memanggil Ui di luar UI Thread
2. *Application Not Responding* (ANR) bisa terjadi karena saat proses memanipulasi bitmap dan proses menghubungi server dilakukan di Ui thread/main thread. ANR biasanya akan muncul setelah 5 detik dari UI yang mengalami Freeze


