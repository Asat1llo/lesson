# 7-KUN: 1-hafta yakuni va Test

**Mavzu:** O'tilgan mavzularni takrorlash, yakuniy test, mini loyiha  
**Maqsad:** 1-hafta materiallarini mustahkamlash va talabalar darajasini baholash  
**Kerakli materiallar:** Test savollari (printerda yoki digital), proyektor

---

## DARS BOSHIDA (5 daqiqa)

### Salomlashish

> "Salom! Bugun **1-haftaning yakuniy kuni**! Sizlar 6 kun mobaynida juda ko'p narsalarni o'rgandilar:
> 
> 1. Kiberxavfsizlik nima va CIA Triad
> 2. Xavfsizlik domenlari
> 3. Tahdidlar va hujumchilar
> 4. Zaifliklar va CVE
> 5. Kriptografiya
> 6. Authentication va Authorization
> 
> Bugun:
> - 1-soat: Tezkor takrorlash + Test
> - 2-soat: Mini amaliy loyiha"

---

## 1-SOAT: Takrorlash va Test (45 daqiqa)

### Tezkor takrorlash (15 daq)

> **O'qituvchi (savol-javob shaklida):**

#### Asosiy tushunchalar bo'yicha:

```
1. CIA Triad - 3 ta harf nima?
   C = Confidentiality (Maxfiylik)
   I = Integrity (Yaxlitlik)
   A = Availability (Mavjudlik)

2. Risk formulasi?
   Risk = Threat × Vulnerability

3. Kiberxavfsizlikning 3 ustuni?
   Texnologiya + Jarayon + Insonlar
```

#### Hujumchilar:

```
4. 6 ta hujumchi turini ayting?
   - Script Kiddie
   - Hacktivist
   - Cybercriminal
   - APT/Nation-State
   - Insider Threat
   - Competitor

5. Eng xavfli hujumchi turi?
   APT (Nation-State)

6. Insider Threat 3 ta turi?
   - Malicious
   - Negligent
   - Compromised
```

#### Zaifliklar:

```
7. CVE nima?
   Common Vulnerabilities and Exposures
   - zaifliklarning xalqaro raqamlash tizimi

8. CVSS 9.5 - bu qanday daraja?
   CRITICAL

9. Zero-Day nima?
   Hech kim bilmaydigan zaiflik (patch yo'q)

10. Heartbleed CVE raqami?
    CVE-2014-0160
```

#### Kriptografiya:

```
11. Symmetric va Asymmetric farqi?
    - Symmetric: 1 kalit
    - Asymmetric: 2 kalit (public + private)

12. AES-256 - bu nima?
    Symmetric encryption algoritmi (256 bit)

13. SHA-256 nima?
    Hash algoritm (bir tomonlama)

14. Hashing va Encryption farqi?
    Hashing: bir tomonlama
    Encryption: ikki tomonlama
```

#### Authentication:

```
15. AAA?
    Authentication, Authorization, Accounting

16. 3 ta auth factor?
    - Know (parol)
    - Have (telefon)
    - Are (barmoq izi)

17. MFA va 2FA?
    Multi/Two Factor Authentication

18. Least Privilege qoidasi?
    Faqat zarur huquqlarni berish
```

### Yakuniy TEST (30 daq)

> **O'qituvchi:**  
> "Endi yakuniy test. **30 daqiqa**, **30 ta savol**. Daftarlarni bekiting!"

---

## 1-HAFTA YAKUNIY TESTI

### A qism: Test savollari (1 ball har biri = 20 ball)

**1.** CIA Triad'da 'I' qaysi so'zni anglatadi?
- a) Information
- b) Internet
- c) Integrity ✓
- d) Identification

**2.** Quyidagilardan qaysi biri **Symmetric encryption** algoritm?
- a) RSA
- b) AES ✓
- c) ECC
- d) DSA

**3.** Risk formulasi qaysi?
- a) Risk = Threat + Vulnerability
- b) Risk = Threat × Vulnerability ✓
- c) Risk = Asset × Threat
- d) Risk = Threat - Vulnerability

**4.** Eng xavfli hujumchi turi:
- a) Script Kiddie
- b) Hacktivist
- c) APT / Nation-State ✓
- d) Cybercriminal

**5.** SHA-256 ning chiqishi necha bit?
- a) 128
- b) 256 ✓
- c) 512
- d) 1024

**6.** Quyidagilardan qaysi biri **2FA factor** EMAS?
- a) Parol
- b) SMS kod
- c) Barmoq izi
- d) Foydalanuvchi nomi ✓

**7.** WannaCry qaysi yili sodir bo'lgan?
- a) 2015
- b) 2017 ✓
- c) 2019
- d) 2021

**8.** CVSS shkalasida 'CRITICAL' bo'lishi uchun ball qancha?
- a) 5.0+
- b) 7.0+
- c) 9.0+ ✓
- d) 10.0 only

**9.** OWASP Top 10 da 1-o'rinda nima?
- a) SQL Injection
- b) XSS
- c) Broken Access Control ✓
- d) CSRF

**10.** Zero-Day vulnerability nima?
- a) Bir kun ishlamaydigan tizim
- b) Hech kim bilmaydigan zaiflik ✓
- c) Birinchi kunda topilgan zaiflik
- d) Eng eski zaiflik

**11.** Public Key bilan shifrlangan ma'lumotni nima bilan deshifrlash mumkin?
- a) Public Key
- b) Private Key ✓
- c) Symmetric Key
- d) Hash

**12.** Stuxnet qaysi mamlakatga qarshi yo'naltirilgan edi?
- a) Iroq
- b) Eron ✓
- c) Suriya
- d) Liviya

**13.** SolarWinds hujumi qaysi turdagi hujum edi?
- a) DDoS
- b) Phishing
- c) Supply Chain ✓
- d) Ransomware

**14.** SSO ning to'liq nomi?
- a) Single Sign-On ✓
- b) Secure Sign Operation
- c) System Security Online
- d) Single Server Operation

**15.** Quyidagilardan qaysi biri **eng xavfli** parol?
- a) MyName2024!
- b) password ✓
- c) Tr0ub4dor&3
- d) horse-battery-staple

**16.** Linux'da `chmod 755` nima anglatadi?
- a) rwxr-xr-x ✓
- b) rwxrwxr-x
- c) rw-r--r--
- d) rwx------

**17.** APT 'P' harfi qaysi so'zga to'g'ri keladi?
- a) Public
- b) Persistent ✓
- c) Private
- d) Penetration

**18.** SSL/TLS qaysi protokolda ishlatiladi?
- a) FTP
- b) HTTPS ✓
- c) Telnet
- d) HTTP

**19.** Insider Threat'ning qaysi turi - xodim ataylab zarar yetkazsa?
- a) Negligent
- b) Compromised
- c) Malicious ✓
- d) Accidental

**20.** Hash funksiyasining xususiyati qaysi?
- a) Bir tomonlama ✓
- b) Qaytarilishi mumkin
- c) Ikki kalit ishlatadi
- d) Faqat parolda ishlatiladi

### B qism: To'g'ri/noto'g'ri (1 ball = 5 ball)

**21.** SMS-based 2FA - eng xavfsiz autentifikatsiya turi.  
Javob: **Noto'g'ri** (SIM Swap xavfli)

**22.** MD5 - hozirgi kunda parol uchun yaxshi hash funksiya.  
Javob: **Noto'g'ri** (eskirgan, buzilgan)

**23.** Cloud Provider mijozning ma'lumotlari uchun **to'liq** mas'ul.  
Javob: **Noto'g'ri** (Shared Responsibility)

**24.** WPA3 - WPA2'dan xavfsizroq.  
Javob: **To'g'ri**

**25.** Least Privilege - foydalanuvchiga maksimal huquq berishni anglatadi.  
Javob: **Noto'g'ri** (eng KAM huquq)

### C qism: Qisqa javob (1-2 jumla, 1 ball = 5 ball)

**26.** Sizning fikringizcha, kompaniyangizdagi eng katta zaiflik nima va nima uchun?

**27.** Phishing email'ni qanday aniqlay olasiz? 3 ta belgi yozing.

**28.** Nega oddiy parol o'rniga **passphrase** ishlatish yaxshi?

**29.** Insider Threat'ni oldini olish uchun 3 ta chora?

**30.** Sizning kompaniyangizda CIA Triad'dan qaysi biri eng muhim va nega?

---

## TANAFFUS (10 daqiqa)

> **Tanaffus paytida:** Talabalar testlarni topshiradi, siz natijalarni hisoblay boshlaysiz.

---

## 2-SOAT: Mini amaliy loyiha (45 daqiqa)

### Loyiha tavsifi (5 daq)

> **O'qituvchi:**  
> "Endi 1-haftaning yakuniy loyihasini bajarasiz. Bu - **Xavfsizlik siyosati** hujjatining 1-versiyasini yozish."

**Loyiha topshirig'i:**

```
LOYIHA: Kichik IT kompaniya uchun 
        Kiberxavfsizlik Siyosati (Security Policy)

KOMPANIYA: "TechUz LLC"
- 30 ta xodim
- Web ilovalar yaratadi
- AWS cloud ishlatadi
- Office 365 (email, fayllar)
- Mijozlar: lokal va xalqaro

TOPSHIRIQ: 5 sahifalik 'Security Policy' yozing
```

### Loyiha shabloni (35 daq)

> "Quyidagi shablon asosida yozing:"

#### 1-bo'lim: Kirish

```markdown
# TechUz LLC - Kiberxavfsizlik Siyosati

## 1. Maqsad
Bu hujjat TechUz LLC kompaniyasi xodimlari uchun 
kiberxavfsizlik talablarini belgilaydi.

## 2. Qo'llanish doirasi
Barcha xodimlar, kontraktorlar va tashriflashlar.
```

#### 2-bo'lim: Parol siyosati

```markdown
## 3. Parol talablari

3.1 Parol uzunligi:
    - Kamida 12 belgi
    - Admin akkauntlar uchun 16+ belgi

3.2 Murakkablik:
    - Katta va kichik harflar
    - Raqamlar
    - Maxsus belgilar (!@#$%)

3.3 Yangilash:
    - Har 90 kunda
    - Oxirgi 5 ta parol qayta ishlatilmasin

3.4 Ko'p faktorli autentifikatsiya:
    - Barcha xodimlar uchun MAJBURIY
    - Asosan: Google Authenticator
    - Admin uchun: YubiKey
```

#### 3-bo'lim: Foydalanuvchi siyosati

```markdown
## 4. Foydalanuvchi javobgarligi

4.1 Xodimlar quyidagilarni qilmasligi kerak:
    - Parolni boshqa xodim bilan ulashish
    - Parolni yozib qo'yish
    - Ish kompyuterida shaxsiy email kirish (faqat kompaniya)
    - USB topib ulash
    - Ofisdagi kompyuterga shaxsiy fayllar yuklash

4.2 Phishing oldini olish:
    - Shubhali email'ga javob bermaslik
    - Linkni bosishdan oldin URL'ni tekshirish
    - Shubhali email'ni IT bo'limga jo'natish
```

#### 4-bo'lim: Tarmoq xavfsizligi

```markdown
## 5. Tarmoq xavfsizligi

5.1 Wi-Fi:
    - Mehmon va xodim Wi-Fi ALOHIDA tarmoqda
    - WPA3 shifrlash
    - Har 6 oyda parol o'zgartirish

5.2 VPN:
    - Uydan ishlasa - VPN majburiy
    - OpenVPN yoki WireGuard

5.3 Firewall:
    - Faqat zarur portlar ochiq
    - SSH faqat statik IP'dan
    - 80 va 443 ochiq (web)
```

#### 5-bo'lim: Ma'lumot himoyasi

```markdown
## 6. Ma'lumot himoyasi

6.1 Klassifikatsiya:
    - PUBLIC: marketing materiallari
    - INTERNAL: ichki hujjatlar
    - CONFIDENTIAL: mijoz ma'lumotlari
    - RESTRICTED: moliyaviy, HR ma'lumotlar

6.2 Backup:
    - 3-2-1 qoida
    - Har kuni avtomatik
    - Oyiga 1 marta tiklash testi

6.3 Shifrlash:
    - Diskda: BitLocker / LUKS
    - Transferda: TLS 1.3
    - Email: S/MIME yoki PGP
```

#### 6-bo'lim: Hodisaga javob

```markdown
## 7. Incident Response

7.1 Hodisa belgilari:
    - Notanish login urinishlari
    - Kompyuter sekinlashishi
    - Shubhali email
    - Antivirus signal beradi

7.2 Hodisa sodir bo'lganda:
    1. KOMPYUTERNI O'CHIRMANG (logs yo'qoladi)
    2. Tarmoqdan uzing (kabel chiqarib oling)
    3. IT bo'limga zudlik bilan xabar bering
    4. Hech narsani o'zingiz tuzatishga urinmang

7.3 Aloqa:
    - IT bo'lim: +998 90 XXX XX XX
    - Email: security@techuz.uz
```

#### 7-bo'lim: Jazo va auditi

```markdown
## 8. Buzilish va jazo

8.1 Buzilishlar darajalari:
    - Engil: ogohlantirish
    - O'rtacha: yozma ogohlantirish
    - Og'ir: hisob to'xtatilishi
    - Juda og'ir: ishdan haydash

8.2 Audit:
    - Har 6 oyda ichki audit
    - Har yili tashqi audit
    - Penetration testing yiliga 1 marta
```

### Loyiha taqdimoti (5 daq)

> **O'qituvchi:**  
> "Endi 1-2 talaba o'z loyihasini tezkor taqdim qiladi. Boshqalar - tinglang va savol bering."

(2 ta talaba taqdim qiladi - har biri 2 daqiqa)

---

## DARS YAKUNI (5 daqiqa)

### 1-hafta xulosasi

> "Tabriklayman! 1-haftani yakunladingiz. Sizlar quyidagilarni o'rgandingiz:
> 
> ✓ Kiberxavfsizlikning asosiy tushunchalari
> ✓ Tahdidlar va hujumchilar dunyosi
> ✓ Zaifliklarni topish va baholash
> ✓ Kriptografiya asoslari
> ✓ Authentication va Authorization
> 
> Bu - **fundament**! Endi kelajakdagi mavzular ustiga quramiz."

### Test natijalari

> "Test natijalarini ertaga e'lon qilaman. Buyuk Britaniya talabalik standartiga ko'ra:
> - 90+ ball: A'lo
> - 75-89: Yaxshi
> - 60-74: Qoniqarli
> - 60 dan past: Qaytadan o'qish kerak
> 
> Hech kim qo'rqmang - bu birinchi hafta!"

### Uy vazifasi

> "Dam olish kuni:
> 1. Test natijalarini kuting
> 2. Loyihani **5 sahifaga to'liq** yozing
> 3. Dam oling - dushanba qiyin kun bo'ladi!"

### Keyingi haftada

> "Dushanba kuni biz **2-haftani** boshlaymiz - **Tarmoq xavfsizligi**! 
> - Wireshark
> - Nmap
> - Firewall
> - VPN
> - Wi-Fi xavfsizligi
> 
> Tayyorgarlik:
> - Wireshark va Nmap o'rnating
> - Kali Linux yoki Ubuntu VM tayyor turing"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Test bo'yicha
- Test natijalarini **30 ball** qilib hisoblang (20 + 5 + 5)
- 60 ball - o'tish chizig'i
- Yomon ball olganlar bilan **alohida suhbatlashing**
- Yaxshi ball olganlarni maqtang

### Loyihani baholash
```
Baholash mezonlari (5 ball):
- To'liqligi (1 ball)
- Aniqligi (1 ball)
- Amaliyligi (1 ball)
- Tushunarliligi (1 ball)
- Original yondashuv (1 ball)
```

### Talabalar bilan suhbat
- Har bir talabaga **shaxsiy fikr-mulohaza** bering
- Kuchli va zaif tomonlarini ayting
- Keyingi haftada nimaga e'tibor berishni tushuntiring
