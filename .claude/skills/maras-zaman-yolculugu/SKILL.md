---
name: maras-zaman-yolculugu
description: "Kahramanmaraş zaman yolculuğu vlog serisi (90'lar karlı gün, 2000'ler karlı gün vb.) için Topview + Seedance 2.0 prompt'u, karakter kartı, referans rol haritası ve sahne listesi üretir. Kullanıcı Maraş/zaman yolculuğu/dönem vlogu/yeni bölüm/yeni sahne/prompt istediğinde veya referans fotoğraf yüklediğinde kullan."
user-invocable: true
tags: [seedance, topview, maras, time-travel, vlog]
---

# maras-zaman-yolculugu

Bu skill, `maras-zaman-yolculugu/` klasöründeki proje paketini yönetir ve prompt yazımını `seedance-20` skill'ine dayandırır.

## Önce oku
1. `maras-zaman-yolculugu/README.md` — iş akışı.
2. `maras-zaman-yolculugu/01-karakter/karakter-karti.md` — **Karakter A** kimlik kilidi. Boş alan varsa önce onu kullanıcıyla doldur; karakter kilitlenmeden sahne prompt'u yazma.
3. İlgili dönem dosyası: `03-donemler/*.md`.
4. İlgili bölüm: `04-sahne-listesi/*.md` ve `05-uretim-takip.md`.

Prompt kuralları için `seedance-20` alt kaynaklarını kullan:
- Kimlik/tutarlılık: `.claude/skills/seedance-20/skills/seedance-characters/SKILL.md`
- Referans etiketleri: `.claude/skills/seedance-20/references/reference-workflow.md`
- Çok çekim: `.claude/skills/seedance-20/references/multishot-grammar.md`
- Geçiş klibi: `.claude/skills/seedance-20/references/first-last-frame-guide.md`
- Devam klibi: `.claude/skills/seedance-20/skills/seedance-continuation/SKILL.md`
- Moderasyon ön kontrolü: `.claude/skills/seedance-20/references/moderation-prescreen.md`

## Sabit kurallar
- **Kimlik tek kaynaktan gelir:** `@Image1` her zaman karakter sayfasıdır. Dönem fotoğrafları yalnızca mekân, doku, ışık, araç, tabela ve kıyafet dönemi taşır; içlerindeki gerçek kişilerin yüzleri **transfer edilmez** — bunu prompt'a açıkça yaz.
- **Etiketler:** `@Image1`…`@Image9`, `@Video1`… harfiyen; köşeli parantez yok. Her etiketin yanında görevi yazılır.
- **Prompt dili İngilizce**, kullanıcıya açıklama Türkçe. Türkçe konuşma/dış ses kurguda eklenir (Seedance Türkçe dudak senkronu doğrulanmadı); klipte karakter konuşacaksa kısa, kameraya bakan, kilitli kamera.
- **15 sn'de en fazla 3 çekim**; çekimler `Shot 1/2/3` ile, saniye yazmadan. Çekim başına tek kamera hareketi.
- **Her çekim bir kilit satırıyla biter:** `Lock: Character A from @Image1 — <imza kıyafet>; <dönem + kar + ışık>; <konum ve bakış yönü>; camera <taraf>.`
- **Kapanış kısıtı:** `No subtitles, no on-screen text, no logos, no watermark. Do not copy faces of people from @Image2–@ImageN.`
- **Marka adı yazma:** "Tofaş Şahin" yerine "a boxy 1990s Turkish sedan" gibi genel tarif; gerçek tabela yazıları referans fotoğraftan gelsin.
- Para/hesap/üretim başlatma yok: sadece prompt ve paket üretilir; üretimi kullanıcı Topview'de yapar.

## Çıktı formatı (her klip için)
```
### Klip <bölüm>-<no> · <başlık>
Mod: Reference-to-video | First/Last frame | Extend
Süre: <4–15> sn · Oran: 9:16 (varsayılan) · Çekim sayısı: <1–3>
Yükleme sırası:
  @Image1 = 01-karakter/karakter-sayfasi.jpg  (kimlik)
  @Image2 = 02-referanslar/...                (mekân)
  ...
Prompt:
  <İngilizce prompt>
Kurguda eklenecek: <Türkçe dış ses / müzik / ses efekti>
Risk: <moderasyon, kalabalık, el, yazı vb.>
```
Sonra `05-uretim-takip.md` tablosuna satır ekle.

## Yeni dönem/bölüm eklerken
`03-donemler/_sablon.md` ve `04-sahne-listesi/_sablon.md` kopyalanır. Dönem dosyasına sadece kullanıcının fotoğraflarında görülen veya kesin bilinen dönem detaylarını yaz; emin olmadığın yerel detayı "kontrol et" diye işaretle.
