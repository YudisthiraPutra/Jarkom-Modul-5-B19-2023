# Laporan Praktikum Modul 5 Jaringan Komputer

Anggota Kelompok
1. Mohammad Ahnaf Fauzan (5025211170)
2. Al-Ferro Yudisthira Putra (5025211176)

## Konfigurasi
<img width="628" alt="Screenshot 2023-12-17 at 17 19 03" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/7a4f4172-0926-414d-9076-64f99fa11778">

### Pembagian Subnet
<img width="727" alt="Screenshot 2023-12-17 at 15 07 06" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/4fa3eb71-69d6-478c-8f64-6f9d9ef9c1ad">

### Pembagian IP Menggunakan Metode VLSM
<img width="461" alt="Screenshot 2023-12-17 at 15 07 35" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/a19e3103-1bab-4b64-beba-d8bf2a025619">

### Tree Pembagian IP Menggunakan Metode VLSM
<img width="705" alt="Screenshot 2023-12-17 at 15 08 09" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/725d90ee-d854-4ace-8182-3b120b229496">

### Konfigurasi Node
#### Aura
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.18.14.149
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.18.14.129
	netmask 255.255.255.252
```
#### Frieren
```
auto eth0
iface eth0 inet static
	address 10.18.14.130
	netmask 255.255.255.252
        gateway 10.18.14.129

auto eth1
iface eth1 inet static
	address 10.18.14.133
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.18.14.145
	netmask 255.255.255.252
```
#### Himmel
```
auto eth0
iface eth0 inet static
	address 10.18.14.134
	netmask 255.255.255.252
	gateway 10.18.14.133

auto eth1
iface eth1 inet static
	address 10.18.12.1
	netmask 255.255.254.0

auto eth2
iface eth2 inet static
	address 10.18.14.1
	netmask 255.255.255.128
```
#### Fern
```
auto eth0
iface eth0 inet static
	address 10.18.14.2
	netmask 255.255.255.128
        gateway 10.18.14.1

auto eth1
iface eth1 inet static
	address 10.18.14.141
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.18.14.137
	netmask 255.255.255.252
```
#### Revolte
```
auto eth0
iface eth0 inet static
	address 10.18.14.138
	netmask 255.255.255.252
        gateway 10.18.14.137
```
#### Richter
```
auto eth0
iface eth0 inet static
	address 10.18.14.142
	netmask 255.255.255.252
        gateway 10.18.14.141
```
#### Schwer Mountain
```
auto eth0
iface eth0 inet dhcp
```
#### Laub Hills
```
auto eth0
iface eth0 inet dhcp
```
#### Heiter
```
auto eth0
iface eth0 inet static
	address 10.18.14.150
	netmask 255.255.255.252
        gateway 10.18.14.149

auto eth1
iface eth1 inet static
	address 10.18.0.1
	netmask 255.255.248.0

auto eth2
iface eth2 inet static
	address 10.18.8.1
	netmask 255.255.252.0
```
#### Stark
```
auto eth0
iface eth0 inet static
	address 10.18.14.146
	netmask 255.255.255.252
	gateway 10.18.14.145

```
#### Turk Region
```
auto eth0
iface eth0 inet dhcp
```
#### Sein
```
auto eth0
iface eth0 inet static
	address 10.18.8.2
	netmask 255.255.252.0
        gateway 10.18.8.1
```
#### Grobe Forest
```
auto eth0
iface eth0 inet dhcp
```

### Konfigurasi Routing
#### Aura
```
route add -net 10.18.14.144 netmask 255.255.255.252 gw 10.18.14.130
route add -net 10.18.14.132 netmask 255.255.255.252 gw 10.18.14.130
route add -net 10.18.12.0 netmask 255.255.254.0 gw 10.18.14.130
route add -net 10.18.14.0 netmask 255.255.255.128 gw 10.18.14.130
route add -net 10.18.14.140 netmask 255.255.255.252 gw 10.18.14.130
route add -net 10.18.14.136 netmask 255.255.255.252 gw 10.18.14.130
route add -net 10.18.0.0 netmask 255.255.248.0 gw 10.18.14.150
route add -net 10.18.8.0 netmask 255.255.252.0 gw 10.18.14.150
```
#### Frieren
```
route add -net 10.18.14.0 netmask 255.255.255.128 gw 10.18.14.134
route add -net 10.18.12.0 netmask 255.255.254.0 gw 10.18.14.134
route add -net 10.18.14.140 netmask 255.255.255.252 gw 10.18.14.134
route add -net 10.18.14.136 netmask 255.255.255.252 gw 10.18.14.134
```
#### Himmel
```
route add -net 10.18.14.140 netmask 255.255.255.252 gw 10.18.14.2
route add -net 10.18.14.136 netmask 255.255.255.252 gw 10.18.14.2
```

### Konfigurasi DNS Server
```
apt-get update
apt-get install isc-dhcp-server

cp /root/dhcpd.conf /etc/dhcp/dhcpd.conf
cp /root/isc-dhcp-server /etc/default/isc-dhcp-server

```
#### dhcpd.conf
```
subnet 10.18.14.0 netmask 255.255.255.128{
    range 10.18.14.2 10.18.14.126;
    option routers 10.18.14.1;
    option broadcast-address 10.18.14.127;
    option domain-name-servers 10.18.14.142;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 10.18.12.0 netmask 255.255.254.0{
    range 10.18.12.2 10.18.13.254;
    option routers 10.18.12.1;
    option broadcast-address 10.18.13.255;
    option domain-name-servers 10.18.14.142;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 10.18.0.0 netmask 255.255.248.0{
    range 10.18.0.2 10.18.7.254;
    option routers 10.18.0.1;
    option broadcast-address 10.18.7.255;
    option domain-name-servers 10.18.14.142;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 10.18.8.0 netmask 255.255.252.0{
    range 10.18.8.2 10.18.11.254;
    option routers 10.18.8.1;
    option broadcast-address 10.18.11.255;
    option domain-name-servers 10.18.14.142;
    default-lease-time 600;
    max-lease-time 7200;
}
subnet 10.18.14.128 netmask 255.255.255.252 {}
subnet 10.18.14.132 netmask 255.255.255.252 {}
subnet 10.18.14.136 netmask 255.255.255.252 {}
subnet 10.18.14.140 netmask 255.255.255.252 {}
subnet 10.18.14.144 netmask 255.255.255.252 {}
subnet 10.18.14.148 netmask 255.255.255.252 {}
```
### Konfigurasi DHCP Server
```
apt-get update
apt-get install bind9 -y
cp /root/named.conf.options /etc/bind/named.conf.options
```
#### named.conf.options
```
options {
        directory "/var/cache/bind";
        forwarders {
                192.168.122.1;
        };
        allow-query { any; };
        auth-nxdomain no;    # conform to RFC1035
        listen-on-v6 { any; };
}
```

## Soal 1
### Soal
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Aura menggunakan iptables, tetapi tidak ingin menggunakan MASQUERADE.
### Jawaban
```
ETH0ADDR=$(ip -br a | grep eth0 | awk '{print $NF}' | cut -d'/' -f1)
iptables --table nat --append POSTROUTING --out-interface eth0 --source 10.18.0.0/20 --jump SNAT --to-source "$ETH0ADDR"
```
> Maka, kita bisa melakukan testing di salah satu client dengan ping google.com seperti gambar dibawah,
<img width="610" alt="Screenshot 2023-12-17 at 15 42 42" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/980bdcc6-87e8-40c0-9d99-c39cdaa0ef5d">

## Soal 2
### Soal
Kalian diminta untuk melakukan drop semua TCP dan UDP kecuali port 8080 pada TCP.
### Jawaban
```
iptables -A INPUT -p udp -j DROP
iptables -A INPUT -p tcp ! --dport 8080 -j DROP
```
> berikut merupakan hasil testing penggunaan port 8080 dimana hasilnya berhasil,

<img width="426" alt="Screenshot 2023-12-17 at 16 00 42" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/c5de4bea-f786-46ef-b20c-41efb61bc08e">
<img width="425" alt="Screenshot 2023-12-17 at 16 00 54" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/9f890dbd-4220-40de-91a7-54b8f2c2bcab">

> berikut merupakan hasil testing penggunaan port 80 dimana hasilnya gagal,
<img width="405" alt="Screenshot 2023-12-17 at 16 01 49" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/404b63ea-cd99-4b05-a7ab-548999285869">
<img width="416" alt="Screenshot 2023-12-17 at 16 02 41" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/b9b1c975-0268-43cf-8399-886b364f5079">

## Soal 3
### Soal
Kepala Suku North Area meminta kalian untuk membatasi DHCP dan DNS Server hanya dapat dilakukan ping oleh maksimal 3 device secara bersamaan, selebihnya akan di drop.
### Jawaban
```
iptables -A INPUT -p icmp -m connlimit --connlimit-above 3 --connlimit-mask 0 -j DROP
```
> kita bisa melakukan testing dengan cara ping kepada salah satu server di 4 device yang berbeda. Pada device ke 4, ping gagal.
<img width="723" alt="Screenshot 2023-12-17 at 16 07 00" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/25f9ae1b-78af-4f96-83e5-440899821831">
<img width="703" alt="Screenshot 2023-12-17 at 16 07 12" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/edf67afd-3401-4e5a-9497-8560fa853340">
<img width="717" alt="Screenshot 2023-12-17 at 16 07 21" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/5d9bdb1e-67b3-44fd-8e96-48a9c4d653e3">
<img width="558" alt="Screenshot 2023-12-17 at 16 07 30" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/9ce8611b-9d00-40c1-aaf8-58994163dae1">

## Soal 4
### Soal
Lakukan pembatasan sehingga koneksi SSH pada Web Server hanya dapat dilakukan oleh masyarakat yang berada pada GrobeForest.
### Jawaban
```
iptables -A INPUT -p tcp --dport 22 -s 10.18.8.0/22 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j DROP
```
> berikut merupakan testing dari Frobe Forest
<img width="411" alt="Screenshot 2023-12-17 at 16 49 19" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/bd4aa85f-29fb-42cf-8f40-ad7e3ee3edd2">
<img width="237" alt="Screenshot 2023-12-17 at 16 49 31" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/89ad930a-99fd-40ae-a6dd-fccbef891cdd">

> berikut merupakan testing diluar grobe forest
<img width="380" alt="Screenshot 2023-12-17 at 16 50 38" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/87ccebad-feb7-4f96-a0f4-e2468d7a0a1f">
<img width="242" alt="Screenshot 2023-12-17 at 16 50 46" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/0fc00f2f-3447-4116-b91e-a0ddffc02c81">


## Soal 5
### Soal
Selain itu, akses menuju WebServer hanya diperbolehkan saat jam kerja yaitu Senin-Jumat pada pukul 08.00-16.00.
### Jawaban
```
iptables -A INPUT -p tcp --dport 80 -m time --timestart 07:00 --timestop 11:59 --weekdays Mon,Tue,Wed,Thu -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 13:01 --timestop 16:00 --weekdays Mon,Tue,Wed,Thu -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 07:00 --timestop 10:59 --weekdays Fri -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 13:01 --timestop 16:00 --weekdays Fri -j ACCEPT

iptables -A INPUT -p tcp --dport 80 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -p tcp --dport 80 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP

iptables -A INPUT -p tcp --dport 80 -j DROP

```
> berikut merupakan hasil testing pada hari jum'at 9.20 pagi
<img width="396" alt="Screenshot 2023-12-17 at 17 11 22" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/edb2a45b-ca08-4f0b-ae59-3cb2f912d50d">
<img width="250" alt="Screenshot 2023-12-17 at 17 11 59" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/c390cfbd-6038-44ca-b52a-53ff6684cba2">

> berikut merupakan hasil testing pada hari jumat jam 11 malam
<img width="422" alt="Screenshot 2023-12-17 at 17 13 01" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/7d463a3a-9736-46d1-8a69-edd49e161fea">
<img width="293" alt="Screenshot 2023-12-17 at 17 13 11" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/c765e112-472e-4c90-bd90-1b30919befd2">

## Soal 6
### Soal
Lalu, karena ternyata terdapat beberapa waktu di mana network administrator dari WebServer tidak bisa stand by, sehingga perlu ditambahkan rule bahwa akses pada hari Senin - Kamis pada jam 12.00 - 13.00 dilarang (istirahat maksi cuy) dan akses di hari Jumat pada jam 11.00 - 13.00 juga dilarang (maklum, Jumatan rek).
### Jawaban
```
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 13:01 --timestop 11:59 --weekdays Mon,Tue,Wed,Thu,Fri -j ACCEPT
iptables -A INPUT -p tcp --dport 80 -m time --timestart 12:00 --timestop 13:00 --weekdays Mon,Tue,Wed,Thu -j DROP
iptables -A INPUT -p tcp --dport 80 -m time --timestart 11:00 --timestop 13:00 --weekdays Fri -j DROP
iptables -A INPUT -p tcp --dport 80 -j DROP

```
> ini merupakan hasil testing pada jam 12.00 siang dimana hasilnya gagal
<img width="423" alt="Screenshot 2023-12-17 at 17 14 51" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/5b3d748c-406d-4e28-a12d-0a6da7f61b55">
<img width="263" alt="Screenshot 2023-12-17 at 17 15 00" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/8f57d04c-64b6-48de-8f31-d9999e0fa522">

> ini merupakan hasil testing pada jam 10.00 siang dimana hasilnya berhasil
<img width="424" alt="Screenshot 2023-12-17 at 17 17 54" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/75bb4ac4-796c-452f-b5b5-cdbb7e6bd71a">
<img width="336" alt="Screenshot 2023-12-17 at 17 18 16" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/33724a03-19e1-450f-967d-f17fbaa7b9b8">

## Soal 7
### Soal
Karena terdapat 2 WebServer, kalian diminta agar setiap client yang mengakses Sein dengan Port 80 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan dan request dari client yang mengakses Stark dengan port 443 akan didistribusikan secara bergantian pada Sein dan Stark secara berurutan.
### Jawaban
```
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.18.8.2 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.18.8.2
iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.18.8.2 -j DNAT --to-destination 10.18.14.146
iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.18.14.146 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.18.14.146
iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.18.14.146 -j DNAT --to-destination 10.18.8.2
```
> berikut merupakan hasil testing dari nomor 7
<img width="399" alt="Screenshot 2023-12-17 at 17 08 31" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/a8bfee4c-be13-4ece-9548-2c0d08eafb2a">

## Soal 8
### Soal
Karena berbeda koalisi politik, maka subnet dengan masyarakat yang berada pada Revolte dilarang keras mengakses WebServer hingga masa pencoblosan pemilu kepala suku 2024 berakhir. Masa pemilu (hingga pemungutan dan penghitungan suara selesai) kepala suku bersamaan dengan masa pemilu Presiden dan Wakil Presiden Indonesia 2024.
### Jawaban
```
iptables -A INPUT -s 10.18.14.138 -p tcp --dport 80 -m time --datestart 2023-12-14 --datestop 2024-06-26 -j DROP
```
> berikut merupakan hasil running dari sebelum tanggal yang ditentukan
<img width="277" alt="Screenshot 2023-12-17 at 16 57 03" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/5d7cae60-3411-4274-9269-17d25e4d872d">
<img width="242" alt="Screenshot 2023-12-17 at 16 57 16" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/33fc5049-41f3-4f5e-8a53-b26aaa1dbcdd">

> berikut merupakan hasil running dari setelah tanggal yang ditentukan
<img width="293" alt="Screenshot 2023-12-17 at 16 58 22" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/213b2326-0be3-482f-b1c6-7a82ff7f9579">
<img width="298" alt="Screenshot 2023-12-17 at 16 58 39" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/79ecaee2-b328-4dff-ab7c-f80259dcc7c0">

## Soal 9
### Soal
Sadar akan adanya potensial saling serang antar kubu politik, maka WebServer harus dapat secara otomatis memblokir  alamat IP yang melakukan scanning port dalam jumlah banyak (maksimal 20 scan port) di dalam selang waktu 10 menit. 
(clue: test dengan nmap)
### Jawaban
```
iptables -N scan_port
iptables -A INPUT -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP
iptables -A FORWARD -m recent --name scan_port --update --seconds 600 --hitcount 20 -j DROP
iptables -A INPUT -m recent --name scan_port --set -j ACCEPT
iptables -A FORWARD -m recent --name scan_port --set -j ACCEPT
```
> berikut merupakan hasil testing dari salah satu client, dimana kita hanya bisa melakukan ping sebesar 20 kali, setelahnya akan loss.
<img width="650" alt="Screenshot 2023-12-17 at 16 52 21" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/e30fdca3-cdeb-4bd2-aec4-6b04f0032c41">

## Soal 10
### Soal
Karena kepala suku ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level. 
### Jawaban
```
iptables -A INPUT  -j LOG --log-level debug --log-prefix 'Packet Sent' -m limit --limit 1/second --limit-burst 10
```
<img width="1149" alt="Screenshot 2023-12-17 at 16 39 52" src="https://github.com/YudisthiraPutra/Jarkom-Modul-5-B19-2023/assets/114007340/ede8bbb6-10da-4e4c-9755-7283d3dd61bc">
