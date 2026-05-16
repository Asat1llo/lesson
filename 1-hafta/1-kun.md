# 1-KUN: Kirish va Kiberxavfsizlik nima?

**Mavzu:** Kursga kirish, kiberxavfsizlik tushunchasi, CIA Triad  
**Maqsad:** Talabalarni kurs bilan tanishtirish, kiberxavfsizlik nima ekanligini tushuntirish  
**Kerakli materiallar:** Proyektor, slaydlar, doska, marker

---

## DARS BOSHIDA (15 daqiqa) - Birinchi kun maxsus

### Salomlashish va tanishuv

> **O'qituvchi:**  
> "Assalomu alaykum, hurmatli talabalar! Bugun biz juda muhim va qiziqarli kursni boshlaymiz - **Kiberxavfsizlik kursi**. Men sizning o'qituvchingizman. Avval o'zim haqimda qisqacha aytib o'tay..."

(O'zingiz haqingizda 2-3 daqiqa: ismingiz, ish tajribangiz, nega bu sohani sevasiz)

> "Endi har biringiz o'zingizni tanishtirib chiqing. Iltimos ayting:
> 1. Ismingiz va familiyangiz
> 2. Qayerda tizim administratori sifatida ishlaysiz?
> 3. Necha yillik tajribangiz bor?
> 4. Kiberxavfsizlik haqida nima bilasiz?
> 5. Bu kursdan nima kutyapsiz?"

(Har bir talabaga 1-2 daqiqa, ularni daftaringizga yozing - ularning darajasini bilish muhim)

### Kurs qoidalari

> "Endi kursimizning qoidalari bilan tanishaylik:
> - Darslar har kuni 2 soat davom etadi
> - Birinchi soat - nazariy, ikkinchi soat - amaliy
> - Har 45 daqiqada 10 daqiqa tanaffus
> - Har kuni uy vazifasi bo'ladi
> - Har hafta yakunida test
> - Oxirida yakuniy loyiha
> 
> Telegram guruhimiz bo'ladi - u yerda materiallar va savollarga javoblar joylashadi."

---

## 1-SOAT: Nazariy qism (45 daqiqa)

### Kirish savol bilan (5 daq)

> **O'qituvchi (savol bilan boshlaydi):**  
> "Aytingchi, kim oxirgi marta o'z parolini o'zgartirgan? Qachon? Necha oy bo'ldi?"

(Talabalar javob beradi, ko'pchilik "ancha bo'ldi" yoki "esimda yo'q" deydi)

> "Mana, ko'rib turibsizki, bizning ko'pchiligimiz parolimizni juda kam o'zgartirib turamiz. Va bu - bu darsning birinchi muammosi. Bugun biz **kiberxavfsizlik nima** va **nega bu muhim** ekanligini o'rganamiz."

### 1-mavzu: Kiberxavfsizlik nima? (10 daq)

> **O'qituvchi (doskaga yozadi):**  
> 
> ```
> KIBERXAVFSIZLIK = Kompyuter tizimlari, tarmoqlar va 
>                   ma'lumotlarni ruxsatsiz kirish, 
>                   o'g'irlash va shikastlanishdan 
>                   himoya qilish
> ```

> "Kiberxavfsizlik - bu faqat antivirus o'rnatish emas. Bu butun bir falsafa, butun bir san'at. U quyidagilardan iborat:
> 
> - **Texnologiya** (firewall, antivirus, shifrlash)
> - **Jarayonlar** (qoidalar, siyosatlar)  
> - **Insonlar** (xodimlarni o'qitish)
> 
> Eng zaif bo'g'in - bu HAR DOIM **inson**. Sizlar buni eslab qoling. Texnologiya qancha kuchli bo'lmasin, agar xodim phishing email'ga 'click' qilsa - hammasi bekor."

**Doskaga chizilgan diagramma:**

```
        ┌─────────────────────────┐
        │   KIBERXAVFSIZLIK        │
        │   (3 ta ustun)          │
        └─────────────────────────┘
              │
    ┌─────────┼─────────┐
    │         │         │
    ▼         ▼         ▼
┌────────┐ ┌────────┐ ┌────────┐
│TEXNO-  │ │JARAYON-│ │INSON-  │
│LOGIYA  │ │LAR     │ │LAR     │
│        │ │        │ │        │
│Firewall│ │Siyosat │ │O'qitish│
│Antivir.│ │ISO27001│ │Trening │
│Shifr.  │ │Audit   │ │Madaniy.│
└────────┘ └────────┘ └────────┘
```

### 2-mavzu: Nima uchun muhim? Real misollar (15 daq)

> **O'qituvchi:**  
> "Endi men sizga 3 ta haqiqiy hodisani aytib beraman. Bularni eshitganingizdan keyin, kiberxavfsizlik nega muhimligini tushunasiz."

#### Misol 1: Stuxnet (2010)

> "**Stuxnet** - bu birinchi 'kibersilohli' virus deb hisoblanadi. U Eronning Natanz yadroviy obyektiga zarar yetkazish uchun yaratilgan edi.
> 
> - Virus oddiy USB flesh orqali tarqaldi
> - Centrifugalar normal ko'rinishda ishlayotgan deb ko'rsatdi
> - Lekin aslida ularni zararladi va Eronning yadro dasturini 2 yilga orqaga surdi
> - Hech kim qurol ishlatmasdan, faqat **kod** orqali!
> 
> Mana shunda dunyo tushundi - kiberhujum **fizik zarar** keltirishi mumkin."

#### Misol 2: WannaCry (2017)

> "**WannaCry** - ransomware (to'lov so'rovchi virus). Bir kun ichida butun dunyoni zarbga keltirdi:
> 
> - 150 dan ortiq mamlakat
> - 200,000 dan ortiq kompyuter
> - Britaniya tibbiyot tizimi (NHS) ishdan chiqdi - operatsiyalar to'xtatildi!
> - Zarar: 4 milliard dollar
> 
> **Sabab nima edi?** Microsoft 2 oy oldin patch chiqargan edi, lekin tizim administratorlari yangilab qo'ymagan edi. Mana shu sizning ishingiz - vaqtida yangilanish o'rnatish!"

#### Misol 3: SolarWinds (2020)

> "**SolarWinds hujumi** - bu zamonaviy hujumning eng oqilanasi:
> 
> - Hujumchilar SolarWinds kompaniyasi serveriga kirdi
> - Kompaniyaning **yangilanish** fayliga zararli kod qo'shdi
> - Mijozlar (jumladan AQSh hukumati!) o'zlari bu yangilanishni o'rnatdi
> - 18,000 ta tashkilot zararlandi
> - Pentagon, FBI, hatto Microsoft ham!
> 
> Bu **Supply Chain hujumi** deyiladi - eng xavflisi."

> **Talabalarga savol:**  
> "Endi siz tushundingizmi, nega tizim administratori kiberxavfsizlikni bilishi shart? Sizning xatoyingiz millionlab dollar zararga olib kelishi mumkin!"

### 3-mavzu: CIA Triad (15 daq)

> **O'qituvchi:**  
> "Endi kiberxavfsizlikning eng muhim tushunchasini o'rganamiz - **CIA Triad**. Bu CIA agentligi emas! Bu uchta so'zning bosh harflari:"

**Doskaga chizing:**

```
              ╔═══════════════╗
              ║   CIA TRIAD   ║
              ╚═══════════════╝
                     △
                    ╱ ╲
                   ╱   ╲
                  ╱     ╲
                 ╱       ╲
        ────────╱─────────╲────────
       │ C - Confidentiality        │
       │     (Maxfiylik)            │
       │                            │
       │ I - Integrity              │
       │     (Yaxlitlik)            │
       │                            │
       │ A - Availability           │
       │     (Mavjudlik)            │
        ────────────────────────────
```

#### C - Confidentiality (Maxfiylik)

> "**Maxfiylik** - bu ma'lumot faqat ruxsat etilgan kishilarga ko'rinadi degani.
> 
> **Misol:** Bankdagi sizning balansingiz - faqat siz va bank xodimi ko'rishi kerak. Boshqalar emas.
> 
> **Qanday himoya qilamiz?**
> - Shifrlash (Encryption)
> - Parollar
> - Access Control
> - VPN
> 
> **Misol vaziyat:** Agar xaker email'ingizni o'qisa - bu maxfiylik buzilishi."

#### I - Integrity (Yaxlitlik)

> "**Yaxlitlik** - ma'lumot o'zgarmagan bo'lishi kerak. Hech kim uni ruxsatsiz o'zgartirmasligi kerak.
> 
> **Misol:** Sizning bank hisobingizda 1,000,000 so'm bor. Xaker uni o'g'irlamasdan, faqat 100,000 ga o'zgartirsa - bu **integrity** buzilishi.
> 
> **Qanday himoya qilamiz?**
> - Hash funksiyalar (MD5, SHA-256)
> - Digital signatures
> - Backup
> - Version control
> 
> **Real misol:** Agar talabaning bahosi 5 dan 3 ga o'zgarsa kompyuter xatosi tufayli - bu integrity muammosi."

#### A - Availability (Mavjudlik)

> "**Mavjudlik** - tizim kerak bo'lganda **ishlashi** kerak.
> 
> **Misol:** Bank bankomati ishlamasa - siz pul ololmaysiz. Bu - availability muammosi.
> 
> **Qanday himoya qilamiz?**
> - Backup tizimlari
> - Redundancy (zaxira nusxalar)
> - DDoS himoya
> - Disaster Recovery Plan
> 
> **Real misol:** 2021-yilda Facebook 6 soat ishlamadi - bu kompaniyaga 100 million dollar zarar keltirdi!"

> **O'qituvchi savol bilan yakunlaydi:**  
> "Aytingchi, agar saytingizni xakerlar buzib, asosiy sahifaga o'z reklamasini qo'yib qo'ysa - bu CIA dan qaysi birining buzilishi?"

(To'g'ri javob: **Integrity** - chunki ma'lumot o'zgartirilgan)

---

## TANAFFUS (10 daqiqa)

---

## 2-SOAT: Amaliy qism (45 daqiqa)

### Kirish (5 daq)

> **O'qituvchi:**  
> "Endi nazariyani amalda ko'ramiz. Ammo dasturlar bilan emas - bugun **fikrlash** mashqlarini qilamiz. Chunki avval xavfsizlik haqida **to'g'ri fikrlashni** o'rganishimiz kerak."

### Mashq 1: Asosiy terminlar (15 daq)

**Doskaga yozing va izohlang:**

```
┌─────────────────┬──────────────────────────────────────┐
│ TERMIN          │ TA'RIF                               │
├─────────────────┼──────────────────────────────────────┤
│ Asset           │ Qimmatli narsa (server, ma'lumot)    │
│ Threat          │ Tahdid (xaker, virus, suv toshqini)  │
│ Vulnerability   │ Zaiflik (eskirgan dastur, zaif parol)│
│ Risk            │ Xatar = Threat × Vulnerability       │
│ Attack          │ Hujum (amalga oshirilgan tahdid)     │
│ Exploit         │ Zaiflikni ishlatish vositasi         │
│ Payload         │ Hujumning "yuk"i (zararli kod)       │
└─────────────────┴──────────────────────────────────────┘
```

**Hayotiy misol bilan tushuntiring:**

> "Tasavvur qiling, sizning uyingiz bor:
> - **Asset** = uyingiz, ichidagi narsalar
> - **Threat** = o'g'rilar, yong'in, suv toshqini
> - **Vulnerability** = ochiq oyna, zaif qulf
> - **Risk** = o'g'irlanish ehtimoli
> - **Attack** = o'g'rining haqiqatda kirib kelishi
> - **Exploit** = u oynani sindirish uchun ishlatgan tosh
> - **Payload** = u olib ketgan narsalar
> 
> **Risk** = O'g'rilar (threat) ko'p + Oynam ochiq (vulnerability) = Yuqori xatar"

### Mashq 2: Talabalar bilan munozara (15 daq)

> **O'qituvchi:**  
> "Endi har biringiz o'zingiz ishlaydigan kompaniyani o'ylang. Quyidagi savollarga javob bering:"

**Savollar (doskaga yozing):**

1. Sizning kompaniyangizdagi eng qimmatli **asset** nima? (server, ma'lumotlar bazasi, mijoz ma'lumotlari?)
2. Bu asset uchun qanday **threat**lar bor? 
3. Hozirgi **vulnerability**laringiz qanday? (eskirgan dasturlar, zaif parollar?)
4. Eng yuqori **risk** qaysi?

(Har bir talabadan 1-2 minutda javob oling. Ularni doskaga yozib boring)

### Mashq 3: Birinchi xavfsizlik tekshiruvi (10 daq)

> **O'qituvchi:**  
> "Endi har biringiz o'z telefoningiz yoki kompyuteringizni oling. Quyidagilarni tekshiring:"

**Tekshirish ro'yxati:**

```
[ ] Telefonimda ekran qulfi bor? (PIN/parol/biometrik)
[ ] Parolim oxirgi 6 oyda o'zgargan?
[ ] Ikki bosqichli autentifikatsiya yoqilgan? (Google, Telegram)
[ ] Operatsion tizim yangilangan?
[ ] Antivirus o'rnatilgan? (Windows uchun)
[ ] Wi-Fi parolim kuchli?
[ ] Ommaviy Wi-Fi'da bank ilovasini ochaman?
```

> "Aytingchi, kim hammasini 'ha' deb javob bera oldi?"

(Odatda hech kim - bu yaxshi o'qitish momenti)

> "Mana, biz tizim administratorlari! Agar **biz** o'zimiz xavfsizlikka rioya qilmasak, mijozlarimizni qanday himoya qilamiz?"

---

## DARS YAKUNI (5 daqiqa)

### Bugungi xulosa

> "Bugun biz quyidagilarni o'rgandik:
> 1. **Kiberxavfsizlik** - bu texnologiya + jarayon + insonlar
> 2. **3 ta yirik hujum** - Stuxnet, WannaCry, SolarWinds
> 3. **CIA Triad** - Confidentiality, Integrity, Availability
> 4. **Asosiy terminlar** - Asset, Threat, Vulnerability, Risk
> 
> Eng muhim xulosa: **Kiberxavfsizlik - bu bir kunlik ish emas, bu doimiy jarayon!**"

### Uy vazifasi

> "Quyidagilarni keyingi darsgacha tayyorlang:
> 
> 1. **Yozma vazifa:** Oxirgi 5 yildagi 3 ta yirik kiberhujum haqida hisobot yozing (har biri 1 sahifa). Quyidagilarni yoriting:
>    - Hujum nomi va sanasi
>    - Kim hujum qildi?
>    - Qanday qildi?
>    - CIA Triad'dan qaysisi buzildi?
>    - Zarar miqdori
>    - Saboq nima?
> 
> 2. **Amaliy vazifa:** O'z parolingizni o'zgartiring (kamida 12 belgi, raqam, harf, simvol). Va 2FA ni yoqing - Google, Telegram, Facebook'da.
> 
> 3. **O'qish:** Telegram guruhga qo'shilib, men yuborgan maqolani o'qing."

### Keyingi darsda

> "Ertaga biz **xavfsizlik turlarini** o'rganamiz: tarmoq, ilova, endpoint, cloud xavfsizliklari. Kelishingiz shart!"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Bu darsda ehtiyot bo'ling
- Birinchi kun bo'lgani uchun **juda chuqur texnikaga** kirmang
- Hikoyalar va misollar bilan **qiziqtiring**
- Talabalar darajasini o'rganib oling - keyingi darslarni shunga moslang

### Foydali manbalar
- **Kitob:** "The Cuckoo's Egg" - Clifford Stoll (kiberxavfsizlik tarixi)
- **Film:** "Mr. Robot" - real xakerlik ko'rsatilgan
- **Sayt:** [haveibeenpwned.com](https://haveibeenpwned.com) - email tekshirish

### Talabalarga ko'rsatish uchun
1. Wikipedia'dan **Stuxnet** haqida video ko'rsating (5 daqiqa)
2. **haveibeenpwned.com** saytida o'z email'ingizni tekshiring va ularga ko'rsating
