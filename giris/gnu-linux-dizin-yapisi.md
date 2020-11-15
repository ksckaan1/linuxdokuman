# GNU/Linux Dizin Yapısı

Bu bölümde GNU/Linux sistemlerdeki dizin \(klasör\) yapısını göreceğiz. Dosya sistemini oluşturan dizinler, kapsadıkları dosyalar ve bunların Linux işletim sistemindeki görevleri de kısaca belirtilecektir.

Linux dizin yapısının geliştirilmesinde FSSTND \(file system standard\) grubunun çalışmalarının payı çok büyük olmuştur.

Linux dizin yapısında bazı dizinlerin işlevi birbiriyle aynıdır. Bu durum, özellikle birbirini takip eden iki Linux sürümünde belirginleşir. Örnek olarak bir dağıtımda `/usr/bin` dizini altında yeralan dosya, diğer sürümde `/bin` altına yerleştirilebiyor.

Dosya sistemleri ve dizinler paylaşımlı olarak da kullanılabilir. Birden fazla kişisel bilgisayarın bağlandığı ağda, disk alanından yer kazanmak için bir makina sunucu \(ana makina\) olarak tayin edilir. Ağ üzerindeki diğer makinalar da sunucu üzerindeki diski paylaşır. Buna örnek olarak kullanıcı ev dizinlerinin yeraldığı `/home`, çalıştırılabilir dosyaların bulunduğu /usr, e-posta ve haber grubu bilgilerinin bulunduğu `/var/spool/mail` ve `/var/spool/news` dizinleri verilebilir.

Kök dizini, kendisine bağlı diğer tüm dizinleri de içerdiğinden, Linux dosya sisteminde önemli bir yere sahiptir. Linux açılırken önce kök dizini `/etc/fstab` dosyasına uygun şekilde bağlanır. Diğer dosya sistemlerinin onarımı ve kontrolü için gerekli olan fsck programları, bu dizinde bulunmalıdır. Benzer şekilde yedekleme için gerekli olan _tar, zip, compress_ gibi arşiv programlarına da kök dizin altından erişilebilmeli, açılış esnasında hafızaya yüklenen çekirdek de kök dizininde yeralmalıdır.

Bir programı yerine koymadan önce bazı "dengelerin" gözönünde tutulmasında yarar vardır. Programlanan her yazılımı kök dizinine koyarsanız, bir süre sonra bu dosya sisteminin şiştiğini görürsünüz. Kök dizinini başlangıçta küçük \(_20-30Mb kadar_\) tutmak, geliştirilen programları daha önceden belirlenen başka bir dosya sistemi altına koymak akıllıca olur. Bu yol, ağ üzerinden genellikle paylaşımı mümkün olmayan kök dizininin her makinadaki sabit diskte mümkün olan en az yer işgal etmesini sağlar.

Sistemdeki önemli dizinlere göz atarsak,

* **/bin** Sistemin açılışı ve kontrolü için gerekli komutlar. Hem kullanıcıların, hem de sistem görevlisinin kullanabileceği dosyalar \(kök dizinde ise fazla şişmemesi koşuluyla\) buraya atılabilir. Sadece root kullanıcının ihtiyaç duyacağı init, getty, updatedb gibi programlar /sbin veya /usr/sbin'de durabilir. Bu dizinde bulunan dosyalara örnek olarak cat, chgrp, chown, date, dd, df, ln, mkdir, mount, ps, rm, sh, su, sync ve umount verilebilir.
* **/dev** G/Ç dosyaları. Linux çekirdeğinde desteklenen her aygıta ait dosya /dev dizini altında bulunur. Kurulum anında bu dosyalar yerine yerleştirilir, bu dosyaların silinmesi durumunda /dev/MAKEDEV ile tekrar yaratılabilirler.
* **/etc** Sistem yapılandırma dosyaları. Bu dizinde çalıştırılabilir dosyalar bulunmamalıdır. 
  * **skel** Buradaki dosyalar, kullanıcı hesabı açıldığında kullanıcının ev dizinine kopyalanır.
  * **rc.d** Bu dizinin içinde, init sürecinin başvurduğu yapılandırma dosyaları vardır. Bunlara "rc dosysları" da denir.
  * **passwd** Kullanıcı veritabanı
  * **fstab** Linux'un açılışı esnasında bindirilecek dosya sistemleri burada listelenir. 
  * **group** passwd'e benzer şekilde kullanıcıların gruplarını tutar.
  * **inittab** init daemon için yapılandırma dosyası
  * **motd** Kullanıcı sisteme girdikten sonra ekranına basılması istenen mesaj burada tutulur.
  * **profile** Kullanıcı sisteme girdiği zaman çalıştırılan dosya \(csh ve sh türevi kabuklar için\)
  * **shells** Sistemde kullanılabilecek kabuk isimleri burada tutulur.
  * **login.access** login komutu için yapılandırma dosyası. Sisteme girişi kullanıcı bazında sınırlamak için kullanılır.
* **/home** Kullanıcılara ayrılmış dizin. Başka şekilde ayarlanmamış ise, açılan her hesaba ait kullanıcı, burayı kullanır. Büyük sistemlerde, bu kısım alt parçalara ayrılabilir \(/home/ftpadm , /home/ogrenci gibi\)
* **/lib** Kütüphane dosyaları.
* **/mnt** Geçici mount edilen dosya sistemleri. Sadece bu iş için kullanıldığından sistem görevlisine zaman kazandırır.
* **/proc** Süreç kontrollerini ve diğer sistem bilgilerini tutan dosya sistemi. Bu dosya sistemi aslında disk üzerinde yer kaplamaz, tüm dosyalar çekirdeğin bir uzantısı sayılabilir.
  * **cpuinfo** işlemci modeli, tipi ve performansını bildirir.
  * **devices** Halihazırda çalışan çekirdek içinde desteği bulunan aygıt sürücülerini listeler.
  * **dma** Hangi dma kanallarının kullanıldığını belirtir.
  * **filesystems** Halihazırda çalışan çekirdek içinde desteği bulunan dosya sistemlerini listeler.
  * **interrupts** Hangi kesintilerin kullanımda olduğunu söyler.
  * **iports** Halen hangi giriş/çıkış iskelelerinin kullanıldığını belirtir.
  * **kcore** Sistem hafızasının görüntüsü
* **/root** Sistem görevlisinin ev dizini. Mümkünse bu dizini sistemdeki diğer kullanıcıların görmeyeceği şekilde ayarlayın.
* **/sbin** Hayati sistem komutları. Bir zamanlar bu dosyalar `/etc` dizini altında yeralıyorlardı. Sadece sistem görevlisinin ihtiyacı olan komutlar, /sbin veya /usr/sbin içinde bulunur.
* **/tmp** Geçici dosyaların koyulduğu dizin. Belirli zaman aralıklarında temizlenmelidir.
* **/usr** Diğer önemli sistem dosyalarını tutar. Bu bölüm genelde en kalabalık dizindir, zira yeni kurulan tüm programlar buraya konulur.
  * **X11R6** X Pencere sistemi bilgileri tutulur.
  * **doc** Belge ve dökümanlar, genellikle HOWTO ve FAQ dosyaları.
  * **lib** Bazı kütüphaneler
  * **man** Man dosyaları
  * **src** Bazı kaynak dosyaları ve linux çekirdeğini oluşturan kodları \(/usr/src/linux\) içeren dizin.
  * **sbin** Kök dosya sisteminde yeralması gerekmeyen çalıştırılabilir sistem görevlisi dosyaları
* **/var** Sürekli değişen sistem bilgileri burada tutulur. İstisnalar dışında diğer makinalarla paylaştırılmaz. 
* **adm** Sistem yönetimini ilgilendiren kayıtlar preserve Sistemin göçmesinden sonra zarar görmesi mümkün dosyaların kaydedildiği yer.
* **spool** Sonra işlenecek olan veriler buraya atılır \(e-posta gibi\)

Yukarıdaki dizin yapıları her sistem için farklılık gösterebilir.

