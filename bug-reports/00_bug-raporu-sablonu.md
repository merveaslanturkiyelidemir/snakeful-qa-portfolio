# Bug Raporu Şablonu

Her bulunan hata için bu şablon kopyalanır. Dosya adı: `BUG-NNN_kisa-baslik.md`. Hata olmayan ama kayda değer gözlemler için `OBS-NNN_kisa-baslik.md` kullanılır.

| Alan | Açıklama |
|---|---|
| **ID** | BUG-001, BUG-002... |
| **Başlık** | Tek cümle: ne, nerede, ne zaman bozuluyor |
| **Durum** | Açık / Çözüldü / Doğrulandı / Geçerli değil |
| **Önem** | Kritik / Yüksek / Orta / Düşük (aşağıya bakın) |
| **Mod / Özellik** | Classic, ColorMatch, Sequence, Leaderboard... |
| **Ortam** | Ürün sürümü, cihaz, işletim sistemi, ağ durumu |
| **Ön koşul** | Hatayı görmek için gereken başlangıç durumu |
| **Tekrar adımları** | Numaralı, başkası uygulayabilecek netlikte |
| **Beklenen sonuç** | Doğru davranış ne olmalı |
| **Gerçekleşen sonuç** | Gözlenen davranış |
| **Tekrarlanma** | Her zaman / bazen / bir kez |
| **Etki** | Oyuncuya etkisi |
| **Kanıt** | Ekran kaydı veya görüntüsü, ilgili senaryo ID'si |
| **Notlar** | Bilinmeyenler, ek gözlemler |

## Önem dereceleri

- **Kritik:** Oyun çöküyor veya oynanamıyor.
- **Yüksek:** Temel kural bozuk (yanlış ölüm, yanlış skor).
- **Orta:** Özellik çalışıyor ama beklenmedik davranış var.
- **Düşük:** Kozmetik veya küçük kullanılabilirlik sorunu.

## Yazım kuralları

- Başlıkta belirti yazılır, tahmin edilen neden yazılmaz.
- Adımlar gerçekten denenmiş olanlardır. Bilinmeyen kısım "Notlar"da açıkça belirtilir.
- Önem, oyuncuya etkisine göre verilir.
