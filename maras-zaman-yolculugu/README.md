# Maraş Zaman Yolculuğu — Topview + Seedance 2.0 paketi

Seyahat vlogu tarzında, bir karakterin geçmişteki bir güne (ör. **1996 karlı bir ocak sabahı**, **2005 karlı bir şubat akşamı**) gidip Kahramanmaraş'ı gezdiği video serisi.

## Klasörler
| Klasör | İçerik |
|---|---|
| `01-karakter/` | Karakter kartı (kimlik kilidi) + karakter sayfası görsel prompt'u |
| `02-referanslar/` | Senin yükleyeceğin gerçek fotoğraflar (dönem başına klasör) |
| `03-donemler/` | Dönem kitapçıkları: görsel kurallar + prompt kalıpları |
| `04-sahne-listesi/` | Bölüm bölüm klip listesi ve hazır prompt'lar |
| `05-uretim-takip.md` | Hangi klip, hangi deneme, ne oldu |

Proje skill'i: `.claude/skills/maras-zaman-yolculugu/` (Claude Code'da `/maras-zaman-yolculugu`). Prompt kuralları `seedance-20` skill'inden gelir.

## İş akışı (5 adım)
1. **Karakteri kilitle** → `01-karakter/karakter-karti.md` doldur, `karakter-sayfasi-prompt.md` ile görsel üret (Topview görsel aracı veya başka bir görsel modeli), en iyisini `02-referanslar/karakter/karakter-sayfasi.jpg` olarak kaydet.
2. **Referansları topla** → dönem klasörlerine fotoğrafları koy, `02-referanslar/README.md`'deki isim düzenine uy.
3. **Klibi seç** → `04-sahne-listesi/` içinden klip; yükleme sırasını birebir uygula (`@Image1` = karakter sayfası, sonra mekân fotoğrafları).
4. **Topview'de üret** → Seedance 2.0, reference/omni modu, süre ve oran klip kartındaki gibi. Prompt'u kopyala-yapıştır.
5. **Kaydet ve zincirle** → beğenilen klibin son karesini `extend`/devam klibi için kullan; `05-uretim-takip.md`'ye yaz. Türkçe dış ses, müzik ve yazılar kurguda (CapCut vb.) eklenir.

## Tutarlılık için 6 kural
1. `@Image1` **her klipte** karakter sayfası. Sıra asla değişmez.
2. Karakterin **imza kıyafeti** hiç değişmez (bütün dönemlerde aynı — zaman yolcusu olduğu böyle anlaşılır).
3. Gerçek fotoğraflar **sadece mekân/doku** taşır; prompt bunu açıkça söyler.
4. 15 sn'de en fazla 3 çekim; her çekim kilit satırıyla biter.
5. Kalabalık sahnede karakter tek "eylem yapan" kişidir; diğerleri arka planda küçük hareket.
6. Beğenilmeyen klipte tüm prompt'u değiştirme; tek bir şeyi değiştir, takip dosyasına yaz.

## Dikkat
- Seedance gerçekçi, tanınabilir yüz içeren referansları reddedebilir. Karakter sayfası özgün/üretilmiş bir karakter olsun; kendi yüzünü kullanacaksan önce kısa bir test yap.
- Fotoğraf hakları: kendi/aile arşivin veya izinli arşiv fotoğrafı kullan.
- Seedance sınırları (Eylül 2026 itibarıyla yaygın bildirilen): üretim başına ≤9 görsel, 4–15 sn. Topview'deki güncel sınırı ekrandan kontrol et.
