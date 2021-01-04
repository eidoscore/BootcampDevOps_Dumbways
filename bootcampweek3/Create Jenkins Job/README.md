# Create Jenkins Job

* buat job baru pilih ``Freestyle Project`` dan berinama :

![1](../assets/38.PNG)

* pada tab Source Code Management pilih Git, dan edit konfigurasi seperti berikut setelah itu simpan:

![1](../assets/39.PNG)
![1](../assets/40.PNG)
![1](../assets/41.PNG)
![1](../assets/42.PNG)

* buat tambahkan semua server untuk membuat job pada jenkins

![1](../assets/43.PNG)

* masuk ke repository github kita dan setting kemudian buat webhook pada github repo private kita seperti gambar :

![1](../assets/44.PNG)

* kemudian test buat perubahan pada server semisal disini saya merubah file test pada repo dan push

![1](../assets/45.PNG)

* lihat pada job yg sudah kita buat dan kita edit repo maka akan menampilkan sukses build seperti ini ini jika berhasil.

![1](../assets/46.PNG)
![1](../assets/47.PNG)

* buat docker compose dan setting seperti berikut
![1](../assets/48.PNG)
![1](../assets/49.PNG)
![1](../assets/50.PNG)

* hubungkan akun docker hub dengan github agar ketika nanti selesai melakukan build maka image docker akan otomatis di push ke docker hub kita
![1](../assets/51.PNG)
![1](../assets/52.PNG)
![1](../assets/53.PNG)
![1](../assets/54.PNG)


# Notifikasi

untuk notifikasi proses build disini saya menggunakan Slack, jadi ketika nanti ada update job pada jenkins seperi berhasil build, gagal build, dan sebagainya akan diinformasikan melalui channel slack saya.

* pertama buat channel Slack baru dan kemudian pilih ``Connect an app`` cari aplikasi jenkins CI
![1](../assets/55.PNG)
![1](../assets/56.PNG)
![1](../assets/57.PNG)
![1](../assets/58.PNG)
![1](../assets/59.PNG)
![1](../assets/60.PNG)
