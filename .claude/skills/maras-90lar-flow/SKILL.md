---
name: maras-90lar-flow
description: "90'lar Kahramanmaraş zaman yolculuğu vlogunu Google Flow'da (Veo 3.1 + görsel üretim) kullanıcının Chrome'u üzerinden baştan sona üretir: karakter referansları, gerçek 90'lar fotoğraflarını indirme, klip klip kare + video üretimi, kredi bitince başka Google hesabına geçiş. Kullanıcı 'Maraş 90lar videosunu üret', 'Flow'da devam et', '/maras-90lar-flow' dediğinde kullan."
user-invocable: true
tags: [flow, veo, chrome, maras, 1990s]
---

# maras-90lar-flow — Flow'da otomatik üretim (yerel oturum)

Bu skill **kullanıcının bilgisayarındaki** Claude oturumunda, **Claude in Chrome** eklentisiyle çalışır. Bulut oturumu Chrome'a erişemez.

Kaynak dosyalar (bu repoda, `maras-zaman-yolculugu/90lar/`):
- `karakter.md` — karakter sayfası + 1:1 yüz portresi prompt'ları
- `kaynaklar.md` — gerçek 90'lar Maraş fotoğrafları (URL, yer, yıl, hangi klipte)
- `senaryo.md` — klip klip anlatım (hafif Maraş ağzı), kare (A) ve video (B) prompt'ları
- `uretim-log.md` — ilerleme kaydı (her adımda güncelle; kaldığın yerden devam etmek için önce bunu oku)

## Kullanıcının kararları (tekrar sorma)
- Her şeyi sen yaparsın; kullanıcıya ara soru sorma. Sadece aşağıdaki "dur" durumlarında dur.
- Format: **9:16 dikey**. Anlatım: **hafif Maraş ağzı**, Türkçe, Veo'nun kendi sesi.
- Kalite: kusursuza yakın, doğal, yapaylık yok; **arka plan geniş** görünsün.
- Bütçe: kullanıcının Chrome'da kayıtlı **tüm Google hesaplarındaki mevcut (satın alınmış) Flow kredileri**. Biri bitince sıradakine geç.
- **Asla** kredi/abonelik satın alma, ödeme sayfasına girme, yeni hesap açma, deneme kredisi için kayıt olma.

## 0 — Hazırlık
1. `tabs_context_mcp` → yeni sekme aç. Flow: `https://labs.google/fx/tools/flow`.
2. Yerel çalışma klasörü: `~/Maras90lar/` → `referans/` (karakter + fotoğraflar), `kareler/`, `klipler/`. Bütün indirilenler buraya; hesap değişince buradan tekrar yüklenir.
3. `uretim-log.md`'yi oku; yarım kalan adım varsa oradan devam et.
4. Flow'da sağ üstteki hesap menüsünden aktif hesabı ve kalan krediyi oku, log'a yaz.

## 1 — Gerçek fotoğrafları topla
`kaynaklar.md`'deki her satır için sayfayı aç, fotoğrafı tam çözünürlükte indir → `referans/NN-yer-yil.jpg`. Görüntüye bak: gerçekten o yer/yıl mı, insanlar ne giyiyor, hangi araçlar, tabelalar. Notlarını `kaynaklar.md`'ye ekle. Eksik yer varsa Google Görseller'de ara (`"eski Maraş" Trabzon Caddesi 199`, `Kahramanmaraş 1990 fotoğraf`, `Kıbrıs Meydanı eski` vb.); yılı belli olanları tercih et. Fotoğraflar yalnızca referans: kişilerin yüzleri karaktere/videoya taşınmaz.

## 2 — Karakter
`karakter.md`: önce karakter sayfası (16:9), sonra onu yükleyerek 1:1 yüz portresi. Her biri için 4 varyasyon üret, en doğal, en tutarlı olanı seç (yüz 5 açıda aynı, eller düzgün, yazı yok, plastik cilt yok). İndir → `referans/karakter-sayfasi.png`, `referans/portre.png`. Flow'da koleksiyona/ingredient olarak kaydet.

## 3 — Klipler (senaryo.md sırasıyla)
Her klip:
1. **A — Kare (görsel üret, 9:16):** karakter sayfası + portre + o klibin gerçek fotoğrafı. 4 varyasyon → seç → indir `kareler/KNN.png`.
   Seçim ölçütü: yüz karakterle aynı; mekân fotoğraftaki yer; 90'lara ait olmayan hiçbir şey yok (klima, çanak anten, LED, akıllı telefon, yeni araç); arka plan geniş ve dolu; cilt doğal.
2. **B — Video (Frames to Video, 8 sn, 9:16):** A kare başlangıç; geçiş kliplerinde ilk/son kare. En yüksek kalite modeli (Quality) ile üret; Fast'i sadece prompt denemesinde kullan. 2 varyasyon → izle → en iyisini indir `klipler/KNN.mp4`.
   Kontrol: yüz/kıyafet sabit; Türkçe konuşma anlaşılır, dudak uyumlu; hareket doğal (kayma, eriyen eller, bozuk yüzler yok); 90'lar dışı obje yok.
3. Bozuksa tek değişiklikle tekrar (en fazla 3 deneme/klip); hâlâ bozuksa log'a yaz ve sonraki klibe geç.
4. Her klip sonrası `uretim-log.md`'ye satır ekle: klip, hesap, deneme, harcanan kredi, sonuç, dosya.

## 4 — Kredi bitince hesap değiştir
1. Kalan kredi bir sonraki üretime yetmiyorsa: log'a "hesap X bitti, son tamamlanan adım" yaz.
2. Flow sağ üst avatar → hesap değiştir → kayıtlı sıradaki Google hesabını seç (giriş otomatik açılıyor).
3. Yeni hesapta yeni proje aç; `referans/` dosyalarını (karakter sayfası, portre, gerekli fotoğraflar, gerekiyorsa son kare) yeniden yükle; kaldığın adımdan devam et.
4. Hesap seçerken şifre/2FA isterse veya kayıtlı hesap kalmadıysa: **dur**, log'a yaz, kullanıcıya bildir.

## 5 — Bitiş
Tüm klipler `klipler/` içinde sırayla. `uretim-log.md` sonuna: toplam klip, kullanılan hesaplar ve krediler, yeniden üretilmesi önerilenler, kurguda eklenecek yazılar (senaryo.md'deki "Kurguda" satırları). Açtığın sekmeleri kapat.

## Dur ve kullanıcıya bildir (sadece bunlar)
- Chrome eklentisi bağlı değil / site izni bekliyor.
- Ödeme, abonelik, şifre, 2FA, CAPTCHA ekranı.
- Tüm hesaplarda kredi bitti.
- Flow aynı içeriği 3 kez politika gerekçesiyle reddetti (prompt'u yumuşatmayı 1 kez dene, sonra atla ve log'a yaz).
