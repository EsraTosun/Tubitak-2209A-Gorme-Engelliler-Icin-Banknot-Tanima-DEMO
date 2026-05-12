[Portfolyo.docx](https://github.com/user-attachments/files/27633125/Portfolyo.docx)# 📱 Görme Engelliler İçin Banknot Tanıma Uygulaması (TÜBİTAK 2209-A)

Bu proje, görme engelli bireylerin günlük hayatta finansal işlemlerini daha güvenli ve bağımsız bir şekilde gerçekleştirebilmeleri için geliştirilmiş, görüntü işleme tabanlı bir mobil yardımcıdır. **TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma Projeleri Destekleme Programı** kapsamında desteklenmiş bir mühendislik çalışmasıdır.

## 🚀 Proje Özeti
Uygulama, akıllı telefon kamerasını kullanarak Türk Lirası banknotlarını gerçek zamanlı olarak tanır ve kullanıcıya sesli geri bildirim verir. Projenin en temel özelliği, yüksek doğruluk oranı için algoritmaların iki farklı katmanda test edilmiş olmasıdır.

## 🛠 Teknik Mühendislik Süreçleri
Bir Yazılım Mühendisi disipliniyle, projenin kararlılığını ölçmek için çapraz doğrulama (cross-validation) yöntemi uygulanmıştır:

### 1. Araştırma ve Algoritma Doğrulama (Python & OpenCV)
Mobil entegrasyon öncesinde, görüntü işleme algoritmaları Python üzerinde prototiplenmiştir. Bu aşamada aşağıdaki teknikler uygulanmıştır:
*   **Görüntü Döndürme (Rotation):** Banknotun kameraya tutulduğu açıdan bağımsız olarak tanınması sağlanmıştır.
*   **Ölçeklendirme (Scaling):** Uzaklık ve yakınlık farklarını normalize etmek için geometrik dönüşümler yapılmıştır.
*   **Gürültü Azaltma (Blurring/Filtering):** Düşük ışıkta veya düşük kaliteli kameralarda oluşan gürültüler temizlenmiştir.

### 2. Mobil Uygulama Geliştirme (Flutter & Dart)
Doğruluğu kanıtlanmış algoritmalar, Flutter ortamına aktarılarak performans odaklı bir mobil uygulama haline getirilmiştir. Gerçek zamanlı görüntü işleme ile düşük gecikmeli sonuçlar elde edilmiştir.

## 📊 İşlem Akışı
```mermaid
graph TD
    A[Ham Kamera Verisi] --> B[Görüntü Döndürme & Normalizasyon]
    B --> C[Ön İşleme & Gürültü Filtreleme]
    C --> D[Öznitelik Çıkarımı]
    D --> E{Banknot Tanıma Kararı}
    E -->|Başarılı| F[Sesli Bildirim: Örn. 100 TL]
    E -->|Başarısız| G[Yeniden Tara Hatırlatıcısı]

<img width="720" height="1600" alt="WhatsApp Görsel 2024-02-13 saat 12 58 44_13677566" src="https://github.com/user-attachments/assets/6596890c-ba6c-4a20-bf81-4b68953f6d3c" />
<img width="720" height="1600" alt="WhatsApp Görsel 2024-02-13 saat 12 58 43_c21f8b89" src="https://github.com/user-attachments/assets/80582f22-b37d-46a2-abe5-be2cda6971a4" />
