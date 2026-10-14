# Snakeful QA Portföyü: Tek Sayfa Özet

**Hazırlayan:** Merve Aslanturkiyeli, QA Engineer
**Ürün:** Snakeful (hyper-casual mobil yılan oyunu, Unity, App Store ve Google Play'de yayında)
**Test edilen sürüm:** App Store üretim sürümü 1.1.5, iPhone 17 Pro, iOS 27.0.1

## Amaç

Kendi yayındaki oyunum için yaptığım testleri, işverene gösterilebilir ve tekrar edilebilir bir QA portföyüne dönüştürmek.

## Yaklaşım

- **Riske göre kapsam:** 16 özellik olasılık ve etkiye göre değerlendirildi. Riski yüksek alanlara (joystick, ekran sarması, ölüm koşulları, yeniden başlatma, üç oyun modu, skor) derin test ayrıldı. Ses, tema ve performans bilinçli olarak kapsam dışı bırakıldı.
- **Senaryo tabanlı manuel test:** Her senaryoda ön koşul, adımlar, beklenen sonuç ve öncelik var. Pozitif ve negatif senaryolar, sınır değerler (örneğin 10. yemde hız artışı) ve durum geçişleri kullanıldı.
- **Regresyon:** Daha önce çözülen ColorMatch yılan rengi sıfırlanma hatası için ayrı senaryo yazıldı (CM-13).
- **İzlenebilirlik:** Her risk, onu karşılayan senaryolara bağlandı. Bilinen boşluklar açıkça yazıldı.

## Sonuçlar

| Alan | Senaryo | Geçti | Kaldı |
|---|---|---|---|
| Classic | 13 | 13 | 0 |
| ColorMatch | 15 | 15 | 0 |
| Sequence | 15 | 15 | 0 |
| Ortak özellikler (joystick, durum, leaderboard, haptik, ekran) | 15 | 15 | 0 |
| **Toplam** | **58** | **58** | **0** |

- Bu çalışmada açık bir hata bulunmadı.
- **BUG-001:** Geliştirme sürecinde yakalanan ve çözülen ColorMatch hatasının kaydı. Regresyon senaryosu mağaza sürümünde geçti.
- **OBS-001:** Çevrimdışı oynanan oyunun skoru leaderboard'a bağlantıdan sonra gecikmeli işlendi. Hata değil, gözlem olarak kaydedildi.
- Belge ve ürün tutarsızlığı bulundu: Snakeful'un kendi README'sinde "kendi kuyruğuna çarpınca ölür" ifadesi eski kalmış, oyunda bu kural hiç olmamış.

## Sınırlamalar

- Tek cihaz (iPhone 17 Pro). Diğer cihazlar ve Android test edilmedi.
- Keşifsel test oturumu bu çalışmada yapılmadı, sonraki çalışmaya bırakıldı.
- Leaderboard'da yavaş ağ ve giriş yapılamaması durumları test edilmedi.
- Testler üretim sürümünde, gerçek leaderboard'la yürütüldü.

## Araçlar ve çıktılar

Manuel test (iOS), Markdown ve Excel ile dokümantasyon, GitHub, ekran kaydı. Tüm belgeler bu repoda: `docs/`, `test-cases/`, `bug-reports/`.
