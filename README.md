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
Sempat mengalami kesulitan saat penyesuaian konfigurasi

## Soal 0
### Cara Pengerjaan
Melakukan setup menggunakan command dan agar tidak perlu dilakukan setiap mengakses terminal dapat disimpan dalam bashrc di setiap node
* Aura (DHCP Relay)
  ```
  apt-get update
  apt-get install isc-dhcp-relay -y
  ```
* Himmel (DHCP Server)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install isc-dhcp-server -y
  ```
* Heiter (DNS Server)
  ```
  echo 'nameserver 192.168.122.1' > /etc/resolv.conf'
  apt-get update
  apt-get install bind9 -y
  ```
* Eisen (Load Balancer)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install apache2-utils -y
  apt-get install nginx -y
  apt-get install lynx -y
  service nginx start
  ```
* Denken (Database Server)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install mariadb-server -y
  service mysql start
  ```
  Mengganti address menjadi 8.8.8.8 dan direstart
  ```
  nano /etc/mysql/mariadb.conf.d/50-server.cnf
  service mysql restart
  ```
* Revolte (Client)
  ```
  apt update
  apt install lynx -y
  apt install htop -y
  apt install apache2-utils -y
  apt-get install jq -y
  ```
* Richter (Client)
  ```
  apt update
  apt install lynx -y
  apt install htop -y
  apt install apache2-utils -y
  apt-get install jq -y
  ```
* Stark (Client)
  ```
  apt update
  apt install lynx -y
  apt install htop -y
  apt install apache2-utils -y
  apt-get install jq -y
  ```
* Sein (Client)
  ```
  apt update
  apt install lynx -y
  apt install htop -y
  apt install apache2-utils -y
  apt-get install jq -y
  ```
* Lawine (PHP Worker)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install nginx -y
  apt-get install wget -y
  apt-get install unzip -y
  apt-get install lynx -y
  apt-get install htop -y
  apt-get install apache2-utils -y
  apt-get install php7.3-fpm php7.3-common php7.3-mysql php7.3-gmp   php7.3-curl php7.3-intl php7.3-mbstring php7.3-xmlrpc php7.3-gd   php7.3-xml php7.3-cli php7.3-zip -y
  service nginx start
  service php7.3-fpm start
  ```
* Linie (PHP Worker)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install nginx -y
  apt-get install wget -y
  apt-get install unzip -y
  apt-get install lynx -y
  apt-get install htop -y
  apt-get install apache2-utils -y
  apt-get install php7.3-fpm php7.3-common php7.3-mysql php7.3-gmp   php7.3-curl php7.3-intl php7.3-mbstring php7.3-xmlrpc php7.3-gd   php7.3-xml php7.3-cli php7.3-zip -y
  service nginx start
  service php7.3-fpm start
  ```
* Lugner (PHP Worker)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install nginx -y
  apt-get install wget -y
  apt-get install unzip -y
  apt-get install lynx -y
  apt-get install htop -y
  apt-get install apache2-utils -y
  apt-get install php7.3-fpm php7.3-common php7.3-mysql php7.3-gmp   php7.3-curl php7.3-intl php7.3-mbstring php7.3-xmlrpc php7.3-gd   php7.3-xml php7.3-cli php7.3-zip -y
  service nginx start
  service php7.3-fpm start
  ```
* Frieren (Laravel Worker)
  ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install lynx -y
  apt-get install mariadb-client -y
  # Test connection from worker to database
  # mariadb --host=192.239.2.1 --port=3306   --user=kelompokait12 --password=passwordit12 dbkelompokit12 -e "SHOW DATABASES;"
  apt-get install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2
  curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
  sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'
  apt-get update
  apt-get install php8.0-mbstring php8.0-xml php8.0-cli   php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl unzip wget -y
  apt-get install nginx -y
  service nginx start
  service php8.0-fpm start
  ```
* Flamme (Laravel Worker)
    ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install lynx -y
  apt-get install mariadb-client -y
  # Test connection from worker to database
  # mariadb --host=192.239.2.1 --port=3306   --user=kelompokait12 --password=passwordit12 dbkelompokit12 -e "SHOW DATABASES;"
  apt-get install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2
  curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
  sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'
  apt-get update
  apt-get install php8.0-mbstring php8.0-xml php8.0-cli   php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl unzip wget -y
  apt-get install nginx -y
  service nginx start
  service php8.0-fpm start
  ```
* Fern (Laravel Worker)
    ```
  echo 'nameserver 192.239.1.2' > /etc/resolv.conf
  apt-get update
  apt-get install lynx -y
  apt-get install mariadb-client -y
  # Test connection from worker to database
  # mariadb --host=192.239.2.1 --port=3306   --user=kelompokait12 --password=passwordit12 dbkelompokit12 -e "SHOW DATABASES;"
  apt-get install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2
  curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
  sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'
  apt-get update
  apt-get install php8.0-mbstring php8.0-xml php8.0-cli   php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl unzip wget -y
  apt-get install nginx -y
  service nginx start
  service php8.0-fpm start
  ```


## Soal 1
### Cara Pengerjaan
Mengubah node Lugner (php worker) dan Fern (laravel worker) untuk menambahkan domain riegel.canyon.it12.com untuk laravel dan granz.channel.it12.com untuk php yang diarahkan pada worker IP berakhiran 1
* Fern (Laravel)
  ```
  auto eth0
  iface eth0 inet static
	address 192.239.4.1
	netmask 255.255.255.0
	gateway 192.239.4.0
  ```
* Lugner (PHP)
  ```
  auto eth0
  iface eth0 inet static
	address 192.239.3.1
	netmask 255.255.255.0
	gateway 192.239.3.0
  ```
Menambahkan kode berikut pada Heiter yang bertindak sebagai DNS Server
```
echo 'zone "riegel.canyon.it12.com" {
    type master;
    file "/etc/bind/jarkom/riegel.canyon.it12.com";
};

zone "granz.channel.it12.com" {
    type master;
    file "/etc/bind/jarkom/granz.channel.it12.com";
};

zone "1.239.192.in-addr.arpa" {
    type master;
    file "/etc/bind/jarkom/1.239.192.in-addr.arpa";
};' > /etc/bind/named.conf.local

mkdir -p /etc/bind/jarkom
cp /etc/bind/db.local /etc/bind/jarkom/riegel.canyon.it12.com
cp /etc/bind/db.local /etc/bind/jarkom/granz.channel.it12.com
cp /etc/bind/db.local /etc/bind/jarkom/1.239.192.in-addr.arpa

echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     riegel.canyon.it12.com. root.riegel.canyon.it12.com. (
                        2023111401      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      riegel.canyon.it12.com.
@       IN      A       192.239.4.1     ; IP Fern
www     IN      CNAME   riegel.canyon.it12.com.' > /etc/bind/jarkom/riegel.canyon.it12.com

echo '
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     granz.channel.it12.com. root.granz.channel.it12.com. (
                        2023111401      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      granz.channel.it12.com.
@       IN      A       192.239.3.1     ; IP Lugner
www     IN      CNAME   granz.channel.it12.com.' > /etc/bind/jarkom/granz.channel.it12.com

echo 'options {
      directory "/var/cache/bind";

      forwarders {
              192.168.122.1;
      };

      // dnssec-validation auto;
      allow-query{any;};
      auth-nxdomain no;    # conform to RFC1035
      listen-on-v6 { any; };
}; ' >/etc/bind/named.conf.options

service bind9 start
```
### Screenshot
![WhatsApp Image 2023-11-18 at 23 32 03](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/3b09b378-9bcf-4780-bbc6-160d73a948dc)
![WhatsApp Image 2023-11-20 at 16 16 12](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/11480e57-ea06-46cd-8893-05e289076be3)
![WhatsApp Image 2023-11-18 at 23 31 32](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/03dca801-2b9c-441f-8c9d-f825f78c9dc8)
![WhatsApp Image 2023-11-20 at 16 16 57](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/4624f282-6bd0-4ba4-8c8d-cbb1f1973bbf)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 2
### Cara Pengerjaan
Menambahkan kode pada Himmel sebagai DHCP Server untuk switch 3 yaitu 
```
echo 'subnet 192.239.1.0 netmask 255.255.255.0 {
}

subnet 192.239.2.0 netmask 255.255.255.0 {
}

subnet 192.239.3.0 netmask 255.255.255.0 {
    range 192.239.3.16 192.239.3.32;
    range 192.239.3.64 192.239.3.80;
    option routers 192.239.3.1;
}' > /etc/dhcp/dhcpd.conf
```
### Screenshot
![WhatsApp Image 2023-11-20 at 16 16 38](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/684dfa5a-beb9-425b-ad53-6d1d9acf4e93)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 3
### Cara Pengerjaan
Menambahkan kode pada Himmel sebagai DHCP Server dari yang sudah dilakukan pada nomer sebelumnya untuk switch 4 yaitu
```
echo 'subnet 192.239.1.0 netmask 255.255.255.0 {
}

subnet 192.239.2.0 netmask 255.255.255.0 {
}

subnet 192.239.3.0 netmask 255.255.255.0 {
    range 192.239.3.16 192.239.3.32;
    range 192.239.3.64 192.239.3.80;
    option routers 192.239.3.1;
}

subnet 192.239.4.0 netmask 255.255.255.0 {
    range 192.239.4.12 192.239.4.20;
    range 192.239.4.160 192.239.4.168;
    option routers 192.239.4.1;
} ' > /etc/dhcp/dhcpd.conf
```
### Screenshot
![WhatsApp Image 2023-11-18 at 16 37 59](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/144fbcde-daed-4d47-9c33-d4b1e0c098c1)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 4
### Cara Pengerjaan
Menambahkan option broadcast address dan option domain name server dari kode yang sebelumnya
```
subnet 192.239.3.0 netmask 255.255.255.0 {
    ...
    option broadcast-address 192.239.3.255;
    option domain-name-servers 192.239.1.2;
    ...
}

subnet 192.239.4.0 netmask 255.255.255.0 {
    option broadcast-address 192.239.4.255;
    option domain-name-servers 192.239.1.2;
} 
```
Lalu melakukan setup untuk DHCP Relay dan menjalankan kode berikut
```
echo '# Defaults for isc-dhcp-relay initscript
# sourced by /etc/init.d/isc-dhcp-relay
# installed at /etc/default/isc-dhcp-relay by the maintainer scripts

#
# This is a POSIX shell fragment
#

# What servers should the DHCP relay forward requests to?
SERVERS="192.239.1.2"

# On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
INTERFACES="eth1 eth2 eth3 eth4"

# Additional options that are passed to the DHCP relay daemon?
OPTIONS=""' > /etc/default/isc-dhcp-relay

service isc-dhcp-relay start 
```
Melakukan uncommend pada file ```/etc/sysctl.conf``` pada bagian ```net.ipv4.ip_forward=1```
Melakukan restart di 4 client
### Screenshot
![WhatsApp Image 2023-11-18 at 17 04 44](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/ce8849da-5745-4e87-ad05-475c393856d1)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 5
### Cara Pengerjaan
Menambahkan command ```default-lease-time``` dan ```max-lease-time``` pada DHCP Server lanjutan dari kode sebelumnya untuk setting peminjaman IP selama 3 menit untuk switch 3 dan peminjaman IP selama 12 menit untuk switch 4 dan waktu maksimal selama 96 menit
```
echo 'subnet 192.239.1.0 netmask 255.255.255.0 {
}

subnet 192.239.2.0 netmask 255.255.255.0 {
}

subnet 192.239.3.0 netmask 255.255.255.0 {
    range 192.239.3.16 192.239.3.32;
    range 192.239.3.64 192.239.3.80;
    option routers 192.239.3.1;
    option broadcast-address 192.239.3.255;
    option domain-name-servers 192.239.1.2;
    default-lease-time 180;
    max-lease-time 5760;
}

subnet 192.239.4.0 netmask 255.255.255.0 {
    range 192.239.4.12 192.239.4.20;
    range 192.239.4.160 192.239.4.168;
    option routers 192.239.4.1;
    option broadcast-address 192.239.4.255;
    option domain-name-servers 192.239.1.2;
    default-lease-time 720;
    max-lease-time 5760;
}' > /etc/dhcp/dhcpd.conf

echo '# Defaults for isc-dhcp-server (sourced by /etc/init.d/isc-dhcp-server)

# Path to dhcpd'\''s config file (default: /etc/dhcp/dhcpd.conf).
DHCPDv4_CONF=/etc/dhcp/dhcpd.conf
DHCPDv6_CONF=/etc/dhcp/dhcpd6.conf

# Path to dhcpd'\''s PID file (default: /var/run/dhcpd.pid).
DHCPDv4_PID=/var/run/dhcpd.pid
DHCPDv6_PID=/var/run/dhcpd6.pid

# Additional options to start dhcpd with.
#<----->Don'\''t use options -cf or -pf here; use DHCPD_CONF/ DHCPD_PID instead
OPTIONS=""

# On what interfaces should the DHCP server (dhcpd) serve DHCP requests?
#<----->Separate multiple interfaces with spaces, e.g. "eth0 eth1".
INTERFACESv4="eth0"
INTERFACESv6=""' > /etc/default/isc-dhcp-server

service isc-dhcp-server restart
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/8de608f4-5f56-499c-9ffb-e4064120c911)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 6
### Cara Pengerjaan
Melakukan konfigurasi untuk mendownload dan unzip setelah set up PHP Worker
```
wget -O '/var/www/granz.channel.it12.com' 'https://drive.google.com/u/0/uc?id=1ViSkRq7SmwZgdK64eRbr5Fm1EGCTPrU1&export=download'
unzip -o /var/www/granz.channel.it12.com -d /var/www/
rm /var/www/granz.channel.it12.com
mv /var/www/modul-3 /var/www/granz.channel.it12.com
```
Melakukan konfigurasi pada nginx
```
cp /etc/nginx/sites-available/default /etc/nginx/sites-available/granz.channel.it12.com
ln -s /etc/nginx/sites-available/granz.channel.it12.com /etc/nginx/sites-enabled/
rm /etc/nginx/sites-enabled/default

echo 'server {
    listen 80;
    server_name _;

    root /var/www/granz.channel.it12.com;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php7.3-fpm.sock;  # Sesuaikan versi PHP dan socket
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}' > /etc/nginx/sites-available/granz.channel.it12.com

service nginx restart
```
Menjalankan command ```lynx localhost``` di masing masing worker
### Screenshot
![WhatsApp Image 2023-11-18 at 23 43 35](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/c2e999a7-1d5c-428f-84d8-90c49374a80c)
![WhatsApp Image 2023-11-19 at 00 02 55](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/849cb759-1419-48a7-ad1f-55f65ed548fa)
![WhatsApp Image 2023-11-19 at 00 09 31](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/6b1fc8f4-da8c-4d9f-b2c6-105a1559bea5)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 7
### Cara Pengerjaan
Melakukan konfigurasi Load Balancing di node Eisen di mana mengarahkan domain DNS Server pada IP Eisen sebagai Load Balancer
```
echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     riegel.canyon.it12.com. root.riegel.canyon.it12.com. (
                        2023111401      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      riegel.canyon.it12.com.
@       IN      A       192.239.2.2     ; IP LB Eiken
www     IN      CNAME   riegel.canyon.it12.com.' > /etc/bind/jarkom/riegel.canyon.it12.com

echo '
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     granz.channel.it12.com. root.granz.channel.it12.com. (
                        2023111401      ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      granz.channel.it12.com.
@       IN      A       192.239.2.2     ; IP LB Eiken
www     IN      CNAME   granz.channel.it12.com.' > /etc/bind/jarkom/granz.channel.it12.com
```
Melakukan konfigurasi nginx pada Eisen
```
cp /etc/nginx/sites-available/default /etc/nginx/sites-available/lb_php

echo ' upstream worker {
    server 192.239.3.1;
    server 192.239.3.2;
    server 192.239.3.3;
}

server {
    listen 80;
    server_name granz.channel.it12.com www.granz.channel.it12.com;

    root /var/www/html;

    index index.html index.htm index.nginx-debian.html;

    server_name _;

    location / {
        proxy_pass http://worker;
    }
} ' > /etc/nginx/sites-available/lb_php

ln -s /etc/nginx/sites-available/lb_php /etc/nginx/sites-enabled/
rm /etc/nginx/sites-enabled/default

service nginx restart
```
Melakukan konfigurasi pada client dan menjalankan printah berikut
```
ab -n 1000 -c 100 http://www.granz.channel.it12.com/ 
```
### Screenshot
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 8
### Cara Pengerjaan
Menggunakan hasil konfigurasi yang sama seperti nomor 7, selanjutkan menjalankan command berikut pada client untuk masing masing algoritma load balancer yaitu round robin, least-connection, IP hash, dan generic hash
```
ab -n 200 -c 10 http://www.granz.channel.it12.com/ 
```
### Screenshot
Round Robin <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/774cc1c3-9bda-4631-bc61-cd620d01b577)

Least-connection <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/789a130f-ba7e-4d8e-beff-1e66716ec298)

IP Hash <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/e3f57b77-3913-4a3a-85ce-83ea69fc4bcd)

Generic-hash <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/8c053a4c-7f33-4de4-a148-59cb7ae06117)

Grafik <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/4c5dc892-d789-4eab-899a-2ec825a1cfa9)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 9
### Cara Pengerjaan
Menggunakan hasil konfigurasi yang sama seperti nomor 7, selanjutkan menjalankan command berikut pada client dengan pengecekan 1 worker, 2 worker, dan 3 worker
```
ab -n 100 -c 10 http://www.granz.channel.it12.com/ 
```
### Screenshot
3 worker <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/962665a4-a964-48d3-88c0-d68da2137d46)

2 worker <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/b3c6b04f-75d3-40b2-9100-692d0193700f)

1 worker <br>
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/7c519721-62bd-4c06-99eb-746ab274477e)

Grafik
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/a1d619e5-da75-4b65-a553-6c808252adb9)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 10
### Cara Pengerjaan
Menambahkan konfigurasi berikut dari setup yang sudah dilakukan sebelumnya
```
mkdir /etc/nginx/rahasisakita
htpasswd -c /etc/nginx/rahasisakita/htpasswd netics
```
Menambahkan password ajkit12
Memasukkan code berikut pada setup nginx
```
auth_basic "Restricted Content";
auth_basic_user_file /etc/nginx/rahasisakita/htpasswd;
```
Mengakses url ```http://www.granz.channel.it12.com/```
### Screenshot
![WhatsApp Image 2023-11-16 at 09 46 48](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/54ab346b-a241-4165-87b8-b21296732892)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 11
### Cara Pengerjaan
Menambahkan konfigurasi pada nginx menjadi
```
echo 'upstream worker {
    server 192.239.3.1;
    server 192.239.3.2;
    server 192.239.3.3;
}

server {
    listen 80;
    server_name granz.channel.it12.com www.granz.channel.it12.com;

    root /var/www/html;
    index index.html index.htm index.nginx-debian.html;

    location / {
        proxy_pass http://worker;
    }

    location ~ /its {
        proxy_pass https://www.its.ac.id;
        proxy_set_header Host www.its.ac.id;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}' > /etc/nginx/sites-available/lb_php
```
Menjalankan perintah berikut pada client
```
lynx www.granz.channel.it12.com/its
```
### Screenshot
![WhatsApp Image 2023-11-16 at 10 11 03](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/8ea9cdfd-2154-4ac0-90d8-97b17680df2b)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 12
### Cara Pengerjaan
Menambahkan konfigurasi pada nginx sebelumnya menjadi
```
echo 'upstream worker {
    server 192.239.3.1;
    server 192.239.3.2;
    server 192.239.3.3;
}

server {
    listen 80;
    server_name granz.channel.it12.com www.granz.channel.it12.com;

    root /var/www/html;
    index index.html index.htm index.nginx-debian.html;

    location / {
        allow 192.239.3.69;
        allow 192.239.3.70;
        allow 192.239.4.167;
        allow 192.239.4.168;
        deny all;
        proxy_pass http://worker;
    }

    location /its {
        proxy_pass https://www.its.ac.id;
        proxy_set_header Host www.its.ac.id;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}' > /etc/nginx/sites-available/lb_php
```
Menambahkan fixed address pada client yang ditambahkan pada konfigurasi dhcp server
```
host Revolte {
    harware ethernet fe:c0:13:f5:1c:02;
    fixed-address 192.239.3.69;
}
```
Restart ulang node client (misalkan revolte)
### Screenshot
![WhatsApp Image 2023-11-16 at 10 48 58](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/400a7824-f72a-4a2d-955e-35fc04e50d92)

![WhatsApp Image 2023-11-16 at 10 52 33](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/a8e48986-89da-402b-abcc-47d275a376a7)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 13
### Cara Pengerjaan
Menambahkan konfigurasi pada database server yaitu Denken
```
echo '# This group is read both by the client and the server
# use it for options that affect everything
[client-server]

# Import all .cnf files from configuration directory
!includedir /etc/mysql/conf.d/
!includedir /etc/mysql/mariadb.conf.d/

# Options affecting the MySQL server (mysqld)
[mysqld]
skip-networking=0
skip-bind-address
' > /etc/mysql/my.cnf
```
Mengganti bind address pada /etc/mysql/mariadb.conf.d/50-server.cnf menjadi 0.0.0.0
Melakukan restart my sql dengan ```service mysql restart```
Menjalankan perintah berikut
```
mysql -u root -p
```
```
CREATE USER 'kelompokit12'@'%' IDENTIFIED BY 'passwordit12';
CREATE USER 'kelompokit12'@'localhost' IDENTIFIED BY 'passwordit12';
CREATE DATABASE dbkelompokit12;
GRANT ALL PRIVILEGES ON *.* TO 'kelompokit12'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'kelompokit12'@'localhost';
FLUSH PRIVILEGES;
```
Mengecek pada laravel worker dengan perintah
```
mariadb --host=192.239.2.1 --port=3306 --user=kelompokit12 --password=passwordit12 dbkelompokit12 -e "SHOW DATABASES;"
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/113072294/c8484d89-40fa-4676-8a1d-1e53e981e07c)

### Kendala yang Dihadapi
Tidak ada kendala

## Soal 14
### Cara Pengerjaan
Melakukan konfigurasi pada Frieren, Flamme. dan Fern dengan menginstall composer
```
wget https://getcomposer.org/download/2.0.13/composer.phar
chmod +x composer.phar
mv composer.phar /usr/local/bin/composer
```
Melakukan install git dan cloning dari resource yang diberikan
```
apt-get install git -y
cd /var/www && git clone https://github.com/martuafernando/laravel-praktikum-jarkom
cd /var/www/laravel-praktikum-jarkom && composer update
```
Melakukan konfigurasi pada worker
```
cd /var/www/laravel-praktikum-jarkom && cp .env.example .env
echo 'APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=192.239.2.1
DB_PORT=3306
DB_DATABASE=dbkelompokit12
DB_USERNAME=kelompokit12
DB_PASSWORD=passwordit12

BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

MEMCACHED_HOST=127.0.0.1

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=mt1

VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
VITE_PUSHER_HOST="${PUSHER_HOST}"
VITE_PUSHER_PORT="${PUSHER_PORT}"
VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"' > /var/www/laravel-praktikum-jarkom/.env
cd /var/www/laravel-praktikum-jarkom && php artisan key:generate
cd /var/www/laravel-praktikum-jarkom && php artisan config:cache
cd /var/www/laravel-praktikum-jarkom && php artisan migrate
cd /var/www/laravel-praktikum-jarkom && php artisan db:seed
cd /var/www/laravel-praktikum-jarkom && php artisan storage:link
cd /var/www/laravel-praktikum-jarkom && php artisan jwt:secret
cd /var/www/laravel-praktikum-jarkom && php artisan config:clear
chown -R www-data.www-data /var/www/laravel-praktikum-jarkom/storage
```
Melakukan konfigurasi nginx pada masing masing worker
```
192.239.4.1:8001; # Fern 
192.239.4.2:8002; # Flamme
192.239.4.3:8003; # Frieren
```
```
echo 'server {
    root /var/www/laravel-praktikum-jarkom/public;

    index index.php index.html index.htm;
    server_name _;

    location / {
            try_files $uri $uri/ /index.php?$query_string;
    }

    # pass PHP scripts to FastCGI server
    location ~ \.php$ {
      include snippets/fastcgi-php.conf;
      fastcgi_pass unix:/var/run/php/php8.0-fpm.sock;
    }

    location ~ /\.ht {
            deny all;
    }

    error_log /var/log/nginx/implementasi_error.log;
    access_log /var/log/nginx/implementasi_access.log;
}' > /etc/nginx/sites-available/laravel-worker
```
Menjalankan command
```
lynx localhost:8001
lynx localhost:8002
lynx localhost:8003
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/113072294/61c9f7fa-ab24-4c61-9733-06551a926a52)

### Kendala yang Dihadapi
Tidak ada kendala

## Soal 15
### Cara Pengerjaan
Melakukan testing dengan apache benchmark pada worker dan dilakukan oleh client.
Sebelumnya, dilakukan pengiriman pada endpoint /api/auth/register menggunakan file.json
```
echo '
{
  "username": "kelompokit12",
  "password": "passwordit12"
}' > register.json
```
Memasukkan command pada client
```
ab -n 100 -c 10 -p register.json -T application/json http://192.239.4.1:8001/api/auth/register
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/6697968b-cd9b-4765-8a58-75f659905671)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 16
### Cara Pengerjaan
Melakukan testing dengan apache benchmark pada worker dan dilakukan oleh client.
Sebelumnya, dilakukan pengiriman pada endpoint /api/auth/login menggunakan file.json
```
echo '
{
  "username": "kelompokit12",
  "password": "passwordit12"
}' > login.json
```
Memasukkan command pada client
```
ab -n 100 -c 10 -p register.json -T application/json http://192.239.4.1:8001/api/auth/login
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/51aaa782-b2dd-411e-9598-2e74aaddb1b1)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 17
### Cara Pengerjaan
Melakukan testing dengan apache benchmark pada worker dan dilakukan oleh client.
Sebelumnya, dilakukan untuk mendapatkan token dengan
```
curl -X POST -H "Content-Type: application/json" -d @login.json http://192.239.4.1:8001/api/auth/login > login_output.txt
```
Menjalankan command untuk set token
```
token=$(cat login_output.txt | jq -r '.token')
```
Melakukan testing
```
ab -n 100 -c 10 -H "Authorization: Bearer $token" http://192.239.4.1:8001/api/me
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/007fdc1e-0171-4b48-8be7-86cb366c063e)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 18
### Cara Pengerjaan
Melakukan konfigurasi nginx untuk melakukan load balancing
```
echo 'upstream worker {
    server 192.239.4.1:8001;
    server 192.239.4.2:8002;
    server 192.239.4.3:8003;
}

server {
    listen 80;
    server_name riegel.canyon.it12.com www.riegel.canyon.it12.com;

    location / {
        proxy_pass http://worker;
    }
} 
' > /etc/nginx/sites-available/laravel-worker

ln -s /etc/nginx/sites-available/laravel-worker /etc/nginx/sites-enabled/laravel-worker

service nginx restart
```
Melakukan testing pada client
```
ab -n 100 -c 10 -p login.json -T application/json http://www.riegel.canyon.it12.com/api/auth/login
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/113072294/9260c379-c5d0-4958-b9fa-8e2270ce9c72)

### Kendala yang Dihadapi
Tidak ada kendala

## Soal 19
### Cara Pengerjaan
Melakukan 4 konfigurasi untuk proses package manager di masing masing worker
```
# Setup Awal
echo '[www]
user = www-data
group = www-data
listen = /run/php/php8.0-fpm.sock
listen.owner = www-data
listen.group = www-data
php_admin_value[disable_functions] = exec,passthru,shell_exec,system
php_admin_flag[allow_url_fopen] = off

; Choose how the process manager will control the number of child processes.

pm = dynamic
pm.max_children = 5
pm.start_servers = 2
pm.min_spare_servers = 1
pm.max_spare_servers = 3' > /etc/php/8.0/fpm/pool.d/www.conf

service php8.0-fpm restart
```
```
echo '[www]
user = www-data
group = www-data
listen = /run/php/php8.0-fpm.sock
listen.owner = www-data
listen.group = www-data
php_admin_value[disable_functions] = exec,passthru,shell_exec,system
php_admin_flag[allow_url_fopen] = off

; Choose how the process manager will control the number of child processes.

pm = dynamic
pm.max_children = 25
pm.start_servers = 5
pm.min_spare_servers = 3
pm.max_spare_servers = 10' > /etc/php/8.0/fpm/pool.d/www.conf

service php8.0-fpm restart
```
```
echo '[www]
user = www-data
group = www-data
listen = /run/php/php8.0-fpm.sock
listen.owner = www-data
listen.group = www-data
php_admin_value[disable_functions] = exec,passthru,shell_exec,system
php_admin_flag[allow_url_fopen] = off

; Choose how the process manager will control the number of child processes.

pm = dynamic
pm.max_children = 50
pm.start_servers = 8
pm.min_spare_servers = 5
pm.max_spare_servers = 15' > /etc/php/8.0/fpm/pool.d/www.conf

service php8.0-fpm restart
```
```
echo '[www]
user = www-data
group = www-data
listen = /run/php/php8.0-fpm.sock
listen.owner = www-data
listen.group = www-data
php_admin_value[disable_functions] = exec,passthru,shell_exec,system
php_admin_flag[allow_url_fopen] = off

; Choose how the process manager will control the number of child processes.

pm = dynamic
pm.max_children = 75
pm.start_servers = 10
pm.min_spare_servers = 5
pm.max_spare_servers = 20' > /etc/php/8.0/fpm/pool.d/www.conf

service php8.0-fpm restart
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/89af1502-3eef-4a78-ba2f-c17777aa88bf)
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/a883c718-a87d-4b6d-938c-772d5ce7b668)
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/a960aba7-667f-462f-8491-c534ca763e59)
### Kendala yang Dihadapi
Tidak ada kendala

## Soal 20
### Cara Pengerjaan
Menambahkan algoritma pada load balancer dengan least connection karena pada konfigurasi sebelumnya hasil yang diberikan dari worker masih kurang dalam peningkatan performa worker. Maka dari itu dengan dilakukan load balancer ini dapat membuat prioritas beban berdasarkan urutan dari terendah 
```
echo 'upstream worker {
    least_conn;
    server 192.239.4.1:8001;
    server 192.239.4.2:8002;
    server 192.239.4.3:8003;
}

server {
    listen 80;
    server_name riegel.canyon.it12.com www.riegel.canyon.it12.com;

    location / {
        proxy_pass http://worker;
    }
} 
' > /etc/nginx/sites-available/laravel-worker

service nginx restart
```
Menambahkan setup berikut pada package manager
```
pm = dynamic
pm.max_children = 75
pm.start_servers = 10
pm.min_spare_servers = 5
pm.max_spare_servers = 20
```
### Screenshot
![image](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/b22ea29a-705e-423f-8553-6e63509277c5)
### Kendala yang Dihadapi
Tidak ada kendala
