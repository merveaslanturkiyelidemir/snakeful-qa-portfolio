# Classic Mod Test Senaryoları

**Ürün:** Snakeful, App Store sürümü 1.1.5
**Cihaz:** iPhone 17 Pro, iOS 27.0.1
**Yürütme tarihi:** 11.10.2026
**Yürüten:** Merve Aslanturkiyeli

| ID | Başlık | Öncelik | Ön koşul | Adımlar | Beklenen sonuç | Sonuç | Not |
|---|---|---|---|---|---|---|---|
| CL-01 | Classic mod başlatılıyor | High | Oyun yüklü ve açık, ana menüde. | 1) Ana menüden Classic modunu seç.<br>2) Oyun ekranının açılmasını bekle. | Oyun başlar, yılan hareket eder, skor 0 görünür. Ekranda en az bir normal yem ve zehirli (kırmızı) yem var. | Geçti | Oyun başladıktan sonra ekranda en az 1 yem ve zehirli yem görüldü. |
| CL-02 | Normal yem yeme | High | Classic modda oyun başladı. | 1) Joystick ile yılanı normal bir yeme götür.<br>2) Yemi ye. | Yılan uzar, skor artar, ekrana yeni normal yem çıkar. Her yem 10 puan verir. | Geçti | Yılan yem yedikçe her yemde 10 puan kazandı. |
| CL-03 | Zehirli yem yeme | High | Classic modda oyun başladı. | 1) Yılanı kırmızı (zehirli) yeme götür.<br>2) Yemi ye. | Oyun anında biter ve skor ekranda gösterilir. | Geçti | Yılan zehirli yemi yediğinde oyun sona erdi ve skor ekranda gösterildi. |
| CL-04 | Zehirli yem sürekli ekranda | Medium | Classic modda oyun başladı. | 1) Zehirli yeme dokunmadan 5 normal yem ye.<br>2) Her yemden sonra ekranı kontrol et. | Oyun boyunca ekranda zehirli yem her zaman bulunur. | Geçti | Oyun boyunca ekranda zehirli yem her zaman bulundu. |
| CL-05 | Hız artışı | High | Classic modda oyun başladı. | 1) Yılanın ilk hızını gözlemle.<br>2) Zehirli yeme dokunmadan yem yemeye devam et.<br>3) Hız artışını ve ne zaman olduğunu not et. | Yılan her 10 yemde bir hızlanır. | Geçti | Yılan her 10 yemde hızlandı. |
| CL-06 | Yılan sürekli hareket ediyor | High | Classic modda oyun başladı. | 1) Joystick ile bir yön ver.<br>2) Parmağını ekrandan çek.<br>3) Birkaç saniye bekle. | Yılan durmaz, son yönünde ilerlemeye devam eder. | Geçti | Yılan son yönlendirildiği yönde hareket etmeye devam etti. |
| CL-07 | Ekran sarması | High | Classic modda oyun başladı. | 1) Yılanı ekranın sağ kenarına yönlendir ve kenardan çıkar.<br>2) Aynısını sol, üst ve alt kenarlar için tekrarla. | Yılan çıktığı kenarın tam karşısından girer. Oyun bitmez, yılanın gövdesi kopmaz. | Geçti | Yılan çıktığı kenarın karşı tarafından ekrana girdi. Oyun akışı bozulmadı. |
| CL-08 | Kendi gövdesine çarpma | High | Classic modda yılan birkaç yem yedi, gövdesi uzadı. | 1) Yılanı kendi gövdesinin üzerinden geçirecek şekilde döndür.<br>2) Çarpışmayı gözlemle. | Yılan ölmez, oyun devam eder (tasarım gereği, bkz. Kapsam ve Risk Analizi). | Geçti | Yılan kendi gövdesinin üzerinden geçecek şekilde yönlendirildi, bir şey olmadan oyun devam etti. |
| CL-09 | Zehirli yeme dokunmadan yakından geçiş | Medium | Classic modda oyun başladı. | 1) Yılanı zehirli yemin hemen yanından, ona dokunmadan geçir. | Oyun bitmez. Yalnızca yeme değen temas ölüme yol açar. | Geçti | Yılan zehirli yeme temas etmediği sürece oyun devam etti. Zehirli yemi yediğinde oyun sona erdi. |
| CL-10 | Yeni rekor ve high score kaydı | High | Classic modda daha önce kaydedilmiş bir high score var. | 1) Mevcut high score'u geçecek skora ulaş.<br>2) Zehirli yemi yiyerek oyunu bitir.<br>3) Uygulamayı tamamen kapat ve yeniden aç.<br>4) Classic high score'u kontrol et. | Yeni rekor yazısı (“New High Score”) gösterilir. High score yeni değere güncellenir ve uygulama kapanıp açılınca korunur. | Geçti | Daha önce kaydedilmemiş bir skor yapıldığında ekranda “New High Score” yazısı belirdi ve oyuna tekrar girildiğinde bu rekor korundu. |
| CL-11 | Düşük skor high score'u değiştirmez | Medium | Classic modda kayıtlı bir high score var. | 1) Mevcut high score'dan düşük bir skorla oyunu bitir.<br>2) High score'u kontrol et. | High score değişmez. | Geçti | Rekor skordan daha düşük bir skor yapıldığında rekor skoru etkilenmedi. |
| CL-12 | Yeni oyunda durum sıfırlanıyor (regresyon) | High | Classic modda bir oyun öldükten sonra sonuç ekranındasın. | 1) Yeni bir oyun başlat.<br>2) Skoru, yılan uzunluğunu, hızını ve ekrandaki yemleri kontrol et.<br>3) Bu adımları art arda 3 oyun için tekrarla. | Skor 0, yılan başlangıç uzunluğunda ve hızında. Önceki oyundan kalan yem veya durum yok. | Geçti | Her yeni oyun başladığında yılanın konumu, hızı ve yemlerin konumu sıfırlandı. |
| CL-13 | Duraklat ve devam et | Medium | Classic modda oyun devam ediyor, skor 0'dan büyük. | 1) Oyunu duraklat.<br>2) Birkaç saniye bekle.<br>3) Devam et. | Duraklatırken yılan durur. Devam edince kaldığı yerden, aynı skor ve hızla ilerler. | Geçti | Oyun duraklatıldığında yılanın konumu, skoru ve yemlerin konumu korundu; devam edildiğinde kaldığı yerden devam edildi. |

## Özet

13 senaryonun 13'ü geçti. Başarısız veya engellenen senaryo yok.
