# SAP SD Malzeme Ana Verisi 

+ SAP SD Malzeme Ana Verisi, tüm lojistik modüller tarafından ortak olarak kullanılan merkezi bir veridir.

+ SD malzeme ana verisi çeşitli malzeme türlerine sahiptir ve her malzeme türünün kendi **'görünümleri'** vardır.
  + Örnek olarak; bir malzemeyi satılabilir bir hale getirmek için *Satış ve Dağıtım Görünümleri* tutulmalıdır, alınan malzeme üzerinde kalite kontrolü yapmak için malzeme ana verisinde *Kalite Yönetimi Görünümü* doğru ayarlarla tutulmalıdır.
 
📌 Her satılabilir malzeme satış işlemlerinin gerçekleştirilebilmesi için bir **Satış Organizasyonu** ve **Dağıtım Kanalı** kombinasyonuna genişletilir. 

📌 Bir malzeme en az bir Dağıtım Kanalına genişletilmedikçe sistem kullanıcının SAP'de **satış kaydı yapmasına izin vermez**. 

+ Aşağıdaki **"Satış Görünümleri"** tüm satılabilir malzemeler için geçerlidir:

  + **SD: Satış Organizasyonu vr. 1:** Temel satışla ilgili veriler, vergi sınıflandırmaları, teslimat tesisi ölçü birimleri
 
  + **SD: Satış Organizasyonu vr. 2:** Malzemenin hesap atama grubu, malzeme gruplamaları (örn ürün hiyerarşisi malzeme grubu)
 
  + **SD: Genel/ÜY Verileri:** Satış ve Nakliye verileri (örn brüt ve net ağırlık, uygunluk, kontrol stratejisi, taşıma grubu, yükleme grubu).
 
+ Aşağıda SAP SD malzeme ana verisi ile ilgili ana işlemler bulunmaktadır:
  + **MM01** - Malzeme yarat
  + **MM02** - Malzeme değiştir
  + **MM03** - Malzeme görüntüle
  + **MM06** - Silinecek malzemeyi işaretle
  + **MM60** - Malzeme listesi


# SD Malzeme Ana Verisi Nasıl Oluşturulur ? 

+ Öncelikle **MM01** işlem koduna gideriz ve malzeme oluşturma ekranını açarız. 

<img width="674" height="512" alt="01_gorunumler-tanimlamalar" src="https://github.com/user-attachments/assets/ff03b190-aece-4c42-b505-66ef685abda7" />

<br> 

+ Üretim yeri (eğitim sunucusunda ZAKD), Depo yeri (eğitim sunucusunda 1001), Satış organizasyonu (Z113) ve Dağıtım kanalı (10) bilgileri girildikten sonra ilgili **görünümler** seçilir:

  + Temel Veriler 1-2
  + SD: Satış Organizasyonu 1-2
  + SD: Genel ÜY Verileri
  + Depo 1-2
  + Muhasebe 1-2  

---

<img width="706" height="596" alt="02_temel-veriler-1" src="https://github.com/user-attachments/assets/26af49ac-c9d0-4d8e-9c04-7f6349d1d5c0" />

+ Temel veriler 1 sekmesi, ürünle ilgil **temel bilgileri** içerir.

<br> 

---

<img width="712" height="580" alt="03_sd-1" src="https://github.com/user-attachments/assets/6c7acff3-6942-43e2-8ab0-47930489fb59" />

+ **SD: Satış Organizasyonu**

+ **Temel Ölçü Birimi:** Depo tarafından en düşük stok tutma birimi

+ **Satış Birimi:** Temel Ölçü Birimi'nden farklı olabilir. Örn; depo bir malzemeyi adet olarak stoklarken satış koliler halinde yapılabilir.

+ **Bölüm:** Bu malzemenin ait olduğu ürün hattı veya mal grubu.

+ **Teslimatı yapan ÜY:** Belirtilen malzemenin müşteriye gönderildiği tesis.

+ **Mal Grubu:** Malzemeleri ve hizmetleri farklı nitelikleri nedeniyle gruplama seçeneği.

+ **Koşullar:** Seçilen malzemenin temel fiyatını koruyabileceğimiz fiyatlandırma ana sistemine götürür.

+ **Vergi verileri** malzemenin ülkeye göre vergilendirme detaylarını içerir. Bu malzeme vergisiz, yarım vergi veya muaf olabilir.

+ **Miktar anlaşmaları**, müşterinin sipariş vermesi gereken minimum sipariş ve teslimat miktarını içerir.

+ **Teslimat Birimi:** Satış belgelerine bağlı teslimatlar için varsayılan değer olarak belirlenebilen ölçü birimi. 

---

<img width="714" height="622" alt="04_sd-2" src="https://github.com/user-attachments/assets/af49e5d6-c2a0-44ee-aa7d-3a4b3951d561" />

+ **Malzeme istatistik grubu:** SIS (LIS) raporlaması için gereklidir.

+ **Malzeme fiyatlandırma grubu:** Fiyatlandırma koşulu amaçları için kullanılır.

+ **Prim grubu:** İade düzenlemesi için kullanılan grup.

+ **Malzeme hesap tayin grubu:** Gelir veya satış indirimi hesabını belirlemek için fatura belgesinden muhasebe belgesi oluşturulurken sistem tarafından kullanılır.

+ **Genel kalem tipi grubu:** Madde kategorilerini tanımlamak ve satış siparişi işleme sırasında ilgili madde kategorilerinin seçimini yapmak için malzemeleri gruplama.

+ **Fiyatlandırma referans malzemesi:** Sistem tarafından fiyatlandırma amaçları için referans olarak kullanılan bir ana malzeme.

+ **Ürün hiyerarşisi:** Farklı özellikleri birleştirerek malzemeleri gruplamak için kullanılır. Analizler ve fiyat belirleme için de kullanılır.

---

<img width="711" height="576" alt="05_sd-genel-uy" src="https://github.com/user-attachments/assets/cbb8f9ed-5129-4d27-9613-e02007542896" />

+ **Kullanılabilirlik Kontrolü:** Malzemenin stoğunu kontrol etmek ve malzeme planlaması için gereksinimleri nasıl oluşturacağını tanımlayan kontrol grubu.
  + Eğitim sunucusunda "KP" seçiliyor.  

+ **Parti Yönetimi:** Malzeme toplu halde yönetiliyor, depolanıyor ve sevk ediliyorsa işaretlenir.

+ **Malzeme navlun grubu:** Malzemeleri taşıma ve nakliye gereksinimlerine göre sınıflandırmak için kullanılır.

---

<img width="715" height="632" alt="06_muhasebe-1" src="https://github.com/user-attachments/assets/44682a0b-da03-40db-b345-05cf8a4da01f" />

---

📌 Parti yönetimi ve üstündeki kutucuklar işaretlenip kaydedilirse MM02'den tekrar düzeltilebilir. Stokları da MIGO işlem kodundan atmamız lazım:
      + MIGO -> A01 -> R10 -> 561 
      + Malzeme - miktar - HF sekmelerinde gerekli bilgileri gir. 

📌 MM01 ile malzeme oluştururken mutlaka Muhasebe 1-2 görünümlerinin açık olması lazım. Yoksa stok atılamıyor. 

📌 Bir partideki malları başka bir partiye eklemek için MIGO işlem kodundan tüm bilgileri önce doldur sonra sağ altta açıklan "parti" sekmesinden stokların gideceği partiyi seç. 















