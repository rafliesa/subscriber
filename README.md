![image](https://github.com/user-attachments/assets/682fe319-1b91-4524-a724-a524011e5053)## a. What is amqp?
AMQP (Advanced Message Queuing Protocol) adalah protokol komunikasi standar terbuka yang dirancag untuk memungkinkan pertukaran pesan secara handal antar aplikasi atau komponen sistem. Protokol ini berperan sebagai middleware untuk komunikasi asinkron dan memungkinkan berbagai aplikasi bertukar informasi tanpa harus terhubung secara langsung. AMQP mendukung beragam pola komunikasi, seperti publish/subscribe, point-to-point, dan routing berbasis topik. Selain itu, AMQP menyediakan fitur-fitur penting seperti transaksi, konfirmasi pengiriman, dan sistem antrian yang tangguh. Beberapa implementasi populer dari AMQP antara lain RabbitMQ, ActiveMQ, dan Apache Qpid, yang memungkinkan sistem terdistribusi berkomunikasi secara efisien, meskipun ditulis dalam bahasa pemrograman atau berjalan di platform yang berbeda.

## b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for?
String koneksi "amqp://guest:guest@localhost:5672" merupakan URI (Uniform Resource Identifier) yang digunakan untuk menjalin koneksi dengan server AMQP. URI ini terdiri dari beberapa komponen penting: bagian pertama "guest" berfungsi sebagai username untuk proses autentikasi ke server AMQP, sedangkan "guest" kedua adalah password yang sesuai, keduanya merupakan kredensial default yang umum digunakan pada implementasi seperti RabbitMQ. Selanjutnya, "localhost:5672" menunjukkan alamat dari server, di mana "localhost" mengacu pada komputer lokal tempat aplikasi dijalankan, dan 5672 adalah port standar yang digunakan oleh protokol AMQP. Dengan menggunakan URI ini, aplikasi dapat terhubung ke broker pesan AMQP di mesin lokal, melakukan autentikasi, dan membentuk saluran komunikasi untuk mengirim serta menerima pesan sesuai dengan konfigurasi yang telah ditentukan.

## Simulating slow subscriber
![image](https://github.com/user-attachments/assets/f74eb3d5-4110-4b0a-bda1-ee7f3e7c76a5)
![image](https://github.com/user-attachments/assets/f445ff7e-8831-48e9-83d8-678bb08387c9)
Jumlah antrean yang terlihat sebagai 2 pada RabbitMQ menunjukkan bahwa ada dua antrean aktif di sistem. Ini bisa terjadi karena pembuatan dua antrean berbeda selama pengujian atau karena subscriber terhubung ke antrean berbeda. Angka ini menunjukkan jumlah antrean, bukan jumlah pesan di dalamnya.

## 3 Subscriber
![image](https://github.com/user-attachments/assets/c9bebfb2-3f53-4eb8-bb0b-70b347c98f28)
![image](https://github.com/user-attachments/assets/f4ebf00b-edaa-4e67-b980-041206a505e5)
Pada gambar pertama, grafik antrean menunjukkan peningkatan kecepatan dengan 3 subscriber, sehingga jumlah pesan dalam antrean menurun signifikan. Gambar kedua memperlihatkan bahwa broker membagikan pesan berbeda ke setiap subscriber, dan pesan yang diambil dihapus dari antrean.
