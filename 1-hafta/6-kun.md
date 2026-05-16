# 6-KUN: Autentifikatsiya va Avtorizatsiya

**Mavzu:** Authentication, Authorization, MFA, SSO, RBAC  
**Maqsad:** Talabalar autentifikatsiya va avtorizatsiyaning farqini tushunishi va kuchli AAA tizimi qura olishi  
**Kerakli materiallar:** Google Authenticator, Linux terminal, slaydlar

---

## DARS BOSHIDA (5 daqiqa)

### Salomlashish va o'tgan dars takrorlash

> "Salom! Kechagi dars - **Kriptografiya**. Tezkor savollar:
> - **Symmetric** va **Asymmetric** farqi nima?
> - **Hashing** shifrlashdan nima bilan farq qiladi?
> - **AES-256** kalit hajmi?
> - **HTTPS** qanday ishlaydi?
> 
> Yaxshi! Bugun **Authentication** va **Authorization** - tizim administratorining **kundalik nonushtasi**."

---

## 1-SOAT: Nazariy qism (45 daqiqa)

### Kirish: Authentication vs Authorization (5 daq)

> **O'qituvchi:**  
> "Eng birinchi narsa - **Authentication** va **Authorization** ni adashtirmang!"

**Doskaga chizing:**

```
┌────────────────────────────────────────────────┐
│ AUTHENTICATION (Auth)                           │
│ "Sen kimsan?"                                   │
│ Misol: Login + parol kirit                     │
└────────────────────────────────────────────────┘

┌────────────────────────────────────────────────┐
│ AUTHORIZATION (AuthZ)                           │
│ "Senga nima ruxsat?"                            │
│ Misol: Sen admin'san, /admin sahifaga kirsang  │
└────────────────────────────────────────────────┘
```

**Hayotiy misol:**

> "Aeroportda:
> - **Authentication** = pasportingizni ko'rsatish ('men shu odamman')
> - **Authorization** = boarding pass ('aynan shu samolyotga chiqishim mumkin')
> 
> Pasport bor, lekin boarding pass'siz - samolyotga kira olmaysiz!"

```
┌─────────────────────────────────────────────┐
│ AAA - 3 ta A                                 │
├─────────────────────────────────────────────┤
│ A - Authentication  (Sen kimsan?)            │
│ A - Authorization   (Nima qila olasan?)      │
│ A - Accounting      (Nima qilding?)  - log   │
└─────────────────────────────────────────────┘
```

### Authentication Factors (10 daq)

> **O'qituvchi:**  
> "**Authentication** uchun 3 ta asosiy 'omil' (factor) bor:"

```
┌─────────────────────────────────────────────┐
│ 3 ta AUTHENTICATION OMILI                    │
├─────────────────────────────────────────────┤
│                                              │
│ 1. SOMETHING YOU KNOW (Bilasan)              │
│    - Parol                                   │
│    - PIN kod                                 │
│    - Maxfiy savol                            │
│                                              │
│ 2. SOMETHING YOU HAVE (Sendasen)             │
│    - Telefon (SMS code)                      │
│    - Token qurilma (RSA SecurID)             │
│    - Smart card                              │
│    - USB security key (YubiKey)              │
│                                              │
│ 3. SOMETHING YOU ARE (Bo'lasen)              │
│    - Barmoq izi                              │
│    - Yuz tanish                              │
│    - Ovoz                                    │
│    - Iris (ko'z)                             │
└─────────────────────────────────────────────┘
```

**Munozara:**

> "Aytingchi, qaysi factor eng kuchli?"

(Talabalar javob beradi)

> "**To'g'ri javob:** Hech bittasi alohida YETARLI EMAS! Eng kuchli - **birga ishlatish**!"

### Multi-Factor Authentication (MFA / 2FA) (10 daq)

> **O'qituvchi:**  
> "**MFA** = **Multi-Factor Authentication** = ikki yoki ko'p factor"

```
┌─────────────────────────────────────────────┐
│ MFA TURLARI                                  │
├─────────────────────────────────────────────┤
│                                              │
│ 1FA: Faqat parol         ← XAVFLI            │
│                                              │
│ 2FA: Parol + SMS kod     ← O'rtacha          │
│      Parol + Authent.    ← Yaxshi            │
│      Parol + USB Key     ← Eng yaxshi        │
│                                              │
│ 3FA: Parol + USB + Bio   ← Maximum xavfsiz   │
└─────────────────────────────────────────────┘
```

**Misol: Bank tizimi**

> "Bank ilovasiga kiring:
> 1. **Login + parol** (something you know)
> 2. **SMS kod** (something you have - telefon)
> 3. **Barmoq izi** (something you are)
> 
> Bu 3FA. Xaker barcha 3 tasini olishi kerak - juda qiyin!"

**Eslatma: SMS xavfli**

> "**OGOHLANTIRISH:** SMS-based 2FA - eng zaif tur!
> 
> **Sabab:** SIM Swap hujum mavjud. Xaker mobil operatorni aldab sizning SIM raqamingizni o'ziga ko'chirishi mumkin.
> 
> **Yaxshi alternativlar:**
> - Google Authenticator
> - Authy
> - Microsoft Authenticator
> - YubiKey (hardware token)"

**Demo: TOTP qanday ishlaydi**

```
TOTP (Time-based One-Time Password):

SHARED SECRET: ABCD1234EFGH5678
+ JOMIY VAQT: 2024-01-15 14:30:00
─────────────────────────────────
HMAC-SHA1 ─►  6 raqamli kod: 482931

Har 30 soniyada yangi kod!

Server va telefon - bir xil hisoblaydi
Xaker secret'ni bilmasa - kod yarata olmaydi
```

### Parol siyosati (10 daq)

> **O'qituvchi:**  
> "Tizim administratorining asosiy javobgarliklaridan biri - **parol siyosati**."

**Yaxshi parol qanday bo'ladi?**

```
┌─────────────────────────────────────────────┐
│ KUCHLI PAROL TALABLARI                       │
├─────────────────────────────────────────────┤
│ ✓ Kamida 12 belgi                           │
│ ✓ Katta va kichik harflar (Aa)              │
│ ✓ Raqamlar (123)                            │
│ ✓ Maxsus belgilar (!@#$%)                   │
│ ✓ Lug'atda yo'q so'z                        │
│ ✓ Boshqa joyda ishlatilmagan                │
│ ✗ Shaxsiy ma'lumot YO'Q                     │
│ ✗ "12345", "qwerty" - YO'Q                  │
└─────────────────────────────────────────────┘
```

**Parolni buzish vaqti:**

```
┌────────────────────────┬────────────────────┐
│ PAROL                  │ BUZISH VAQTI       │
├────────────────────────┼────────────────────┤
│ 12345                  │ Bir lahzada        │
│ qwerty                 │ Bir lahzada        │
│ password123            │ < 1 soniya         │
│ MyName2024             │ 5 daqiqa           │
│ MyN@me2024             │ 1 soat             │
│ MyN@me!2024            │ 1 kun              │
│ Tr0ub4dor&3            │ 3 yil              │
│ correct horse battery  │ 550 yil            │
│ K7$mP9!qZ@vN3xY        │ Trillion yil       │
└────────────────────────┴────────────────────┘
```

> "Eng yaxshi yondashuv - **passphrase**. 4 ta tasodifiy so'zni birlashtiring:
> - 'Olma Daryo Quyosh Mashina'
> - Eslab qolish oson, buzish qiyin"

**Parol manager - eng yaxshi yechim:**

```
┌─────────────────────────────────────────────┐
│ PAROL MANAGERS                               │
├─────────────────────────────────────────────┤
│ • Bitwarden    (BEPUL, open source)         │
│ • 1Password    (pulli, eng yaxshi)          │
│ • LastPass     (bepul, lekin buzilgan!)     │
│ • KeePass      (offline, bepul)             │
└─────────────────────────────────────────────┘
```

### Single Sign-On (SSO) (5 daq)

> **O'qituvchi:**  
> "**SSO** - **bitta marta** kirib, **hamma joyda** ishlatish."

```
SSO (Single Sign-On):

ODDIY YONDASHUV:               SSO:
┌─────────────┐               ┌─────────────┐
│ Email login │               │             │
│ Slack login │               │ Google      │
│ JIRA login  │               │ Workspace   │ ← BIR MARTA
│ AWS login   │               │ Login       │
│ Office login│               │             │
│ ...         │               └─────────────┘
└─────────────┘                      │
                                     ▼
                              [Email] [Slack]
                              [JIRA]  [AWS]
                              [Office]
```

**SSO protokollari:**
- **SAML 2.0** - eski, korporativ
- **OAuth 2.0** - zamonaviy, "Login with Google"
- **OpenID Connect** - OAuth ustiga authentication
- **Kerberos** - Active Directory

**Afzalliklari:**
- Foydalanuvchi qulayligi
- Xavfsizlik (kuchli auth bir joyda)
- Markaziy boshqaruv

**Kamchilik:**
- "**Single Point of Failure**" - SSO buzilsa, hammasi buziladi!

### Authorization Models (5 daq)

> **O'qituvchi:**  
> "Endi **Authorization** modellarini ko'ramiz:"

#### 1. RBAC (Role-Based Access Control)

```
RBAC:
USERS ──► ROLES ──► PERMISSIONS

Misol:
Ali        ──► Admin       ──► Hammasi
Vali       ──► Developer   ──► Code, deploy
Salim      ──► User        ──► Faqat o'qish
Karim      ──► Guest       ──► Public sahifa
```

#### 2. ABAC (Attribute-Based)

```
ABAC: Atributlarga asoslangan
- Vaqt: Faqat 9-18 da kirish
- Joylashuv: Faqat ofisda
- Qurilma: Faqat korporativ laptop
- IP: Faqat O'zbekistondan
```

#### 3. MAC (Mandatory) va DAC (Discretionary)

```
MAC: Hukumat darajasi
- "Top Secret", "Secret", "Confidential"
- Foydalanuvchi o'zgartira olmaydi

DAC: Linux/Windows fayl ruxsatlari
- Egasi o'zgartira oladi
- chmod 755 file.txt
```

### Principle of Least Privilege (5 daq)

> **O'qituvchi:**  
> "**Eng muhim qoida:** **Least Privilege** - eng kam huquq.
> 
> Ya'ni: **Foydalanuvchiga FAQAT ZARUR huquqlarni bering. Bittasi ham ortiqcha emas!**"

**Yomon misol:**

```
SCENARIO: 
Yangi xodim - Marketing bo'limida
Berildi: Domain Admin huquqi
                ⬇
3 oy keyin u phishing'ga tushdi
                ⬇
Xaker uning kompyuteri orqali butun
Active Directory'ni nazoratga oldi
                ⬇
ZARAR: 100 million dollar
```

**To'g'ri yondashuv:**

```
SCENARIO:
Yangi xodim - Marketing bo'limida
Berildi: faqat Marketing fayllariga
                ⬇
3 oy keyin u phishing'ga tushdi
                ⬇
Xaker faqat Marketing fayllariga kirdi
                ⬇
ZARAR: minimal
```

---

## TANAFFUS (10 daqiqa)

---

## 2-SOAT: Amaliy qism (45 daqiqa)

### Mashq 1: 2FA o'rnatish (15 daq)

> **O'qituvchi:**  
> "Endi har biringiz **Google Authenticator** o'rnatasiz va 2FA yoqasiz."

**Qadamlar:**

```
1. Telefoningizga "Google Authenticator" yoki "Authy"ni
   yuklab oling (App Store / Play Market)

2. Quyidagi servislarda 2FA yoqing:

   GMAIL:
   - myaccount.google.com → Security → 2-Step Verification
   - "Authenticator app" tanlang
   - QR kodni telefon bilan skanerlang

   TELEGRAM:
   - Settings → Privacy and Security → Two-Step Verification
   - Cloud Password yarating

   GITHUB:
   - Settings → Password and authentication → 2FA
   - Authenticator app

3. Backup kodlarini SAQLANG! Bosqichni o'tkazib yubormang!
```

> **Muhim eslatma:**  
> "Backup kodlarini **printerda chop eting** va xavfsiz joyda saqlang. Telefon yo'qolsa - bu kodlar bilan kirish mumkin!"

### Mashq 2: Linux'da User va Permissions (15 daq)

> **O'qituvchi:**  
> "Linux serverda foydalanuvchi va huquqlar bilan ishlaymiz."

#### User yaratish:

```bash
# Yangi user yaratish
sudo useradd -m -s /bin/bash testuser

# Parol o'rnatish
sudo passwd testuser
# Parol kiriting

# User ma'lumotini ko'rish
id testuser
# uid=1001(testuser) gid=1001(testuser) groups=1001(testuser)

# /etc/passwd da ko'rish
grep testuser /etc/passwd
```

#### Group bilan ishlash:

```bash
# Yangi group
sudo groupadd developers

# User'ni group'ga qo'shish
sudo usermod -aG developers testuser

# Tekshirish
groups testuser
# testuser : testuser developers
```

#### Sudo huquqi:

```bash
# Sudoers faylini tahrirlash
sudo visudo

# Yo'l 1: Faqat aniq komandalar
testuser ALL=(ALL) /usr/bin/apt update, /usr/bin/apt upgrade

# Yo'l 2: Hammasi (xavfli!)
testuser ALL=(ALL:ALL) ALL

# Yo'l 3: Group orqali
%developers ALL=(ALL) /usr/bin/systemctl restart nginx
```

#### File Permissions:

```bash
# Test fayl yaratish
touch test.txt

# Permissions ko'rish
ls -la test.txt
# -rw-r--r-- 1 user user 0 Jan 15 10:00 test.txt
#  ↑↑↑↑↑↑↑↑↑
#  rwx rwx rwx
#  owner group others

# Permissions o'zgartirish
chmod 755 test.txt
# rwxr-xr-x

chmod 600 test.txt  # Faqat egasi o'qiy va yoza oladi
chmod 644 test.txt  # Egasi RW, qolganlar R
chmod 700 test.txt  # Faqat egasi hammasi

# Egasini o'zgartirish
sudo chown testuser:developers test.txt
```

**Permissions qisqacha:**

```
chmod XYZ:
  X = User (egasi)
  Y = Group
  Z = Others (boshqalar)

Qiymatlar:
  4 = Read (r)
  2 = Write (w)
  1 = Execute (x)

Misollar:
  7 = 4+2+1 = rwx (hammasi)
  6 = 4+2   = rw-
  5 = 4+1   = r-x
  4 = 4     = r--
  0 =       = ---
```

### Mashq 3: Kuchli parol siyosati (10 daq)

> **O'qituvchi:**  
> "Endi Linux'da **parol siyosati**ni sozlaymiz."

```bash
# PAM password module sozlash
sudo nano /etc/security/pwquality.conf
```

**Quyidagilarni qo'shing:**

```bash
# Kamida 12 belgi
minlen = 12

# Kamida 1 ta katta harf
ucredit = -1

# Kamida 1 ta kichik harf
lcredit = -1

# Kamida 1 ta raqam
dcredit = -1

# Kamida 1 ta maxsus belgi
ocredit = -1

# Foydalanuvchi nomidan farq qilsin
gecoscheck = 1
```

#### Parol vaqti:

```bash
# Parol amal qilish muddati
sudo nano /etc/login.defs

PASS_MAX_DAYS   90    # 90 kunda yangilash
PASS_MIN_DAYS   1     # Kamida 1 kun saqlash
PASS_WARN_AGE   7     # 7 kun oldindan ogohlantirish

# User uchun majburiy o'zgartirish
sudo chage -d 0 testuser
# Keyingi loginda parol o'zgartirishga majbur qiladi
```

#### Account locking - bruteforce'dan himoya:

```bash
# fail2ban o'rnatish
sudo apt install fail2ban

# SSH himoyasi
sudo nano /etc/fail2ban/jail.local

[sshd]
enabled = true
port = ssh
maxretry = 3        # 3 marta xato
bantime = 3600      # 1 soat blok
findtime = 600      # 10 daqiqada

# Restart
sudo systemctl restart fail2ban

# Status
sudo fail2ban-client status sshd
```

### Mashq 4: SSH Key-based Authentication (5 daq)

> **O'qituvchi:**  
> "Eng xavfsiz yo'l - **SSH Key**. Parol o'rniga kalit ishlatish."

```bash
# Mahalliy mashinada kalit yaratish
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
# Enter, Enter, Enter (parolni qo'yishingiz ham mumkin)

# Yaratilgan kalitlar:
ls ~/.ssh/
# id_rsa       <- Private (HECH KIMGA BERMA!)
# id_rsa.pub   <- Public  (serverga yuboriladi)

# Public key'ni serverga yuborish
ssh-copy-id testuser@server-ip

# Endi parolsiz kirish:
ssh testuser@server-ip
# Login muvaffaqiyatli (parol so'ralmaydi)

# Server tomonida parolni butunlay o'chirish
sudo nano /etc/ssh/sshd_config
PasswordAuthentication no
PermitRootLogin no

sudo systemctl restart sshd
```

---

## DARS YAKUNI (5 daqiqa)

### Bugungi xulosa

> "Bugun o'rgandik:
> 1. **Authentication** - kim ekanligini tasdiqlash
> 2. **Authorization** - nima qila olishni belgilash
> 3. **3 ta auth factor** - know, have, are
> 4. **MFA** - eng kam 2 factor
> 5. **Password policy** - kuchli parollar
> 6. **SSO** - bitta marta kirish
> 7. **Least Privilege** - eng kam huquq
> 8. **Linux'da** user, group, permissions, SSH key"

### Uy vazifasi

> "1. **Amaliy:**
>    - 2FA hamma asosiy akkauntlaringizda yoqing
>    - Bitwarden o'rnating va parollarni ko'chiring
>    - Linux serverda yangi user yarating, kuchli parol siyosati o'rnating
>    - SSH key bilan ulanishni sozlang
> 
> 2. **Yozma:**
>    - O'z kompaniyangiz uchun **parol siyosati** hujjatini yozing (1 sahifa)
>    - **RBAC matritsasi** chizing (rollar, permissionlar)
> 
> 3. **O'qish:** OAuth 2.0 va SAML asoslari"

### Keyingi darsda

> "Ertaga **birinchi haftaning yakuniy testi**! Tayyorlanib keling!"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Diqqat
- **Authentication vs Authorization** - bu eng ko'p adashtiriladigan joy. Aniq tushuntiring
- **Least Privilege** - kursning **mantra**si bo'lishi kerak
- **2FA o'rnatish** - hamma talaba o'z akkauntida yoqsin (amalda)

### Foydali resurslar
- **NIST 800-63** - parol siyosati standardi
- **OWASP Authentication Cheat Sheet**
- **Have I Been Pwned** - email tekshiruvi
