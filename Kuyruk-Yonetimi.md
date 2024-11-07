# Kuyruk Yönetimi

## Message Queue Nedir? Nasıl Çalışır?

Mesaj kuyrukları, uygulamalar veya uygulama bileşenleri arasında asenkron olarak mesajları iletmek için kullanılan bir araçtır.
Kuyruk yapısı, gönderilmesi istenen veriyi kuyrukta saklayıp ilgili bileşene uygun zamanda iletir.

**Producer:** Mesajı oluşturur, kuyruğa ekler.   *( işi üreten, talep eden )*  
**Consumer:** Mesajı kuyruktan alır, işler ve kuyruktan siler.   *( işi yapan )*

*Bu ikisi arasındaki yönetimi kuyruk yönetimi sağlar.*  

## Message Queue Kullanım Avantajları/Dezavantajları
**Avantajları:**  
-**Asenkron İletim:**  Uygulamalar arasında senkron olmasına gerek kalmadan veri iletimi sağlanır.  
-**Yük Dengeleme:** Yoğun trafikte mesajlar kuyrukta saklanır ve sistem kapasitesine göre işlenir. Böylece yoğun yüklerde sistem çökmesi engellenir.  
-**Hata Toleransı:** Mesajın iletilemediği durumlarda hata yönetimi mekanizmaları kullanılabilir.  
-**Dağıtık Sistemlerde Entegrasyon:** Farklı teknolojilere ait veya farklı konumlardaki sistemler arasında güvenli iletişim sağlanır.  
-**Dinamik Ölçeklendirme:** Trafik artışına göre consumer sayısı artırılabilir böylece sistem performansı korunur.  

**Dezavantajları:**  
-**Komplekslik:** Mesaj kuyrukları sisteme ekstra bileşen ekleyerek yönetim ve izleme açısından ekstra yük getirebilir.  
-**Kaynak Kullanımı ve Maliyet:** Kuyruk yapısı bazen fazladan bellek veya depolama kaynaklarına ihtiyaç duyabilir. Hata ayıklama ve yönetim için ek maliyetlere neden olabilir.

### Message Queue Ne Zaman Kullanılmalı?  
- Yüksek trafiğin söz konusu olduğu, ölçeklenebilirlik gerektiren durumlarda  
- Arka plan işlemlerinin asenkron yürütülmesi gerektiğinde  
- Sistem entegrasyonu gerektiğinde  

### Ne Zaman Kullanılmamalı?
- Basit, tek sunuculu uygulamalar için  
- Senkron işlemlerde  

## Basic Message Queue  
- Temel producer-consumer işlemlerini destekler.  
- Mesajlar genelde RAM’de tutulur bu yüzden sistem çökmesi durumunda mesajlar kaybolabilir.  
- Dinamik olarak ölçeklendirilebilme özelliği yoktur.  
- Mesaj tüketiminde gelişmiş kuyruk yönetimlerinden farklı olarak FIFO harici bir yöntem işlenmez.  
- Hata yönetim stratejileri bulunmaz.  

## RabbitMQ Nedir?
RabbitMQ açık kaynak kodlu bir message broker’dır. AMQP protokolünü (MQTT ve STOMP da desteklenir) kullanarak servisler arasında asenkron bir şekilde iletişim kurmayı sağlar.

## Pub/Sub Nedir?
Message queue sistemindeki klasik kullanım olan 1-1 yaklaşım dışında pub/sub kullanımı ile tek bir mesajı birden fazla aboneye göndermeyi sağlar. Örnek olarak bir youtube kanalı yeni bir video yüklediğinde abonelerine bildirim gider.

## Routing Nedir?
RabbitMQ'da routing, mesajların hangi kuyruğa gönderileceğini belirlemek için kullanılır.  
-Direct  
-Fanout  
-Topic   
-Header  

![image](https://github.com/user-attachments/assets/1c25cc98-c462-4845-8720-93ea33630d93)  

## RabbitMQ RPC
RPC (Remote Procedure Call), bir bilgisayarın ağ üzerindeki başka bir bilgisayarda çalışan bir fonksiyonu veya prosedürü çağırmasını sağlayan bir protokoldür. Bu, farklı sistemler arasında veri alışverişi yapmak ve işlemleri gerçekleştirmek için kullanılır. RPC, istemcinin ve sunucunun farklı lokasyonlarda olmasına rağmen sanki yerel bir fonksiyon çağırıyormuş gibi hissetmesini sağlar.

## Veri Kalıcılığı Nasıl Sağlanır?
Publisher Confirms: Mesajın RabbitMQ broker'a ulaşıp ulaşmadığını kontrol eden bir mekanizmadır.  
RabbitMQ mesajların kaybolmasını engellemek için disk üzerinde veya bellekte mesajları saklama yeteneğine sahiptir.

# Apache Kafka Nedir?

Apache Kafka, yüksek hacimli ve gerçek zamanlı veri akışını işlemek için kullanılan bir dağıtık veri akış platformudur. 2010 yılında LinkedIn tarafından geliştirilen Kafka, günümüzde dünyanın en popüler mesajlaşma sistemlerinden biridir. Scala ve Java ile yazılmıştır. 

Kafka'nın geliştirilmesinin temel nedeni, LinkedIn'in yüksek hacimli ve gerçek zamanlı veri akışını işleme ihtiyacıydı. LinkedIn, web sitelerinden, mobil uygulamalardan ve diğer sistemlerden gelen büyük miktarda veriyi işlemek zorundaydı. Kafka, bu ihtiyacı karşılamak için geliştirildi. 

Günümüzde Apache Kafka, Confluent tarafından sürdürülmektedir ve açık kaynaklı bir akış işleme yazılımıdır.

## Kuyruk Sistemi ve Apache Kafka
Kafka, mesajların bir yerden bir yere aktarılmasını sağlayan  bir kuyruk sistemidir. Kafka, verileri bir kuyrukta tutar ve bu kuyruktan diğer sistemlere aktarır. Mesajlar index yapısına göre yazılır ve okunur.

Kafka, bir kuyruk sistemi olarak aşağıdaki avantajları sağlar:  
 -Gerçek zamanlı veri işleme: Kafka, verileri gerçek zamanlı olarak işlemeye olanak tanır.  
 -Ölçeklenebilirlik: Kafka, yüksek hacimli veri akışını işlemek için ölçeklenebilir.  
 -Esneklik: Kafka, farklı veri formatlarını ve protokollerini destekler.  

## Apache Kafka Kullanım Alanları
Kafka, bir kuyruk sistemi olarak 
aşağıdaki kullanım alanlarına sahiptir:

Mesajlaşma: Kafka, farklı sistemler arasında mesajlaşma için kullanılabilir.  
Etkinlik takibi: Kafka, web siteleri, mobil uygulamalar ve diğer sistemlerden gelen etkinlikleri izlemek için kullanılabilir.  
Log toplama: Kafka, uygulamalardan ve sistemlerden log toplamak için kullanılabilir.  
Büyük veri entegrasyonu: Kafka, büyük veri platformlarıyla entegre olmak için kullanılabilir.  

## Event Streaming
**Event streaming** (Olay/Etkinlik akışı), bir sistemde meydana gelen değişiklikleri **gerçek zamanlı olarak yakalayıp işleme** sürecidir. Event streaming platformları, bu değişiklikleri olaylar (events) olarak temsil eder ve bu olayları farklı uygulamalara ve sistemlere dağıtır.

Kafka, event streaming için yaygın olarak kullanılan bir platformdur ve aşağıdaki kullanım alanlarına sahiptir:  

Müşteri davranışı analizi: Kafka, web siteleri, mobil uygulamalar ve diğer dijital kanallardan gelen müşteri davranışı verilerini gerçek zamanlı olarak analiz etmek için kullanılabilir.  
IoT analizi: Kafka, sensörlerden gelen IoT verilerini gerçek zamanlı olarak analiz etmek için kullanılabilir.  
Fraud tespiti: Kafka, gerçek zamanlı olarak finansal işlemleri izlemek ve dolandırıcılık tespit etmek için kullanılabilir.  
Risk yönetimi: Kafka, gerçek zamanlı olarak risk faktörlerini izlemek ve riskleri azaltıcı önlemler almak için kullanılabilir.  

![image](https://github.com/user-attachments/assets/04da8c56-6aff-4991-9988-89b035d8f256)

## Apache Kafka Çalışma Prensibi
Kafka, aşağıdaki temel kavramlara dayanır:

**Broker:** Kafka cluster'ını oluşturan sunuculardır.  
**Topic:** Verilerin tutulduğu bir konteynırdır.  
**Partition:** Bir topic'i oluşturan bölümlerdir.  
**Producer:** Verileri Kafka'ya gönderen uygulamalardır.  
**Consumer:** Kafka'dan veri alan uygulamalardır.  


Kafka, aşağıdaki şekilde çalışır:

**1- Producer,** verileri bir topic'e yazar. Producer, verileri Kafka'nın bir broker'ına yazar. Broker, verileri diskte kalıcı olarak tutar.  
**2- Broker,** verileri topic'e yazar. Broker, verileri topic'in bir partition'ına yazar.  
**3- Consumer,** Kafka'dan veri alır. Consumer, topic'ten verileri okur. Consumer, verileri belirli bir partition'dan veya tüm partition'lardan okuyabilir.  












