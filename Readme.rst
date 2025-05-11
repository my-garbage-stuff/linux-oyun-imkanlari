Linuxta Oyun Oynama Yöntemleri
==============================
Bu yazıda sizlere Linux dağıtımlarında nasıl oyun oynanabilir ve ne gibi imkanlar vardır onlar anlatılacaktır.
Dağıtım olarak debian baz alınacakdır. Diğer dağıtımlarda da benzer yöntemler geçerlidir.

Oyun Platformu Desteği
-----------------------

.. list-table:: Oyun Platformu Desteği
	:widths: auto
	:header-rows: 1

	* - Oyun Platformu
	  - Linux Desteği
	  - Açıklama

	* - Steam
	  - Var
	  - Popüler oyun platformu, geniş bir oyun kütüphanesi sunar.

	* - Epic Games
	  - Var
	  - Linux için heroic launcher ile erişilebilir.

	* - Xbox Gamepass
	  - Yok
	  - Xbox Gamepass desteği bulunmamaktadır.

	* - itch.io
	  - Var
	  - Bağımsız oyunların bulunduğu bir platformdur.

	* - Eski Oyunlar
	  - Var
	  - Emülatör gerekebilir.

Avantajları
-----------
1. Daha Yüksek Performans
^^^^^^^^^^^^^^^^^^^^^^^^^
Linux dağıtımları, genellikle daha hafif yapıları sayesinde oyunları daha verimli bir şekilde çalıştırır. Açık kaynak yapısı, daha az hata ve daha stabil bir oyun deneyimi sunar. Ayrıca, gereksiz ağ yükü oluşturan tracker gibi bileşenler içermediği için daha verimli bir ağ bağlantısı sağlar. Bu durum, oyunlarda hissedilir bir performans farkı yaratır.

2. Daha Yüksek Gizlilik
^^^^^^^^^^^^^^^^^^^^^^^^
Kapalı kaynaklı yazılımlar, genellikle gizlilik sorunlarına yol açabilir. Linux dağıtımları ile oyun oynandığında, oyunlar sistemden bağımsız ve izole bir şekilde çalıştırılabilir. Bu, kullanıcı verilerinin daha az izlenmesi ve toplanması anlamına gelir, böylece Linux kullanıcıları gizliliklerini koruma konusunda daha fazla kontrol sahibi olurlar.

3. Daha Az Donanım Gereksinimi
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Linux dağıtımları, daha hafif ve optimize edilmiş yapılar sunduğundan, daha az güçlü donanımlarla bile iyi performans gösterebilir. Bu, eski veya düşük özellikli bilgisayarların bile verimli bir şekilde kullanılabilmesini sağlar.

4. Uyumluluk
^^^^^^^^^^^^
Linux dağıtımlarında, bir oyunun eğer desteği varsa Linux uyumlu sürümünü, yoksa Windows sürümünü ara katman (Wine/Proton) yardımıyla oynayabilirsiniz. Ara katmanlar, oyunun hangi Windows sürümüne göre çalıştırılacağı ve hangi kütüphanelerin nasıl kullanılacağı konusunda ayarlama imkanı sunar.

5. Daha Fazla Kontrolcü Desteği
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Linux dağıtımlarında, birçok farklı oyun kontrolcüsü sorunsuz bir şekilde çalışabilir. Ekstra bir sürücü veya araç yüklemeden kullanılabilir ve bu sayede oyun kontrolcülerinden daha yüksek verim alabilirsiniz.

Dezavantajları
--------------
1. Anti-cheat sistemleri
^^^^^^^^^^^^^^^^^^^^^^^^
Bazı oyun yapımcıları hile engellemek için sisteminize çekirdek seviyesinde kod ekleyerek hile tespit etmeye çalışır. Linux dağıtımlarında bu tür yapılara izin verilmediği için bu tür oyunlar çalışmaz. Bu tür oyunlar siz oyunu oynamasanız bile arkada sürekli olarak çekirdek seviyesinde kod çalıştırdığı için hem gzlilik açısından sorunludur, hem de sistemin verimliliğini düşürür. Bu sebeple anti-cheat sistemi içeren oyunların çalışmamasını avantaj olarak kabul edebilirsiniz :D 

2. Oyun desteği
^^^^^^^^^^^^^^^
Linux dağıtımı ile genellikle tüm oyunları oynayabilirsiniz fakat bazı oyunlar hiç çalışmayabilir veya hatalı çalışabilir. Bu durumla ilgili olarak kullanıcılar tarafından test edilmiş oyunları ve durumları görmek için https://www.protondb.com/ adresine bakabilirsiniz.

Oyun platformları ve kurulumları
================================
Steam
-----
Steam doğrudan linux dağıtımları içi destek veren bir oyun platformudur. 2 farklı şekilde yüklenebilir. Eğer flatpak üzerinden yüklerseniz izole çalışacağı için daha yüksek gizililik sağlar.

Debian paketi ile
^^^^^^^^^^^^^^^^^
Debian tabanlı dağıtımlara Steam yüklemek için aşağıdaki adımları izleyin:

1. **Steam'in resmi web sitesine gidin**:
`https://store.steampowered.com/about/`

2. **Debian paketi indirin**:
"Install Steam" veya benzeri bir bağlantıya tıklayarak `.deb` dosyasını indirin.

3. **Terminali açın**:
İndirilen dosyanın bulunduğu dizine gidin. Genellikle bu dizin `~/İndirilenler` (Downloads) klasörüdür.

4. **Paketi yükleyin**:
Aşağıdaki komutu kullanarak paketi yükleyebilirsiniz:

.. code-block:: bash

	sudo dpkg -i steam_latest.deb

5. **Bağımlılıkları düzeltin**:
Eğer yükleme sırasında bağımlılık hataları alırsanız, aşağıdaki komutu çalıştırarak bağımlılıkları düzeltebilirsiniz:

.. code-block:: bash

	sudo apt-get install -f

Bu adımları takip ederek Steam'i Debian tabanlı bir dağıtımda başarıyla yükleyebilirsiniz.

Flatpak ile
^^^^^^^^^^^
1. **Flatpak'ı yükleyin**:
Eğer sisteminizde Flatpak yüklü değilse, aşağıdaki komutla yükleyebilirsiniz:

.. code-block:: bash

	sudo apt install flatpak

2. **Flathub deposunu ekleyin**:
Flathub, Flatpak uygulamaları için en yaygın depodur. Aşağıdaki komutla Flathub deposunu ekleyin:

.. code-block:: bash

	flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

3. **Steam'i yükleyin**:
Aşağıdaki komutu kullanarak Steam'i yükleyebilirsiniz:

.. code-block:: bash

	flatpak install flathub com.valvesoftware.Steam

4. **Steam'i başlatın**:
Yükleme tamamlandıktan sonra Steam'i başlatmak için uygulama menüsünden veya aşağıdaki komutu kullanabilirsiniz:

.. code-block:: bash

	flatpak run com.valvesoftware.Steam


Bu adımları takip ederek Flatpak ile Steam'i başarıyla yükleyebilirsiniz.

Heroic Launcher
---------------
Heroic Launcher, Epic Games Store ve GOG (Good Old Games) oyunlarını Linux üzerinde oynamak için kullanılan bir oyun başlatıcısıdır. 

- **Epic Games Store ve GOG Desteği**: Bu platformlardan oyunları yönetme ve oynama imkanı.
- **Oyun Kütüphanesi Yönetimi**: Oyunlarınızı kolayca bulabilir ve yönetebilirsiniz.
- **Proton ve Wine Desteği**: Windows oyunlarını Linux üzerinde çalıştırmak için gerekli araçları entegre eder.
- **Açık Kaynak**: Geliştiriciler ve kullanıcılar tarafından sürekli olarak güncellenir ve iyileştirilir.

Heroic launcher yüklemek için https://heroicgameslauncher.com/downloads adresine gidebilirsiniz.

Emülatörler ve Ara Katmanlar
============================

Linux, oyun oynamak için giderek daha popüler bir platform haline geliyor. Ancak, bazı oyunlar yalnızca Windows üzerinde çalıştığı için, Linux kullanıcıları için emülatörler ve ara katmanlar önemli bir rol oynamaktadır.

1. **Wine/Proton**: Windows uygulamalarını Linux üzerinde çalıştırmak için kullanılan bir uyumluluk katmanıdır. Oyunlar dahil birçok Windows yazılımını çalıştırmak için kullanılabilir. Wine, Windows API'sini Linux üzerinde taklit ederek çalışır.

2. **Lutris**: Linux üzerinde oyunları yönetmek için kullanılan bir oyun platformudur. Hem native Linux oyunlarını hem de Windows oyunlarını (Wine ile) destekler. Lutris, oyunları yüklemek ve çalıştırmak için gerekli olan tüm bağımlılıkları otomatik olarak yönetir.

3. **RetroArch**: Birçok eski oyun konsolunu emüle eden bir platformdur. NES, SNES, Sega Genesis, PlayStation ve daha birçok konsolu destekler. Kullanıcı dostu arayüzü ile oyunları kolayca bulup oynamanızı sağlar.

Minecraft
=========

Linux üzerinde Minecraft oynamak için **Prism Launcher** gibi bir başlatıcı kullanabilirsiniz. Prism Launcher, Minecraft'ı başlatmak ve yönetmek için kullanıcı dostu bir arayüz sunar.

Kurulum Adımları
----------------

1. **İndirme**: 
Prism Launcher'ın en son sürümünü https://github.com/PrismLauncher/PrismLauncher/releases adresinden indirin.

2. **Kurulum**:
- Eğer `.AppImage` dosyası indirdiyseniz, terminalde şu komutları kullanarak çalıştırılabilir hale getirin:

.. code-block:: bash

	chmod +x PrismLauncher-*.AppImage
	./PrismLauncher-*.AppImage

- Eğer `.tar.gz` dosyası indirdiyseniz, dosyayı çıkartın ve içindeki dosyaları uygun bir dizine taşıyın. Ardından terminalden çalıştırabilirsiniz.

3. **Minecraft Hesabı**: 
Prism Launcher'ı açtıktan sonra, Minecraft hesabınızı ekleyin. Bu, oyunu oynamak için gereklidir.

4. **Oyun Sürümleri ve Modlar**: 
İstediğiniz Minecraft sürümünü seçebilir ve modlar ekleyebilirsiniz.

5. **Oynamaya Başlayın**: 
Tüm ayarları yaptıktan sonra oyunu başlatabilirsiniz.


