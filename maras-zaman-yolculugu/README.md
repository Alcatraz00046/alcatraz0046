# Maraş Zaman Yolculuğu — Google Flow (Veo 3.1) paketi

Seyahat vlogu tarzında, Yolcu'nun bugünkü karlı Maraş'tan **2005'te karlı bir akşam, Trabzon Caddesi**'ne gidip gezdiği video serisi.

**Aktif proje:** `90lar/` — 90'lar Kahramanmaraş, gerçek fotoğraf referanslı vlog; Google Flow'da **yerel oturum** (Claude in Chrome) skill `/maras-90lar-flow` ile üretir. Eski planlar `04-sahne-listesi/arsiv/`.

## Klasörler
| Klasör | İçerik |
|---|---|
| `01-karakter/` | Karakter kartı (kimlik kilidi) + karakter sayfası görsel prompt'u |
| `02-referanslar/` | Senin yükleyeceğin gerçek fotoğraflar (dönem başına klasör) |
| `03-donemler/` | Dönem kitapçıkları: görsel kurallar + prompt kalıpları |
| `04-sahne-listesi/` | Bölüm bölüm klip listesi ve hazır prompt'lar |
| `05-uretim-takip.md` | Hangi klip, hangi deneme, ne oldu |

Proje skill'i: `.claude/skills/maras-zaman-yolculugu/` (Claude Code'da `/maras-zaman-yolculugu`). Prompt kuralları `seedance-20` skill'inden gelir.

## İş akışı (Flow)
1. **Karakter** hazır: `02-referanslar/karakter/karakter-sayfasi.jpg`.
2. **Referans:** 2000'ler Trabzon Caddesi fotoğraflarını `02-referanslar/2000ler-kar/` içine koy.
3. **Her klip iki adım:** A) Flow'da görsel üret (karakter sayfası + referans foto, kare prompt'u, 9:16) → B) Frames to Video (A'daki kare başlangıç; geçişlerde ilk/son kare), video prompt'u, 8 sn.
4. **Kaydet:** `05-uretim-takip.md`. Ekran yazıları ve müzik kurguda (CapCut vb.).

## Tutarlılık için 6 kural
1. Karakter sayfası **her kare üretiminde** yüklenir.
2. Karakterin **imza kıyafeti** hiç değişmez (bütün dönemlerde aynı — zaman yolcusu olduğu böyle anlaşılır).
3. Gerçek fotoğraflar **sadece mekân/doku** taşır; prompt bunu açıkça söyler.
4. Klip başına tek çekim, tek ana hareket (8 sn).
5. Kalabalık sahnede karakter tek "eylem yapan" kişidir; diğerleri arka planda küçük hareket.
6. Beğenilmeyen klipte tüm prompt'u değiştirme; tek bir şeyi değiştir, takip dosyasına yaz.

## Dikkat
- Veo Türkçe konuşabiliyor ama telaffuz/dudak senkronu her denemede iyi olmayabilir; kötüyse sessiz üretip sesi kurguda ekle.
- Fotoğraf hakları: kendi/aile arşivin veya izinli arşiv fotoğrafı kullan.
- Flow çıktıları SynthID filigranı taşır; yayında yapay zekâ ile üretildiğini belirt.
