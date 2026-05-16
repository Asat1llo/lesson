# 3-HAFTA: Tizim va Server Xavfsizligi (15-21 kunlar)

## 15-KUN: Operatsion tizim xavfsizligi - Linux
**Maqsad:** Linux serverlarini himoya qilishni o'rganish.

### 1-soat: Nazariy qism
- Linux xavfsizlik arxitekturasi
- Foydalanuvchi va guruh boshqaruvi
- File permissions (chmod, chown)
- SUID, SGID, Sticky bit
- SELinux va AppArmor

### 2-soat: Amaliy qism
- Ubuntu Server'da xavfsiz user yaratish
- SSH konfiguratsiyasini qattiqlashtirish (`/etc/ssh/sshd_config`):
  - Root login o'chirish
  - Port o'zgartirish
  - Key-based authentication
- `fail2ban` o'rnatish va sozlash
- Praktika: Linux server'ni hardening qilish (CIS Benchmark asosida)

---

## 16-KUN: Operatsion tizim xavfsizligi - Windows
**Maqsad:** Windows serverlarini himoya qilish.

### 1-soat: Nazariy qism
- Windows xavfsizlik modeli
- Active Directory asoslari
- Group Policy Objects (GPO)
- Windows Defender va xavfsizlik xususiyatlari
- BitLocker, EFS

### 2-soat: Amaliy qism
- Windows Server'da User va Group boshqaruvi
- GPO orqali parol siyosati o'rnatish
- Windows Update va patch management
- Praktika: Windows Server'ni xavfsizlashtirish

---

## 17-KUN: Patch Management va Yangilanishlar
**Maqsad:** Tizimlarni dolzarb holda saqlash.

### 1-soat: Nazariy qism
- Nima uchun patch management muhim?
- Patch turlari: Security, Critical, Optional
- Patch management jarayoni: Test → Pilot → Production
- WSUS (Windows Server Update Services)
- Linux'da paket boshqaruvi va yangilanishlar

### 2-soat: Amaliy qism
- Ubuntu'da `unattended-upgrades` sozlash
- Windows Update siyosatini GPO orqali boshqarish
- Praktika: Patch management rejasini yozish
- Demo: Eskirgan tizimning zaifligini ko'rsatish

---

## 18-KUN: Backup va Disaster Recovery
**Maqsad:** Ma'lumotlarni yo'qotmaslik strategiyasi.

### 1-soat: Nazariy qism
- Backup turlari: Full, Incremental, Differential
- 3-2-1 Backup qoidasi
- RPO (Recovery Point Objective) va RTO (Recovery Time Objective)
- Disaster Recovery Plan (DRP)
- Business Continuity Plan (BCP)
- Ransomware'dan himoya

### 2-soat: Amaliy qism
- Linux'da `rsync` bilan backup
- `tar` va `cron` orqali avtomatik backup
- Windows'da Volume Shadow Copy
- Praktika: Backup va restore stsenariyini sinab ko'rish

---

## 19-KUN: Endpoint Security va Antivirus
**Maqsad:** Oxirgi qurilmalarni himoya qilish.

### 1-soat: Nazariy qism
- Malware turlari: Virus, Worm, Trojan, Ransomware, Spyware, Rootkit
- Antivirus qanday ishlaydi (Signature-based, Heuristic, Behavior-based)
- EDR (Endpoint Detection and Response)
- XDR (Extended Detection and Response)
- DLP (Data Loss Prevention)

### 2-soat: Amaliy qism
- ClamAV o'rnatish va Linux'da skanerlash
- Windows Defender'ni boshqarish
- Praktika: Test malware (EICAR) bilan antivirusni sinash
- Shubhali fayllarni VirusTotal'da tekshirish

---

## 20-KUN: Web Server va Database xavfsizligi
**Maqsad:** Web va DB serverlarini himoya qilish.

### 1-soat: Nazariy qism
- Web server zaifliklari: Apache, Nginx
- HTTPS sozlash, SSL/TLS sertifikatlari (Let's Encrypt)
- Database xavfsizligi: MySQL, PostgreSQL
- SQL Injection asoslari
- Database backup va shifrlash

### 2-soat: Amaliy qism
- Nginx'da HTTPS sozlash
- Security headers qo'shish (HSTS, CSP, X-Frame-Options)
- MySQL'da xavfsiz konfiguratsiya (`mysql_secure_installation`)
- Praktika: Web server hardening checklist

---

## 21-KUN: 3-hafta yakuni va Amaliy loyiha
**Maqsad:** Server xavfsizligini amalda qo'llash.

### 1-soat: Takrorlash
- Hafta mavzularini takrorlash
- Qiyin joylarni muhokama qilish

### 2-soat: Amaliy loyiha
- **Loyiha:** To'liq xavfsiz Linux server tayyorlash:
  - SSH hardening
  - Firewall sozlamalari
  - Fail2ban
  - Avtomatik yangilanishlar
  - Backup tizimi
  - Monitoring
- Loyihalarni baholash va muhokama
