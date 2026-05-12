# 📱 Görme Engelliler İçin Banknot Tanıma Uygulaması (TÜBİTAK 2209-A)

Bu proje, görme engelli bireylerin günlük hayatta finansal işlemlerini daha güvenli ve bağımsız bir şekilde gerçekleştirebilmeleri için geliştirilmiş, görüntü işleme tabanlı bir mobil yardımcıdır. **TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma Projeleri Destekleme Programı** kapsamında desteklenmiş bir mühendislik çalışmasıdır.

## 🚀 Proje Özeti
Uygulama, akıllı telefon kamerasını kullanarak Türk Lirası banknotlarını gerçek zamanlı olarak tanır ve kullanıcıya çok kanallı geri bildirim verir. Projenin en temel özelliği, yüksek doğruluk oranı için algoritmaların iki farklı katmanda test edilmiş ve doğrulanmış olmasıdır.

## 🛠 Teknik Mühendislik Süreçleri
Bir Yazılım Mühendisi disipliniyle, projenin kararlılığını ölçmek için çapraz doğrulama (cross-validation) yöntemi uygulanmıştır:

### 1. Araştırma ve Algoritma Doğrulama (Python & OpenCV)
Mobil entegrasyon öncesinde, görüntü işleme algoritmaları Python üzerinde prototiplenmiştir:
*   **Görüntü Döndürme (Rotation):** Banknotun kameraya tutulduğu açıdan bağımsız olarak tanınması sağlanmıştır.
*   **Ölçeklendirme (Scaling):** Uzaklık ve yakınlık farklarını normalize etmek için geometrik dönüşümler yapılmıştır.
*   **Gürültü Azaltma (Blurring/Filtering):** Düşük ışıkta veya düşük kaliteli kameralarda oluşan gürültüler temizlenmiştir.

### 2. Mobil Uygulama Geliştirme (Flutter & Dart)
Doğruluğu kanıtlanmış algoritmalar, Flutter ortamına aktarılarak performans odaklı bir mobil uygulama haline getirilmiştir. Gerçek zamanlı görüntü işleme ile düşük gecikmeli sonuçlar elde edilmiştir.

## 📸 Mobil Uygulama Arayüzü

Uygulamanın kullanıcı dostu ve erişilebilir arayüzünden örnek ekran görüntüleri aşağıdadır. Görsellerde gerçek zamanlı banknot tanıma süreci simüle edilmektedir.

<p align="center">
  <img src="https://github.com/user-attachments/assets/6596890c-ba6c-4a20-bf81-4b68953f6d3c" width="300" alt="Banknot Tanıma Ekranı - 1" />
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/80582f22-b37d-46a2-abe5-be2cda6971a4" width="300" alt="Banknot Tanıma Ekranı - 2" />
</p>

> **♿ Erişilebilirlik Odaklı Tasarım:** Uygulama, hem **Sesli Geri Bildirim** (Text-to-Speech) hem de **Haptik (Titreşimli) Bildirim** özelliklerine sahiptir. Bu sayede gürültülü ortamlarda dahi kullanıcının banknot değerini doğru bir şekilde anlaması sağlanmaktadır.

## 📊 İşlem Akışı
```mermaid
graph TD
    A[Ham Kamera Verisi] --> B[Görüntü Döndürme & Normalizasyon]
    B --> C[Ön İşleme & Gürültü Filtreleme]
    C --> D[Öznitelik Çıkarımı]
    D --> E{Banknot Tanıma Kararı}
    E -->|Başarılı| F[Sesli ve Titreşimli Bildirim]
    E -->|Başarısız| G[Yeniden Tara Hatırlatıcısı]
