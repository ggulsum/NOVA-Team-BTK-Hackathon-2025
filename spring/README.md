# Backend 
## Özet
Bu backend servisi, e-ticaret ürün görsellerinden elde edilen açıklamaları işleyerek detaylı ürün açıklaması, kategoriye özel pazarlama önerileri ve SEO uyumlu başlık & hashtag bilgileri sağlar.
Sistem, Google Gemini API ve LangChain Servisi ile entegre çalışır.

## Amaç
- Ürün görsellerini analiz ederek anlamlı açıklamalar üretmek
- Ürün açıklamasını LangChain servisine göndererek pazarlama önerileri almak
- SEO başlığı ve hashtag üretiminde kullanılmak üzere veriyi frontend’e iletmek

## Proje Mimarisinde Rolü
Backend, projenin **görsel işleme ve veri iletimi** katmanıdır:

- Girdi: React arayüzünden gelen ürün görseli.
- İşlem:
  - Görseli Base64 formatına çevirir.
  - Google Gemini API üzerinden görsel analizi yapar.
  - Elde edilen açıklamayı LangChain servisine gönderir.

- Çıktı:
  - Ürün açıklaması (React arayüzünde gösterilir)
  - Pazarlama önerileri (LangChain’den)
  - SEO bilgileri (frontend’in sonraki isteğinde alınır)

## Kullanılan Teknolojiler
- **Java 17+**
- **Spring Boot**
- **Spring Web**
- **RestTemplate**
- **Lombok**
- **Google Gemini API**
- **LangChain API**
- **Multipart File Upload**
- **Base64 Encoding**

## Çalışma Akışı
- **React Arayüzü** görseli /api/gemini/analyze endpoint’ine gönderir.

- **ImageServiceImpl** görseli Base64’e çevirir.

- **GeminiServiceImpl** görseli ve prompt bilgisini Google Gemini API’ye gönderir, açıklama alır.

- **LangchainServiceImpl** bu açıklamayı LangChain servisine gönderir, pazarlama metnini alır.

- **API**, React arayüzüne açıklamayı döner.

- **Frontend**, pazarlama metnini kullanarak SEO endpoint’ini çağırır.

## API Endpointleri
### 1️⃣ Ürün Görseli Analizi

**URL:**  
```bash
POST /api/gemini/analyze
```
**Parametreler:**
- files (MultipartFile) — Ürün görseli
- Accept-Language (Header) — tr veya en

**Döndürülen Örnek Cevap:**
```json
"Bu kablosuz kulaklık, gürültü engelleme özelliği ve uzun pil ömrü ile..."
```

### 2️⃣ Görsel Yükleme 

**URL:**  
```bash
POST /api/images/upload
```

**Parametreler:**
- file (MultipartFile) — Görsel dosyası

**Döndürülen Cevap:**
```bash
Dosya başarı bir şekilde yüklendi. /uploads/uuid_dosya.jpg
```

## Proje Paket Yapısı
```bash
src/main/java/com/hackathon/hack
│
├── Config/              # RestTemplate ve config ayarları
├── Controller/          # API uç noktaları
├── Dto/                 # Veri transfer objeleri
├── Service/             # İş mantığı servisleri
└── HackApplication.java # Ana uygulama dosyası
```


