# Jarkom-Modul-3-IT12-2023

## Nama Anggota IT 12
1. Raditya Pratama - 5027211047
2. Salmaa Satifha Dewi - 5027211011

## Persiapan Topologi
## Cara Pengerjaan
Config
* Aura
  ```
  auto eth0
  iface eth0 inet dhcp

  auto eth1
  iface eth1 inet static
  	address 192.239.1.1
  	netmask 255.255.255.0
  
  auto eth2
  iface eth2 inet static
  	address 192.239.2.1
  	netmask 255.255.255.0
  
  auto eth3
  iface eth3 inet static
  	address 192.239.3.254
  	netmask 255.255.255.0
  
  auto eth4
  iface eth4 inet static
  	address 192.239.4.254
  	netmask 255.255.255.0
  ```
* Himmel = DHCP server
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.1.2
  	netmask 255.255.255.0
  	gateway 192.239.1.1
  ```
* Heiter = DNS server
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.1.3
  	netmask 255.255.255.0
  	gateway 192.239.1.1
  ```
* Denken = database server
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.2.2
  	netmask 255.255.255.0
  	gateway 192.239.2.1
  ```
* Eisen = load balancer
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.2.3
  	netmask 255.255.255.0
  	gateway 192.239.2.1
  ```
* Frieren = laravel worker
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.4.3
  	netmask 255.255.255.0
  	gateway 192.239.4.254
  ```
* Flamme = laravel worker
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.4.4
  	netmask 255.255.255.0
  	gateway 192.239.4.254
  ```
* Fern = laravel worker
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.4.5
  	netmask 255.255.255.0
  	gateway 192.239.4.254
  ```
* Lawine = php worker
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.3.3
  	netmask 255.255.255.0
  	gateway 192.239.3.254
  ```
* Linie = php worker
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.3.2
  	netmask 255.255.255.0
  	gateway 192.239.3.254
  ```
* Lugner = php worker
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.3.1
  	netmask 255.255.255.0
  	gateway 192.239.3.254
  ```
* Revolte = client
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.3.5
  	netmask 255.255.255.0
  	gateway 192.239.3.254
  ```
* Richter = client
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.3.4
  	netmask 255.255.255.0
  	gateway 192.239.3.254
  ```
* Sein = client
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.4.1
  	netmask 255.255.255.0
  	gateway 192.239.4.254
  ```
* Stark = client
  ```
  auto eth0
  iface eth0 inet static
  	address 192.239.4.2
  	netmask 255.255.255.0
  	gateway 192.239.4.254
  ```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/b5b1350c-e88e-4d95-b3d8-fe6dc97c4a33)
### Kendala yang Dihadapi


## Soal 0
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 1
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 2
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 3
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 4
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 5
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 6
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 7
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 8
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 9
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 10
### Cara Pengerjaan
### Screenshot
![WhatsApp Image 2023-11-16 at 09 46 48](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/54ab346b-a241-4165-87b8-b21296732892)
### Kendala yang Dihadapi


## Soal 11
### Cara Pengerjaan
### Screenshot
![WhatsApp Image 2023-11-16 at 10 11 03](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/8ea9cdfd-2154-4ac0-90d8-97b17680df2b)
### Kendala yang Dihadapi


## Soal 12
### Cara Pengerjaan
### Screenshot
![WhatsApp Image 2023-11-16 at 10 48 58](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/400a7824-f72a-4a2d-955e-35fc04e50d92)

![WhatsApp Image 2023-11-16 at 10 52 33](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/a8e48986-89da-402b-abcc-47d275a376a7)
### Kendala yang Dihadapi


## Soal 13
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 14
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 15
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 16
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 17
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 18
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 19
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi


## Soal 20
### Cara Pengerjaan
### Screenshot
### Kendala yang Dihadapi
