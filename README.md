# Docker Web Server using NGINX, PHP 7.4, dan MYSQL (latest)

Repo ini akan membantu kalian melakukan setup docker webserver menggunakan NGINX, PHP 7.4 FPM, dan My SQL terbaru. Pastikan docker engine terinstall, referensi banyak diinternet, atau ini https://docs.docker.com/engine/install/

## Setup Docker

Langsung aja setelah clone, berikut terdapat 2 cara untuk setupnya (pilih salah satu)
1. ```$ docker-compose up --build``` docker akan menampilkan log live setelah setup container sekaligus membuat image (biasanya dipakai buat backup atau share2), untuk menghentikan tampilan log live, `CTRL + C`
2. ```$ docker-compose up -d``` jika ingin supaya jalan sebagai daemon atau _background process_ setelah up container tanpa membuild image nya

Jika ingin menghapus container beserta volume2nya (posisi harus berada di lokasi project dan file docker-compose.yaml berada!)
```sh
$ docker-compose down -v
```
>**Peringatan!**
Jika kalian sudah melakukan setup khusus seperti memberikan password khusus di phpmyadmin atau sudah ada db di mysql, dengan menjalankan perintah hapus container diatas akan juga menghapus seluruh apa saja yang ada didalam containernya (berarti yang disebutkan diatas akan dihapus), pastikan untuk membackup nya terlebih dahulu!


# Selanjutnya?
Buka browser, ketikan URL:  
  ``http://localhost`` atau ``localhost`` atau ``alamat_ip_server``

untuk akses phpmyadmin:  
  ``http://localhost:8081`` atau ``localhost:8081`` atau ``alamat_ip_server:8081``

>**Jangan lupa untuk mengganti password root dan user biasa** , direkomendasikan untuk se segera memodifikasi hak akses phpmyadmin dan database untuk akun `homestead`

# Aku ingin koneksikan aplikasi ke db, kok salah mulu kalo hostnamenya ``localhost`` ?
isikan `hostname='db'` (darimana dapat `db` ? cek `docker-compose.yaml` didalam `services` terdapat `db`)

selain diatas, berarti kalian setup local, bukan container, seharusnya work diisi localhost (TANPA PORT!), 127.0.0.1, ataupun informasi yg tercantum di halaman depan phpmyadmin
  
