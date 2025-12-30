# 🛡️ DoS Attack Simulation And Mitigation

![Security Status](https://img.shields.io/badge/Security-Educational-blue?style=for-the-badge&logo=kalilinux)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-black?style=for-the-badge&logo=linux)
![Language](https://img.shields.io/badge/Tool-Python-yellow?style=for-the-badge&logo=python)

> **⚠️ DISCLAIMER / PERINGATAN HUKUM**
>
> Proyek ini didokumentasikan semata-mata untuk **tujuan pendidikan** dan **riset keamanan** di lingkungan laboratorium yang terkendali (Virtual Environment).
> Penggunaan teknik ini terhadap target tanpa izin tertulis adalah **ilegal** dan melanggar hukum. Penulis tidak bertanggung jawab atas penyalahgunaan informasi ini.

---

## 📋 Daftar Isi
- [Skenario & Topologi](#-skenario--topologi)
- [Prasyarat](#-prasyarat)
- [Langkah Eksekusi](#-langkah-eksekusi)
- [Hasil & Analisis](#-hasil--analisis)
- [Mitigasi & Pencegahan](#-mitigasi--pencegahan)

---

## 🌐 Skenario & Topologi

Dalam praktikum ini, kita mensimulasikan serangan **Denial of Service (DoS) Layer 7** menggunakan metode **Slowloris**. Serangan ini bertujuan untuk membuat layanan web server (HTTP) menjadi tidak responsif dengan cara membanjiri server menggunakan koneksi yang terbuka setengah (partial connections).

| Perangkat | Peran | OS | IP Address |
| :--- | :--- | :--- | :--- |
| **Attacker** | Penyerang | Kali Linux | `192.168.221.128` (Contoh) |
| **Victim** | Target | Windows/Metasploitable | `192.168.221.129` |

---

## 🛠 Prasyarat

Sebelum menjalankan simulasi, pastikan hal berikut:
1.  **VirtualBox/VMware** sudah terinstall.
2.  Koneksi jaringan antar VM diatur ke **Bridged** atau **Host-only** (Satu segmen jaringan).
3.  Tool **Slowloris** (Python script) sudah tersedia di mesin Kali Linux.

---

## 🚀 Langkah Eksekusi

### 1. Pengecekan Koneksi & Target
Memastikan target hidup dan port 80 (HTTP) terbuka.

```bash
ping 192.168.221.129
nmap -p 80 192.168.221.129
