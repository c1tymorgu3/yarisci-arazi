# TRT Çocuk Yarışçı (2009) - hata düzeltmeleri

2009'da çıkan TRT Çocuk Yarışçı oyununun decompile edilmiş kaynakları ve modern
bilgisayarlarda oyunu kırılır hâle getiren üç hatanın düzeltilmiş hâli.

Oyun yüksek FPS'te çalıştığı için birkaç şey bozuluyor. Düzeltmelerin hepsi bununla
ilgili.

**Araç seçme ekranında Enter çalışmıyordu.** Klavye girdisi `FixedUpdate` içinde
dinleniyordu ve yüksek FPS'te iki kare arasına sıkışıp kayboluyordu. Dinleyiciler
`Update`'e taşındı. Artık Enter'a hızlı basmaya gerek yok, tek basışta seçiyor.

**Araçlar fırıldak gibi dönüyordu.** Aynı sebep: menüdeki dönme animasyonu kare
sayısına bağlıydı, saniyede yüzlerce tur atıyordu. Animasyon FPS'ten bağımsız hâle
getirildi, araçlar normal hızda dönüyor.

**Sunucu istekleri.** Oyun açılışta kullanıcı adı ve şifre soruyor, sonra bunları ve
bitiş skorunu ölü bir adrese yolluyordu. Bir işe yaramıyordu, TRT'ye boşuna istek
gitmesin diye kapatıldı.

**Soru ekranı beklemesi.** Kum saati toplayınca açılan soru ekranında cevaptan sonra
3.5 saniye bekletiyordu. 1 saniyeye indirildi.

Oyun tarayıcıda çalışacak şekilde yeniden yazılıyor: `yarisci-web` altında three.js
sürümü var.
