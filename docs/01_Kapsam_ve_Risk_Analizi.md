# Snakeful - Kapsam ve Risk Analizi

**Hazırlayan:** Merve Aslanturkiyeli
**Tarih:** 10.10.2026
**Ürün:** Snakeful (Unity 6.3, 2D URP; iOS ve Android'de yayında)
**Görev:** T1 - Kapsam ve risk analizi

## 1. Amaç

Bu belge, Snakeful'da neyin test edileceğini, neyin test edilmeyeceğini ve testlerin hangi sırayla ve ne kadar derin yapılacağını belirler. Sonraki belgeler (test planı, test senaryoları) bu belgeye dayanır.

## 2. Yöntem

Her özellik için iki şey değerlendirildi:

- **Olasılık:** Bu alanda sorun çıkma ihtimali.
- **Etki:** Sorun çıkarsa oyuncunun deneyimine etkisi.

İkisi de yüksekse risk **Yüksek**, biri yüksekse **Orta**, ikisi de düşükse **Düşük** kabul edildi. Daha önce yaşanmış sorunlar ve dokümanla gerçek davranış arasındaki farklar riski artıran etkenler olarak sayıldı.

## 3. Kapsam

**Kapsam içinde:** 3 oyun modu (Classic, ColorMatch, Sequence), joystick, ekran sarması, ölüm koşulları, oyunu yeniden başlatma, skor ve high score, leaderboard, pause/resume, haptik, ekran boyutu ve cihaz uyumu.

**Kapsam dışında:** Ses, tema ve parçacık efektleri, performans ölçümü, planlanan özellikler (can sistemi, ayarlar menüsü, tutorial, kamera sarsıntısı, sahne geçişi, zorluk ölçekleme).

**Test ortamı:** Bu çalışmada yalnızca iOS (iPhone 17 Pro, iOS 27.0.1), mağazadaki üretim sürümü. Android sonraki çalışmaya bırakıldı.

## 4. Risk Tablosu

| # | Özellik | Risk | Neden | Karar |
|---|---|---|---|---|
| 1 | Floating joystick (360°) | Yüksek | Tek kontrol yolu. Çoklu dokunma, parmağı kaldırma, ekran kenarı, hızlı yön değişimi | Derin test |
| 2 | Ekran sarması (Pac-Man) | Yüksek | Yılan kenardan geçerken gövde, yem ve çarpışma birlikte çalışmalı | Derin test |
| 3 | Ölüm koşulları ve gövde zinciri | Yüksek | Ölüm sadece moda özel kurallardan geliyor (zehirli yem, yanlış renk, sıra dışı yem). Yılan kendi gövdesine çarpınca ölmüyor; bu kural oyunda hiç olmadı, README'deki "kuyruğundan kaçın" ifadesi eski. Gövde mesafeye göre çiziliyor, hız artınca bozulabilir | Derin test |
| 4 | Oyunu yeniden başlatma ve durum sıfırlama | Yüksek | Daha önce yaşanan sorun: ColorMatch'te yeni oyun başlayınca yılanın rengi sıfırlanmıyordu. Önceki oyunun son rengi (örneğin yeşil) hafızada kalıyor, yeni oyunda yılan sarı olduğu halde sarı yem yenince yanlış renk sayılıp oyun bitiyordu. Sorun kodda bulundu ve birkaç commit'te çözüldü. Regresyon olarak tekrar doğrulanmalı | Derin test (regresyon) |
| 5 | Sequence modu | Yüksek | En çok duruma sahip mod: sıra takibi, her 10 yemde zorluk artışı | Derin test |
| 6 | ColorMatch modu | Yüksek | Yılan rengi her eşleşmede değişiyor. Yeniden başlatma hatası bu modda ortaya çıkmıştı | Derin test |
| 7 | Classic modu | Orta | Basit kurallar. Zehirli yem her zaman ekranda, yenince anında bitiyor | Test |
| 8 | Skor ve high score (moda özel) | Yüksek | Yanlış kayıt veya kayıp oyuncu güvenini zedeler. 3 modun skoru ayrı tutuluyor | Derin test |
| 9 | UGS Leaderboard | Yüksek | Ağa bağlı: internet yokken, yavaşken, giriş yapılamadığında | Test |
| 10 | Pause / resume | Orta | Arka plana atma, arama, uygulama değiştirme sonrası durum | Test |
| 11 | Haptik | Orta | Etkisi düşük. iOS'ta Taptic Engine kullanılıyor. Android'deki motor türü ve API seviyesi farkları bu çalışmada test edilmeyecek | Temel test (sadece iOS) |
| 12 | Ekran boyutu ve cihaz uyumu | Orta | Sarma ekran sınırına bağlı. Tek cihazla test edildiği için sonuçlar iPhone 17 Pro ile sınırlı | Temel test (tek cihaz) |
| 13 | Ses (efekt ve müzik döngüsü) | Düşük | Oynanışı bozmaz | Test edilmeyecek |
| 14 | Tema sistemi ve parçacık efektleri | Düşük | Görsel, oynanışı etkilemez | Test edilmeyecek |
| 15 | Performans (yüksek hız, uzun yılan) | Orta | Önemli ama ayrı araç ve ölçüm gerektirir | Kapsam dışı |
| 16 | Planlanan özellikler | - | Henüz yayında değil | Kapsam dışı |

## 5. Testlerin Öncelik Sırası

1. Ölüm koşulları ve gövde zinciri (3), oyunu yeniden başlatma (4)
2. Joystick (1), ekran sarması (2)
3. Üç mod: Sequence (5), ColorMatch (6), Classic (7)
4. Skor ve high score (8), leaderboard (9)
5. Pause/resume (10), haptik (11), ekran boyutu (12)

## 6. Notlar ve Doğrulanması Gereken Noktalar

- **Kendi gövdesine çarpma:** Oyunda bu kural hiç olmadı, yılan kendine çarpınca ölmüyor. Test beklentisi: çarpma ölüm yaratmaz. README'deki "kuyruğundan kaçın" ifadesi güncel değil, düzeltilecek (belge ve ürün tutarsızlığı bulgusu).
- **Yeniden başlatma sorunu:** Yılan rengi yeni oyunda sıfırlanmıyordu, çözüldü. Test planında regresyon olarak tekrar doğrulanacak: farklı renklerde ölüp yeni oyun başlatma, art arda birkaç oyun.
- **Android:** Bu çalışmada test edilmeyecek. Android'e özgü riskler (cihaz çeşitliliği, haptik motor farkları) sonraki çalışmaya kaldı.
