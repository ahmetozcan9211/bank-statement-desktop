# Banka Ekstre Görüntüleyici (Masaüstü)

Bankaların web servislerinden hesap hareketlerini çekip tek ekranda gösteren, Excel'e aktaran hafif bir araç. Sadece Python standart kütüphanesi kullanılır, kurulum gerektirmez.

> Bu depo bir proje vitrinidir. Kaynak kod paylaşılmamaktadır.

## Özellikler

- Farklı bankaların SOAP servislerine tek arayüzden bağlanma (Ziraat Bankası, DenizBank)
- Vergi numarasıyla hesap listesini otomatik bulma
- Tarih aralığına göre hareket sorgulama, tüm hesapları tek tabloda birleştirme
- Ortak Excel çıktısı
- Eklenti mimarisi: yeni bir banka, `Banka` temel sınıfından türeyen tek bir dosyayla eklenir
- Hata ayıklama araçları: ham XML kaydı, WSDL'den metot ve alan keşfi, komut satırı test modu

## Mimari

```
bankalar/
  temel.py      → Banka (soyut sınıf: hesaplar(), hareketler())
  soap.py       → bağımlılıksız SOAP istemcisi
  ziraat.py     → Ziraat uygulaması
  denizbank.py  → DenizBank uygulaması
app.py          → yerel HTTP sunucusu + JSON API
static/         → tek sayfalık web arayüzü
```

## Teknolojiler

`Python 3.10+` (yalnızca standart kütüphane) · `SOAP/WSDL` · `HTML/JS`

## İlgili proje

Aynı işi yapan, Docker ile sunucuda çalışan web sürümü: **bank-transactions-web**
