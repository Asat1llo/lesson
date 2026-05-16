# 3-KUN: Tahdidlar va Hujumchilar turlari

**Mavzu:** Kim bizga hujum qiladi va nega? Threat actors va ularning motivatsiyasi  
**Maqsad:** Talabalar har xil hujumchilar turlarini bilish va threat modeling asoslarini tushunish  
**Kerakli materiallar:** Slaydlar, internet, MITRE ATT&CK demo

---

## DARS BOSHIDA (5 daqiqa)

### Salomlashish va o'tgan dars takrorlash

> **O'qituvchi:**  
> "Assalomu alaykum! Kechagi 6 ta domenni eslay olasizmi? 
> - 1-domen?
> - 2-domen?
> ..."

(Tezkor savollar bilan eslatib chiqing)

> "Bugun biz **dushmanni** o'rganamiz. Sun Tzu degan qadimgi hind generali aytgan: 'Dushmanni bilmasdan, urushga kirma'. Biz ham hujumchilarni bilishimiz kerak."

---

## 1-SOAT: Nazariy qism (45 daqiqa)

### Kirish: Threat Actors kim? (3 daq)

> **O'qituvchi:**  
> "**Threat Actor** (yoki Hujumchi) - bu kim sizga hujum qilishi mumkin. Ko'pchilik o'ylaydi - bu yolg'iz xaker, qora kapyushonli, qorong'i xonada. **YO'Q!** Hujumchilar - har xil bo'ladi.
> 
> Bugun biz 6 ta turdagi hujumchilarni o'rganamiz."

**Doskaga chizing:**

```
                ┌─────────────────┐
                │ THREAT ACTORS    │
                └─────────────────┘
                        │
   ┌────────┬────────┬──┴───┬────────┬────────┐
   ▼        ▼        ▼      ▼        ▼        ▼
┌─────┐ ┌──────┐ ┌──────┐┌──────┐┌──────┐┌──────┐
│Scrip│ │Hackt-│ │Cyber-││APT/  ││Insid-││Compe-│
│t Ki-│ │ivists│ │crimin││Nation││er    ││titor │
│ddies│ │      │ │als   ││State ││Threat││      │
└─────┘ └──────┘ └──────┘└──────┘└──────┘└──────┘
 Past     O'rta    Yuqori  Yuqori  Yuqori  O'rta
 daraja   daraja   daraja  daraja  daraja  daraja
```

### 1-tur: Script Kiddies (5 daq)

> **O'qituvchi:**  
> "**Script Kiddie** (yoki Skript Kid) - bu yangi boshlovchi 'xaker'. Odatda yoshlar.
> 
> **Xususiyatlar:**
> - Tayyor dasturlarni (skriptlarni) yuklab ishlatadi
> - Texnik bilim past
> - Maqsad: 'qiziq ekan', 'do'stlarga ko'rsatish'
> - Internetda topgan tutorialga ergashadi
> 
> **Misol:**
> 14 yoshli o'g'il bola 'YouTube'dan SQL Injection o'rgandim' deb maktab saytini buzadi. Bu - script kiddie."

**Xavf darajasi:** Past, lekin **e'tiborsiz qoldirsa bo'lmaydi!**

```
┌────────────────────────────────────┐
│ HIMOYA: Asosiy chora-tadbirlar     │
│ • Yangilangan dasturlar            │
│ • Kuchli parollar                  │
│ • Asosiy firewall                  │
└────────────────────────────────────┘
```

### 2-tur: Hacktivists (7 daq)

> **O'qituvchi:**  
> "**Hacktivist** = Hacker + Activist. Ya'ni siyosiy yoki ijtimoiy maqsadli xakerlar.
> 
> **Xususiyatlar:**
> - Pul uchun emas, **e'tiqod** uchun
> - Hukumatlarga, korporatsiyalarga qarshi
> - Saytlarni 'deface' qiladi (asosiy sahifaga o'z xabarini qo'yadi)
> - DDoS hujumlari uyushtiradi"

**Mashhur misollar:**

#### Anonymous

> "**Anonymous** - bu hacktivist guruh. Hech kim ularning kim ekanini bilmaydi. Niqobi mashhur:
> 
> - Scientology cherkoviga qarshi
> - PayPal, Visa'ga DDoS (chunki ular WikiLeaks'ga pul yuborilishini bloklagan)
> - ISIS akkauntlariga qarshi
> 
> Ular **'Guy Fawkes'** niqobini taqib oladi."

#### LulzSec

> "**LulzSec** - 'lulz' ya'ni 'kulgu' uchun. Sony, FBI, CIA saytlariga hujum qildi."

**Xavf darajasi:** O'rta-yuqori

> "Tizim administratori sifatida bilishingiz kerak: agar kompaniyangiz biror **siyosiy bahsli** ish qilsa - hacktivist hujum kelishi mumkin."

### 3-tur: Cybercriminals (10 daq)

> **O'qituvchi:**  
> "**Cybercriminal** - bu **pul** uchun ishlovchi xaker. Eng katta guruh, eng katta xavf.
> 
> **Xususiyatlar:**
> - Asosiy maqsad: **PUL**
> - Yaxshi tashkillashgan, ko'pincha mafia kabi
> - Texnik darajasi yuqori
> - Ko'p mamlakatdagi, asosan Rossiya, Sharqiy Yevropa, Xitoy"

**Asosiy biznes modellari:**

```
┌─────────────────────────────────────────────┐
│ CYBERCRIMINAL "BIZNES"                       │
├─────────────────────────────────────────────┤
│ 1. RANSOMWARE                                │
│    - Ma'lumotlarni shifrlaydi                │
│    - Pul talab qiladi (Bitcoin)              │
│                                              │
│ 2. CARD FRAUD                                │
│    - Kredit karta ma'lumotlarini o'g'irlash  │
│    - Internetda sotish (Dark Web)            │
│                                              │
│ 3. BUSINESS EMAIL COMPROMISE (BEC)           │
│    - CEO niqobida email                      │
│    - Pul o'tkazishni so'rash                 │
│                                              │
│ 4. CRYPTOJACKING                             │
│    - Sizning serverda kripto kazib chiqaradi │
└─────────────────────────────────────────────┘
```

#### Ransomware misollari

> "**WannaCry** (2017) - 4 milliard dollar zarar
> **Conti** - rus xakerlar guruhi, 150+ million dollar to'lov
> **REvil** - Kaseya kompaniyasini buzdi - 1500 ta mijozni zararladi"

**Misol vaziyat:**

> "Ofisingizga ertalab kelasiz - barcha kompyuterlarda **qizil ekran**:
> 
> ```
> ┌────────────────────────────────────────┐
> │  YOUR FILES HAVE BEEN ENCRYPTED        │
> │                                         │
> │  Pay 500,000 USD in Bitcoin            │
> │  to wallet: 1A2B3C4D5E6F...            │
> │                                         │
> │  You have 72 hours                     │
> └────────────────────────────────────────┘
> ```
> 
> Endi nima qilasiz?"

(Talabalar javob beradi - munozara qiling)

> "**To'g'ri javob:** TO'LAMANG! 
> - To'lasangiz - 50% holatda ham fayllarni qaytarib bermaydi
> - Ikkinchi marta hujum qiladi (siz to'laysiz deb biladi)
> - Backup'ingiz bo'lishi kerak edi - tiklash."

**Xavf darajasi:** YUQORI - eng katta tahdid!

### 4-tur: APT / Nation-State (10 daq)

> **O'qituvchi:**  
> "**APT** = **Advanced Persistent Threat**. Va **Nation-State** - bu **davlat** tomonidan moliyalashtiriladigan xakerlar.
> 
> **Xususiyatlar:**
> - **Eng yuqori daraja**
> - Cheksiz resurslar (davlat byudjeti)
> - **Persistent** - oylab, yillab tarmoqda yashiringan turadi
> - Maqsad: ayg'oqchilik, sabotaj, intellektual mulk o'g'irlash"

**Mashhur APT guruhlari:**

```
┌─────────────────────────────────────────┐
│ MAMLAKAT │ APT GURUHLARI                 │
├──────────┼──────────────────────────────┤
│ Rossiya  │ Fancy Bear (APT28)           │
│          │ Cozy Bear (APT29)            │
│ Xitoy    │ APT1, APT41                  │
│ Eron     │ APT34, APT35 (Charming Kit.) │
│ Sh. Korea│ Lazarus Group                │
│ AQSh     │ Equation Group (NSA)         │
└──────────┴──────────────────────────────┘
```

**APT bosqichlari:**

```
1. RECONNAISSANCE  →  Maqsadni o'rganish
2. INITIAL ACCESS  →  Phishing yoki zaiflik
3. PERSISTENCE     →  Tarmoqda doimiy bo'lish
4. PRIVILEGE ESC.  →  Admin huquqlari olish
5. LATERAL MOVE.   →  Boshqa serverlarga o'tish
6. EXFILTRATION    →  Ma'lumotlarni o'g'irlash
```

**Real misol: APT - SolarWinds (2020)**

> "Rus APT (Cozy Bear) **9 oy davomida** SolarWinds tarmog'ida yashirin yashadi. Hech kim bilmadi! Keyin ular yangilanish faylga zararli kod qo'shdi va 18,000 ta tashkilotni zararladi."

**Xavf darajasi:** ENG YUQORI

### 5-tur: Insider Threat (Ichki tahdid) (7 daq)

> **O'qituvchi:**  
> "**Insider Threat** - bu **ichkaridan** kelgan tahdid. Ya'ni **xodim**, **kontraktor**, **eski xodim**.
> 
> **Statistika:** 60% kompaniyalardagi ma'lumot oqishlari **ichkaridan** keladi!
> 
> **Bu eng xavfli tur. Nega?**
> - Xodim allaqachon **tarmoqqa kirish huquqiga ega**
> - Antivirus uni xaker deb o'ylamaydi
> - Firewall'ni aylanib o'tadi"

**Insider Threat turlari:**

```
┌──────────────────┬────────────────────────────────┐
│ TUR              │ MOTIVATSIYA                    │
├──────────────────┼────────────────────────────────┤
│ Malicious        │ Pul, qasos, ayg'oqchilik       │
│ (Yomon niyatli)  │ Misol: ishdan haydaldim, qasos │
├──────────────────┼────────────────────────────────┤
│ Negligent        │ E'tiborsizlik, dangasalik      │
│ (E'tiborsiz)     │ Misol: parolini yozib qo'ydi   │
├──────────────────┼────────────────────────────────┤
│ Compromised      │ Akkaunti o'g'irlangan          │
│ (Buzilgan)       │ Misol: phishing tushgan        │
└──────────────────┴────────────────────────────────┘
```

**Mashhur misol: Edward Snowden**

> "**Edward Snowden** - NSA xodimi. 2013-yilda u **1.7 million** maxfiy faylni o'g'irladi va dunyoga oshkor qildi. U xaker emas edi - oddiy admin edi! Lekin **kirish huquqlari** bor edi.
> 
> Saboq: **Least Privilege** - xodimga faqat kerakli huquqlarni bering!"

### 6-tur: Competitors / Corporate Espionage (3 daq)

> **O'qituvchi:**  
> "**Raqobatchilar** - boshqa kompaniyalar. Sizning sirlaringizni o'g'irlamoqchi:
> - Mijozlar ro'yxati
> - Yangi mahsulot tafsilotlari
> - Narxlar
> 
> Ko'pincha **insider** orqali ishlaydi - sizning xodimingizga pul taklif qilishadi."

### Threat Modeling - tahdidlarni baholash (10 daq)

> **O'qituvchi:**  
> "Endi biz **Threat Modeling** ni o'rganamiz. Bu - tahdidlarni baholash usuli."

**STRIDE - Microsoft tomonidan yaratilgan model:**

```
┌─┬─────────────────┬──────────────────────────┐
│S│ Spoofing        │ Boshqa shaxsdek ko'rinish │
│T│ Tampering       │ Ma'lumotni o'zgartirish   │
│R│ Repudiation     │ Ish qilganini inkor etish │
│I│ Info Disclosure │ Ma'lumot oshkor qilish    │
│D│ Denial of Serv. │ Xizmatdan voz kechirish   │
│E│ Elev. of Privi. │ Huquqlarni ko'tarish      │
└─┴─────────────────┴──────────────────────────┘
```

**Misol:**

> "Sizning veb sayt uchun STRIDE:
> 
> - **S** - Phishing email - admin niqobida
> - **T** - SQL Injection - DB ma'lumotini o'zgartirish
> - **R** - Log'lar yo'q - kim nima qilganini bilmaymiz
> - **I** - HTTPS yo'q - parollar ochiq ko'rinadi
> - **D** - DDoS hujum - sayt ishlamay qoladi
> - **E** - Oddiy user admin bo'lib qoladi"

---

## TANAFFUS (10 daqiqa)

---

## 2-SOAT: Amaliy qism (45 daqiqa)

### Mashq 1: MITRE ATT&CK Framework bilan tanishish (20 daq)

> **O'qituvchi:**  
> "Endi biz **MITRE ATT&CK** - kiberxavfsizlikning eng muhim 'kutubxona'sini o'rganamiz."

**MITRE ATT&CK nima?**

> "Bu xakerlar **qanday hujum qiladi** ning to'liq ro'yxati. AQSh tashkiloti yaratgan, hammaga ochiq.
> 
> Sayt: **attack.mitre.org**"

**Sayt ko'rsating va tushuntiring:**

```
ATT&CK MATRIX (qisqacha):
┌─────────────┬─────────────┬─────────────┐
│ TACTIC      │ TECHNIQUE   │ MISOL       │
├─────────────┼─────────────┼─────────────┤
│ Recon       │ Active scan │ Nmap        │
│ Init Access │ Phishing    │ Email link  │
│ Execution   │ PowerShell  │ Skript      │
│ Persistence │ Reg. Keys   │ Auto-start  │
│ Priv Esc    │ Token Manip.│ Token theft │
│ Defense Eva.│ Disable AV  │ AV o'chir.  │
│ Credentials │ Brute Force │ Parol top.  │
│ Discovery   │ AD recon    │ Tarmoq tek. │
│ Lateral M.  │ RDP         │ Server-ser. │
│ Collection  │ Screen Cap. │ Skrinshot   │
│ Exfiltration│ DNS Tunnel. │ Ma'lumot ol.│
│ Impact      │ Encrypt     │ Ransomware  │
└─────────────┴─────────────┴─────────────┘
```

**Amaliy mashq:**

> "Endi attack.mitre.org saytini oching. Quyidagilarni topib, daftaringizga yozing:
> 
> 1. **T1566 - Phishing** texnikasini toping. U haqida 3 ta gap yozing.
> 2. **APT29** guruhini toping. Ular qaysi mamlakatdan?
> 3. **Mitigations** bo'limidan **M1017 - User Training** ni toping. Nima yozilgan?"

(15 daqiqa - talabalar kompyuterda yoki telefonda izlaydi)

### Mashq 2: Threat Modeling - kompaniyangiz uchun (15 daq)

> **O'qituvchi:**  
> "Endi har biringiz o'z kompaniyangiz uchun **threat model** yozing."

**Shablon (doskaga):**

```
KOMPANIYA: __________________

ASSETS (himoyalangan narsalar):
1. ______________________
2. ______________________
3. ______________________

THREAT ACTORS (kim hujum qilishi mumkin?):
1. _________ Nega? __________
2. _________ Nega? __________
3. _________ Nega? __________

ATTACK VECTORS (qanday yo'l bilan?):
1. ______________________
2. ______________________
3. ______________________

PRIORITY (eng yuqori xavf qaysi?):
______________________
```

(10 daqiqa - 2-3 talaba taqdim qiladi)

### Mashq 3: Insider Threat aniqlash (10 daq)

**Stsenariy:**

> "Sizning kompaniyangizda quyidagi belgilar paydo bo'ldi:
> 
> 1. Bir xodim **kechqurun soat 11 da** serverga kiryapti
> 2. **Birinchi marta** Marketing bo'limidan moliyaviy ma'lumotlarga kirish
> 3. **3 GB** ma'lumot 'export' qilingan
> 4. Bu xodim **2 oy** keyin ishdan ketmoqchi
> 5. Tashqi USB qurilma ulangan"

**Savollar:**
1. Bu insider threatmi? Qaysi turi?
2. Qanday choralar ko'rasiz?
3. Bunday holatlarni oldini olish uchun nima qilish kerak?

(Talabalar muhokama qiladi - 8 daqiqa)

**To'g'ri javoblar:**
- HA, **Malicious Insider** belgilari
- Choralar: Logirovaniya, IT bo'limga xabar, kirishni vaqtincha cheklash
- Oldini olish: UEBA (User Behavior Analytics), DLP, audit

---

## DARS YAKUNI (5 daqiqa)

### Bugungi xulosa

> "Bugun o'rgandik:
> 1. **6 ta hujumchi turi** - har biri turli motivatsiya
> 2. **Eng xavfli:** APT va Insider Threat
> 3. **MITRE ATT&CK** - tahdidlarni o'rganish framework'i
> 4. **Threat Modeling** - tahdidlarni baholash
> 
> **Eslatma:** Tahdidning kim ekanligini bilsangiz, kerakli himoyani tanlay olasiz!"

### Uy vazifasi

> "1. **MITRE ATT&CK**'da o'zingizga qiziq bo'lgan **bitta APT guruhini** tanlang. U haqida 1 sahifalik hisobot yozing:
>    - Qaysi davlatdan?
>    - Qanday hujum qiladi?
>    - Mashhur hujumlari
>    - Qanday himoyalanish kerak?
> 
> 2. **STRIDE** modelini ishlatib, o'z kompaniyangiz uchun **threat model** yozing
> 
> 3. **O'qish:** OWASP Top 10 - to'liqroq"

### Keyingi darsda

> "Ertaga **Zaifliklar va CVE** mavzusini o'rganamiz. Tahdidchilar bizga qanday yo'llar bilan kiradi?"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Diqqat
- **APT** mavzusini juda chuqur kirishtirmang - bu murakkab
- **Insider Threat** - alohida e'tibor bering, ko'pchilik buni unutadi
- **MITRE ATT&CK** saytini darsdan oldin oching - tezroq ko'rsating

### Qo'shimcha resurslar
- Krebs on Security blog: krebsonsecurity.com
- CSO Online: csoonline.com
- Mandiant Threat Reports - bepul yuklash mumkin
