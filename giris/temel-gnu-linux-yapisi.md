# Temel GNU/Linux Yapısı

GNU/Linux yapısı birçok farklı parçalardan oluşur. Bu parçaların birleşimine işletim sistemi adını veririz.

Temel GNU/Linux İS parçaları şunlardır:

## Bootloader \(Önyükleyici\)

Bilgisayarınızın önyükleme sürecini yöneten yazılımdır. Çoğu kullanıcı için bu, basitçe açılan ve sonunda işletim sistemine önyükleme yapmak için kaybolan bir açılış ekranı olacaktır. \(Örn: GRUB\)

## Kernel \(Çekirdek\)

Bu, aslında "Linux" olarak adlandırılan bütünün tek parçasıdır. Çekirdek, sistemin çekirdeğidir ve CPU, bellek ve çevre birimlerini yönetir. Çekirdek, işletim sisteminin en düşük seviyesidir.

## Init System \(Sistem Önyükleyici\)

Kullanıcı alanını önyükleyen ve arka plan yordamlarını kontrol etmekle görevlendirilen bir alt sistemdir. En yaygın kullanılan init sistemlerinden biri systemd'dir \(en tartışmalı olanlardan biri\). Önyükleme sürecini, önyükleyiciden \(yani GRUB veya GRand Unified Bootloader\) teslim aldıktan sonra yöneten init sistemidir. Sistemin çalışmasındaki kilit oyuncudur.

## Daemons \(Arkaplan Hizmetleri\)

Önyükleme sırasında veya masaüstünde oturum açtıktan sonra başlayan arka plan hizmetleridir \(yazdırma, ses, programlama, vb...\)

## Graphical Server \(Grafik Sunucuları\)

Monitörünüzdeki grafikleri görüntüleyen alt sistemdir. Genellikle X sunucusu veya yalnızca X olarak adlandırılır. \(Xorg, Wayland...\)

## Desktop Environment \(Masaüstü Ortamı\)

Kullanıcıların gerçekte etkileşimde bulunduğu parçadır. Aralarından seçim yapabileceğiniz birçok masaüstü ortamı vardır \(GNOME, Cinnamon, Mate, Pantheon, Enlightenment, KDE, Xfce, vb.\). Her masaüstü ortamı yerleşik uygulamalar \(dosya yöneticileri, yapılandırma araçları, web tarayıcıları ve oyunlar gibi\) içerir. Birçok yerde DE olarak kısaltmasını görebilirsiniz.

## Applications \(Uygulamalar\)

Masaüstü ortamları tüm uygulamaları sunmaz. Tıpkı Windows ve macOS gibi Linux, kolayca bulunabilen ve kurulabilen binlerce yüksek kaliteli yazılım başlığı sunar. Modern Linux dağıtımlarının çoğu, uygulama kurulumunu merkezileştiren ve basitleştiren App Store benzeri araçlar içerir. Örneğin, Ubuntu Linux, binlerce uygulama arasında hızlı bir şekilde arama yapmanıza ve bunları tek bir merkezi konumdan yüklemenize olanak tanıyan Ubuntu Yazılım Merkezi'ne \(GNOME Yazılım Merkezinin üzerinde oynanmış haline\) sahiptir.

