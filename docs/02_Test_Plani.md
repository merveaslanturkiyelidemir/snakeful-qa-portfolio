# Snakeful - Test Planı

**Hazırlayan:** Merve Aslanturkiyeli
**Tarih:** 10.10.2026
**Görev:** T2 - Test planı
**Dayandığı belge:** 01_Kapsam_ve_Risk_Analizi.md

## 1. Amaç

Snakeful'un App Store'daki üretim sürümünün oynanış kurallarının, skor ve leaderboard davranışının ve temel kullanım akışlarının beklendiği gibi çalıştığını doğrulamak. Test sonuçları işverene gösterilebilecek bir QA portföyü olarak yayınlanacak.

## 2. Test Edilen Ürün

| Alan | Değer |
|---|---|
| Ürün | Snakeful (hyper-casual yılan oyunu, Unity 6.3) |
| Sürüm | App Store üretim sürümü 1.1.5 |
| Platform | iOS |
| Modlar | Classic, ColorMatch, Sequence |

## 3. Kapsam

Kapsam ve risk seviyeleri 01_Kapsam_ve_Risk_Analizi.md'de ayrıntılı. Özet:

- **Derin test:** Joystick, ekran sarması, ölüm koşulları ve gövde zinciri, oyunu yeniden başlatma (regresyon), Sequence, ColorMatch, skor ve high score.
- **Test:** Classic, leaderboard, pause/resume.
- **Temel test:** Haptik, ekran boyutu (tek cihaz).
- **Kapsam dışı:** Ses, tema ve parçacık efektleri, performans ölçümü, planlanan özellikler, **Android** (sonraki çalışmaya bırakıldı).

## 4. Test Yaklaşımı

Test riske göre derinleştirilir: riski yüksek alanlara daha çok senaryo ve zaman ayrılır.

| Yaklaşım | Ne için | Çıktı |
|---|---|---|
| Senaryo tabanlı manuel test | Modlar ve ortak özellikler. Her senaryonun adımları ve beklenen sonucu yazılı | test-cases/ klasörü (T3, T5, T6, T7) |
| Regresyon testi | Daha önce çözülen yılan rengi sıfırlanma hatası | ColorMatch senaryoları içinde |
| Keşifsel test | Senaryoların dışında beklenmeyen davranışları bulmak. Charter'lı, süreli, notlu oturum | exploratory/ klasörü (T9) |

Kullanılacak teknikler:

- **Durum geçişi:** oyun başlat, öl, yeniden başlat, modu değiştir.
- **Sınır değer:** Sequence'te zorluk artışının olduğu 10. yem civarı.
- **Negatif test:** yanlış renk, sıra dışı yem, zehirli yem.
- **Ağ koşulları:** internet var, yok, yavaş (leaderboard için).

## 5. Test Ortamı

| Alan | Değer |
|---|---|
| Cihaz | iPhone 17 Pro |
| İşletim sistemi | iOS 27.0.1 |
| Sürüm türü | Mağazadan indirilen üretim sürümü |
| Ağ | Wi-Fi, mobil veri, uçak modu |
| Kayıt aracı | iOS ekran kaydı ve ekran görüntüsü |

**Üretim ortamı notu:** Skorlar gerçek global leaderboard'a gidiyor. Gerçek oyuncuların sıralamasını bozmamak için leaderboard senaryoları az sayıda ve düşük skorla yapılacak, ayrı bir oyuncu adı kullanılacak.

## 6. Giriş ve Çıkış Kriterleri

**Teste başlamak için:**
- Üretim sürümü cihazda yüklü ve açılıyor.
- Kapsam ve risk belgesi hazır.
- Ekran kaydı ve not alma araçları hazır.

**Testi bitirmek için:**
- Planlanan tüm senaryolar yürütüldü ve her biri Geçti / Kaldı / Engellendi olarak işaretlendi.
- Derin test alanlarındaki bütün senaryolar yürütüldü.
- Bulunan her bug raporlandı.
- Bir keşifsel test oturumu yapıldı ve notları kaydedildi.

## 7. Hata Yönetimi

- Bulunan hatalar bug raporu şablonuyla (T8) yazılır: başlık, ortam, adımlar, beklenen ve gerçekleşen sonuç, etki, kanıt.
- Her hataya **önem derecesi** verilir:
  - **Kritik:** Oyun çöküyor veya oynanamıyor.
  - **Yüksek:** Temel kural bozuk (yanlış ölüm, yanlış skor).
  - **Orta:** Özellik çalışıyor ama beklenmedik davranış var.
  - **Düşük:** Kozmetik veya küçük kullanılabilirlik sorunu.
- Her hatanın yanında ekran kaydı veya görüntüsü bulunur.

## 8. Takvim ve Sorumluluk

Tek kişi (Merve) hazırlar ve yürütür.

| Gün | Görev |
|---|---|
| Cumartesi | T3 Classic senaryoları, T4 repo iskeleti |
| Pazar | T5 ColorMatch senaryoları |
| Pazartesi | T6 Sequence senaryoları, T7 çapraz özellik senaryoları |
| Salı | T8 bug raporu şablonu, T9 keşifsel oturum |
| Çarşamba | T10 portföyün tamamlanması |

## 9. Riskler ve Kısıtlar

| Risk veya kısıt | Etkisi | Önlem |
|---|---|---|
| Tek cihazla test | Sonuçlar iPhone 17 Pro ile sınırlı, diğer iPhone modelleri ve Android test edilmedi | Raporda belirtilir, Android sonraki çalışmaya kalır |
| Üretim leaderboard'u kirlenebilir | Gerçek oyuncuların sıralaması bozulur | Az ve düşük skorla test, ayrı oyuncu adı |
| Tek kişi test | Bağımsız ikinci bir göz yok | Keşifsel test ve notlarla fark edilmeyenleri azaltmak |
| Sınırlı süre (yaklaşık 10 saat) | Tüm kombinasyonlar denenemez | Riske göre öncelik, düşük riskli alanlar dışarıda |
| Haptik hissi öznel | Doğrulama gözleme dayanır | Sonuç "hissedildi / hissedilmedi" olarak kaydedilir |

## 10. Teslim Edilecekler

- 01_Kapsam_ve_Risk_Analizi.md
- 02_Test_Plani.md
- test-cases/ (Classic, ColorMatch, Sequence, ortak özellikler)
- bug-reports/ (şablon ve örnekler)
- exploratory/ (charter, notlar, bulgular)
- README.md (portföy özeti)
