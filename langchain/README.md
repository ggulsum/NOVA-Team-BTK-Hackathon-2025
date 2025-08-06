# LangChain Servisi — Doğal Dil İşleme Modülü

## Özet
LangChain servisi, ürün görsellerinden elde edilen açıklamaları işleyerek **kategori tahmini**, **kategoriye özel pazarlama metni** ve **SEO uyumlu başlık & hashtag** üretimi yapar.  
Bu sayede e-ticaret satıcıları, ürünlerini hem daha etkili tanıtabilir hem de arama motorlarında görünürlüklerini artırabilir.

---

## Amaç
Bu modül, görselden elde edilen ürün açıklamalarını **anlamlı, pazarlamaya hazır metinlere** dönüştürmeyi hedefler:

- Ürünün hangi kategoriye ait olduğunu belirler.
- Kategoriye uygun, **3 adet ilgi çekici pazarlama cümlesi** üretir.
- SEO açısından güçlü başlıklar ve hashtagler hazırlar.

---

## Sistemdeki Yeri ve Görevi
- **Girdi:** Spring Boot + Gemini API tarafından üretilen ürün açıklaması.  
- **İşlem:** LangChain + Google Gemini LLM ile metin analizi ve üretim.  
- **Çıktı:** Kategori, pazarlama önerileri, SEO başlığı ve hashtag listesi.  

Bu modül sayesinde metin üretim süreci tamamen otomatikleşir, manuel içerik yazma ihtiyacı ortadan kalkar.

---

## Kullanılan Teknolojiler
- **FastAPI**  
- **LangChain**
- **Google Gemini API** 
- **Pydantic**  
- **CORS Middleware** 

---

## Çalışma Prensibi
1. **Kategori Tahmini** — `category_classifier.py` dosyası, ürün açıklamasını analiz ederek önceden tanımlı kategorilerden birini seçer.  
2. **Kategoriye Özel Pazarlama** — `chains.py` dosyasındaki `get_chain_for_category` fonksiyonu, kategoriye ve dile uygun pazarlama cümleleri üretir.  
3. **SEO Üretimi** — `seo_chain`, pazarlama metninden SEO uyumlu başlık ve hashtag listesi oluşturur.  
4. **API Yanıtı** — Sonuç JSON formatında geri döner, frontend tarafından direkt kullanılabilir.

---

## API Uç Noktaları

### 1️⃣ `/generate-marketing`
**Girdi:**
```json
{
  "description": "Kablosuz bluetooth kulaklık, gürültü engelleme özellikli.",
  "language": "tr"
}
```

**Çıktı:**
```json
{
  "category": "Teknoloji",
  "marketing_ideas": "1. Müzik keyfini özgürce yaşayın...\n2. Gürültü engelleme ile net ses deneyimi...\n3. Uzun pil ömrü ile kesintisiz kullanım..."
}
```

### 2️⃣ `/generate-seo`
**Girdi:**
```json
{
  "marketing_text": "Kablosuz özgürlüğü keşfedin...",
  "language": "tr"
}
```

**Çıktı:**
```json
{
  "title": "Kablosuz Müzik Keyfi: Gürültü Engelleme Özellikli Kulaklık",
  "hashtags": ["#kablosuzkulaklık", "#müzik", "#gürültüengelleme", "#teknoloji", "#sesdeneyimi"]
}
```
