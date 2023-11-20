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
www     IN      CNAME   riegel.canyon.it12.com.' > /etc/bind/jarkom/riegel.canyon.a09.com

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
@       IN      NS      granz.channel.a09.com.
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
### Kendala yang Dihadapi


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
### Kendala yang Dihadapi


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
### Kendala yang Dihadapi


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
### Kendala yang Dihadapi


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
### Kendala yang Dihadapi


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
### Kendala yang Dihadapi


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
www     IN      CNAME   riegel.canyon.it12.com.' > /etc/bind/jarkom/riegel.canyon.a09.com

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


## Soal 8
### Cara Pengerjaan
Menggunakan hasil konfigurasi yang sama seperti nomor 7, selanjutkan menjalankan command berikut pada client untuk masing masing algoritma load balancer yaitu round robin, least-connection, IP hash, dan generic hash
```
ab -n 200 -c 10 http://www.granz.channel.it12.com/ 
```
### Screenshot
### Kendala yang Dihadapi


## Soal 9
### Cara Pengerjaan
Menggunakan hasil konfigurasi yang sama seperti nomor 7, selanjutkan menjalankan command berikut pada client dengan pengecekan 1 worker, 2 worker, dan 3 worker
```
ab -n 100 -c 10 http://www.granz.channel.it12.com/ 
```
### Screenshot
### Kendala yang Dihadapi


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
    fixed-address 192.173.3.69;
}
```
Restart ulang node client (misalkan revolte)
### Screenshot
![WhatsApp Image 2023-11-16 at 10 48 58](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/400a7824-f72a-4a2d-955e-35fc04e50d92)

![WhatsApp Image 2023-11-16 at 10 52 33](https://github.com/RP-Tama/Jarkom-Modul-3-IT12-2023/assets/107543354/a8e48986-89da-402b-abcc-47d275a376a7)
### Kendala yang Dihadapi


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
CREATE DATABASE dbkelompoka09;
GRANT ALL PRIVILEGES ON *.* TO 'kelompokit12'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'kelompokit12'@'localhost';
FLUSH PRIVILEGES;
```
Mengecek pada laravel worker dengan perintah
```
mariadb --host=192.239.2.1 --port=3306 --user=kelompokit12 --password=passwordit12 dbkelompokit12 -e "SHOW DATABASES;"
```
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
