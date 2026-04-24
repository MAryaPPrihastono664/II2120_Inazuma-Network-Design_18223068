# Tugas Besar Desain Jaringan - PT Inazuma Bersinar Selamanya

Repositori ini berisi dokumentasi perancangan dan implementasi jaringan komputer untuk kompleks perkantoran PT Inazuma Bersinar Selamanya (IBS). Proyek ini mencakup desain topologi, konfigurasi subnetting, layanan server, hingga kebijakan keamanan.

## Proyek
* **Mata Kuliah:** II2120 - Jaringan Komputer
* **Mahasiswa:** Muhammad Arya Putra Prihastono (18223068)

---

## Deskripsi Kebutuhan
Jaringan dirancang untuk kompleks dua gedung dengan pembagian sebagai berikut:
* **Gedung 1:** Terdiri dari Ruangan Barat (Subnet A - STI), Ruangan Timur (Subnet B - EL), Ruangan Tengah (Subnet C - Tamu/WAP), dan Ruangan Server.
* **Gedung 2:** Berisi Ruangan Administrasi (Subnet D).
* **Koneksi ISP:** Menggunakan Cisco Router 2901 dengan alamat publik 182.135.196.16/27.

---

## Arsitektur Jaringan

### 1. Subnetting & VLAN
Setiap divisi dipisahkan dalam subnet yang berbeda untuk keamanan dan manajemen:
- **Subnet A (VLAN 10):** Jasa STI (192.168.0.0/26).
- **Subnet B (VLAN 20):** Jasa Teknik Elektro (192.168.0.64/26).
- **Subnet C:** Ruang Tamu dengan DHCP & Wireless Access Point (192.168.0.192/27).
- **Subnet D:** Administrasi (192.168.0.128/26).

### 2. Layanan Jaringan (Milestone 2)
Beberapa layanan utama yang dikonfigurasi meliputi:
* **DHCP:** Otomatisasi IP untuk client di setiap subnet.
* **NAT (PAT):** Menggunakan *Port Address Translation* pada Router Server agar IP privat dapat mengakses internet melalui satu IP publik.
* **DNS:** Domain utama `inazuma.com` dengan subdomain untuk setiap divisi (admin, sti, el).
* **Email & Web:** Layanan SMTP/POP3 internal dan host website HTTP/HTTPS untuk masing-masing divisi.

---

## Keamanan (ACL)
Kebijakan keamanan diterapkan menggunakan **Access Control List (ACL)** pada router untuk:
1. Membatasi akses antar subnet.
2. Mengatur akses dari jaringan publik ke server internal.
3. Memastikan Subnet A, B, C, dan D tidak dapat diakses langsung secara publik dari luar.

---
