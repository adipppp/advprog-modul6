# advprog-modul6

## Reflection 1
Pertama, function `handle_connection()` menerima argument `stream` yang merupakan instance dari `TcpListener`. Argument `stream` tersebut kemudian akan di-<i>wrap</i> oleh sebuah `BufReader` untuk mempercepat operasi read dari stream tersebut. Kemudian, method `lines()` akan mengembalikan sebuah iterator `Lines` terhadap setiap `Option` baris yang dibaca oleh `buf_reader`. Selanjutnya, method `map()` akan melakukan mapping terhadap setiap `Option` baris dalam `Lines` dan memanggil method `unwrap()` pada setiap `Option`. Baris-baris hasil transformasi tersebut akan disimpan dalam sebuah `Map` baru. Method `take_while()` akan dipanggil pada instance `Map` baru yang sudah dibuat, melakukan filter dengan cara menyimpan baris-baris pada sebuah `Map` sampai sebuah baris kosong ditemukan. Terakhir, method `collect()` mengubah iterator `Map` menjadi sebuah collection dan menyimpan collection tersebut pada variable `http_request`.

Macro `println!()` akan melakukan print collection `http_request` ke console.

## Reflection 2
Function `fs::read_to_string()` berfungsi untuk membaca konten file `hello.html`, kemudian memanggil method `unwrap()` untuk mendapatkan return valuenya. Setelah itu, konten file `hello.html` yang sudah didapatkan dari pemanggilan method `unwrap()` disimpan pada variable `contents`. Variable `response` merupakan sebuah string yang mendefinisikan sebuah HTTP response dengan status line, header Content-Length, dan response body. String tersebut diformat sedemikian rupa sehingga value status line, header Content-Length, dan response body pada string tersebut menggunakan value dari variable `status_line`, `contents`, dan `length` secara berturut-turut. Karena method `stream.write_all()` hanya menerima bytes sebagai argument, kita konversi variable `response` menjadi bentuk bytes menggunakan method `response.as_bytes()`. Terakhir, kita menuliskan HTTP response pada TCP stream untuk dikirimkan kembali kepada pengirim request.

![Commit 2 screen capture](assets/commit2.png)
