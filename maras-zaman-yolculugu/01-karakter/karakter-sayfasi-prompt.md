# Karakter Sayfası Görsel Prompt'u

Amaç: Seedance'a `@Image1` olarak verilecek **tek bir görsel**: aynı kişi, aynı kıyafet, birden fazla açı.
Topview'in görsel aracı veya herhangi bir görsel modeliyle üret. 3–4 deneme yap, yüzü en net ve kıyafeti en temiz olanı seç.

Kaydet: `02-referanslar/karakter/karakter-sayfasi.jpg` (yatay, en az 2048 px genişlik önerilir).

## Prompt (İngilizce — doldurulmuş, kopyala-yapıştır)
```
Character reference sheet of one original character, photorealistic, consistent identity across all views.
Subject: a 30-year-old man, short dark-brown slightly wavy hair, a short neatly trimmed beard, warm brown eyes, medium height and a slim athletic build, wearing a mustard-yellow modern puffer jacket (zipped), a red knit beanie, dark navy jeans and white chunky sneakers, holding a long black extended selfie stick (about arm-length, fully extended) with a small black action camera mounted at its tip, gripped in his right hand. The selfie stick is clearly visible and fully extended in every view.
Layout: one horizontal sheet with five full-body views side by side — front, three-quarter left, side profile, three-quarter right, back — plus one close-up head portrait in the top right corner.
Same person, same outfit, same proportions in every view. Neutral relaxed pose, arms slightly away from the body so the jacket shape is readable.
Background: plain light-grey studio backdrop, soft even studio light, no shadows on the background.
Sharp focus, true-to-life skin texture, natural colours.
No text, no labels, no logos, no watermark, no extra people.
```

## Ek (isteğe bağlı) — kışlık versiyon kontrolü
Karda nasıl göründüğünü test etmek için ikinci bir görsel:
```
The same character from the reference sheet, standing on a snowy street, light snowfall, overcast winter daylight, full body, three-quarter view, looking at camera with a curious smile. Same outfit, same face. Photorealistic. No text, no logos.
```
Bu görsel yalnızca kontrol içindir; `@Image1` olarak her zaman **karakter sayfası** kullanılır.

## Kontrol listesi
- [ ] 5 açıda da yüz aynı kişi
- [ ] Kıyafet renkleri tüm açılarda aynı
- [ ] Ellerde bozulma yok
- [ ] Üzerinde yazı/logo yok
- [ ] Arka plan düz
