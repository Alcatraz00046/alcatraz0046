# alcatraz0046

Topview + Seedance 2.0 ile "zaman yolculuğu" seyahat vlogu (ör. 90'lar karlı Kahramanmaraş) üretimi için çalışma alanı.

## Kurulu skill
- `.claude/skills/seedance-20/` — [Emily2040/seedance-2.0](https://github.com/Emily2040/seedance-2.0) v6.7.0 (MIT, commit `4668457`).
  Karakter tutarlılığı (`seedance-characters`), çok çekimli sahne (`seedance-sequence`), devam klibi (`seedance-continuation`) vb. alt skill'leri içerir.
  Claude Code'da `/seedance-20` ile çağrılır. Prompt hazırlar; video üretimi ve maliyeti Topview/Seedance tarafındadır.

## Maraş zaman yolculuğu paketi
- `maras-zaman-yolculugu/` — karakter kartı, karakter sayfası prompt'u, referans klasörleri, dönem kitapçıkları (90'lar kar, 2000'ler kar), Bölüm 1 (1996) ve Bölüm 2 (2005) sahne listeleri, üretim takibi. Başlangıç: `maras-zaman-yolculugu/README.md`.
- `.claude/skills/maras-zaman-yolculugu/` — proje skill'i (`/maras-zaman-yolculugu`): yeni klip/bölüm prompt'larını bu paket ve `seedance-20` kurallarıyla yazar.
