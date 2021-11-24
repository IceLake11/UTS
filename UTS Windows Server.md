## UTS Windows Server

#### Grahito Ardani B(1202199006)

------

### Instalasi Windows Server

Pertama-tama kita harus mendownload dahulu windows server. disini saya menggunakan windows server 2022. Setelah di download lalu kita melakukan instalasi dengan menggunakan Virtual Mechine.

kita membuat VM baru dengan setting seperti gambar dibawah

![1](https://user-images.githubusercontent.com/93030868/143235541-720588ac-3244-428e-875d-874207073f75.PNG)

lalu kita setting untuk ram yang digunakan, untuk ram yang digunakan saya saran kan lebih dari 4gb agar tidak terjadi lag pada saat menjalankannya

![2](https://user-images.githubusercontent.com/93030868/143235542-7668ee2f-509e-4391-8871-6539cd3ce525.PNG)

![3](https://user-images.githubusercontent.com/93030868/143235545-954b369c-830d-4a31-b5e9-26ce7b21a73c.PNG)

![4](https://user-images.githubusercontent.com/93030868/143235546-d1f2eb04-6e4a-4dcb-bed1-b66012c26003.PNG)

![5](https://user-images.githubusercontent.com/93030868/143235547-72525407-6af1-4fd2-8813-e65eac647f15.PNG)

![6](https://user-images.githubusercontent.com/93030868/143235550-87953ca8-53fa-47be-a85e-1b2f54c3f937.PNG)

setelah mengatur size virtual disk nya kita setting networknya menjadi Bridge Adapter

![7](https://user-images.githubusercontent.com/93030868/143235553-86ce6d1f-06dc-44b0-ae78-897912a3cea6.PNG)

lalu kita jalankan vm yang telah kita buat, setelah kita menjalankanny akan muncul seperti dibawah dan kita harus memilih file .ISO yang telah kita download yakni file windows server 2022

![8](https://user-images.githubusercontent.com/93030868/143235558-8eb7b026-e3ac-42a6-9ffd-21ee2f72b0b0.PNG)

![9](https://user-images.githubusercontent.com/93030868/143235559-0f82ef5f-4c7c-4646-aa4f-2b759cf4f3fa.PNG)
![10](https://user-images.githubusercontent.com/93030868/143235564-b20241f1-1d24-4776-88ec-4dc728c35069.PNG)

pada file iso yang kita download terdiri dari beberapa versi windows server nah kita menggunakan windows server 2022 datacenter evaluation(Dektop Experience)

![11](https://user-images.githubusercontent.com/93030868/143235568-ef02a122-bb0c-4f17-8697-558669f451c6.PNG)

![12](https://user-images.githubusercontent.com/93030868/143235570-5067b563-8589-4eef-b19c-ce645f35e5c4.PNG)

![13](https://user-images.githubusercontent.com/93030868/143235571-fb005a74-1ea8-49f7-ac0b-60306a2b42a6.PNG)

dan proses penginstalan sedang berjalan dan tunggu hingga selesai

![14](https://user-images.githubusercontent.com/93030868/143235575-4946a98f-990b-47c4-9419-fc4aa5cd8439.PNG)

jika sudah selesai akan tampil layar awal seperti gambar dibawah. untuk login kita harus 

klik input lalu pilih keyboard dan pilih insert Ctrl+Alt+Del dan masukkan password yang telah disetting sebelumnya

![15](https://user-images.githubusercontent.com/93030868/143235576-027acd26-cc08-4839-8e7d-46a9e3cc50c2.PNG)

Lalu klik ke device lalu insert guest additions CD image

jika sudah pergi ke file explorer lalu cd Drive Virtual box lalu pilih Vbox WindowsAdditions

![16](https://user-images.githubusercontent.com/93030868/143235592-0816e799-01ec-4197-9e85-b01e0410fec7.PNG)

![17](https://user-images.githubusercontent.com/93030868/143235649-7aa1b8dc-a2f4-4c66-8375-f4ca4ad82426.PNG)

![18](https://user-images.githubusercontent.com/93030868/143235433-41f82e84-9443-45d9-b6e9-d037eebbca25.PNG)

![19](https://user-images.githubusercontent.com/93030868/143235435-28e66a91-2f93-4dfc-988c-7c0834200416.PNG)

tunggu instalasi berlangsung jika sudah selesai akan muncul seperti gambar dibawah dan pilih reboot now

![20](https://user-images.githubusercontent.com/93030868/143235438-7cebcee7-a90a-4914-b146-26ab8c0fd82c.PNG)

### Instalasi Active Directory Domain Server

Pertama-tama kita masuk ke windows Powershell dengan administrator

```markdown
rename-computer -Newname Server2022
```

![21](https://user-images.githubusercontent.com/93030868/143235442-615a118d-3fb9-4e95-865e-71f05fc4349a.PNG)
setelah itu disarankan agar reboot vm nya agar perubahan nama yang kita lakukan bisa berhasil, setelah itu masuk ke server manager dan pilih menu manage lalu pilih menu add roles and Features

![22](https://user-images.githubusercontent.com/93030868/143235445-192bc18f-8a1a-431d-ba13-8b0eaa06d034.PNG)

Pada installation Type kita menggunakan role-based or feature-based installation

![23](https://user-images.githubusercontent.com/93030868/143235448-abc950e0-f234-4c1e-8f0c-9ec4fd596418.PNG)

setelah itu checklist server from the server pool

![24](https://user-images.githubusercontent.com/93030868/143235450-47dbc8cb-dc10-4fd4-9d09-4233bcf6be79.PNG)

setelah server selection kita masuk pada server roles lalu checklist active directory domain server

![25](https://user-images.githubusercontent.com/93030868/143235454-d8124bb0-0a60-47e7-93d1-2cc736a957e4.PNG)

setelah server roles tinggal next lalu muncul pop up lalu pilih add features lalu install

![26](https://user-images.githubusercontent.com/93030868/143235460-b26a45ad-355e-468c-bb43-3843b813527d.PNG)

apabila instalasi sudah selesai kita akan setting ip nya agar static dengan menggunakan cmd yang diakses dengan administrator

```markdown
sconfig
```

![27](https://user-images.githubusercontent.com/93030868/143235463-f5dd598c-4663-4d94-a0b3-6513a1b49853.PNG)
lalu akan masuk ke tampilan seperti gambar dibawah dan ketik angka 8 untuk masuk ke network settings

![28](https://user-images.githubusercontent.com/93030868/143235467-83caf6be-f0d0-4bea-b9d0-1d1debceb232.PNG)

lalu kita mulai setting dengan ketik angka 1 untuk masuk ke setting network adapter address setelah itu ada pilihan DHCP atau Static kita ketik s untuk memilih static lalu masukkan ip static yang ingin digunakan berserta subnet dan gateway nya

![30](https://user-images.githubusercontent.com/93030868/143235475-11186da4-61dd-4185-a56c-b2506b34fcfd.PNG)

### Instalasi DNS

Penginstalan DNS server untuk langkah-langkah yang dilakukan sams seperti menginstal domain

![31](https://user-images.githubusercontent.com/93030868/143235480-38e80da6-cb1d-4dd8-aefd-f3aae2e3f7f2.PNG)

### Instalasi Net Framework 3.5

Penginstalan Net framework 3.5 sama seperti domain dan DNS![Net]![Net](https://user-images.githubusercontent.com/93030868/143235536-cbefced2-dbaa-42bb-a6c8-99d73a21b3c2.png)

### Promote Server to a Domain

kemudian promote server to domain controller dengan bendera yang terdapat tanda warning kuning setelah itu masuk pada deployment configuration lalu checklist add a new forest dan masukkan root domain name bebas sesuai keiginan anda

![32](https://user-images.githubusercontent.com/93030868/143235485-138f9e61-886b-4352-ac23-57e1d14a2eee.PNG)

masukkan pasword untuk DRSM

![33](https://user-images.githubusercontent.com/93030868/143235488-71f6c12b-c507-4138-a624-d109598cf8e6.PNG)

lalu masukkan nama NetBIOS domain sesuai keinginan dan kebutuhan anda

![34](https://user-images.githubusercontent.com/93030868/143235494-66db9d18-82af-4971-a3c6-3060e55eadfe.PNG)

![35](https://user-images.githubusercontent.com/93030868/143235495-f7ff4781-5039-4b41-9bd3-82e035448a74.PNG)

![36](https://user-images.githubusercontent.com/93030868/143235496-784a1564-9c1f-44d5-b40f-5e9e181eb27e.PNG)

lalu pilih install dan tunggu instalasi nya hingga selesai

![37](https://user-images.githubusercontent.com/93030868/143235503-24772413-7544-4a99-8302-bae2b067011c.PNG)

![38](https://user-images.githubusercontent.com/93030868/143235507-466aa3cc-7812-46d2-9fcf-7bbbff7ed63b.PNG)

setelah itu reboot vm nya untuk memastikan instalasinya berhasil

![39](https://user-images.githubusercontent.com/93030868/143235512-09477818-593e-4b9a-8ba6-8c5924944692.PNG)

lalu lakukan pengecekan konfigurasi pada cmd untuk mengetahui kesuksesan insatalasi

```markdown
ipconfig
```



![40](https://user-images.githubusercontent.com/93030868/143235528-c79e7103-be5a-4c37-8433-eb711213ee4a.PNG)









