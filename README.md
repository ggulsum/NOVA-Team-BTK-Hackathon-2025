# Ürün Açıklama ve Pazarlama Öneri Sistemi (AI Tabanlı)

Bu proje, e-ticaret satıcılarının ürün görselleri üzerinden otomatik olarak **ürün açıklamaları**, **kategoriye özel pazarlama önerileri** ve **SEO uyumlu içerikler** oluşturabilmesini sağlayan yapay zeka destekli bir sistemdir.

BTK Akademi HACKATHON 2025 kapsamında geliştirilmiştir.

---

## Genel Mimari

Proje 3 ana bileşenden oluşur:

1. **Frontend (React)**  
   Kullanıcı arayüzü: Görsel yükleme, dil seçimi, çıktıların gösterimi.

2. **Backend (Spring Boot)**  
   Görsel işleme, Google Gemini API üzerinden açıklama üretimi ve LangChain servisine yönlendirme.

3. **LLM Servisi (FastAPI & LangChain)**  
   Açıklamaya göre kategori tahmini, pazarlama önerileri ve SEO içerik üretimi.

---

## Amaç

- Ürün görselinden **açıklama üretimi** (Gemini Vision API ile)
- Ürün açıklamasından **pazarlama metni ve SEO içerikleri** (LangChain + LLM)
- Kullanıcıya kolay ve hızlı bir içerik üretim deneyimi sunmak

---
## Kullanılan Teknolojiler

Proje üç ana katmandan oluşur. Her katmanla ilgili kullanılan teknolojiler, mimari detaylar ve çalışma prensipleri ilgili klasörün `README.md` dosyasında detaylı olarak açıklanmıştır:

| Katman | Açıklama | Link |
|--------|----------|------|
| **Frontend** | React tabanlı kullanıcı arayüzü | [react/README.md](./react/README.md) |
| **Backend** | Spring Boot tabanlı görsel işleme ve API yönetimi | [spring/README.md](./spring/README.md) |
| **LangChain API** | FastAPI + LangChain ile LLM işlemleri | [langchain/README.md](./langchain/README.md) |

Her klasör altında, kullanılan kütüphaneler, işlevsel modüller ve sistemin nasıl çalıştığına dair teknik açıklamalar mevcuttur.


---

## Uçtan Uca Akış

1. Kullanıcı ürün görselini frontend üzerinden yükler.
2. Görsel, Spring Boot API’ye iletilir.
3. Görsel, Gemini API ile işlenir ve açıklama oluşturulur.
4. Bu açıklama LangChain servisine gönderilir:
   - Kategori tahmini yapılır.
   - Pazarlama önerileri üretilir.
   - SEO başlığı + hashtag listesi çıkarılır.
5. Tüm çıktı frontend’de kullanıcıya gösterilir.

---


## Katılımcılar

| İsim | GitHub |
|------|--------|
| Gülsüm Küntür | [@ggulsum](https://github.com/ggulsum) |
| Yunus Meriç | [@YunusMeric](https://github.com/YunusMeric) |

---

