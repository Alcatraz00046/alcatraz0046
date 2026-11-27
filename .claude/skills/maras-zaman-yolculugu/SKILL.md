---
name: maras-zaman-yolculugu
description: "Kahramanmaraş zaman yolculuğu vlog serisi (aktif: 2005 Trabzon Caddesi, normal gün, kar yok) için Google Flow (Veo 3.1) kare + video prompt'ları, karakter tutarlılığı ve sahne listesi üretir. Kullanıcı Maraş/zaman yolculuğu/yeni klip/yeni bölüm/prompt istediğinde, referans fotoğraf veya üretilmiş klip gönderdiğinde kullan."
user-invocable: true
tags: [flow, veo, maras, time-travel, vlog]
---

# maras-zaman-yolculugu

Üretim aracı **Google Flow (Veo 3.1)**. Paket: `maras-zaman-yolculugu/`.

## Önce oku
1. `maras-zaman-yolculugu/01-karakter/karakter-karti.md` — Yolcu (değişmez).
2. `maras-zaman-yolculugu/04-sahne-listesi/bolum-01-2005-trabzon-caddesi.md` — aktif bölüm, ortak bloklar.
3. `maras-zaman-yolculugu/03-donemler/2000ler-kar.md` ve `05-uretim-takip.md`.
`04-sahne-listesi/arsiv/` eski Seedance/1996 planıdır; kullanıcı istemedikçe kullanma.

## Flow kuralları
- Etiket yok (`@Image1` yazma). Görseller yüklenir; prompt "the man from the character sheet", "the street photo" diye anar.
- Her klip iki adım: **A** kare (görsel üret: karakter sayfası + referans foto, 9:16) → **B** Frames to Video (8 sn, 9:16). Geçiş kliplerinde ilk kare = `02-referanslar/gecis-beyaz-kare.png`.
- Klip başına tek çekim, tek ana hareket, en fazla bir kısa Türkçe cümle (sayıları yazıyla: "iki bin beş").
- Video prompt'u her zaman şunu içerir: `Keep his face, stubble, curly hair, green parka, orange beanie and selfie stick exactly the same throughout.` ve `No subtitles, no on-screen text, no logos.`
- 2005 dönemi: akıllı telefon, düz ekran TV, LED ekran, modern araç yok. Okunur yazı/plaka/logo isteme.
- Gerçek fotoğraflardaki insanların yüzleri karaktere taşınmaz; yalnızca mekân ve dönem.
- Kullanıcı klip gönderirse: ffmpeg ile saniyede bir kare çıkarıp kontrol et (yüz, kıyafet, mekân, dönem hatası, geçiş), sesi dinleyemediğini söyle, `05-uretim-takip.md`'ye yaz.

## Çıktı
Kullanıcıya her seferinde **bir klip**: yüklenecekler, A prompt'u, B prompt'u, kontrol listesi. Kısa ve Türkçe açıklama, prompt'lar İngilizce (konuşma Türkçe).
