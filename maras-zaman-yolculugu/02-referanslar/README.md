# Referans Fotoğrafları

| Klasör | Ne koyulur |
|---|---|
| `karakter/` | `karakter-sayfasi.png` (zorunlu), isteğe bağlı kontrol görselleri |
| `gunumuz/` | Bugünkü Maraş (açılış/geçiş klibi için) |
| `1990lar-kar/` | 1990'lardan karlı Maraş fotoğrafları |
| `2000ler-kar/` | 2000'lerden karlı Maraş fotoğrafları |

## İsimlendirme
`NN-yer-yil.jpg` → ör. `01-trabzon-caddesi-1996.jpg`, `02-kale-manzara-1994.jpg`, `03-kapali-carsi-1998.jpg`

Yıl kesin değilse `199x` yaz. Fotoğrafı eklediğinde aşağıdaki tabloya bir satır ekle; Claude prompt yazarken bu tabloyu okur.

## Fotoğraf seçimi
- **İyi referans:** sokak, cadde, çarşı, bina cepheleri, araçlar, tabelalar, karlı manzara, kalabalığın genel dokusu.
- **Zayıf referans:** yakın plan insan yüzleri (moderasyona takılabilir, kimliği karıştırır), çok bulanık/küçük fotoğraflar.
- Siyah-beyaz fotoğraf da olur; prompt'ta "renk paleti dönem kitapçığından" denir.
- Fotoğraf hakları: kendi/aile arşivin veya izinli kaynak.
- Rol: dönem fotoğrafları **sadece mekân, ışık, doku, araç, kıyafet modası** için. Kimlik her zaman `@Image1`.

## Envanter
| Dosya | Dönem | Yer | Ne gösteriyor | Kullanıldığı klip |
|---|---|---|---|---|
| (örnek) 01-trabzon-caddesi-1996.jpg | 1990lar | Trabzon Caddesi | karlı cadde, eski sedanlar, dükkân tabelaları | 1-02 |
