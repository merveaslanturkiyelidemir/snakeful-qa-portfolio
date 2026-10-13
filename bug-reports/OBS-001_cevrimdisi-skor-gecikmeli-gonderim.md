# OBS-001: Çevrimdışı oynanan oyunun skoru leaderboard'a gecikmeli işleniyor

Bu bir hata değil, gözlemdir. Skor kaybolmadı, sonradan göründü. Gecikmenin süresi ve nedeni belirlenemedi.

| Alan | Değer |
|---|---|
| **ID** | OBS-001 |
| **Önem** | Düşük (gözlem) |
| **Mod / Özellik** | Sequence, leaderboard |
| **Ortam** | Snakeful 1.1.5 (App Store), iPhone 17 Pro, iOS 27.0.1, Wi-Fi ve uçak modu |
| **İlgili senaryo** | CP-12, CP-13 |

## Adımlar

1. Uçak modunu aç.
2. Sequence modunda iki oyun oyna. İkinci oyunda mevcut rekoru (110) geç (150 puan).
3. Menüdeki leaderboard panelini aç: yerel panel 150, 110 ve 60 skorlarını gösterir.
4. Uçak modunu kapat, bağlantı gelsin.
5. Global leaderboard'u aç (Sequence sekmesi).

## Gözlenen

- Bağlantı geldikten hemen sonra (yaklaşık 15 saniye) global leaderboard'da oyuncunun sırası **#34, 110** idi. 150 skoru görünmüyordu.
- 13.10.2026'da tekrar bakıldığında aynı oyuncu **#30, 150** ile görünüyordu. Yani skor sonradan gönderilmiş.
- Gönderim durumuyla ilgili ekranda bir bildirim görülmedi.

## Bilinmeyenler

- Skorun ne kadar sürede göründüğü.
- Uygulamayı kapatıp açmanın veya yeni bir oyun oynamanın gönderimi tetikleyip tetiklemediği.

## Değerlendirme

Skor kaybolmadığı için hata sayılmadı. Çevrimdışı oynayan oyuncu skorunun hemen yansımadığını görebilir. Gecikme süresi ölçülürse veya gönderim durumu oyuncuya gösterilirse deneyim iyileşebilir. Bu bir öneridir, doğrulanmış bir kusur değildir.

## Kanıt

Ekran kaydı (12.10.2026) ve 13.10.2026 tarihli leaderboard ekran görüntüsü yürütme sırasında alındı.
