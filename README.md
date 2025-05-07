# Tutorial Modul Pemrograman Lanjut (2024/2025)

<details> <summary>a. How much data your publisher program will send to the message broker in one run?</summary>
Dalam satu kali eksekusi, program publisher akan mengirimkan lima buah pesan ke message broker. Setiap pesan berupa objek UserCreatedEventMessage yang berisi user_id dan user_name. Karena data diserialisasi menggunakan Borsh (yang efisien dalam ukuran), setiap pesan kira-kira berukuran kecil, hanya beberapa byte per string. Secara total, jumlah data yang dikirim akan tergantung panjang string-nya, namun secara kasar tidak akan lebih dari beberapa kilobyte untuk semua pesan yang dikirim sekaligus. Ini menjadikan publisher efisien untuk digunakan bahkan dalam skala besar.

</details> <details> <summary>b. The url of “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?</summary>
Penggunaan URL amqp://guest:guest@localhost:5672 yang sama di publisher dan subscriber menunjukkan bahwa keduanya berkomunikasi dengan message broker (dalam hal ini RabbitMQ) yang sama. guest:guest adalah username dan password default untuk otentikasi, sedangkan localhost menunjukkan bahwa RabbitMQ dijalankan secara lokal di komputer yang sama, dan 5672 adalah port default untuk protokol AMQP. Dengan demikian, publisher dan subscriber terhubung ke broker yang sama untuk saling bertukar pesan melalui antrian yang telah ditentukan.

</details>

### Screenshot: RabbitMQ Running in Localhost

![RabbitMQ berjalan di localhost](images/RabbitMQrunning.png)
