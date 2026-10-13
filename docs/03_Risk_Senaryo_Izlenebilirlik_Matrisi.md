# Risk – Senaryo İzlenebilirlik Matrisi

**Hazırlayan:** Merve Aslanturkiyeli
**Dayandığı belgeler:** `01_Kapsam_ve_Risk_Analizi.md`, `test-cases/`

Bu matris, risk analizindeki her özelliğin hangi test senaryolarıyla karşılandığını ve sonuçlarını gösterir. Amaç, testlerin riske göre seçildiğini ve boşlukların nerede kaldığını görünür kılmaktır.

| # | Özellik | Risk | Karar | Karşılayan senaryolar | Sonuç |
|---|---|---|---|---|---|
| 1 | Floating joystick (360°) | Yüksek | Derin test | CP-01, CP-02, CP-03, CP-04, CP-05, CL-06 | 6/6 Geçti |
| 2 | Ekran sarması (Pac-Man) | Yüksek | Derin test | CL-07, CM-08, SQ-09 | 3/3 Geçti |
| 3 | Ölüm koşulları ve gövde zinciri | Yüksek | Derin test | CL-03, CL-08, CL-09, CM-04, CM-06, CM-09, CM-10, SQ-04, SQ-05, SQ-06, SQ-10, SQ-11 | 12/12 Geçti |
| 4 | Oyunu yeniden başlatma ve durum sıfırlama | Yüksek | Derin test (regresyon) | CL-12, CM-13, CM-14, SQ-14, CP-07 | 5/5 Geçti |
| 5 | Sequence modu | Yüksek | Derin test | SQ-01 … SQ-15 | 15/15 Geçti |
| 6 | ColorMatch modu | Yüksek | Derin test | CM-01 … CM-15 | 15/15 Geçti |
| 7 | Classic modu | Orta | Test | CL-01 … CL-13 | 13/13 Geçti |
| 8 | Skor ve high score (moda özel) | Yüksek | Derin test | CL-10, CL-11, CM-11, CM-12, SQ-12, SQ-13, CP-06, CP-10 | 8/8 Geçti |
| 9 | UGS Leaderboard | Yüksek | Test | CP-11, CP-12, CP-13 (gözlem: OBS-001) | 3/3 Geçti |
| 10 | Pause / resume | Orta | Test | CL-13, CM-15, SQ-15, CP-08, CP-09 | 5/5 Geçti |
| 11 | Haptik | Orta | Temel test (sadece iOS) | CP-14 | 1/1 Geçti |
| 12 | Ekran boyutu ve cihaz uyumu | Orta | Temel test (tek cihaz) | CP-15 | 1/1 Geçti |
| 13 | Ses (efekt ve müzik döngüsü) | Düşük | Test edilmeyecek | - | - |
| 14 | Tema sistemi ve parçacık efektleri | Düşük | Test edilmeyecek | - | - |
| 15 | Performans (yüksek hız, uzun yılan) | Orta | Kapsam dışı | - | - |
| 16 | Planlanan özellikler | - | Kapsam dışı | - | - |

Toplam 58 senaryo, 58 Geçti. Bir senaryo birden fazla riski karşılayabilir (örneğin CL-12 hem yeniden başlatma hem Classic modu için).

## Bilinen boşluklar

Yüksek riskli alanlarda tam karşılanmayan noktalar:

- **Gövde zinciri (risk 3):** Hız arttıktan sonra gövdenin çizimi ayrı bir senaryoyla kontrol edilmedi. CL-07 ve hız artışı senaryoları (CL-05, CM-07, SQ-07, SQ-08) bunu dolaylı olarak gözlemledi.
- **Leaderboard (risk 9):** İnternet var ve yok senaryoları yürütüldü (CP-11, CP-12, CP-13). Yavaş ağ ve giriş yapılamaması senaryoları yürütülmedi. Çevrimdışı skorun gecikmeli işlenmesi OBS-001 olarak kaydedildi, gecikme süresi ölçülmedi.
- **Ekran boyutu (risk 12):** Yalnızca iPhone 17 Pro. Diğer cihazlar ve Android test edilmedi.
- **Keşifsel test:** Bu çalışmada yapılmadı, sonraki çalışmaya bırakıldı.

## Kapsam dışı bırakılanlar

Ses, tema ve parçacık efektleri, performans ölçümü ve planlanan özellikler bilinçli olarak test edilmedi (bkz. risk analizi).
