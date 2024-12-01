# Jarkom-5-IT06-2024

Laporan Resmi Jarkom Modul 5
Masih Pemula yg belajar GNS3

| Nama | NRP |
| ---- | ---- |
| Callista Meyra Azizah | 5027231060 |
| Renjamin Khawarizmi Habibi | 5027231078 |

IP Prefix untuk IT06

| IT06 | 192.236 |
|----|----|

# Misi 1: Memetakan Kota New Eridu
1.  Sebuah topologi sederhana menggambarkan jaringan New Eridu:
![WhatsApp Image 2024-11-30 at 00 34 21_ad765985](https://github.com/user-attachments/assets/9d1971dc-1ee9-47e4-978b-05df8e661ad3)
Keterangan:
- HDD: Berfungsi sebagai DNS Server.
- Fairy: Berfungsi sebagai DHCP Server.
- Web Servers: HIA, HollowZero.
Client:
- Burnice: Memiliki 5 host.
- Lycaon: Memiliki 20 host.
- Policeboo: Memiliki 30 host.
- Caesar: Memiliki 50 host
- Ellen: Memiliki 100 host.
- Jane: Memiliki 200 host.

2. Setelah membagi alamat IP menggunakan VLSM, gambarkan pohon subnet yang menunjukkan hierarki pembagian IP di jaringan New Eridu. Lingkari subnet-subnet yang akan dilewati dalam jaringan.
- Gambar Rute:
![RUTE FIX](https://github.com/user-attachments/assets/925ab161-8bff-4a33-8075-caaab7189d68)
- Pembagian Rute: [SPREADSHEET](https://docs.google.com/spreadsheets/d/1zI3OmMxX0yAr5VX4vVDV8RhfkD-QKsDZj-OfU2oCOCw/edit?gid=671499381#gid=671499381)
- Gambar Tree:
![Tree VLSM_#2](https://github.com/user-attachments/assets/e4501f31-4384-48d1-88c1-37482650570b)
  
3. Setelah pembagian IP selesai, buatlah konfigurasi rute untuk menghubungkan semua subnet dengan benar di jaringan New Eridu. Pastikan perangkat dapat saling terhubung.
# Network Configuration

- NewEridu
```
# NAT
auto eth0
iface eth0 inet dhcp

# A1
auto eth1
iface eth1 inet static
    address 192.236.0.1
    netmask 255.255.255.252

# A5
auto eth2
iface eth2 inet static
    address 192.236.2.1
    netmask 255.255.255.252
```

- LuminaSquare
```
# A1
auto eth0
iface eth0 inet static
    address 192.236.0.2
    netmask 255.255.255.252
    gateway 192.236.0.1

# A2
auto eth1
iface eth1 inet static
    address 192.236.0.5
    netmask 255.255.255.0

# A4
auto eth2
iface eth2 inet static
    address 192.236.1.9
    netmask 255.255.255.128
```
- BalletTwins
```
# A2
auto eth0
iface eth0 inet static
    address 192.236.0.6
    netmask 255.255.255.0
    gateway 192.236.0.5

# A3
auto eth1
iface eth1 inet static
    address 192.236.1.1
    netmask 255.255.255.248
```
- SixStreet
```
# A5
auto eth0
iface eth0 inet static
    address 192.236.2.2
    netmask 255.255.255.252
    gateway 192.236.2.1

# A6
auto eth1
iface eth1 inet static
    address 192.236.2.5
    netmask 255.255.255.248

# A9
auto eth2
iface eth2 inet static
    address 192.236.3.65
    netmask 255.255.255.252
```    
- HollowZero
```
# A9
auto eth0
iface eth0 inet static
    address 192.236.3.66
    netmask 255.255.255.252
    gateway 192.236.3.65
 ```   
- Fairy (DHCP Server)
```
# A6
auto eth0
iface eth0 inet static
    address 192.236.2.6
    netmask 255.255.255.248
    gateway 192.236.2.5
```    
- HDD (DNS Server)
```
# A6
auto eth0
iface eth0 inet static
    address 192.236.2.7
    netmask 255.255.255.248
    gateway 192.236.2.5
```    
- Burnice
```
# A8
auto eth0
iface eth0 inet dhcp
 ```   
- Caesar
```
# A8
auto eth0
iface eth0 inet dhcp
```    
- Ellen
```
# A4
auto eth0
iface eth0 inet sdhcp
```    
- Lycaon
```
# A4
auto eth0
iface eth0 inet dhcp
 ```   
- Jane
```
# A2
auto eth0
iface eth0 inet dhcp
```    
- Policeboo
```
# A2
auto eth0
iface eth0 inet dhcp
```
- HIA
```
# A3
auto eth0
iface eth0 inet static
    address 192.236.1.2
    netmask 255.255.255.248
    gateway 192.236.1.1
```
- ScootOutpost
```
# A9
auto eth0
iface eth0 inet static
    address 192.236.3.66
    netmask 255.255.255.252
    gateway 192.236.3.65
```
- OuterRing
```
# A7
auto eth0
iface eth0 inet static
    address 192.236.2.13
    netmask 255.255.255.248
    gateway 192.236.2.12
```

# Routing + Bashrc
- NewEridu
```

```
