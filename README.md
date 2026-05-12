# Planner

Editorial bir etkinlik & toplantı planlayıcı. Tek-dosya vanilla HTML/CSS/JS PWA.

## Özellikler

- **Ana Sayfa** — Yaklaşan / Geçmiş / Favoriler sekmeleriyle etkinlik listesi, sıradaki etkinliği vurgulayan hero kart
- **Etkinlik Detayı** — Açıklama, detaylar (etkinlik türü, kapsam, konum, katılımcılar), gün planı timeline'ı, .ics olarak takvime ekleme
- **Yeni Etkinlik / Düzenleme** — 7 kategori (Lansman, Etkinlik, Konser, Brief, Deadline, Toplantı, Keşif), alt tür, tarih, açıklama, kapsam, konum, katılımcılar, gün planı adımları
- **Favoriler** — Detay sayfasındaki yıldız butonuyla
- **Çok Yakında** placeholder'lar — Takvim, Bildirimler, Profilim
- **Offline çalışır** — Service worker ile cache
- **PWA** — Telefona "Ana Ekrana Ekle" ile native gibi yüklenir
- **localStorage** — Veri telefonda yerel olarak tutulur

## Yapı

```
index.html              # Tüm uygulama (HTML + CSS + JS tek dosya)
manifest.json           # PWA manifest
service-worker.js       # Offline cache
icon-192.png            # 192×192 ikon
icon-512.png            # 512×512 ikon
icon-512-maskable.png   # Maskable 512×512
apple-touch-icon.png    # iOS 180×180
favicon-32.png          # Favicon
```

## GitHub Pages Deploy

```bash
# Yeni repo (örnek: pankiznatdet/planner)
git init
git add .
git commit -m "Initial: Planner PWA"
git branch -M main
git remote add origin https://github.com/pankiznatdet/planner.git
git push -u origin main
```

GitHub'da repo ayarları → Pages → Source: `main` branch, `/ (root)`.
URL: `https://pankiznatdet.github.io/planner/`

## Kullanım

İlk açılışta 11 örnek etkinlikle yüklenir (10 yaklaşan + 1 geçmiş). Tüm veri telefonda lokal saklanır — sıfırlamak için tarayıcıda `localStorage.removeItem('plannerApp.v1')`.

## Yazı Tipleri

- **Fraunces** — başlıklar (italic serif)
- **Inter** — gövde
- **JetBrains Mono** — etiketler ve sayılar

Google Fonts üzerinden yüklenir. İlk açılışta internet gerekir; sonra cache'lenir.

## Sonraki Adımlar

- Filtre fonksiyonu (kategori bazlı)
- Takvim ekranı (aylık görünüm)
- Bildirim sistemi (yaklaşan etkinlikler için)
- Profil ekranı + tercih ayarları
- Bulut senkronizasyonu (opsiyonel)
