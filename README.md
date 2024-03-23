# advprog-modul6

## Reflection 1
Pertama, function `handle_connection()` menerima argument `stream` yang merupakan instance dari `TcpListener`. Argument `stream` tersebut kemudian akan di-<i>wrap</i> oleh sebuah `BufReader` untuk mempercepat operasi read dari stream tersebut. Kemudian, method `lines()` akan mengembalikan sebuah iterator `Lines` terhadap setiap `Option` baris yang dibaca oleh `buf_reader`. Selanjutnya, method `map()` akan melakukan mapping terhadap setiap `Option` baris dalam `Lines` dan memanggil method `unwrap()` pada setiap `Option`. Baris-baris hasil transformasi tersebut akan disimpan dalam sebuah `Map` baru. Method `take_while()` akan dipanggil pada instance `Map` baru yang sudah dibuat, melakukan filter dengan cara menyimpan baris-baris pada sebuah `Map` sampai sebuah baris kosong ditemukan. Terakhir, method `collect()` mengubah iterator `Map` menjadi sebuah collection dan menyimpan collection tersebut pada variable `http_request`.

Macro `println!()` akan melakukan print collection `http_request` ke console.
