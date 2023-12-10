# Cisco Router DHCP Config

Önceki yazılarımızda router'larımızı kullanarak ağ yönlendirmelerini nasıl gerçekleştireceğimizi inceledik, bu sefer ise router'ların ağlardaki cihazlara IP adresi ve diğer ağ konfigürasyon bilgilerini otomatik olarak dağıtan DHCP sunucusu olarak nasıl kullanılacağını ele alacağız.

## ROUTER DHCP; ARTILARI VE EKSİLERİ

### Artılar:
1. Kolay Yönetim ve Otomasyon:
Router üzerinde DHCP sunucusu kullanmak, ağ yönetimini kolaylaştırır. Cihazların IP adresleri otomatik olarak atanır, bu da elle yapılandırma ihtiyacını ortadan kaldırır ve yöneticilere zaman kazandırır.
2. Dinamik IP Adresleri:
DHCP, ağdaki cihazlara dinamik IP adresleri atayarak IP adresi havuzunu daha etkili bir şekilde kullanmayı sağlar. Her bağlanan cihaz farklı bir IP alabilir, bu da kaynakların daha verimli kullanılmasını sağlar.
3. IP Adres Çakışmalarını Engelleme:
DHCP sunucuları, atanmış IP adreslerini takip eder ve çakışmaları önlemek için gerekli kontrolleri yapar. Bu, ağdaki kararlılığı artırır.
4. Merkezi Kontrol:
Router üzerinde DHCP sunucusu, ağ yapılandırmasını tek bir merkezi konumda yönetmeyi sağlar. Yöneticiler, IP adresi atama politikalarını kolayca belirleyebilir ve değiştirebilir.

### Eksiler:
1. Tek Nokta Arızası:
Router üzerinde DHCP sunucusu, tek bir nokta arızası potansiyeline sahiptir. Eğer router arızalanırsa veya devre dışı kalırsa, DHCP hizmeti de etkilenir, bu da ağdaki tüm cihazları etkileyebilir.
2. Sınırlı Özellikler:
Router tabanlı DHCP sunucuları genellikle daha sınırlı özelliklere sahiptir. Büyük ve karmaşık ağlar için özel DHCP sunucu çözümleri daha fazla özellik ve esneklik sağlayabilir.
3. Performans Sorunları:
Yoğun trafik durumlarında router üzerindeki DHCP performansı düşebilir. Bu durum, büyük ağlarda performans sorunlarına yol açabilir.
Router üzerinde DHCP sunucusu kullanmak, küçük ve orta ölçekli ağlarda genellikle etkili ve uygun bir çözümdür. Ancak, büyük ve karmaşık ağlarda daha özel DHCP sunucu çözümleri veya yedekli DHCP sunucuları düşünülmelidir.
