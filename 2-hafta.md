# 2-HAFTA: Tarmoq Xavfsizligi (8-14 kunlar)

## 8-KUN: Tarmoq asoslari (takrorlash)
**Maqsad:** Tarmoq tushunchalarini xavfsizlik nuqtai nazaridan ko'rib chiqish.

### 1-soat: Nazariy qism
- OSI va TCP/IP modeli takrorlash
- IP adresslar, MAC adresslar, portlar
- TCP, UDP, ICMP protokollari
- DNS, DHCP, ARP qanday ishlaydi
- Har bir protokolning zaifliklari

### 2-soat: Amaliy qism
- Wireshark o'rnatish va tanishtirish
- Tarmoq trafigini kuzatish
- Praktika: ARP, DNS, HTTP paketlarini tahlil qilish

---

## 9-KUN: Firewall va IDS/IPS
**Maqsad:** Tarmoq himoyasi vositalari bilan ishlash.

### 1-soat: Nazariy qism
- Firewall turlari: Packet Filter, Stateful, Application Layer
- Hardware vs Software firewall
- IDS (Intrusion Detection System) va IPS (Intrusion Prevention System)
- DMZ (Demilitarized Zone) tushunchasi
- Next-Generation Firewall (NGFW)

### 2-soat: Amaliy qism
- Linux'da `iptables` bilan ishlash
- `ufw` (Uncomplicated Firewall) sozlash
- Windows Defender Firewall sozlash
- Praktika: Ma'lum portlarni ochish/yopish qoidalari

---

## 10-KUN: VPN va Shifrlangan ulanishlar
**Maqsad:** Xavfsiz uzoqdan ulanish.

### 1-soat: Nazariy qism
- VPN nima va qanday ishlaydi?
- VPN protokollari: OpenVPN, IPSec, WireGuard, L2TP
- Site-to-Site va Remote Access VPN
- SSL/TLS protokoli
- HTTPS qanday ishlaydi?

### 2-soat: Amaliy qism
- OpenVPN server o'rnatish (Ubuntu Server'da)
- Client konfiguratsiyasi
- WireGuard bilan tanishuv
- Praktika: VPN orqali xavfsiz ulanishni sinab ko'rish

---

## 11-KUN: Tarmoq skanerlash va Reconnaissance
**Maqsad:** Tarmoqni tahlil qilish va zaifliklarni topish.

### 1-soat: Nazariy qism
- Reconnaissance turlari: Active va Passive
- Footprinting tushunchasi
- OSINT (Open Source Intelligence)
- Port skanerlash texnikalari

### 2-soat: Amaliy qism
- **Nmap** chuqur o'rganish:
  - `nmap -sS`, `-sT`, `-sU`, `-sV`, `-O`
  - Skript skanerlash (`-sC`, `--script`)
  - Tezlik va aniqlik sozlamalari
- Praktika: Lokal tarmoqni skanerlash (faqat o'z muhitida!)
- Etik masalalar muhokamasi

---

## 12-KUN: Wi-Fi xavfsizligi
**Maqsad:** Simsiz tarmoqlarni himoya qilish.

### 1-soat: Nazariy qism
- Wi-Fi standartlari: 802.11 a/b/g/n/ac/ax
- Shifrlash protokollari: WEP, WPA, WPA2, WPA3
- WPS zaifligi
- Rogue Access Points
- Evil Twin attacks

### 2-soat: Amaliy qism
- `aircrack-ng` to'plamini o'rganish
- Wi-Fi tarmoqlarini skanerlash (`airodump-ng`)
- Demo: WPA2 handshake ushlash (faqat o'z tarmog'ida)
- Praktika: Wi-Fi router'ni xavfsiz sozlash

---

## 13-KUN: Tarmoq monitoringi va Log tahlili
**Maqsad:** Tarmoqdagi shubhali harakatlarni aniqlash.

### 1-soat: Nazariy qism
- SIEM (Security Information and Event Management)
- Log turlari: System, Application, Security, Network
- Syslog protokoli
- Network monitoring vositalari: Nagios, Zabbix, PRTG

### 2-soat: Amaliy qism
- Linux'da log fayllari bilan ishlash (`/var/log/`)
- `journalctl`, `grep`, `awk` bilan log tahlili
- Wireshark bilan shubhali trafikni topish
- Praktika: Brute-force urinishlarini logdan topish

---

## 14-KUN: 2-hafta yakuni va Amaliy loyiha
**Maqsad:** Tarmoq xavfsizligini amalda tatbiq etish.

### 1-soat: Takrorlash va savol-javob
- 2-hafta mavzularini takrorlash
- Qiyin joylarni muhokama qilish

### 2-soat: Amaliy loyiha
- **Loyiha:** Kichik ofis tarmog'i uchun xavfsizlik arxitekturasini loyihalash:
  - Firewall qoidalari
  - VPN konfiguratsiyasi
  - Wi-Fi xavfsizligi
  - Monitoring rejasi
- Loyihalarni taqdim qilish va muhokama
