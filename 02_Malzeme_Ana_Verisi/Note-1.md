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














