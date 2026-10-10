# Snakeful QA Portföyü

Bu repo, yayında olan mobil oyunum **Snakeful** (Unity, iOS ve Android) için hazırladığım test dokümantasyonunu içerir. Amacım, yaptığım testleri işverene gösterilebilir ve tekrar edilebilir bir şekilde sunmaktır.

> Durum: Çalışma devam ediyor. Klasörler sprintler ilerledikçe dolacak.

## Test Edilen Ürün

| Alan | Değer |
|---|---|
| Ürün | Snakeful (hyper-casual yılan oyunu) |
| Sürüm | App Store üretim sürümü 1.1.5 |
| Platform | iOS (iPhone 17 Pro, iOS 27.0.1) |
| Modlar | Classic, ColorMatch, Sequence |

Android bu çalışmada test edilmedi, sonraki çalışmaya bırakıldı.

## İçerik

| Klasör | Ne içerir | Durum |
|---|---|---|
| `docs/` | Kapsam ve risk analizi, test planı | Hazır |
| `test-cases/` | Mod ve özellik bazlı test senaryoları | Devam ediyor (Classic hazır) |
| `bug-reports/` | Bug raporu şablonu ve örnek raporlar | Planlandı |
| `exploratory/` | Keşifsel test oturumu (charter, notlar, bulgular) | Planlandı |

## Nereden Başlamalı

1. `docs/01_Kapsam_ve_Risk_Analizi.md`: Neyin neden test edildiği
2. `docs/02_Test_Plani.md`: Testlerin nasıl yürütüldüğü
3. `test-cases/`: Yazılı test senaryoları ve sonuçları

## Hazırlayan

Merve Aslanturkiyeli, QA Engineer
