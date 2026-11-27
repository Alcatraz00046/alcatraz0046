# Üretim Takip

Her denemeyi bir satır olarak yaz. Bir sonraki denemede **tek bir şeyi** değiştir.

Durum: `bekliyor` · `üretildi` · `kabul` · `ret`

| Klip | Deneme | Tarih | Değişen şey | Sorun (yüz kayması / el / yazı / kalabalık / ışık / diğer) | Durum | Dosya |
|---|---|---|---|---|---|---|
| 1-01 | 1 | | — | | bekliyor | |
| 1-02 | 1 | | — | | bekliyor | |
| 1-03 | 1 | | — | | bekliyor | |
| 1-04 | 1 | | — | | bekliyor | |
| 1-05 | 1 | | — | | bekliyor | |
| 1-06 | 1 | | — | | bekliyor | |
| 1-07 | 1 | | — | | bekliyor | |
| 1-08 | 1 | | — | | bekliyor | |
| 2-01 | 1 | | — | | bekliyor | |
| 2-02 | 1 | | — | | bekliyor | |
| 2-03 | 1 | | — | | bekliyor | |
| 2-04 | 1 | | — | | bekliyor | |
| 2-05 | 1 | | — | | bekliyor | |
| 2-06 | 1 | | — | | bekliyor | |
| 2-07 | 1 | | — | | bekliyor | |

## Sık sorunlar → tek değişiklik
| Sorun | Önce şunu dene |
|---|---|
| Yüz kayıyor | Çekim sayısını azalt; kamera hareketini `locked` yap; karakter sayfasını daha net bir sürümle değiştir |
| Kıyafet değişiyor | Kilit satırında kıyafeti renkleriyle tekrar et; dönem fotoğrafında kıyafeti baskın kişi varsa o fotoğrafı değiştir |
| Fotoğraftaki kişinin yüzü geliyor | Fotoğrafı kırp (insanları çıkar) veya `do not copy any face` cümlesini başa al |
| Bozuk yazı/tabela | Prompt'tan yazıyla ilgili kelimeleri sil; tabelayı fotoğraf taşısın |
| Modern obje sızıyor | `no smartphones, no LED signs, no modern cars` ekle |
| Klip reddedildi (moderasyon) | Yakın plan yüz içeren referansı çıkar; `seedance-20` moderasyon ön kontrolünü çalıştır |
