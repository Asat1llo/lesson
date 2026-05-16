# 5-KUN: Kriptografiya asoslari

**Mavzu:** Shifrlash, hashing, raqamli imzo, sertifikatlar  
**Maqsad:** Talabalar kriptografiyaning asosiy tushunchalarini tushunishi va OpenSSL bilan ishlay olishi  
**Kerakli materiallar:** Linux/Mac terminal yoki Windows + Git Bash, OpenSSL

---

## DARS BOSHIDA (5 daqiqa)

### Salomlashish va o'tgan dars takrorlash

> "Salom! Kechagi mavzu - **Vulnerability**. Tezkor savollar:
> - **CVE** nima?
> - **CVSS 10.0** - bu nima darajasi?
> - **Zero-Day** nimasi xavfli?
> - **Attack Surface** ni qanday kichraytiramiz?
> 
> Yaxshi! Bugun biz **kriptografiya** - bu butun kiberxavfsizlik asosi!"

---

## 1-SOAT: Nazariy qism (45 daqiqa)

### Kirish: Kriptografiya nima? (5 daq)

> **O'qituvchi:**  
> "**Kriptografiya** so'zi yunoncha:  
> - **Kryptos** = yashirin  
> - **Graphein** = yozmoq  
> 
> Ya'ni 'yashirin yozuv'. Ma'lumotni shifrlash va o'qib bo'lmaydigan qilish ilmi.
> 
> **Tarixiy misol:** Yuliy Sezar 2000 yil oldin **Caesar cipher** ishlatgan:"

**Doskaga chizing:**

```
CAESAR CIPHER (Sezar shifri):
Har bir harfni 3 ta orqaga siljiting.

A → D     L → O
B → E     O → R
C → F     V → Y
                          
"SALOM" → "VDORP" 
```

> "Bu - eng oddiy shifr. Bugun zamonaviy shifrlash juda murakkab. Ammo asosiy g'oya **bir xil**: ma'lumotni o'qib bo'lmaydigan qilish."

### Kriptografiyaning 4 ta maqsadi (5 daq)

```
┌─────────────────────────────────────┐
│ KRIPTOGRAFIYA NIMA UCHUN?            │
├─────────────────────────────────────┤
│ 1. CONFIDENTIALITY                   │
│    Maxfiylik (faqat o'zim o'qiyman) │
│                                      │
│ 2. INTEGRITY                         │
│    Yaxlitlik (o'zgartirilmagan)     │
│                                      │
│ 3. AUTHENTICATION                    │
│    Kim ekanligini tasdiqlash        │
│                                      │
│ 4. NON-REPUDIATION                   │
│    Inkor eta olmaslik               │
└─────────────────────────────────────┘
```

> "Ko'rdingizmi - **CIA Triad**'dan 2 tasi bu yerda! Kriptografiya - kiberxavfsizlikning asosiy quroli."

### Symmetric (Simmetrik) Encryption (10 daq)

> **O'qituvchi:**  
> "Birinchi tur - **Symmetric**. **Bitta** kalit bor - shifrlash va deshifrlash uchun."

**Doskaga chizing:**

```
┌──────────────────────────────────────────────┐
│        SYMMETRIC ENCRYPTION                   │
└──────────────────────────────────────────────┘

   ALICE                                  BOB
   ┌────────┐                          ┌────────┐
   │        │                          │        │
   │ Salom  │                          │ Salom  │
   │  Bob!  │                          │  Bob!  │
   └────┬───┘                          └────┬───┘
        │                                    ▲
        │ ENCRYPT                            │ DECRYPT
        │ (Key: 12345)                       │ (Key: 12345)
        ▼                                    │
   ┌────────────┐                       ┌────────────┐
   │ %#@!&*X9zP │  ─────INTERNET────►  │ %#@!&*X9zP │
   └────────────┘                       └────────────┘
   
   Bir XIL kalit ishlatiladi!
```

**Mashhur algoritmlar:**

```
┌───────────┬──────────┬─────────────────────┐
│ ALGORITM  │ KALIT    │ HOLAT               │
├───────────┼──────────┼─────────────────────┤
│ DES       │ 56 bit   │ ESKIRGAN! Ishlatma. │
│ 3DES      │ 168 bit  │ Eskirib boryapti    │
│ AES-128   │ 128 bit  │ Yaxshi              │
│ AES-256   │ 256 bit  │ ENG YAXSHI          │
│ ChaCha20  │ 256 bit  │ Mobil uchun yaxshi  │
└───────────┴──────────┴─────────────────────┘
```

**Afzalliklar:**
- Tezkor (katta fayllar uchun)
- Oddiy

**Kamchilik:**
- **Kalit almashish muammosi!** Bobga kalitni qanday yuboraman?

> "Tasavvur qiling: Bobga shifrlangan xat yuboraman, lekin kalitni qanday yetkazaman? Email orqali? Lekin email ham xavfsiz emas! Bu - **simmetrik shifrlashning katta muammosi**."

### Asymmetric (Assimetrik) Encryption (10 daq)

> **O'qituvchi:**  
> "Bu muammoni hal qilish uchun **Asymmetric Encryption** o'ylab topildi - **2 ta** kalit ishlatadi:
> - **Public Key** (ochiq kalit) - hammaga
> - **Private Key** (xususiy kalit) - faqat o'zimga"

**Doskaga chizing:**

```
┌──────────────────────────────────────────────┐
│       ASYMMETRIC ENCRYPTION (RSA)             │
└──────────────────────────────────────────────┘

   ALICE                                  BOB
   ┌────────┐                          ┌──────────┐
   │ Salom  │                          │PUBLIC KEY│
   │  Bob!  │                          │ (ochiq)  │
   └────┬───┘                          ├──────────┤
        │                              │PRIV. KEY │
        │  Bobning PUBLIC kaliti b/n   │ (xususiy)│
        │  shifrlash                   └──────────┘
        ▼                                    ▲
   ┌────────────┐                            │
   │ %#@!&*X9zP │  ───INTERNET─►             │
   └────────────┘                            │
                                              │
                         Bobning PRIVATE      │
                         kaliti bilan ─────────
                         deshifrlash
```

**Qanday ishlaydi?**

> "1. Bob 2 ta kalit yaratadi: **Public** va **Private**
> 2. Bob **Public** kalitni hammaga beradi (Internetga qo'yadi)
> 3. Alice xat yozadi va **Bobning Public** kaliti bilan shifrlaydi
> 4. Alice xatni jo'natadi
> 5. Faqat **Bob** o'z **Private** kaliti bilan deshifrlay oladi
> 6. Hatto Alice ham bu xatni endi o'qiy olmaydi!
> 
> **Sehrli matematikadan:** Public kalit bilan shifrlangan narsa - faqat Private kalit bilan ochiladi!"

**Mashhur algoritmlar:**

```
┌───────────┬──────────┬─────────────────────┐
│ ALGORITM  │ KALIT    │ HOLAT               │
├───────────┼──────────┼─────────────────────┤
│ RSA-1024  │ 1024 bit │ Eskirib boryapti    │
│ RSA-2048  │ 2048 bit │ Yaxshi              │
│ RSA-4096  │ 4096 bit │ Juda kuchli         │
│ ECC       │ 256 bit  │ Tez va kuchli       │
│ DSA       │ -        │ Faqat imzo uchun    │
└───────────┴──────────┴─────────────────────┘
```

**Kamchilik:** Sekin! Faqat kichik ma'lumotlar uchun.

### Hybrid Approach (3 daq)

> **O'qituvchi:**  
> "Amaliyotda **ikkalasi birga** ishlatiladi - **Hybrid**:"

```
HYBRID (HTTPS qanday ishlaydi):

1. Asymmetric bilan kalit almashinuvi (sekin, lekin xavfsiz)
2. Keyin Symmetric bilan ma'lumot uzatish (tez)

Misol: HTTPS
┌───────────────────────────────────────────┐
│ 1. Sayt RSA Public Key beradi              │
│ 2. Brauzer AES kalit yaratadi              │
│ 3. AES kalitni RSA bilan shifrlab yuboradi │
│ 4. Endi AES bilan barcha trafik shifrlanad.│
└───────────────────────────────────────────┘
```

### Hashing - Sezilmas barmoq izi (7 daq)

> **O'qituvchi:**  
> "**Hashing** - bu shifrlash EMAS! Hashing - **bir tomonlama** funksiya."

**Hashing xususiyatlari:**

```
HASH FUNKSIYA:

INPUT (har xil hajmda)         OUTPUT (doim bir xil)
"salom"            ──HASH──►   "9d1c..."  (256 bit)
"katta matn..."    ──HASH──►   "f2e8..."  (256 bit)
"a"                ──HASH──►   "ca97..."  (256 bit)

XUSUSIYATLARI:
1. Bir tomonlama (qaytarib o'qib bo'lmaydi)
2. Determinik (bir xil input → bir xil output)
3. Kichik o'zgarish - katta farq
4. Collision-resistant (ikki xil input bir xil hash bermaydi)
```

**Mashhur algoritmlar:**

```
┌────────────┬──────────┬─────────────────────┐
│ ALGORITM   │ HAJM     │ HOLAT               │
├────────────┼──────────┼─────────────────────┤
│ MD5        │ 128 bit  │ ESKIRGAN! Buzilgan  │
│ SHA-1      │ 160 bit  │ ESKIRGAN!           │
│ SHA-256    │ 256 bit  │ Yaxshi              │
│ SHA-512    │ 512 bit  │ Juda yaxshi         │
│ bcrypt     │ -        │ Parol uchun ENG YAX.│
│ Argon2     │ -        │ Parol uchun yangi   │
└────────────┴──────────┴─────────────────────┘
```

**Hashing nima uchun?**

```
1. PAROLNI SAQLASH:
   ┌────────────────────────────────────┐
   │ Database'da yo'q:                   │
   │ user1 | "qwerty123"                 │
   │                                     │
   │ Database'da bor:                    │
   │ user1 | "65e84be33532fb784c..."     │
   └────────────────────────────────────┘

2. FAYL YAXLITLIGI:
   ┌────────────────────────────────────┐
   │ Yuklab olganingizda hash tekshirish │
   │ - Original: abc123                  │
   │ - Sizniki: abc123 ✓                 │
   └────────────────────────────────────┘

3. DIGITAL SIGNATURE
4. BLOCKCHAIN
5. GIT (har commit hash)
```

### Digital Signature - Raqamli imzo (5 daq)

> **O'qituvchi:**  
> "**Digital Signature** = Hash + Asymmetric encryption."

```
RAQAMLI IMZOLASH:

1. ALICE xat yozadi
2. Xatning HASH'ini hisoblaydi
3. Hash'ni o'z PRIVATE kaliti bilan shifrlaydi
4. Bu - "imzo"
5. Xat + imzo'ni Bob'ga yuboradi

ALICE:
[Xat] ─HASH─► [Hash] ─PRIVATE KEY─► [IMZO]
[Xat] + [Imzo] ───→  Bob

BOB tasdiqlaydi:
1. Xatning HASH'ini hisoblaydi
2. Imzoni Alice'ning PUBLIC kaliti b/n deshifrlaydi
3. Ikkala HASH'ni solishtiradi
4. Mos kelsa - imzo to'g'ri!
```

**Bu nima berar:**
- **Authentication** - Bu haqiqatan Alice yuborgan
- **Integrity** - Xat o'zgartirilmagan
- **Non-repudiation** - Alice "men yubormaganman" deya olmaydi

---

## TANAFFUS (10 daqiqa)

---

## 2-SOAT: Amaliy qism (45 daqiqa)

### Kirish (3 daq)

> **O'qituvchi:**  
> "Endi **OpenSSL** bilan amalda kriptografiyani ko'ramiz! OpenSSL - bu Linux'da o'rnatilgan, kriptografiyaning **Swiss Army Knife**'i."

**Tekshiring (Linux/Mac):**
```bash
openssl version
# OpenSSL 3.0.x
```

**Windows uchun:** Git Bash o'rnating, unda OpenSSL bor.

### Mashq 1: Hashing (10 daq)

#### MD5 hash:

```bash
echo -n "salom" | md5sum
# d3d8a8c2c8f8a3e9c8a3e9c8a3e9c8a3
```

#### SHA-256:

```bash
echo -n "salom" | sha256sum
# 9d1c3a5f7c8b... 
```

#### Eksperiment - bir harfni o'zgartiring:

```bash
echo -n "salom" | sha256sum
echo -n "Salom" | sha256sum
# Ikki butunlay boshqa hash!
```

> "Ko'rdingizmi? **Bitta harf farqi** - butunlay boshqa hash. Bu - **avalanche effect**."

#### Fayl hash:

```bash
# Fayl yarating
echo "Bu test fayli" > test.txt

# Hash hisoblash
sha256sum test.txt
# abc123...  test.txt

# Faylni ozgina o'zgartiring
echo "Bu test faili" > test.txt   # 'fayli' → 'faili'

# Yana hash
sha256sum test.txt
# Butunlay boshqa hash!
```

#### Parol hashing (vazifa):

```bash
# 3 ta parol uchun hash hisoblang:
echo -n "qwerty123" | sha256sum
echo -n "Password123!" | sha256sum
echo -n "MyKuchliParol@2024" | sha256sum
```

### Mashq 2: Symmetric Encryption (12 daq)

#### Faylni shifrlash:

```bash
# Test fayl yarating
echo "Bu maxfiy ma'lumot" > maxfiy.txt

# AES-256 bilan shifrlash
openssl enc -aes-256-cbc -salt -in maxfiy.txt -out maxfiy.enc
# Parol so'raladi: ParolMening123

# Shifrlangan faylni ko'ring
cat maxfiy.enc
# Ko'rib bo'lmaydigan belgilar...

# Deshifrlash
openssl enc -aes-256-cbc -d -in maxfiy.enc -out maxfiy_deshifr.txt
# Parol kiriting

cat maxfiy_deshifr.txt
# Bu maxfiy ma'lumot
```

> **Talabalarga vazifa:**  
> "1. O'z ismingiz va familiyangizni faylga yozing  
> 2. AES bilan shifrlang  
> 3. Qo'shni talaba bilan shifrlangan fayl va parolni almashtiring  
> 4. Uning faylini deshifrlang"

### Mashq 3: RSA Key Pair (15 daq)

#### Private key yaratish:

```bash
# 2048-bit RSA private key
openssl genrsa -out private.pem 2048

# Faylni ko'ring
cat private.pem
# -----BEGIN PRIVATE KEY-----
# MIIEvQIBADANBgkqhkiG9w0BA...
# -----END PRIVATE KEY-----
```

#### Public key chiqarish:

```bash
# Private'dan Public yaratish
openssl rsa -in private.pem -pubout -out public.pem

cat public.pem
# -----BEGIN PUBLIC KEY-----
# MIIBIjANBgkqhkiG9w0BAQEF...
# -----END PUBLIC KEY-----
```

#### Faylni Public Key bilan shifrlash:

```bash
echo "Maxfiy xabar" > xabar.txt

# Public key bilan shifrlash
openssl rsautl -encrypt -inkey public.pem -pubin -in xabar.txt -out xabar.enc

# Private key bilan deshifrlash
openssl rsautl -decrypt -inkey private.pem -in xabar.enc -out xabar_dec.txt

cat xabar_dec.txt
# Maxfiy xabar
```

> **Eksperiment:** Public bilan deshifrlashga harakat qiling - **xato chiqadi**!

```bash
openssl rsautl -decrypt -inkey public.pem -pubin -in xabar.enc -out test.txt
# Error: A private key is needed for this operation
```

### Mashq 4: Digital Signature (5 daq)

```bash
# Faylni imzolash
echo "Men bu hujjatni tasdiqlayman" > hujjat.txt

# Imzo yaratish (Private key bilan)
openssl dgst -sha256 -sign private.pem -out hujjat.sig hujjat.txt

# Imzoni tekshirish (Public key bilan)
openssl dgst -sha256 -verify public.pem -signature hujjat.sig hujjat.txt
# Verified OK

# Faylni o'zgartiring va qayta tekshiring
echo "Men bu hujjatni TASDIQLAMAYMAN" > hujjat.txt
openssl dgst -sha256 -verify public.pem -signature hujjat.sig hujjat.txt
# Verification Failure!
```

> "Mana, **Digital Signature** ishlaydi! O'zgartirsangiz - tasdiqlash buziladi."

---

## DARS YAKUNI (5 daqiqa)

### Bugungi xulosa

> "Bugun o'rgandik:
> 1. **Symmetric** - bitta kalit, tezkor (AES-256)
> 2. **Asymmetric** - ikki kalit (RSA, ECC)
> 3. **Hashing** - bir tomonlama (SHA-256)
> 4. **Digital Signature** = Hash + Asymmetric
> 5. **HTTPS** - hybrid yondashuv
> 
> **OpenSSL** bilan amalda ishladik!"

### Uy vazifasi

> "1. **Amaliy:** O'z 'pochta tizimingiz' yaratish:
>    - O'z RSA kalitlarini yarating
>    - Public key'ni qo'shni talabaga yuboring
>    - U sizga shifrlangan xabar yuborsin
>    - Siz deshifrlang
> 
> 2. **Yozma:** O'z so'zlaringizda tushuntiring:
>    - HTTPS qanday ishlaydi?
>    - Nega parolni hash qilamiz, shifrlash emas?
>    - Digital signature nima uchun?
> 
> 3. **O'qish:** TLS Handshake jarayoni"

### Keyingi darsda

> "Ertaga **Authentication va Authorization** - kim siz va nima qila olasiz?"

---

## QO'SHIMCHA: O'qituvchi uchun maslahatlar

### Diqqat
- Kriptografiya **murakkab** mavzu - sekin tushuntiring
- **Matematik formulalar**ga kirmang - amaliyotga e'tibor
- **Hashing va Encryption farqi** - eng ko'p adashtiriladigan joy

### Foydali resurslar
- **Cryptopals**: cryptopals.com - amaliy mashqlar
- **Khan Academy**: Cryptography kursi
- **OpenSSL Cookbook**: bepul kitob
