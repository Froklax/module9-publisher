# Publisher Reflection

### a. How much data your publisher program will send to the message broker in one run?

Setiap kali program publisher dijalankan, program ini akan mengirimkan lima messages ke message broker. Saya bisa mengetahui ini karena di dalam function `main` pada file `main.rs`, terdapat lima baris perintah yang masing-masing memanggil function `publish_event`, yang artinya ada lima message terpisah yang dikirim.

### b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

Ketika program publisher dan subscriber menggunakan URL “amqp://guest:guest@localhost:5672” yang sama persis, ini artinya kedua program tersebut akan "berbicara" dengan message broker amqp yang sama. Dengan terhubung ke message broker yang sama, messages yang dikirimkan oleh publisher dapat diterima oleh subscriber yang juga terhubung ke message broker tersebut dan mendengarkan pada event name atau queue yang ada. Jika URL yang digunakan berbeda, maka subscriber tidak akan menerima message dari publisher karena subscriber akan terhubung ke instance message broker atau konfigurasi yang berbeda dari yang ditujukan oleh publisher saat mengirimkan messagenya.