## UTS Windows Server

#### Grahito Ardani B(1202199006)

------

### Instalasi Windows Server

Pertama-tama kita harus mendownload dahulu windows server. disini saya menggunakan windows server 2022. Setelah di download lalu kita melakukan instalasi dengan menggunakan Virtual Mechine.

kita membuat VM baru dengan setting seperti gambar dibawah

![](D:\Semester5\administrasi Server\Windows Server pict\1.PNG)

lalu kita setting untuk ram yang digunakan, untuk ram yang digunakan saya saran kan lebih dari 4gb agar tidak terjadi lag pada saat menjalankannya

![2](D:\Semester5\administrasi Server\Windows Server pict\2.PNG)

![3](D:\Semester5\administrasi Server\Windows Server pict\3.PNG)

![4](D:\Semester5\administrasi Server\Windows Server pict\4.PNG)

![5](D:\Semester5\administrasi Server\Windows Server pict\5.PNG)

![6](D:\Semester5\administrasi Server\Windows Server pict\6.PNG)

setelah mengatur size virtual disk nya kita setting networknya menjadi Bridge Adapter

![7](D:\Semester5\administrasi Server\Windows Server pict\7.PNG)

lalu kita jalankan vm yang telah kita buat, setelah kita menjalankanny akan muncul seperti dibawah dan kita harus memilih file .ISO yang telah kita download yakni file windows server 2022

![8](D:\Semester5\administrasi Server\Windows Server pict\8.PNG)

![9](D:\Semester5\administrasi Server\Windows Server pict\9.PNG)

![10](D:\Semester5\administrasi Server\Windows Server pict\10.PNG)

pada file iso yang kita download terdiri dari beberapa versi windows server nah kita menggunakan windows server 2022 datacenter evaluation(Dektop Experience)

![11](D:\Semester5\administrasi Server\Windows Server pict\11.PNG)

![12](D:\Semester5\administrasi Server\Windows Server pict\12.PNG)

![13](D:\Semester5\administrasi Server\Windows Server pict\13.PNG)

dan proses penginstalan sedang berjalan dan tunggu hingga selesai

![14](D:\Semester5\administrasi Server\Windows Server pict\14.PNG)

jika sudah selesai akan tampil layar awal seperti gambar dibawah. untuk login kita harus 

klik input lalu pilih keyboard dan pilih insert Ctrl+Alt+Del dan masukkan password yang telah disetting sebelumnya

![15](D:\Semester5\administrasi Server\Windows Server pict\15.PNG)

Lalu klik ke device lalu insert guest additions CD image

jika sudah pergi ke file explorer lalu cd Drive Virtual box lalu pilih Vbox WindowsAdditions

![16](D:\Semester5\administrasi Server\Windows Server pict\16.PNG)

![17](D:\Semester5\administrasi Server\Windows Server pict\17.PNG)

![18](D:\Semester5\administrasi Server\Windows Server pict\18.PNG)

![19](D:\Semester5\administrasi Server\Windows Server pict\19.PNG)

tunggu instalasi berlangsung jika sudah selesai akan muncul seperti gambar dibawah dan pilih reboot now

![20](D:\Semester5\administrasi Server\Windows Server pict\20.PNG)

### Instalasi Active Directory Domain Server

Pertama-tama kita masuk ke windows Powershell dengan administrator

```markdown
rename-computer -Newname Server2022
```

![21](D:\Semester5\administrasi Server\Windows Server pict\21.PNG)

setelah itu disarankan agar reboot vm nya agar perubahan nama yang kita lakukan bisa berhasil, setelah itu masuk ke server manager dan pilih menu manage lalu pilih menu add roles and Features

![22](D:\Semester5\administrasi Server\Windows Server pict\22.PNG)

Pada installation Type kita menggunakan role-based or feature-based installation

![23](D:\Semester5\administrasi Server\Windows Server pict\23.PNG)

setelah itu checklist server from the server pool

![24](D:\Semester5\administrasi Server\Windows Server pict\24.PNG)

setelah server selection kita masuk pada server roles lalu checklist active directory domain server

![25](D:\Semester5\administrasi Server\Windows Server pict\25.PNG)

setelah server roles tinggal next lalu muncul pop up lalu pilih add features lalu install

![26](D:\Semester5\administrasi Server\Windows Server pict\26.PNG)

apabila instalasi sudah selesai kita akan setting ip nya agar static dengan menggunakan cmd yang diakses dengan administrator

```markdown
sconfig
```

![](D:\Semester5\administrasi Server\Windows Server pict\27.PNG)

lalu akan masuk ke tampilan seperti gambar dibawah dan ketik angka 8 untuk masuk ke network settings

![28](D:\Semester5\administrasi Server\Windows Server pict\28.PNG)

lalu kita mulai setting dengan ketik angka 1 untuk masuk ke setting network adapter address setelah itu ada pilihan DHCP atau Static kita ketik s untuk memilih static lalu masukkan ip static yang ingin digunakan berserta subnet dan gateway nya

![30](D:\Semester5\administrasi Server\Windows Server pict\30.PNG)

### Instalasi DNS

Penginstalan DNS server untuk langkah-langkah yang dilakukan sams seperti menginstal domain

![31](D:\Semester5\administrasi Server\Windows Server pict\31.PNG)

### Instalasi Net Framework 3.5

Penginstalan Net framework 3.5 sama seperti domain dan DNS![Net](D:\Semester5\administrasi Server\Windows Server pict\Net.png)

### Promote Server to a Domain

kemudian promote server to domain controller dengan bendera yang terdapat tanda warning kuning setelah itu masuk pada deployment configuration lalu checklist add a new forest dan masukkan root domain name bebas sesuai keiginan anda

![32](D:\Semester5\administrasi Server\Windows Server pict\32.PNG)

masukkan pasword untuk DRSM

![33](D:\Semester5\administrasi Server\Windows Server pict\33.PNG)

lalu masukkan nama NetBIOS domain sesuai keinginan dan kebutuhan anda

![34](D:\Semester5\administrasi Server\Windows Server pict\34.PNG)

![35](D:\Semester5\administrasi Server\Windows Server pict\35.PNG)

![36](D:\Semester5\administrasi Server\Windows Server pict\36.PNG)

lalu pilih install dan tunggu instalasi nya hingga selesai

![37](D:\Semester5\administrasi Server\Windows Server pict\37.PNG)

![38](D:\Semester5\administrasi Server\Windows Server pict\38.PNG)

setelah itu reboot vm nya untuk memastikan instalasinya berhasil

![39](D:\Semester5\administrasi Server\Windows Server pict\39.PNG)

lalu lakukan pengecekan konfigurasi pada cmd untuk mengetahui kesuksesan insatalasi

```markdown
ipconfig
```



![40](D:\Semester5\administrasi Server\Windows Server pict\40.PNG)









