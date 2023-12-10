# Cisco Router DHCP Config

Önceki yazılarımızda router'larımızı kullanarak ağ yönlendirmelerini nasıl gerçekleştireceğimizi inceledik, bu sefer ise router'ların ağlardaki cihazlara IP adresi ve diğer ağ konfigürasyon bilgilerini otomatik olarak dağıtan DHCP sunucusu olarak nasıl kullanılacağını ele alacağız.


Network tasarımımızda 3 adet bilgisayar 1 adet switch 1 adet router bulunmaktadır.

## ROUTER DHCP CONFİG

```bash
Router>en
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#service dhcp
Router(config)#ip dhcp pool my_dhcp
Router(dhcp-config)#network 192.168.1.0 255.255.255.0
Router(dhcp-config)#default-router 192.168.1.1
Router(dhcp-config)#dns-server 8.8.8.8
```


```bash
Router(config)#interface fastEthernet 0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#no shutdown
```

Yapılandırmaları yaptıktan sonra bilgisayarları Static'ten DHCP ye çekmeniz gerekmektedir.


`Show ip dhcp binding` komutunu yazarak atanan IP adreslerini görebilirsiniz.

```bash
Router#show ip dhcp binding
IP address       Client-ID/              Lease expiration        Type
                 Hardware address
192.168.1.2      00D0.BC4A.1205           --                     Automatic
192.168.1.3      00D0.D38B.36EA           --                     Automatic
192.168.1.4      0030.F2C9.E40A           --                     Automatic
```



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
