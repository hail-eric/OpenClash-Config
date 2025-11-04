# 🚀 Konfigurasi OpenClash oleh B Σ N (hail-eric)

File konfigurasi OpenClash (Clash Meta) yang sudah dioptimalkan untuk kebutuhan gaming, streaming, dan sosial media.

Konfigurasi ini menggunakan **Full Geo** dan **rule-provider** agar mudah dikelola.

---

**Target Core:** Konfigurasi ini berasal dari backup **DMS Core** dan ditujukan untuk arsitektur **x86_64**.

---

## ⚡ Fitur Unggulan: Dukungan Dual Modem (Multi-WAN)

Konfigurasi ini dirancang untuk mendukung setup **Dual Modem** (atau lebih) secara *native*.

* **Bagaimana Caranya?** Di dalam file templat `proxy_provider/` (misal: `pp-indo.yaml`), Anda akan menemukan baris:
    ```yaml
    interface-name: eth1
    ```
* **Untuk Pengguna Dual Modem:** Anda bisa mengarahkan akun-akun tertentu untuk keluar melalui interface modem yang berbeda.
    * Contoh: Akun di `pp-indo.yaml` diatur ke `interface-name: eth1` (Modem A).
    * Akun di `pp-browsing.yaml` diatur ke `interface-name: eth2` (Modem B).
* **💡 Untuk Pengguna Modem Tunggal (1 Modem):**
    Jangan khawatir, ini tetap bisa dipakai! Pastikan Anda **menyamakan** semua baris `interface-name:` di semua file akun Anda.
    * Contoh: Jika modem Anda adalah `usb0` atau `eth1`, atur `interface-name: eth1` di **SEMUA** file akun Anda (`pp-indo.yaml`, `pp-browsing.yaml`, dll). Ini akan memastikan semua trafik keluar lewat modem Anda yang tunggal.

---

## 📌 Filosofi Aturan (Rules)

Konfigurasi ini dirancang sebagai **"Full Geo"**, artinya routing utama bergantung pada `GEOSITE` dan `GEOIP` (dari file `geosite.dat`, `geoip.dat`, dan `country.mmdb`). Ini membuat pemeliharaan aturan tetap simpel dan ter-update secara otomatis.

Meskipun begitu, folder `rule_provider/` beserta file `.yaml` di dalamnya **sengaja disertakan**. Ini bertujuan agar:

1.  Anda memiliki cadangan jika file `GeoSite`/`GeoIP` mengalami masalah.
2.  Anda bisa dengan mudah beralih ke mode `RULE-SET` (aturan manual berbasis file `.yaml`) jika Anda lebih suka mengelola *ruleset* Anda sendiri. Cukup edit file `config-wrt.yaml` untuk menggunakan `RULE-SET` alih-alih `GEOSITE`.

---

## 🚀 Cara Penggunaan (Subscribe)

Anda bisa menggunakan file `config-wrt.yaml` ini sebagai file konfigurasi utama di OpenClash Anda.

1.  Buka OpenClash -> `Config Manage`.
2.  Buat file subscribe baru dan tempel URL di bawah ini:

    *(Ganti `NAMA-REPO-ANDA` dengan nama repositori Anda, misal: OpenClash-Config)*
    ```
    [https://raw.githubusercontent.com/hail-eric/NAMA-REPO-ANDA/main/config-wrt.yaml](https://raw.githubusercontent.com/hail-eric/NAMA-REPO-ANDA/main/config-wrt.yaml)
    ```
3.  Klik `Subscribe` dan gunakan profil tersebut.

## 📥 Download Backup (Untuk Restore Langsung)

[cite_start]Jika Anda tidak ingin subscribe, Anda bisa mengunduh file backup `.tar.gz`  utuh dan me-restore-nya langsung di OpenClash (`Config Manage` -> `Upload Backup`).

[**➡️ Download Backup v1.0 (klik di sini)**]([https://github.com/hail-eric/NAMA-REPO-ANDA/releases/download/v1.0/Backup-OpenClash-DMS-x86_64-2025-11-04-20-33-12.tar.gz](https://github.com/hail-eric/OpenClash-Config/releases/tag/v1.0))

---

## ⚠️ PERINGATAN PENTING

Konfigurasi ini **TIDAK MENYERTAKAN AKUN PROXY**. Akun di dalam folder `proxy_provider/` hanyalah templat.

Anda **HARUS** mengedit file di dalam `proxy_provider/` (seperti `pp-indo.yaml` dan `pp-browsing.yaml`) dan mengisinya dengan akun Trojan/Vmess Anda sendiri.

---

## 📂 Struktur File

* `/config-wrt.yaml`: File konfigurasi utama. Mengatur grup proxy dan aturan "Full Geo".
* `/proxy_provider/`: Berisi templat untuk akun-akun Anda. **(WAJIB DIISI SENDIRI)**.
* `/rule_provider/`: (Opsional) Berisi file `.yaml` aturan manual jika Anda ingin beralih dari mode "Full Geo".

---

### 📬 Hubungi Saya

Jika ada masalah atau pertanyaan, hubungi saya di Telegram:

<br>

<a href="https://t.me/hail_ct0S" target="_blank">
  <img src="https://img.shields.io/badge/Telegram-@hail_ct0S-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram: @hail_ct0S">
</a>
