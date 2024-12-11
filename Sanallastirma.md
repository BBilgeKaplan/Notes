# Sanallaştırma
## Sanallaştırma Nedir?
Sanallaştırma, fiziksel kaynakların (bilgisayar, sunucu vb.) yazılım aracılığıyla sanal ortamlarda çalıştırılmasıdır. Bu teknoloji, kaynakların daha etkili ve verimli kullanılmasını sağlar. Örneğin:  
•	Bir sunucunun, birden fazla işletim sistemi ve uygulama çalıştırması mümkün hale gelir.  
•	Daha az fiziksel cihaz ve enerji kullanımı ile maliyet avantajı sunar.  

### Sanallaştırmanın Önemi
Sanallaştırma sayesinde:  
•	Fiziksel kaynaklar optimize edilir.  
•	Altyapı maliyetleri azalır.  
•	İş yüklerinin kolayca yönetilmesi sağlanır.  

## Hypervisor Nedir?
Hypervizör, sanal makineleri oluşturmak ve yönetmek için kullanılan bir yazılımdır. İki tür hypervizör vardır:  
1.	Tip 1: Doğrudan fiziksel donanım üzerinde çalışır (ör. VMware ESXi, Microsoft Hyper-V). Daha yüksek performans sağlar.  
2.	Tip 2: Mevcut bir işletim sistemi üzerinde çalışır (ör. VMware Workstation, Oracle VirtualBox). Daha çok test ve geliştirme için uygundur.  

**Sanallaştırma Türleri**
1.	Sunucu Sanallaştırma: Bir sunucunun birden fazla sanal sunucu olarak çalıştırılması.  
2.	Depolama Sanallaştırma: Depolama cihazlarının sanal olarak yönetilmesi.  
3.	Ağ Sanallaştırma: Ağ kaynaklarının sanal olarak yapılandırılması.  
4.	Veri Sanallaştırma: Farklı veri kaynaklarının sanal bir havuzda birleştirilmesi.  
5.	Uygulama Sanallaştırma: Uygulamaların sanal ortamda çalıştırılması.  
6.	Masaüstü Sanallaştırma: Kullanıcı masaüstlerinin sanal olarak sunulması.  


### Konteyner Tabanlı Sanallaştırma
Konteynerler, bir işletim sistemi üzerinde izole edilmiş çalışma ortamları sağlar. Docker ve OpenVZ gibi teknolojiler, bu yaklaşımı temsil eder. Avantajları:  
•	Daha az kaynak kullanımı.  
•	Hızlı kurulum ve yönetim.  
 
### Docker Nedir?
Docker, uygulamaları ve bağımlılıklarını izole bir ortamda çalıştırmak için konteyner teknolojisi kullanan bir platformdur. Docker, hypervizör yerine Docker Engine ile çalışır, bu nedenle:  
•	Daha az kaynak tüketir.  
•	Taşınabilirlik ve kolay paylaşım sağlar.  

**Docker'ın Çalışma Prensibi**
Docker, bir uygulamanın çalışması için gereken her şeyi (kod, bağımlılıklar, kütüphaneler) bir "container" adı verilen hafif, izole bir ortamda çalıştırır. Bu sayede uygulamalar farklı platformlarda uyumlu bir şekilde çalışabilir.  
1.	Image Oluşturma: Docker, uygulama ve bağımlılıklarını içeren bir "image" oluşturur. Bu işlem genellikle bir Dockerfile kullanılarak yapılır. Örneğin, bir Python uygulaması için bir Dockerfile'da Python sürümü ve gerekli kütüphaneler tanımlanır.  
2.	Image Paylaşımı: Oluşturulan Docker image'ları Docker Hub gibi depolama platformlarında paylaşılır. Böylece başka geliştiriciler ya da sistemler bu image'ları kullanabilir.  
3.	Container Oluşturma: Docker image, Docker Engine üzerinde çalıştırılarak bir container oluşturulur. Container, yalnızca ihtiyacı olan kaynakları kullanır ve işletim sisteminin çekirdeğini diğer container'larla paylaşır.  
4.	Container Yönetimi: Docker, çalışan container'ların durumunu izlemek, durdurmak veya yeniden başlatmak için araçlar sunar.  

### Kubernetes Nedir?
Kubernetes (k8s), konteynerli uygulamaların otomatik olarak dağıtımını ve yönetimini sağlayan açık kaynaklı bir platformdur. Özellikleri:  
•	Ölçeklenebilirlik.  
•	Konteyner yaşam döngüsü yönetimi.  

**Konteyner Orkestrasyonu Yazılımları**
•	Docker Swarm  
•	Kubernetes  
•	Apache Mesos  
•	OpenShift  

*********************************
#### Orkestrasyon Nedir?
Orkestrasyon, birden fazla konteynerin dağıtımı, yönetimi, ölçeklendirilmesi ve izlenmesi işlemlerinin bir araya getirilerek organize bir şekilde yapılmasını ifade eder. Basit bir ifadeyle, konteynerlerin birden fazla fiziksel veya sanal makineye yayıldığı, bu süreçlerin bir düzen içinde yürütülmesini sağlayan otomasyon sürecidir.

#### Kubernetes ve Orkestrasyon
Kubernetes, konteynerlerin yönetimini otomatikleştiren ve sistemin iş yüklerini daha verimli bir şekilde çalıştırmasını sağlayan bir konteyner orkestrasyon platformudur. Orkestrasyon kavramını anlamak için Kubernetes’in sağladığı özellikler şu şekilde sıralanabilir:
1. Dağıtım Yönetimi:  
•	Kubernetes, birden fazla konteyneri otomatik olarak dağıtabilir ve bu konteynerlerin tutarlı bir şekilde çalışmasını sağlayabilir.  
•	Örnek: Bir e-ticaret sitesinde, kullanıcı trafiği arttığında Kubernetes, daha fazla konteyner oluşturarak uygulamanın ölçeklenmesini sağlar.  

2. Ölçeklendirme:
•	Sistem kaynakları kullanıma göre otomatik olarak artırılabilir veya azaltılabilir. Bu, hem maliyet hem de performans açısından avantaj sağlar.  
•	Örnek: Kubernetes, yoğun dönemlerde daha fazla işlem gücü sunmak için konteynerleri çoğaltabilir, düşük talep olduğunda ise konteyner sayısını azaltır.  

3. Hata Toleransı ve Yüksek Erişilebilirlik:  
•	Kubernetes, çöken veya hatalı çalışan konteynerleri otomatik olarak yeniden başlatabilir.  
•	Yüksek erişilebilirlik için aynı uygulamanın birden fazla konteyner örneği çalıştırılabilir.  
•	Örnek: Bir uygulama çalışmayı durdurursa Kubernetes, bu uygulamayı başka bir düğümde (node) yeniden başlatır.  

4. Kaynak Yönetimi:  
•	Konteynerlerin CPU, RAM ve disk gibi kaynaklara olan ihtiyaçları otomatik olarak ayarlanabilir.  
•	Örnek: Bir veri analitiği uygulamasının daha fazla RAM veya işlemci gücüne ihtiyacı varsa Kubernetes, bu kaynakları dinamik olarak tahsis edebilir.  

5. Yük Dengeleme:  
•	Kubernetes, gelen trafiği konteynerler arasında dengeler ve sistemin yük altındayken performansını korumasını sağlar.  
•	Örnek: Kullanıcılar bir web uygulamasına erişim sağladığında, Kubernetes bu kullanıcı isteklerini birden fazla konteyner arasında eşit şekilde dağıtır.  
*********************************
### Çalışma Soruları ve Cevapları

1. Sanallaştırma neden önemlidir?  
Sanallaştırma, fiziksel kaynakların daha verimli kullanılması ve maliyetlerin azaltılması açısından kritik bir teknolojidir.  
Tek bir sunucudan birden fazla kaynak oluşturarak ölçeklendirme ve yönetim kolaylığı sağlar.  

2. Hypervizör nedir? Tip 1 ve Tip 2 hypervizörler arasındaki farkları açıklayın.  
Hypervizör, sanal makineleri çalıştırmak ve yönetmek için kullanılan bir yazılımdır.  
•	Tip 1 Hypervizör: Doğrudan fiziksel donanım üzerinde çalışır, yüksek performans sunar (ör. VMware ESXi).  
•	Tip 2 Hypervizör: Bir işletim sistemi üzerine kurulur, daha düşük performanslıdır (ör. Oracle VirtualBox).  

3. Docker ile geleneksel sanallaştırma arasındaki farklar nelerdir?  
•	Docker, konteyner teknolojisi ile çalışır, daha hafif ve hızlıdır.  
•	Geleneksel sanallaştırma, hypervizör kullanarak her sanal makine için ayrı bir işletim sistemi gerektirir.  

4. Kubernetes nedir? Hangi sorunları çözmek için kullanılır?  
Kubernetes, konteynerli uygulamaların otomatik dağıtımı ve yönetimi için kullanılan bir platformdur. Ölçeklendirme, kullanılabilirlik ve yaşam döngüsü yönetimini kolay
laştırır. Kubernetes, konteynerlerin kümeler halinde düzenlenmesini ve bu kümelerin verimli bir şekilde çalıştırılmasını sağlar. Örneğin, bir uygulamanın trafik yoğunluğuna göre ölçeklendirilmesi ya da bir konteynerin başarısız olması durumunda otomatik olarak yeniden başlatılması gibi işlemleri yapabilir.  


5. Konteyner tabanlı sanallaştırmanın avantajları nelerdir?  
•	Kaynak Verimliliği: Konteynerler, işletim sistemi çekirdeğini paylaşır ve bu nedenle geleneksel sanal makinelerden daha az kaynak tüketir.  
•	Hızlı Başlatma: Konteynerler saniyeler içinde çalıştırılabilir.  
•	Taşınabilirlik: Docker gibi teknolojiler sayesinde uygulamalar herhangi bir platformda çalışabilir.  
•	Kolay Dağıtım ve Yönetim: Konteynerler tek bir image kullanılarak hızlı bir şekilde dağıtılabilir.  

6. Sanallaştırma türlerinden hangisi bir veri merkezinin kaynaklarını en verimli şekilde kullanmasını sağlar?  
Sunucu sanallaştırma, birden fazla işletim sistemi ve uygulamayı tek bir fiziksel sunucu üzerinde çalıştırarak veri merkezlerinin kaynaklarını en verimli şekilde kullanmasını sağlar. Ayrıca, depolama sanallaştırma da depolama cihazlarını merkezi bir sistemden yöneterek verimliliği artırır.

7. Docker ve Kubernetes birlikte nasıl çalışır?  
Docker, konteyner oluşturmak ve yönetmek için kullanılırken Kubernetes, bu konteynerleri kümeler halinde organize eder ve yönetir. Örneğin:  
•	Docker, bireysel konteynerleri çalıştırır.  
•	Kubernetes, bu konteynerlerin ölçeklendirilmesi, yük dengelemesi ve hata toleransı gibi işlemleri yönetir.  
