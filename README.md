# MyBackgroundThread
Project ini memuat simulasi dari background thread yang dapat mempengaruhi processing data di android. Teknologi yang digunakan yaitu bahasa kotlin yang merupakan deklaratif function dan XML sebagai interfacenya.
# Implementasi
1. Membuat countdown
2. Menjalankan aplikasi dan mengalami freeze
3. Menambahkan Executor Service
4. Menjalankan aplikasi kembali dan tidak terjadi freeze
5. Menambahkan Coroutine sebagai alternative Executor Service di Kotlin
# What I Learn
1. **Aturan dalam membuat Thread Baru:**
* Tidak memblokir UI Thread
* Tidak memanggil Ui di luar UI Thread
2. *Application Not Responding* (ANR) bisa terjadi karena saat proses memanipulasi bitmap dan proses menghubungi server dilakukan di Ui thread/main thread. ANR biasanya akan muncul setelah 5 detik dari UI yang mengalami Freeze.
3. Executor = komponen untuk memanajemen banyak thread sekaligus (urutan proses, penjadwalan, maupun menjalankan proses secara paralel)
  * #### *Jenis Executor*:
    * *1. newSingleThreadExecutor* = membuat 1 thread.
        * Alasan? Apabila ada beberapa request yang berjalan maka request selanjutnya akan dijalankan setelah thread 1 selesai.
    * *2. newFixedThreadPool(nThreads)* = membuat banyak thread dengan memasukkan nThread dengan jumlah thread yang ingin dibuat. CONTOH? newFixedThreadPool(4)
        * Membuat 4 thread yang tetap.
        * Sehingga apabila ada beberapa request yang berjalan, maka dibagi ke 4 thread tersebut secara paralel.
    * *3. newCachedThreadPool* = sesuai dengan kebutuhan
        * Menggunakan thread sebelumnya misal bisa dipakai. Lalu, thread yang sudah tidak dipakai selama 1 menit akan otomatis dihapus dari cache.

4. ExecutorService = turunan dari Executor
  * Fungsi:
  * ExecutorService dapat memantau proses yang berjalan dengan memakai fungsi submit yang menghasilkan Future. 
*Ada fungsi shutdown = untuk menolak task baru
* Fungsi Cancel = membatalkan task.
5. Handler.post = berpindah antar thread

### *Contoh code membuat freeze:*
* Metode setText pada MainActivity =
  * SetText berada dalam process asynchronous background thread, yaitu thread sedang menjalankan loadStringFromNetwork( ) 
  * Bagian dari textView. Sementara itu textView adalah salah satu komponen ui
### *How to fix it?*
* Membuat thread baru dan menggunakan fungsi post untuk menampilkan data



