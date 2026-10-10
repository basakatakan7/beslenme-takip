# Beslenme Defteri

SwiftUI ZIP’inden uyarlanan Türkçe, iPhone ve masaüstü uyumlu beslenme takip uygulaması. Harici çalışma zamanı paketi, hesap veya sunucu veritabanı gerektirmez.

## Geliştirme

Node.js 24 (testler) ve Python 3 (statik geliştirme sunucusu) ile:

```sh
cd /workspace/beslenme-takip
npm start
```

Sunucu 8080 portunda çalışır. `npm test`, ZIP’teki kalori ve makro hesaplarını, geçmiş kiloyu, tarih geçişlerini, takvim değerlendirmesini ve yedek doğrulamasını kontrol eder. Paket bağımlılığı olmadığından `npm install` gerekmez.

## Kullanım

- Günüm: tarih seçimi; yemek adı, öğün, kalori ve makrolar; yürüyüş süresi ve temposu. Kayda dokunarak düzenle veya sil.
- Takvim: günlük kalori ve makro hedeflerine göre renkler; güne dokunarak kayıtları aç.
- Haftalar: kayıtlı günlerin ortalama net kalorisi ve yürüyüş süresi.
- Kilo ve profil: tarihli kilo kayıtları, yaş, boy, başlangıç kilosu ve cinsiyet. Varsayılan profil ZIP’teki 61 yaş / 167 cm / 98 kg değerlerini kullanır; ilk kullanımda düzenleyin.
- JSON yedek indirme ve yükleme. Orijinal iOS uygulamasının `profile` ve `days` biçimi desteklenir. Geri yükleme mevcut kayıtları değiştirir ve onay ister.

Kayıtlar `localStorage` içinde bu tarayıcıya ve site adresine bağlıdır. Cihazlar, tarayıcılar ve Safari ile ana ekran uygulaması arasında aynı depolamanın paylaşılacağını varsaymayın. Tarayıcı verilerini silmek kayıtları silebilir; düzenli yedek alın. Bulut eşitlemesi yoktur.

## iPhone’da kurulum / yayınlama

Depodaki statik dosyaları HTTPS destekleyen bir statik barındırma hizmetinde yayınlayın. Herhangi bir derleme veya API anahtarı gerekmez. Uygulama henüz genel bir internet adresinde yayınlanmış değildir.

Safari’de yayın adresini açın → Paylaş → Ana Ekrana Ekle. Manifest ve PNG simgeleri hazırdır. İlk başarılı açılıştan sonra service worker uygulama dosyalarını önbelleğe alır; HTTPS ortamında çevrimdışı çalışabilir. Yerel geliştirmedeki localhost istisnası telefondan HTTP erişimine uygulanmaz. Gerçek iPhone/Safari üzerinde kurulum ayrıca doğrulanmalıdır.

Hedefler ZIP’teki Mifflin–St Jeor hesapları ve yürüyüş MET değerlerine dayanır; tıbbi öneri değildir. Kalori hedefi en az 1500, aktivite çarpanı 1.375, kalori açığı 500; protein kilo × 1.2, yağ hedef kalorinin %30’u ve kalan karbonhidrattır. Kişisel hedeflerin uygunluğunu sağlık uzmanıyla değerlendirin.
