# linuxwebsunucu

Linux Web Sunucusu Kurulumu, Host Etme ve SSL/TLS Yapılandırma

Merhaba! Bugün, Nginx web sunucusuna nasıl SSL/TLS sertifikası kurulacağını adım adım öğreneceğiz. SSL/TLS sertifikası, web sitenizin güvenliğini sağlamak ve HTTPS üzerinden iletişimi şifrelemek için önemlidir. Şimdi, bu süreci başlatarak adımları inceleyelim.

Adım 1: Nginx Web Sunucusu Kurulumu ve Web Sitesi Oluşturma
Öncelikle Nginx'i kurmamız gerekiyor. Nginx, hafif ve performanslı bir web sunucusudur ve birçok web sitesi tarafından tercih edilmektedir.

Web sitemizi barındırmak için bir dizin oluşturalım:

/var/www/verkosis.com/html dizini, verkosis.com adındaki web sitemizin dosyalarını içerecek şekilde oluşturalım.
Ayrıca, Nginx sunucu bloğu yapılandırması için gerekli adımları izleyelim:

Yeni bir Nginx sunucu bloğu yapılandırma dosyası oluşturarak (/etc/nginx/sites-available/verkosis.com), web sitemizin Nginx'e nasıl tanıtılacağını belirtelim.
Yapılandırma dosyasını etkinleştirmek için sembolik bir bağlantı oluşturarak (/etc/nginx/sites-enabled), Nginx'e bu yeni yapılandırmayı yükleyelim.
Son olarak, yapılan değişiklikleri uygulamak için Nginx'i yeniden başlatalım.

Adım 2: SSL/TLS Sertifikası Oluşturma ve Yapılandırma
Şimdi sıra SSL/TLS sertifikası oluşturmaya geldi. Güvenli iletişim için bir sertifikaya ihtiyacımız var:

Bir özel anahtar (private key) oluşturarak (server.key), sertifikamızı güvenli bir şekilde kullanabileceğiz.
Sertifika İmzalama İsteği (CSR) dosyası oluşturarak (server.csr), sertifikamızı imzalayacak olan yetkili birimlere başvuru yapacağız.
Kendi kendimize imzalı (self-signed) bir sertifika oluşturarak (server.crt), test veya geliştirme amaçları için kullanabileceğiz.
Oluşturduğumuz SSL/TLS sertifikalarını Nginx'in SSL/TLS dizinine (/etc/nginx/tls ve /etc/nginx/key) taşıyarak, Nginx'in bu sertifikaları kullanmasını sağlayacağız.

Adım 3: Nginx SSL/TLS Sertifikası Yapılandırması
Artık SSL/TLS sertifikamızı Nginx'e tanıtmamız gerekiyor:

Nginx'in ana yapılandırma dosyasını (/etc/nginx/nginx.conf) düzenleyerek, SSL/TLS sertifikalarını belirtelim.
Sunucu bloğu içine SSL/TLS ayarlarını ekleyerek, verkosis.com adındaki web sitemizin HTTPS üzerinden güvenli bağlantılarını yapılandıralım.
Adım 4: Nginx'i Yeniden Başlatma
Yapılan SSL/TLS yapılandırma değişikliklerini uygulamak için Nginx'i yeniden başlatarak (sudo systemctl restart nginx), web sunucumuzu güncelleyelim ve sertifikaları etkin hale getirelim.

Artık Nginx web sunucusunda SSL/TLS sertifikasını başarıyla kurduk! Web sitemiz artık HTTPS üzerinden güvenli bir şekilde erişilebilir durumda. Bu adımları izleyerek, web sitenizin güvenliğini artırabilir ve ziyaretçilerinizin bilgilerini koruyabilirsiniz.

Umarım bu yazı size yardımcı olmuştur. İyi çalışmalar! 🌐🔒
