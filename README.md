# Atölye Envanteri

Hobi odasındaki hırdavat, devre elemanı ve alet edevatı kutulara göre kataloglayıp isim/açıklama/etikete göre anında arayabildiğin, tek dosyalık bir web uygulaması. Apple cihazları ve bilgisayardan aynı hesapla erişilir, veriler cihazlar arasında senkron çalışır.

**Canlı:** https://hazine.flythespirit.workers.dev

## Özellikler

- Kutu oluşturma, parça ekleme (isim, açıklama, fotoğraf, adet, etiket)
- Fotoğraflar 800px/~100KB'a sıkıştırılıp veritabanında ikili (bytea) veri olarak tutulur; listelemede çekilmez, sadece parça detayında yüklenir
- Etiketlere göre arama/filtreleme, önceden kullanılan etiketlerden hızlı seçim
- Belirli etiketler için özel ikon gösterimi (`tool`, bahçecilik etiketleri vb.)
- E-posta/şifre ile giriş, "beni hatırla" ile kalıcı oturum
- JSON olarak yedek alma / geri yükleme

## Teknik yapı

- Derleme adımı yok — tek bir `index.html` dosyası (HTML + CSS + vanilla JS)
- Veritabanı: [Supabase](https://supabase.com) (Postgres), doğrudan REST API'ye `fetch()` ile bağlanıyor — resmi SDK kullanılmıyor
- Barındırma: Cloudflare Workers (static assets), `wrangler.toml` ile yapılandırılmış
- `_headers` dosyası, tarayıcı önbelleğini kapatarak her ziyaretçinin her zaman güncel sürümü görmesini sağlıyor

## Kurulum


## Dosyalar

- `index.html` — uygulamanın tamamı
- `wrangler.toml` — Cloudflare Workers yapılandırması
- `_headers` — önbellek ayarları
