# 4-KUN: Zaifliklar va Hujum vektorlari

**Mavzu:** Vulnerability nima, CVE/CVSS tizimi, attack vectors  
**Maqsad:** Talabalar zaifliklarni qidirish va baholashni o'rganishi  
**Kerakli materiallar:** Internet, cve.mitre.org, nvd.nist.gov

---

## DARS BOSHIDA (5 daqiqa)

### Salomlashish va o'tgan dars takrorlash

> "Salom! Kechagi mavzu - **Threat Actors**. 
> - Eng xavfli hujumchi turi qaysi? (APT)
> - Insider Threat turlari qanday? (Malicious, Negligent, Compromised)
> - MITRE ATT&CK nima?
> 
> Yaxshi! Bugun biz **dushman qanday yo'l bilan kiradi**ni o'rganamiz."

---

## 1-SOAT: Nazariy qism (45 daqiqa)

### Kirish: Vulnerability nima? (5 daq)

> **O'qituvchi:**  
> "Esda tutaylik:
> - **Threat** = tahdid (xaker)  
> - **Vulnerability** = zaiflik (eshik ochiq)
> - **Risk** = xatar = ikkalasi birga"

**Doskaga yozing:**

```
VULNERABILITY (Zaiflik) TURLARI:

┌─────────────────────────────────────┐
│ 1. SOFTWARE VULNERABILITIES         │
│    - Bug'lar, kodlash xatolari      │
│    - Buffer overflow                │
│    - SQL Injection                  │
│                                      │
│ 2. CONFIGURATION ERRORS              │
│    - Default parollar                │
│    - Open ports                      │
│    - Misconfigured firewall          │
│                                      │
│ 3. HUMAN VULNERABILITIES             │
│    - Zaif parollar                   │
│    - Phishing'ga tushish             │
│    - Social engineering              │
│                                      │
│ 4. PHYSICAL VULNERABILITIES          │
│    - Ochiq server xonasi             │
│    - USB topib ulash                 │
└─────────────────────────────────────┘
```

### CVE - Common Vulnerabilities and Exposures (10 daq)

> **O'qituvchi:**  
> "**CVE** - bu zaifliklarning **xalqaro raqamlash tizimi**. Har bir zaiflik o'z noyob raqamiga ega."

**CVE format:**

```
CVE-YYYY-NNNN

CVE-2017-0144  →  EternalBlue (WannaCry ishlatdi)
CVE-2014-0160  →  Heartbleed (OpenSSL)
CVE-2021-44228 →  Log4Shell (Log4j)
CVE-2017-5638  →  Apache Struts (Equifax buzildi)
```

**Saytlar:**
- **cve.mitre.org** - asosiy CVE database
- **nvd.nist.gov** - kengaytirilgan ma'lumot
- **exploit-db.com** - haqiqiy exploit kodlari (oson topish uchun)

**Real misol: Heartbleed (CVE-2014-0160)**

> "**Heartbleed** - bu OpenSSL'dagi **catastrophic** zaiflik edi. 
> 
> **Tarixchasi:** 2014-aprel. Tadqiqotchi OpenSSL kodida xatolik topdi - server xotirasidan **64 KB** ma'lumotni qaytarib berardi. Bu ma'lumotda **parollar, xususiy kalitlar** bo'lishi mumkin edi.
> 
> **Zarar:**
> - 500,000 web sayt zaif edi
> - Bank, hukumat saytlari ham
> - Hech kim hujum bo'lganini bilmasdi (loglar yo'q!)
> 
> **Saboq:** Open Source kod ham xato bo'lishi mumkin. Audit qilish kerak."

### CVSS - Common Vulnerability Scoring System (10 daq)

> **O'qituvchi:**  
> "**CVSS** - bu zaiflik **qanchalik xavfli** ekanligini bahosi. 0 dan 10 gacha."

**CVSS shkalasi:**

```
┌──────────┬──────────────┬──────────────────┐
│ BALL     │ DARAJASI     │ TA'RIF           │
├──────────┼──────────────┼──────────────────┤
│ 0.0      │ None         │ Xavfsiz          │
│ 0.1-3.9  │ LOW          │ Past xatar       │
│ 4.0-6.9  │ MEDIUM       │ O'rta xatar      │
│ 7.0-8.9  │ HIGH         │ Yuqori xatar     │
│ 9.0-10.0 │ CRITICAL     │ KRITIK!          │
└──────────┴──────────────┴──────────────────┘
```

**CVSS qanday hisoblanadi?**

```
ATTACK VECTOR (AV):
  N - Network (eng xavfli)
  A - Adjacent
  L - Local
  P - Physical

ATTACK COMPLEXITY (AC):
  L - Low (oson)
  H - High (qiyin)

PRIVILEGES REQUIRED (PR):
  N - None (kirish kerak emas)
  L - Low
  H - High

USER INTERACTION (UI):
  N - None
  R - Required

CIA Impact (qanday ta'sir):
  H - High
  L - Low
  N - None
```

**Misol: Log4Shell CVSS skorini ko'rib chiqamiz**

> "**Log4Shell (CVE-2021-44228)** - 2021-yil dekabrining eng katta zaifligi
> 
> ```
> CVSS: 10.0 (CRITICAL!)
> Vector: AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H
> 
> Tarjima:
> - Network orqali (AV:N) - Internet'dan
> - Oson (AC:L) - oddiy textbox'ga zararli matn yozish
> - Kirish kerak emas (PR:N) 
> - User aralashishi shart emas (UI:N)
> - Confidentiality: HIGH
> - Integrity: HIGH  
> - Availability: HIGH
> ```
> 
> Bu **eng yomon stsenariy**! Shuning uchun butun internet sahniga 'butun dunyo Log4j ishlatadi' xabari kelgan."

### Zero-Day Vulnerabilities (5 daq)

> **O'qituvchi:**  
> "**Zero-Day** - bu zaiflik **hech kim** bilmaydi. Hatto dasturchi ham. **0 kun** o'tgan, patch yo'q.
> 
> Bu **eng xavfli** turdagi zaiflik!"

```
┌─────────────────────────────────────┐
│ ZERO-DAY HAYOT TSIKLI                │
├─────────────────────────────────────┤
│ 1. Zaiflik mavjud (hech kim bilmas) │
│ 2. Xaker topadi (hech kim hali bil. │
│    masdan)                           │
│ 3. Xaker exploit yozadi             │
│ 4. Hujum boshlanadi                  │
│ 5. Vendor topadi va patch chiqaradi │
│ 6. Endi "1-day" yoki "n-day"         │
└─────────────────────────────────────┘
```

**Zero-Day bozori:**

> "Sizni hayron qoldiradi: **Zero-day exploitlar sotiladi!**
> 
> - **Pegasus** (NSO Group) - hukumatlarga sotiladi
> - **Zerodium** sayti - 1 ta iOS zero-day uchun **$2,500,000** to'laydi!
> - Davlatlar uchun bu **strategik qurol**
> 
> Saboq: Tizimingizni doimo yangilang. Lekin zero-day'larga qarshi - **defense in depth** kerak."

### Attack Vectors - Hujum yo'llari (10 daq)

> **O'qituvchi:**  
> "**Attack Vector** - bu xaker tizimga kiradigan **yo'l**. Shuncha attack vector turlari bor:"

```
HUJUM VEKTORLARI (8 ta asosiy):

1. PHISHING / EMAIL
   ┌─────────────────────────────────┐
   │ Email orqali zararli link       │
   │ yoki fayl yuborish              │
   └─────────────────────────────────┘
   Ulush: 90% hujumlarning boshlanishi!

2. WEB APPLICATION
   ┌─────────────────────────────────┐
   │ SQL Injection, XSS, CSRF        │
   └─────────────────────────────────┘

3. MALWARE
   ┌─────────────────────────────────┐
   │ Virus, Trojan, Ransomware       │
   └─────────────────────────────────┘

4. DRIVE-BY DOWNLOAD
   ┌─────────────────────────────────┐
   │ Sayt ochilishida avtomatik      │
   │ virus yuklab olinadi            │
   └─────────────────────────────────┘

5. USB / REMOVABLE MEDIA
   ┌─────────────────────────────────┐
   │ Stuxnet shu yo'l bilan kirgan   │
   └─────────────────────────────────┘

6. SUPPLY CHAIN
   ┌─────────────────────────────────┐
   │ Yetkazib beruvchi orqali        │
   │ (SolarWinds misoli)             │
   └─────────────────────────────────┘

7. INSIDER
   ┌─────────────────────────────────┐
   │ Ichki xodim                     │
   └─────────────────────────────────┘

8. UNPATCHED SYSTEMS
   ┌─────────────────────────────────┐
   │ Eski, yangilanmagan dasturlar   │
   └─────────────────────────────────┘
```

### Attack Surface - Hujum maydoni (5 daq)

> **O'qituvchi:**  
> "**Attack Surface** - bu sizning tizimingiz **qancha 'eshik'** tashqariga ochilgan."

**Misol:**

```
KICHIK ATTACK SURFACE:           KATTA ATTACK SURFACE:
┌─────────────┐                  ┌─────────────────┐
│ 1 ta server │                  │ 100 ta server    │
│ 2 port ochiq│                  │ 50 port ochiq    │
│ 1 ilova     │                  │ 30 ilova         │
│ 5 user      │                  │ 5000 user        │
│             │                  │ Ko'p o'rni VPN'l.│
└─────────────┘                  └─────────────────┘
   XAVFSIZROQ                       XAVFLI!
```

**Maslahat:**

> "**Attack Surface'ni kichraytiring!**
> - Keraksiz portlarni yoping
> - Ishlatilmaydigan ilovalarni o'chiring
> - Eski user akkauntlarini olib tashlang
> - Faqat zarurini ochiq qoldiring"

---

## TANAFFUS (10 daqiqa)

---

## 2-SOAT: Amaliy qism (45 daqiqa)

### Mashq 1: CVE Database bilan ishlash (15 daq)

> **O'qituvchi:**  
> "Endi siz CVE Database'ni o'zingiz ishlatib ko'rasiz."

**Vazifa 1:** Brauzeringizda **nvd.nist.gov** ni oching.

```
QADAMLAR:
1. https://nvd.nist.gov ga kiring
2. "Search Vulnerabilities" tugmasini bosing
3. Quyidagi CVE'larni qidiring va ma'lumot oling:
```

**Talabalarga vazifa:**

```
┌──────────────────┬──────┬──────┬─────────┐
│ CVE              │ CVSS │ YIL  │ MAHSULOT│
├──────────────────┼──────┼──────┼─────────┤
│ CVE-2017-0144    │ ?    │ ?    │ ?       │
│ CVE-2014-0160    │ ?    │ ?    │ ?       │
│ CVE-2021-44228   │ ?    │ ?    │ ?       │
│ CVE-2019-0708    │ ?    │ ?    │ ?       │
│ CVE-2020-1472    │ ?    │ ?    │ ?       │
└──────────────────┴──────┴──────┴─────────┘
```

(15 daqiqa - talabalar to'ldiradi, keyin birga tekshirasiz)

**To'g'ri javoblar:**

```
CVE-2017-0144  → 8.1 HIGH | 2017 | Windows SMB (EternalBlue)
CVE-2014-0160  → 7.5 HIGH | 2014 | OpenSSL (Heartbleed)
CVE-2021-44228 → 10.0 CRIT| 2021 | Apache Log4j (Log4Shell)
CVE-2019-0708  → 9.8 CRIT | 2019 | Windows RDP (BlueKeep)
CVE-2020-1472  → 10.0 CRIT| 2020 | Netlogon (Zerologon)
```

### Mashq 2: O'z kompyuteringizni tekshirish (15 daq)

> **O'qituvchi:**  
> "Endi siz **o'z kompyuteringizdagi** zaifliklarni tekshirasiz."

#### Windows uchun:

```powershell
# PowerShell'ni Administrator sifatida oching
# O'rnatilgan dasturlarni ro'yxat oling:
Get-WmiObject -Class Win32_Product | Select-Object Name, Version
```

#### Linux uchun:

```bash
# O'rnatilgan paketlar va versiyalari
dpkg -l | head -50

# Kernel versiyasi
uname -a

# Eskirgan paketlar
apt list --upgradable
```

**Vazifa:**

> "1. O'z kompyuteringizdagi 5 ta dasturni tanlang
> 2. Har biri uchun versiyani aniqlang
> 3. **nvd.nist.gov** da qidiring (masalan: 'Chrome 95')
> 4. Topganlaringizni daftaringizga yozing"

### Mashq 3: Attack Surface Mapping (15 daq)

> **O'qituvchi:**  
> "Endi siz **attack surface**'ni xarita qilasiz."

**Sizning kompaniyangiz uchun xarita chizing:**

```
┌─────────────────────────────────────────┐
│           ATTACK SURFACE MAP             │
├─────────────────────────────────────────┤
│                                          │
│  INTERNET                                │
│      │                                   │
│      ├─ Web Sayt (port 443)             │
│      ├─ Email Server (port 25)          │
│      ├─ FTP (port 21) ← Kerakmi?        │
│      ├─ SSH (port 22)                   │
│      └─ VPN                              │
│                                          │
│  ICHKI TARMOQ                            │
│      ├─ AD Server                        │
│      ├─ File Server                      │
│      ├─ Database                         │
│      └─ Printerlar                       │
│                                          │
│  CLOUD                                   │
│      ├─ AWS S3                           │
│      └─ Office 365                       │
│                                          │
│  ENDPOINT                                │
│      ├─ 50 ta kompyuter                  │
│      ├─ 30 ta telefon                    │
│      └─ Mehmon Wi-Fi                     │
└─────────────────────────────────────────┘
```

**Topshiriq:**

> "Har biringiz o'zingizning kompaniyangiz uchun shunday xarita chizing. Keyin har bir nuqta uchun:
> 
> 1. Bu kerakmi?
> 2. Yangilanganmi?
> 3. Kuchli parol bilan himoyalanganmi?
> 4. Qanday qilib hujum bo'lishi mumkin?"

(10 daqiqa, keyin 2 talaba taqdim qiladi)

---

## DARS YAKUNI (5 daqiqa)

### Bugungi xulosa

> "Bugun o'rgandik:
> 1. **Vulnerability turlari** - Software, Config, Human, Physical
> 2. **CVE** - zaifliklarning xalqaro raqamlash tizimi
> 3. **CVSS** - zaifliklar bahosi (0-10)
> 4. **Zero-Day** - eng xavfli zaifliklar
> 5. **Attack Vectors** - 8 ta asosiy hujum yo'li
> 6. **Attack Surface** - hujum maydoni
> 
> **Eslatma:** Sizning tizimingizdagi har bir 'eshik' - bu potentsial zaiflik!"

### Uy vazifasi

> "1. **CVE qidiruv:** Sizning ish joyingizda ishlatiladigan **5 ta dastur** uchun (server OS, web server, DB, email server) ulardagi oxirgi 1 yildagi CVE'larni toping. Jadvalga yozing.
> 
> 2. **Attack Surface:** O'z kompaniyangiz uchun xarita chizing va eng zaif joyni belgilang.
> 
> 3. **Maqola o'qish:** OWASP Top 10 - to'liq ko'rib chiqing"

### Keyingi darsda

> "Ertaga **Kriptografiya** mavzusi! Shifrlash, hashing, raqamli imzo - hammasini o'rganamiz!"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Diqqat
- **CVSS** ni juda chuqur tushuntirmang - faqat asosiy ball bilishlari yetarli
- **Zero-day** mavzusi qiziqarli, lekin ko'p vaqt sarflamang
- **Live demo:** nvd.nist.gov saytini ko'rsating

### Foydali resurslar
- exploit-db.com - real exploitlar (faqat o'qish uchun!)
- cvedetails.com - oson o'qiladigan CVE ma'lumotlari
- Vulners.com - CVE qidiruv tizimi
