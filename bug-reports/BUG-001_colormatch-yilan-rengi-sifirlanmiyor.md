# BUG-001: ColorMatch'te yeni oyunda yılanın rengi sıfırlanmıyor

| Alan | Değer |
|---|---|
| **ID** | BUG-001 |
| **Durum** | Çözüldü (geçmiş kayıt). Düzeltme mağaza sürümü 1.1.5'te regresyon senaryosuyla doğrulandı (CM-13) |
| **Önem** | Yüksek (temel kural bozuk: yanlış ölüm) |
| **Mod / Özellik** | ColorMatch, oyunu yeniden başlatma |
| **Ortam** | Geliştirme sürecinde bulundu (Unity 6.3, 2D URP) |
| **Ön koşul** | ColorMatch modunda bir oyun, yılan belirli bir renkteyken (örneğin yeşil) bitmiş. |

## Tekrar adımları

1. ColorMatch modunda oyna ve yılan yeşil renkteyken oyunu bitir.
2. Yeni oyun başlat.
3. Yılan başlangıç renginde (örneğin sarı) iken ekrandaki aynı renkteki (sarı) yemi ye.

## Beklenen sonuç

Yeni oyunda yılan başlangıç durumuna döner. Yılanın gerçek rengindeki yem doğru sayılır, oyun devam eder.

## Gerçekleşen sonuç

Yılanın önceki oyundaki son rengi hafızada kalıyordu. Yeni oyunda yılan sarı olduğu halde, sarı yemi yemek yanlış renk sayılıyor ve oyun haksız yere bitiyordu.

## Etki

Oyuncu doğru yemi yediği halde ölüyordu. ColorMatch modunun temel kuralı bozuk olduğu için oyuncu güvenini zedeleyen bir hataydı.

## Neden bulundu ve nasıl çözüldü

Sorun kodda incelenerek bulundu: oyun yeniden başlatıldığında yılan rengi durumu sıfırlanmıyordu. Düzeltme birkaç commit'te yapıldı.

## Kanıt ve notlar

- Bu rapor, geçmişte düzeltilmiş bir hatanın hatırlanan davranıştan yeniden yazılmış kaydıdır. Eski sürümden ekran kaydı bulunmuyor.
- Tekrar adımlarındaki renkler örnektir.
- Bu hata, test planında "oyunu yeniden başlatma ve durum sıfırlama" alanının yüksek riskli sayılma nedenidir (bkz. `docs/01_Kapsam_ve_Risk_Analizi.md`).
- Regresyon: `test-cases/02_colormatch-test-cases.md` içinde CM-13. Mağaza sürümü 1.1.5'te Geçti.
