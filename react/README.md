# React Arayüzü
## Özet

Bu React tabanlı arayüz, e-ticaret satıcılarının ürün görsellerinden yola çıkarak ürün açıklaması, kategoriye özel pazarlama önerileri ve SEO uyumlu başlık & hashtagler elde etmesini sağlar.
Kullanıcı dostu tasarımı sayesinde teknik bilgiye sahip olmayan kişiler bile kolayca içerik üretebilir.

---

## Temel Özellikler
**Dil Seçimi —** Türkçe ve İngilizce destekler.

**Görsel Yükleme —** Ürün fotoğrafını sisteme yükleyebilme.

**Anında Önizleme —** Yüklenen görselin arayüzde önizlenmesi.

**Ürün Açıklaması —** Görsel analizi sonrası yapay zeka tarafından oluşturulur.

**Kategoriye Özel Pazarlama Önerileri —** 3 adet ilgi çekici pazarlama cümlesi sunar.

**SEO İçeriği —** SEO uyumlu başlık ve 5 adet hashtag üretir.

**Tek Tıkla Kopyalama —** Her çıktı, kopyalama butonu ile panoya alınabilir.

---

## Arayüz Akışı
### Görsel Yükleme
- Kullanıcı "Dosya Seç" butonuyla görsel yükler.
- Yüklenen görsel arayüzde önizlenir.

### Dil Seçimi
- Kullanıcı çıktıların Türkçe mi İngilizce mi olacağını belirler.

### Gönder Butonu
- Spring Boot API’ye görsel gönderilir, Google Gemini ile açıklama üretilir.

### Pazarlama ve SEO İçeriği
- LangChain servisiyle kategori tahmini yapılır, 3 pazarlama önerisi ve SEO içeriği döner.

### Sonuçların Görüntülenmesi
- Ürün açıklaması, pazarlama önerileri ve SEO çıktıları ayrı kutucuklarda gösterilir.
- Her kutucukta kopyalama butonu bulunur.

---

## Backend Entegrasyonu
**Spring Boot Servisi —** Görsel analizi ve ürün açıklaması üretimi.

**FastAPI LangChain Servisi —** Kategori tahmini, pazarlama önerisi ve SEO içeriği.

