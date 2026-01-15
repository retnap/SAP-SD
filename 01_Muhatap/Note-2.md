# Müşteri Yönetimi (Muhatap) 

+ Bir SAP muhatabı, şirketinizin bir iş ilgisi bulunduğu bir **kuruluş** (firma, şube, ofis...), **kişi** veya **şirketler** grubudur. 

+ Bir muhatap, genel veriler (adres, banka bilgileri vb.) ve role özgü bilgilerden (örn. müşteri/tedarikçi/çalışan vb.) oluşur.
  + Bu roller, SAP içindeki diğer bölümlere bağlanır.
 
📌 Bir muhatap müşteri rolünü aldığında **müşteri/satış alt yönetimi** ve **genel muhasebe** ile olan bağlantısı **zorunludur**. 

📌 **BP** işlem kodu, **müşteri** ve **tedarikçi** oluşturmanın tek yoludur. 

---

# Muhatap Nasıl Oluşturulur ? 

+ Muhatap, işletmenin ticari ilişkisi olan kişi **organizasyon** veya **grup** olarak oluşturulabilir.

📌 İşlem Kodu: **BP**

<br> 

<img width="975" height="372" alt="01_bp-1" src="https://github.com/user-attachments/assets/34a03b8f-f26e-48c9-b4bb-68c397ea1024" />

<br> 

+ Üst kısımda bulunan **Organizasyon** butonuna basıyoruz.

<br> 

<img width="843" height="625" alt="02_adres-bilgileri" src="https://github.com/user-attachments/assets/eae296cf-86d9-44da-bf17-39320eb6c30b" />

+ Varsayılan olarak 000000 (Muhatap Genel) rolü alınır.

+ Bir muhataba atanan muhatap rolleri, onun sahip olduğu işlevleri ve dahil olacağı ticari işlemleri yansıtır.

+ Sağ tarafta bulunan **Gruplama** butonuna basarak **B001-Standard Müşteri Gruplaması**nı seçiyoruz.
  + Gruplama (grouping) şunu belirtir:
  + BP numarasını sistem mi versin, kullanıcı mı girsin?
  + B001 seçildiğinde numara sistem tarafından **otomatik** verilir.  

+ Adres sekmesindeki bilgiler gerekli şekilde doldurulur.

+ Adres bilgileri doldurulduktan sonra üst kısımda bulunan **Muhatap Rolleri** butonundan ilgili muhatap rolleri seçilir.

---

## Muhatap Rolleri

+ S/4HANA sisteminde müşteri ve satıcı kavramları **Business Partner (BP)** yapısı altında birleştirilmiştir.

+ BP işlemi ile tek bir muhatap oluşturulur, ancak bu muhatabın sistemde **hangi işlevleri yerine getireceği**, seçilen **muhatap rolleri** ile belirlenir.

+ BP işlem kodu girildiğinde ilk olarak **"Muhatap (Genel)"** rolü açılır. Bu rol, muhatabın kimlik bilgilerini içerir. Bu aşamada girilen bilgiler:
  + Firma adı
  + Adres bilgileri
  + Ülke, şehir, posta kodu
  + Arama terimi
  + Vergi kimlik bilgileri
 
+ Bu veriler:
  + Tüm modüller tarafından ortak kullanılır.
  + SD, FI veya başka bir rol açıldığında tekrar girilmez.

+ Yani "Bu firma kimdir ve nerede bulunur?" sorusu bu rolde cevaplanır.

+ Genel muhatap yalnızca **tanımlayıcı** bir roldür. Tek başına:
  + Satış siparişi oluşturamaz
  + Fatura kesemez
  + Muhasebe kaydı oluşturamaz

+ Bu nedenle muhatabın sistemde aktif bir müşteri olabilmesi için **işlevsel rollerin** açılması gerekir.     

### FLCU00 - Müşteri (FI) Rolü 

+ FLCU00, muhatabın **muhasebe (FI)** açısından müşteri olmasını sağlar.

+ Bu rolde girilen bilgiler:
  + Şirket kodu bazlı veriler (TR03)
  + Mutabakat hesabı
  + Ödeme koşulları
  + Vergi ve muhasebe ayarları
 
+ Bu rol sayesinde:
  + Satıştan doğan alacaklar muhasebeye yansır.
  + Fatura kesildiğinde FI kaydı oluşur.
  + Müşteri borç/alacak takibi yapılır.
 
+ Yani "Bu müşterinin muhasebe kayıtları nasıl tutulacak?" sorusu FLCU00 rolü ile cevaplanır.

### FLCU01 - Müşteri (SD) Rolü 

+ FLCU01, muhatabın **satış ve dağıtım (SD)** süreçlerinde müşteri olarak kullanılmasını sağlar.

+ Bu rolde girilen bilgiler:
  + Satış organizasyonu
  + Dağıtım kanalı
  + Bölüm (sales area)
  + Fiyatlandırma ayarları
  + Teslimat ve faturalandırma bilgileri
 
+ Bu rol sayesinde:
  + Satış siparişi (VA01) açılabilir.
  + Teslimat ve faturalama süreçleri başlatılabilir.
  + Fiyatlandırma ve vergi hesaplamaları çalışır.
 
+ Kısaca "Bu müşteriye hangi satış alanından, hangi koşullarla satış yapacağım?" sorusu cevaplanır.     

<br> 

:pushpin: **SAP'de Normal Mantık** 

| Kavram | Nerede Tanımlanır | 
| :--- | :--- |
| Müşteri | BP -> FLCU00 / FLCU01 | 
| Satıcı | BP -> FLVN00 / FLVN01 | 


---

+ Üst kısımda bulunan **Muhatap Rolleri** butonundan **FLCU01 - Müşteri (SD)** rolünü seçiyoruz.

<br> 

<img width="1020" height="614" alt="03_flcu01-musteri-sd" src="https://github.com/user-attachments/assets/8faa00e4-f536-4086-b42e-7b78e93a058e" />

<br> 

+ Ardından sağ üstte açılan **Satış ve Dağıtım** butonuna tıkladıktan sonra açılan ekranlarda gerekli bilgileri dolduruyoruz.  

<br> 

<img width="994" height="517" alt="042_flcu01-bilgiler-1" src="https://github.com/user-attachments/assets/4e1e0a93-c847-4331-ad7c-2308fc92501a" />

<br>
<br> 

<img width="1000" height="763" alt="04_flcu01-bilgiler-2" src="https://github.com/user-attachments/assets/3a3166b9-93bf-4823-8d5a-540151530737" />

<br> 

+ Gerekli bilgileri doldurduktan sonra bu sefer **FLCU00 - Müşteri (FI)** muhatap rolünü seçiyoruz.

<br> 

<img width="1011" height="646" alt="05_flcu00-müsteri-fi" src="https://github.com/user-attachments/assets/0dc9686b-48b3-43e8-8032-0ecd33483efc" />

<br> 

+ Rolü seçtikten sonra açılan **Şirket Kodu** butonuna basıyoruz. 

+ Açılan ekranda ve sekmelerinde gerekli bilgileri dolduruyoruz.

<br> 

<img width="1012" height="762" alt="06_flcu00-musteri-bilgiler" src="https://github.com/user-attachments/assets/77e03dfd-75c7-4827-9e08-4b75177a04d5" />

<br> 

+ Oluşturulan müşterinin kredi işlemleri bulunuyorsa muhatap rollerinden **UKM00 - SAP Kredi Yönetimi** rolünü seçebiliriz.

<img width="1018" height="613" alt="07_ukm000-kredi" src="https://github.com/user-attachments/assets/516fa924-71a0-4889-9a60-1e6f838658a8" />

+ Bu bölümden kredinin yöntemi, risk sınıfı, limit belirleme ve kredi bölümü seçme gibi işlemler gerçekleştirilir.


