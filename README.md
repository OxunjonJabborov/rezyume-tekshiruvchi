# Rezyume Tekshiruvchi

PDF rezyumeni vakansiya talablari bilan solishtirib, moslik ballini (0–100), topilgan va yetishmayotgan ko'nikmalarni hamda o'zbek tilida aniq tavsiyalarni beradigan web-ilova. Tashqi AI API'larsiz, qoidalar va matematik algoritmlar asosida ishlaydi.

## Muammo

**Kim uchun:** ish izlayotgan nomzodlar (birinchi navbatda IT sohasida) va rezyumelarni saralaydigan HR mutaxassislari.

**Hozirgi holat:** ko'plab kompaniyalar rezyumelarni avtomatik tizimlar (ATS) yoki kalit so'zlar orqali saralaydi. Nomzod rezyumesi nega rad etilganini bilmaydi: kerakli ko'nikma yozilmaganmi, bo'limlar topilmadimi yoki kontaktlar o'qilmadimi?

**Nega mavjud yechimlar yetarli emas:** mashhur rezyume tekshirish servislari ingliz tiliga mo'ljallangan va asosan pullik. Ular o'zbek tilining xususiyatlarini hisobga olmaydi:
- qo'shimchalar: `Python'da`, `loyihalarni`, `ma'lumotlar bazasida`;
- ikki yozuv: lotin va kirill;
- `o'` va `g'` harflarining turli yozilishi: `o'`, `o‘`, `oʻ`, `` o` ``.

**Yechim:** o'zbek tilini tushunadigan, natijasini tushuntirib bera oladigan (har bir ball qayerdan kelganini ko'rsatadigan) bepul tahlil vositasi.

## MVP chegarasi

### Kiradi
- Matnli PDF rezyume (5 MB gacha) va vakansiya matnini qabul qilish
- Ko'nikmalarni lug'at va sinonimlar orqali aniqlash, vakansiya bilan solishtirish
- Kontaktlarni tekshirish: email, telefon (`+998`), LinkedIn/GitHub, manzil
- Bo'limlarni tekshirish: Summary, Experience, Education, Skills
- Sana formati, so'zlar soni va o'lchanadigan natijalar (raqam, foiz) tekshiruvi
- 0–100 ball va uning tarkibiy qismlari
- O'zbek tilidagi tavsiyalar
- REST API va bitta sahifali web interfeys

### Kirmaydi (keyingi versiyalarda)
- Skanerlangan (rasm ko'rinishidagi) PDF va OCR
- DOCX va boshqa formatlar
- Tashqi AI API'lar (ChatGPT, Gemini va h.k.)
- Ro'yxatdan o'tish va shaxsiy kabinet
- Rezyumeni avtomatik tuzatish yoki qayta yozish
- Bitta rezyumeni bir vaqtda bir nechta vakansiyaga solishtirish
- Rus tilidagi rezyumelarni to'liq tahlil qilish

## Tillar

| Til | MVP'da | Izoh |
|---|---|---|
| O'zbek (lotin) | ✅ To'liq | Asosiy til |
| O'zbek (kirill) | ✅ To'liq | Ichkarida lotin yozuviga o'giriladi |
| Ingliz | ✅ Texnik atamalar | `Python`, `Docker`, `REST API` kabi atamalar rezyumelarda deyarli doim inglizcha yoziladi |
| Rus | ❌ | Keyingi versiyada |

Foydalanuvchi interfeysi va tavsiyalar o'zbek tilida bo'ladi.

## Muvaffaqiyat mezonlari

Tizim qo'lda belgilangan test to'plamida (golden dataset: 20+ rezyume, 10+ vakansiya) quyidagi natijalarni ko'rsatsa, MVP tayyor hisoblanadi:

| Nimani o'lchaymiz | Metrika | Maqsad | Nega shu raqam |
|---|---|---|---|
| Ko'nikmalarni topish | Precision | ≥ 0.95 | Noto'g'ri topilgan ko'nikma ballni sun'iy oshiradi va foydalanuvchini aldaydi |
| Ko'nikmalarni topish | Recall | ≥ 0.90 | Topilmay qolgan ko'nikma nomzodga nohaq past ball beradi |
| Email va telefonni topish | Aniqlik | ≥ 0.99 | Format qat'iy belgilangan, xato deyarli bo'lmasligi kerak |
| Bo'limlarni topish | Aniqlik | ≥ 0.90 | Sarlavhalar har xil yoziladi, biroz xatoga yo'l qo'yiladi |
| Tezlik | 2 sahifali PDF tahlili (p95) | < 300 ms | Foydalanuvchi natijani darhol ko'rishi kerak |

## Natijani talqin qilish

| Ball | Daraja | Ma'nosi |
|---|---|---|
| 0–39 | Past moslik | Rezyume vakansiyaga jiddiy moslashtirilishi kerak |
| 40–69 | O'rtacha moslik | Asosiy talablar bor, lekin muhim kamchiliklar mavjud |
| 70–100 | Yuqori moslik | Rezyume vakansiyaga yaxshi mos keladi |

## Holat

🚧 Loyiha ishlab chiqilmoqda. Joriy bosqich: **Sprint 0, test to'plamini tayyorlash**.