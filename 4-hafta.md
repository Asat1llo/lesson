# 4-HAFTA: Hujumlar, Himoya va Yakuniy Loyihalar (22-30 kunlar)

## 22-KUN: Social Engineering va Phishing
**Maqsad:** Inson omiliga asoslangan hujumlarni tushunish.

### 1-soat: Nazariy qism
- Social Engineering nima?
- Phishing turlari: Spear Phishing, Whaling, Vishing, Smishing
- Pretexting, Baiting, Tailgating, Quid Pro Quo
- Real misollar: yirik kompaniyalarga qarshi hujumlar

### 2-soat: Amaliy qism
- Phishing email belgilarini aniqlash
- Email headers tahlil qilish
- GoPhish bilan tanishuv (etik test uchun)
- Praktika: Foydalanuvchilar uchun xavfsizlik treningi materiali yaratish

---

## 23-KUN: Malware tahlili asoslari
**Maqsad:** Zararli dasturlarni tushunish va aniqlash.

### 1-soat: Nazariy qism
- Malware hayot tsikli
- Static vs Dynamic analiz
- Sandbox muhitlari
- Indicators of Compromise (IoC)
- YARA qoidalari

### 2-soat: Amaliy qism
- VirusTotal va Hybrid Analysis
- Demo: Sandbox'da malware ishga tushirish (xavfsiz muhitda)
- Hash bilan malware aniqlash
- Praktika: IoC ro'yxatini yaratish

---

## 24-KUN: Penetration Testing asoslari
**Maqsad:** Etik xakerlik va zaiflik testlash.

### 1-soat: Nazariy qism
- Penetration Testing nima?
- Pentest bosqichlari: Reconnaissance → Scanning → Exploitation → Post-Exploitation → Reporting
- Black Box, White Box, Gray Box testing
- Etik va huquqiy masalalar
- Pentest standartlari: OSSTMM, PTES, NIST

### 2-soat: Amaliy qism
- Kali Linux bilan tanishuv
- Metasploit Framework asoslari
- Praktika: Lokal virtual mashinada zaiflikni topish va exploit qilish (DVWA yoki Metasploitable)

---

## 25-KUN: Web ilovalar xavfsizligi - OWASP Top 10
**Maqsad:** Web zaifliklarni chuqur o'rganish.

### 1-soat: Nazariy qism
- OWASP Top 10 (2021):
  1. Broken Access Control
  2. Cryptographic Failures
  3. Injection (SQL, Command)
  4. Insecure Design
  5. Security Misconfiguration
  6. Vulnerable Components
  7. Authentication Failures
  8. Software/Data Integrity Failures
  9. Logging Failures
  10. SSRF

### 2-soat: Amaliy qism
- DVWA (Damn Vulnerable Web Application) o'rnatish
- SQL Injection demo
- XSS (Cross-Site Scripting) demo
- Burp Suite bilan tanishuv
- Praktika: Web ilovani audit qilish checklist'i

---

## 26-KUN: Incident Response (Hodisaga javob)
**Maqsad:** Kiberhujum sodir bo'lganda harakat qilishni o'rganish.

### 1-soat: Nazariy qism
- Incident Response bosqichlari (NIST):
  1. Preparation
  2. Detection & Analysis
  3. Containment
  4. Eradication
  5. Recovery
  6. Lessons Learned
- CSIRT (Computer Security Incident Response Team)
- Forensics asoslari
- Chain of Custody

### 2-soat: Amaliy qism
- Incident Response Plan shabloni
- Praktika: Stsenariy asosida hujumga javob berish (table-top exercise)
- Log tahlili orqali hujumni qayta tiklash
- Hisobot yozish

---

## 27-KUN: Compliance, standartlar va qonunlar
**Maqsad:** Huquqiy va me'yoriy talablarni bilish.

### 1-soat: Nazariy qism
- Xalqaro standartlar:
  - ISO 27001/27002
  - NIST Cybersecurity Framework
  - PCI DSS (to'lov kartalari)
  - GDPR (ma'lumotlar himoyasi)
  - HIPAA (tibbiyot)
- O'zbekiston qonunchiligi:
  - "Kiberxavfsizlik to'g'risida"gi qonun
  - Shaxsiy ma'lumotlar himoyasi qonuni

### 2-soat: Amaliy qism
- ISO 27001 talablar bilan tanishuv
- Risk assessment matritsasi tuzish
- Praktika: Kompaniya uchun compliance checklist

---

## 28-KUN: Cloud Security asoslari
**Maqsad:** Cloud muhitida xavfsizlik.

### 1-soat: Nazariy qism
- Cloud modellari: IaaS, PaaS, SaaS
- Public, Private, Hybrid Cloud
- Shared Responsibility Model
- Cloud xavfsizlik xavf-xatarlari
- AWS, Azure, GCP xavfsizlik xizmatlari (umumiy)

### 2-soat: Amaliy qism
- AWS IAM (Identity and Access Management) demo
- S3 bucket xavfsizligi
- Cloud Security Posture Management
- Praktika: Cloud xavfsizlik checklist

---

## 29-KUN: Kursning yakuniy amaliy loyihasi
**Maqsad:** Barcha bilimlarni amalda birlashtirish.

### 1-soat: Loyiha boshlanishi
**Loyiha:** "Kichik kompaniya uchun to'liq kiberxavfsizlik strategiyasi"

Talabalar quyidagilarni tayyorlashlari kerak:
- Tashkilot uchun xavfsizlik siyosati
- Tarmoq arxitekturasi diagrammasi
- Server hardening rejasi
- Backup va DR rejasi
- Incident Response rejasi
- Xodimlarni o'qitish dasturi

### 2-soat: Loyiha ustida ishlash
- Talabalar guruhlarda yoki yakka ishlaydi
- O'qituvchi maslahat berib boradi
- Loyiha matnini, diagrammalarni tayyorlash

---

## 30-KUN: Yakuniy taqdimot va sertifikatlash
**Maqsad:** Kursni yakunlash va kelajak rejalari.

### 1-soat: Loyihalarni taqdim qilish
- Har bir talaba/guruh o'z loyihasini taqdim qiladi
- Savol-javob va muhokama
- Baholash

### 2-soat: Yakuniy qism
- Kurs bo'yicha umumiy takrorlash
- Yakuniy test (50 ta savol)
- Kelajakda o'rganish uchun yo'nalishlar:
  - Sertifikatlar: CompTIA Security+, CEH, CISSP, OSCP
  - Foydali resurslar: TryHackMe, HackTheBox, OverTheWire
  - Kasbiy yo'llar: SOC Analyst, Pentester, Security Engineer
- Sertifikatlarni topshirish
- Fikr-mulohazalar va xayrlashuv
