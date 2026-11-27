# Üretim Takip

Üretim aracı: **Google Flow (Veo 3.1)** — prompt'lar Flow'a uyarlanıyor (etiketsiz, 8 sn, Türkçe konuşma Veo'da).

Her denemeyi bir satır olarak yaz. Bir sonraki denemede **tek bir şeyi** değiştir.

Durum: `bekliyor` · `üretildi` · `kabul` · `ret`

| Klip | Deneme | Tarih | Değişen şey | Sorun (yüz kayması / el / yazı / kalabalık / ışık / diğer) | Durum | Dosya |
|---|---|---|---|---|---|---|
| 1 | 1 | 2026-11-27 | Yeni karakter, kar yok, ışık geçişi | Kullanıcı kontrol etti: sorun yok; son beyaz kare SS alındı | kabul | (kullanıcıda) |
| 2 | 1 | | — | | bekliyor | |
| 3 | 1 | | — | | bekliyor | |
| 4 | 1 | | — | | bekliyor | |
| 5 | 1 | | — | | bekliyor | |
| 6 | 1 | | — | | bekliyor | |
| 7 | 1 | | — | | bekliyor | |
| 8 | 1 | | — | | bekliyor | |

Bölüm: `04-sahne-listesi/bolum-01-2005-trabzon-caddesi.md`

Arşiv (eski 1996 planı): 1-01 deneme 1, 2026-11-27, Flow — karakter tutarlı, beyaz kareyle bitiyor, cadde Trabzon Caddesi'ne benzemedi, replik "doksanlara" dediği için yeni planda yeniden üretilecek.

## Sık sorunlar → tek değişiklik
| Sorun | Önce şunu dene |
|---|---|
| Yüz kayıyor | Çekim sayısını azalt; kamera hareketini `locked` yap; karakter sayfasını daha net bir sürümle değiştir |
| Kıyafet değişiyor | Kilit satırında kıyafeti renkleriyle tekrar et; dönem fotoğrafında kıyafeti baskın kişi varsa o fotoğrafı değiştir |
| Fotoğraftaki kişinin yüzü geliyor | Fotoğrafı kırp (insanları çıkar) veya `do not copy any face` cümlesini başa al |
| Bozuk yazı/tabela | Prompt'tan yazıyla ilgili kelimeleri sil; tabelayı fotoğraf taşısın |
| Modern obje sızıyor | `no smartphones, no LED signs, no modern cars` ekle |
| Klip reddedildi | Yakın plan yüz içeren referansı kırp; kalabalığı azalt |
| Türkçe telaffuz kötü | Konuşma cümlesini sil, `He smiles at the camera without speaking` yaz; sesi kurguda ekle |
