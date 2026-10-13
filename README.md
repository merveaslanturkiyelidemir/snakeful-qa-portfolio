# Snakeful QA Portföyü

Bu repo, yayında olan mobil oyunum **Snakeful** (Unity, iOS ve Android) için hazırladığım test dokümantasyonunu içerir. Amacım, yaptığım testleri işverene gösterilebilir ve tekrar edilebilir bir şekilde sunmaktır.

> Durum: Çalışma devam ediyor. Son düzenlemeler eklenecek.

## Test Edilen Ürün

| Alan | Değer |
|---|---|
| Ürün | Snakeful (hyper-casual yılan oyunu) |
| Sürüm | App Store üretim sürümü 1.1.5 |
| Platform | iOS (iPhone 17 Pro, iOS 27.0.1) |
| Modlar | Classic, ColorMatch, Sequence |

Android ve keşifsel test bu çalışmada yapılmadı, sonraki çalışmaya bırakıldı.

## İçerik

| Klasör | Ne içerir | Durum |
|---|---|---|
| `docs/` | Kapsam ve risk analizi, test planı, risk-senaryo izlenebilirlik matrisi | Hazır |
| `test-cases/` | Mod ve özellik bazlı test senaryoları ve sonuçları (Classic, ColorMatch, Sequence, ortak özellikler) | Hazır, 58 senaryo |
| `bug-reports/` | Bug raporu şablonu, çözülmüş hata kaydı, gözlem notu | Hazır |

## Nereden Başlamalı

1. `docs/01_Kapsam_ve_Risk_Analizi.md`: Neyin neden test edildiği
2. `docs/02_Test_Plani.md`: Testlerin nasıl yürütüldüğü
3. `test-cases/`: Yazılı test senaryoları ve sonuçları
4. `bug-reports/`: Şablon ve kayıtlar
5. `docs/03_Risk_Senaryo_Izlenebilirlik_Matrisi.md`: Hangi risk hangi senaryolarla karşılandı, boşluklar neler

## Sonuç Özeti

| Alan | Senaryo | Geçti | Kaldı |
|---|---|---|---|
| Classic | 13 | 13 | 0 |
| ColorMatch | 15 | 15 | 0 |
| Sequence | 15 | 15 | 0 |
| Ortak özellikler | 15 | 15 | 0 |
| **Toplam** | **58** | **58** | **0** |

Bu çalışmada açık bir hata bulunmadı. Bir çözülmüş hata kaydı (BUG-001) ve bir gözlem notu (OBS-001) `bug-reports/` klasöründe.

## Hazırlayan

Merve Aslanturkiyeli, QA Engineer
