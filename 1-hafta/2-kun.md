# 2-KUN: Axborot xavfsizligi turlari

**Mavzu:** Xavfsizlikning turli sohalari va ularni qaysi biri sizga kerakligini bilish  
**Maqsad:** Talabalar 6 ta xavfsizlik domeni bilan tanish bo'lishi  
**Kerakli materiallar:** Slaydlar, doska, marker

---

## DARS BOSHIDA (5 daqiqa)

### Salomlashish va o'tgan dars takrorlash

> **O'qituvchi:**  
> "Assalomu alaykum! Kechagi darsdan keyin har biringiz qanchaga kuchaydingiz? Aytingchi:
> 
> 1. **CIA Triad** - bu nima?
> 2. **Risk** formulasini eslay olasizmi?
> 3. Uy vazifasini kim bajardi - parolini o'zgartirib, 2FA yoqdi?"

(2-3 talabadan javob oling. Maqtang yoki maslahat bering)

> "Bugun biz **xavfsizlik domenlarini** o'rganamiz. Kiberxavfsizlik bitta soha emas - u 6 ta katta bo'limdan iborat. Tizim administratori sifatida siz **hammasini** bilishingiz kerak."

---

## 1-SOAT: Nazariy qism (45 daqiqa)

### Kirish: Xavfsizlikning 6 ta domeni (5 daq)

**Doskaga chizing:**

```
                 ┌──────────────────────┐
                 │  AXBOROT XAVFSIZLIGI  │
                 └──────────────────────┘
                            │
        ┌──────────┬────────┼────────┬──────────┐
        ▼          ▼        ▼        ▼          ▼
   ┌─────────┐┌─────────┐┌─────────┐┌─────────┐┌─────────┐
   │NETWORK  ││APPLICA- ││ENDPOINT ││ CLOUD   ││PHYSICAL │
   │SECURITY ││TION SEC.││SECURITY ││SECURITY ││SECURITY │
   └─────────┘└─────────┘└─────────┘└─────────┘└─────────┘
                            │
                            ▼
                       ┌─────────┐
                       │OPERATIO-│
                       │NAL SEC. │
                       └─────────┘
```

> "Endi har bir domenni alohida ko'ramiz. Har biriga 5-7 daqiqa beramiz."

### 1-domen: Network Security (Tarmoq xavfsizligi) - 7 daq

> **O'qituvchi:**  
> "**Network Security** - bu tarmoqlar orqali o'tayotgan ma'lumotlarni himoya qilish.
> 
> **Tasavvur qiling:** Sizning tarmog'ingiz - bu shahar yo'llari. Mashinalar (paketlar) yo'llardan o'tadi. Sizning vazifangiz - bu yo'llarni xavfsiz qilish."

**Network Security'da nimalarni himoya qilamiz?**

```
┌────────────────────────────────────────────┐
│ NETWORK SECURITY                            │
├────────────────────────────────────────────┤
│ • Routerlar va Switchlar                    │
│ • Wi-Fi tarmoqlar                           │
│ • VPN ulanishlar                            │
│ • Internet trafigi                          │
└────────────────────────────────────────────┘
```

**Asosiy himoya vositalari:**
- **Firewall** - tarmoqning "qulf"i
- **IDS/IPS** - tahdidlarni aniqlash tizimlari
- **VPN** - shifrlangan tunnel
- **Network Segmentation** - tarmoqni bo'laklash

**Real misol:**

> "Bir bankda hujumchi Wi-Fi orqali tarmoqqa kirdi. **Network Segmentation** bo'lmaganligi uchun u to'g'ridan-to'g'ri serverga yetib bordi va 50 million dollar o'g'irladi. Agar mehmon Wi-Fi va asosiy tarmoq alohida bo'lganda - bu sodir bo'lmas edi."

**Tizim administratori roli:**
- Firewall qoidalarini sozlash
- VPN o'rnatish va boshqarish
- Tarmoq monitoringi
- Wi-Fi xavfsizligini ta'minlash

### 2-domen: Application Security (7 daq)

> **O'qituvchi:**  
> "**Application Security** - bu dasturiy ta'minotning xavfsizligi. Web saytlar, mobil ilovalar, dasturlar."

**Eng keng tarqalgan ilovalar zaifliklari:**

```
TOP zaifliklari (OWASP Top 10):
┌─────────────────────────────────────────┐
│ 1. SQL Injection                         │
│ 2. Broken Authentication                 │
│ 3. Cross-Site Scripting (XSS)            │
│ 4. Insecure Configuration                │
│ 5. Sensitive Data Exposure               │
└─────────────────────────────────────────┘
```

**Misol: SQL Injection**

> "Tasavvur qiling, login formasida user 'admin' deb yozadi va parol o'rniga `' OR '1'='1` deb yozsa - va sayt **zaif** bo'lsa, u parolsiz kiraversa! Bu SQL Injection."

**Tizim administratori nima qilishi kerak:**
- Web serverni xavfsiz sozlash
- HTTPS sertifikatlarini boshqarish
- Logirovaniyalarni kuzatish
- WAF (Web Application Firewall) o'rnatish

### 3-domen: Endpoint Security (7 daq)

> **O'qituvchi:**  
> "**Endpoint** - bu 'oxirgi nuqta'. Ya'ni foydalanuvchining qurilmasi: kompyuter, telefon, planshet, server."

**Endpointlar - eng zaif joy! Nega?**

```
ENDPOINT XAVFLAR:
┌────────────────────────────────────┐
│ • Foydalanuvchi xatolari            │
│ • Phishing email'lar                │
│ • USB virus                         │
│ • Eskirgan dasturlar                │
│ • Zaif parollar                     │
└────────────────────────────────────┘
```

**Himoya vositalari:**
- **Antivirus / EDR** (Endpoint Detection and Response)
- **Disk Encryption** (BitLocker, FileVault)
- **Patch Management** - yangilanishlar
- **DLP** (Data Loss Prevention)

**Misol:**

> "Bir kompaniyada xodim USB topib, kompyuteriga ulagan. USB'da **BadUSB** virus bor edi. 5 daqiqa ichida butun kompaniya tarmog'i zararlandi. Yo'qotish: 2 million dollar."

### 4-domen: Cloud Security (7 daq)

> **O'qituvchi:**  
> "**Cloud Security** - bu AWS, Azure, Google Cloud kabi bulutli xizmatlar xavfsizligi. Bugun ko'p kompaniyalar bulutga ko'chyapti."

**Cloud'da xavfsizlik kim mas'ul?**

```
SHARED RESPONSIBILITY MODEL:
┌─────────────────────────────────────┐
│ MIJOZ MAS'UL                         │
├─────────────────────────────────────┤
│ • Foydalanuvchi ma'lumotlari        │
│ • Identity va Access                │
│ • Ilova xavfsizligi                 │
│ • Konfiguratsiya                    │
├─────────────────────────────────────┤
│ CLOUD PROVIDER MAS'UL                │
├─────────────────────────────────────┤
│ • Fizik xavfsizlik                  │
│ • Server hardware                   │
│ • Virtualizatsiya                   │
│ • Tarmoq infratuzilmasi             │
└─────────────────────────────────────┘
```

**Mashhur xato:** "Bulutda hammasini AWS himoya qiladi" - **YO'Q!** Siz ham mas'ulsiz.

**Misol:**

> "2017-yil. Verizon kompaniyasi AWS S3'da 14 million mijoz ma'lumotlarini saqlardi. Lekin **bucket'ni public** qoldirib qo'ydi. Natija: butun ma'lumot Internetda ochiq qoldi."

### 5-domen: Operational Security - OpSec (6 daq)

> **O'qituvchi:**  
> "**OpSec** - bu kundalik operatsiyalar xavfsizligi. Ya'ni qoidalar, jarayonlar, siyosatlar."

**OpSec qamrab oladi:**

```
┌────────────────────────────────────────┐
│ OPERATIONAL SECURITY                    │
├────────────────────────────────────────┤
│ • Xodimlar uchun siyosatlar            │
│ • Patch management jarayoni            │
│ • Incident Response Plan               │
│ • Backup strategiyasi                  │
│ • Access control protseduralari        │
│ • Audit va monitoring                  │
└────────────────────────────────────────┘
```

**Misol:**

> "Ko'p kompaniyalarda **Joiner-Mover-Leaver** muammo bor:
> - Yangi xodim keladi - access olishi 1 hafta!
> - Boshqa bo'limga o'tadi - eski access'lar saqlanib qoladi
> - Ishdan ketadi - access'lar olib tashlanmaydi!
> 
> Natija: ishdan ketgan xodim 1 yildan keyin ham serverga kira oladi. Bu - **OpSec** muammosi."

### 6-domen: Physical Security (5 daq)

> **O'qituvchi:**  
> "Ko'pchilik **fizik xavfsizlikni** unutadi. Lekin agar xaker server xonangizga kirsa - barcha shifrlash, firewall'lar bekor."

**Physical Security:**

```
┌────────────────────────────────────────┐
│ FIZIK XAVFSIZLIK                        │
├────────────────────────────────────────┤
│ • Server xonalariga kirish nazorati    │
│ • CCTV kameralar                        │
│ • Biometrik qulf                        │
│ • UPS va generator (elektr)             │
│ • Sovutish tizimi                       │
│ • Yong'in himoyasi                      │
└────────────────────────────────────────┘
```

**Misol:**

> "Bir kompaniyada serverlar oddiy ofis xonasida turardi. Tozalovchi xodim USB kirgizdi - ma'lumotlar o'g'irlandi. Saboq: **fizik kirishni cheklash kerak!**"

### Xulosa (3 daq)

> **O'qituvchi:**  
> "Mana, biz 6 ta domenni ko'rib chiqdik. **Esda tuting:**
> 
> ```
> Xavfsizlik = ZANJIR
> Eng zaif halqasi qaysi - butun zanjir shunchalik kuchli
> ```
> 
> Tizim administratori sifatida sizning vazifangiz - hamma domenlarda kuchli bo'lish!"

---

## TANAFFUS (10 daqiqa)

---

## 2-SOAT: Amaliy qism (45 daqiqa)

### Mashq 1: Domenlarni aniqlash (15 daq)

> **O'qituvchi:**  
> "Endi har biringiz daftarga **6 ta ustun** chizing - har bir domen uchun. Sizning kompaniyangizda har bir domen uchun:
> 
> 1. Hozirgi vositalar nima?
> 2. Qanday muammolar bor?
> 3. Nima qo'shish kerak?"

**Doskaga shablon:**

```
┌───────────┬────────────┬────────────┬────────────┐
│ DOMEN     │ HOZIRGI    │ MUAMMOLAR  │ TAKLIFLAR  │
├───────────┼────────────┼────────────┼────────────┤
│ Network   │ Mikrotik FW│ Eski qoid. │ FW yangil. │
│ App       │ HTTPS yo'q │ HTTP only  │ SSL sert.  │
│ Endpoint  │ Antivirus  │ User access│ EDR        │
│ Cloud     │ -          │ -          │ AWS audit  │
│ Operat.   │ -          │ Siyosat yo'q│ Yozish    │
│ Physical  │ Qulf bor   │ CCTV yo'q  │ Kamera     │
└───────────┴────────────┴────────────┴────────────┘
```

(15 daqiqa - har talaba o'zi to'ldiradi, keyin 2-3 talaba taqdim qiladi)

### Mashq 2: Hujum stsenariyasini tahlil qilish (20 daq)

**Stsenariy:** (doskaga yozing yoki proektorga chiqaring)

> "**Stsenariy:** 'XYZ' kompaniyasi - 50 xodimi bor. Online do'kon yuritadi. Shanba kuni ertalab bosh administrator quyidagilarni ko'rdi:
> 
> 1. Sayt ishlamayapti - 'Server Error' chiqyapti
> 2. Bosh administratorning email'ida g'alati 'login' bildirishnomalari bor
> 3. Mijozlardan qo'ng'iroqlar kelyapti - 'banking ma'lumotlarim sayotsidan o'g'irlangan' deb
> 4. Server xonasi eshigi qulflanmagan turibdi
> 5. Backup oxirgi marta 3 oy oldin bo'lgan
> 
> **Savollar:**
> 1. Qaysi xavfsizlik domenlari buzilgan?
> 2. CIA Triad'dan qaysi biri buzilgan?
> 3. Qanday choralar ko'rish kerak (qisqa muddatli va uzoq muddatli)?"

**Talabalar 10 daqiqa o'ylaydi va guruhda muhokama qiladi.**

**To'g'ri javoblar (siz tushuntiring):**

```
DOMENLAR BUZILGAN:
✗ Application Security  (sayt buzilgan)
✗ Endpoint Security     (admin email'i buzilgan)
✗ Network Security      (xaker tarmoqqa kirgan)
✗ Physical Security     (eshik ochiq)
✗ Operational Security  (backup yo'q!)
✗ Cloud Security        (agar saytda mijoz ma'lumotlari bo'lsa)

CIA BUZILGAN:
✗ Confidentiality - mijoz ma'lumotlari o'g'irlangan
✗ Integrity       - sayt o'zgartirilgan bo'lishi mumkin
✗ Availability    - sayt ishlamayapti
HAMMA UCHTASI HAM!

QISQA MUDDATLI CHORALAR:
1. Saytni o'chirish (yangi hujumlar oldini olish)
2. Politsiya/CERT'ga xabar berish
3. Mijozlarga ogohlantirish
4. Forensics tahlil

UZOQ MUDDATLI:
1. WAF o'rnatish
2. Backup tizimini yo'lga qo'yish (3-2-1 qoida)
3. 2FA hamma admin'larga
4. Server xonasini xavfsizlashtirish
5. SIEM o'rnatish
6. Incident Response Plan yozish
```

### Mashq 3: Birinchi siyosat (10 daq)

> **O'qituvchi:**  
> "Endi har biringiz **bitta xavfsizlik qoida** yozing. Qisqa, aniq, amaliyotda bajarsa bo'ladigan."

**Misollar:**
- "Barcha xodimlar 90 kunda parolni o'zgartirishi shart"
- "USB qurilmalar faqat IT bo'limida ulangandan keyin ishlatish mumkin"
- "Server xonasiga faqat ID karta orqali kirish"
- "Har kuni avtomatik backup"

(Har talabadan 1 ta qoida - daftarga yozsin)

---

## DARS YAKUNI (5 daqiqa)

### Bugungi xulosa

> "Bugun o'rgandik:
> 1. **6 ta xavfsizlik domeni** - Network, App, Endpoint, Cloud, Operational, Physical
> 2. Har bir domen **bir-biri bilan bog'liq** - bittasi zaif bo'lsa, hammasi zaif
> 3. **Shared Responsibility** - cloud'da javobgarlik bo'lingan
> 4. **Real hujum stsenariyasi** - bir vaqtda bir necha domen buzilishi mumkin"

### Uy vazifasi

> "1. Sizning kompaniyangiz uchun **6 ta domen bo'yicha audit** yozing (kechagi jadvalda boshlagan ish)
> 2. **3 ta xavfsizlik qoida** yozing va nega muhim ekanligini tushuntiring
> 3. **O'qish:** OWASP Top 10 (qisqacha) - keyingi mavzuga tayyorgarlik"

### Keyingi darsda

> "Ertaga **Tahdidlar va Hujumchilar turlari**ni o'rganamiz. Kim bizga hujum qiladi va nega?"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Diqqat qaratish kerak bo'lgan joylar
- Talabalar **Network Security** va **Application Security**ni adashtiradi - aniq tushuntiring
- **Shared Responsibility** model - juda ko'p bahsli mavzu, vaqt ajrating
- **Physical Security** - ko'p admin unutadi, alohida urg'u bering

### Qo'shimcha resurslar
- **AWS Shared Responsibility Model** rasmini ko'rsating
- **OWASP** rasmiy saytidan tayyor materiallar yuklab oling
- **MITRE ATT&CK** matrix - keyingi darsda kerak bo'ladi
