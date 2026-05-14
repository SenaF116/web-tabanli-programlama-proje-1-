# Galaxy War

Bu oyun, basit bir tarayıcı oyunu olarak hazırlandı. HTML, CSS ve JavaScript kullanarak yazıldı. Oynadığın ekran `index.html` üzerinden açılıyor ve grafikler `canvas` üzerine çiziliyor.

## Oyun nedir?

Galaxy War'da iki karakterden birini seçiyorsun: Stitch veya Angel. Sonra düşmanlara ateş ediyor, kalpler toplayıp mermini yeniliyor, tuzaklardan kaçıyorsun.

## Oyun içindeki şeyler

- Karakter seçimi: Stitch veya Angel
- Düşman uzaylılar: normal ya da silahlı uzaylılar
- Mermini doldurmak için kalp toplama
- Tuzaklar: çarparsan hasar alırsın
- Zaman ve seviye sistemi: ilerledikçe zorlaşıyor
- Tuşlar: WASD / ok tuşlarıyla hareket, fareyle nişan, boşlukla ateş

## Dosyaların işi ne?

- `index.html`: Oyun ekranını ve menüleri tutuyor. Başlangıç düğmelerini, seçim ekranını ve ana scripti içeriyor.
- `style[1].css`: Oyun ekranının görünümünü sağlar. Menü stili, arka fon ve buton tasarımları burada.
- `game[1].js`: Oyunun tüm mantığı burada. Resim yükleme, hareket, vurma, can hesapları ve çizim burada.
- Görseller: `stitch.png`, `angel-clean.png`, `alien-clean.png`, `gun-alien-clean.png`, `heart.webp`, `trap-clean.png`

## Kodda neler oluyor?

### Resimler nasıl yükleniyor?
`game[1].js` içinde `assets` diye bir liste var. Bu listede karakter ve düşman resimleri tanımlanıyor. Resimler `Image()` kullanılarak yükleniyor.

### Ekran nasıl ayarlanıyor?
`fitCanvas()` fonksiyonu, oyun alanını ekrana göre ayarlıyor. Bu sayede her çözünürlükte oyun düzgün görünüyor.

### Oyun nasıl çalışıyor?
`loop()` fonksiyonu sürekli çalışıyor ve her karede iki şey yapıyor:
- `update(dt)` ile oyuncu, düşman ve nesnelerin durumunu güncelliyor
- `draw()` ile güncel halini ekrana çiziyor

### `update(dt)` fonksiyonu ne yapıyor?
- Klavyeden ve fareden gelen komutları okuyor
- Karakteri hareket ettiriyor
- Düşmanların ve mermilerin hareketini hesaplıyor
- Kalp ve tuzakları güncelliyor
- Zaman dolduğunda veya hedef sayısına ulaşınca seviyeyi kontrol ediyor

### `collide()` fonksiyonu ne yapıyor?
Oyundaki çarpışma kontrolünü yapıyor:
- Kahraman düşmana çarparsa can azalıyor
- Kahramanın mermisi düşmana çarparsa düşman yok oluyor
- Kahraman kalp toplarsa mermi miktarı artıyor
- Tuzaklara çarparsa ekstra zarar alıyor

### Çizim işleri nasıl yapılıyor?
- `drawSprite()`: Resimleri doğru açıyla çiziyor
- `drawImageCentered()`: Resmi ortalayarak çiziyor
- `drawAmmoHud()`: Sağ üstte kalan mermiyi gösteriyor
- `drawSpace()`: Arka plandaki yıldızları ve uzay efektini çiziyor

## Oyun nasıl hissediyor?

Oyuna başladığında önce karakter seçiyorsun. Sonra uzaylılar geliyor, ateş ediyorsun, kalpleri topluyorsun, tuzaklardan kaçıyorsun. Oyunda süre var ve hedef sayısı var, bu yüzden hızlı hareket etmek gerekiyor.



Bu proje, basit bir oyun yapmayı gösteriyor. HTML tasarımı, CSS görünümü ve JavaScript ile mantığı bir araya getiriyor.

