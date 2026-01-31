# Fiyatlandırma ve İndirimler 

"SAP, satış belgesinde hangi fiyata bakacağını *kural + arama mantığı* ile bulur."

---

## 1. Koşul Tablosu (Condition Table)

+ *"Fiyat hangi bilgilere göre farklılaşacak?"*

+ Örnekler:
  + Sadece Malzeme bazlı fiyat
  + Müşteri + Malzeme bazlı fiyat
  + Satış Org + Dağıtım Kanalı + Malzeme bazlı fiyat
 
+ Teknik olarak:
  + Koşul tablosu = **Anahtar alan seti**
 
+ Yani SAP'ye diyoruz ki: *"Fiyatı hesaplarken bu alanlara bak"*

<br> 

## 2. Erişim Sırası (Access Sequence) 

+ *"Bu fiyatı hangi sırayla arayayım?"*

+ Erişim sırası, **bir koşul türü** için SAP'nin **fiyatı arama sırasını** belirler.

+ Mantık: SAP fiyatı **en spesifikten en genele** doğru arar.

+ Örnek erişim sırası:
  + 1. Müşteri + Malzeme
    2. Müşteri
    3. Malzeme
    4. Genel Fiyat
   
+ SAP ne yapar ?
  + 1. tabloda fiyat bulamazsa
    2. tabloya geçer
  + Orada bulursa durur
 
+ 📌 **Bulunca durur, devam etmez.**

<br> 

## 3. Koşul Türü (Condition Type) 

+ *"Bu neyin fiyatı / indirimi / vergisi?"* 

+ Koşul türü, fiyatlandırmanın **anlamını** belirler.

+ Örnek koşul türleri:

| Koşul Türü | Anlamı | 
| :--- | :--- | 
| PR00 | Liste fiyat | 
| K004 | Malzeme indirimi | 
| K007 | Müşteri indirimi | 
| MWST | KDV |
| KF00 | Taşıma bedeli | 

+ Koşul türü şu alanları belirler:
  + Artı mı eksi mi ?
  + Yüzde mi tutar mı ?
  + Erişim sırası var mı ?
  + Manuel girilebilir mi ?
  + İstatistik mi ?
 
+ Koşul türü = **Fiyatın karakteri**

<br> 

## 4. Hesaplama Şeması (Pricing Procedure) 

+ *"Fiyat hangi adımlarla hesaplanacak?"*

+ Hesaplama şeması, **fiyatlandırmanın ana aklıdır**.

+ İçinde:
  + Hangi koşul türler var
  + Hangi sırayla çalışacaklar
  + Toplama/çıkarma nasıl olacak
 
+ Örnek şema akışı:
  + 1. PR00 -> Liste fiyat
    2. K004 -> Malzeme indirimi
    3. K007 -> Müşteri indirimi
    4. Net fiyat
    5. MWST -> KDV
    6. Brüt Fiyat

+ 📌 Satış belgesi yaratıldığında SAP şunu sorar:
  + "Bu müşteri + bu satış org için hangi hesaplama şemasını kullanacağım?"
 
<br> 

## 5. Koşul Kaydı (Condition Record) 

+ *"Somut fiyat ne?"*

+ Koşul kaydı, **gerçek fiyatın girildiği yer**dir.

+ Örnek:
  + Malzeme: M-100
  + Müşteri: STECH
  + Fiyat: 1000 EUR
 
+ Bu kayıt VK11 / VK12 / VK13 ile girilir.

+ 📌 Diğer her şey kuraldır, para burada girilir.


## Satış Belgesi Yaratıldığında SAP Ne Yapar ? 

+ 1. **Hesaplama şemasını** bulur.
  + "Hangi koşul türleri var?"
 
+ 2. Her **koşul türü** için:
  + Erişim sırasına bakar
  + Koşul tablolarını sırayla denetler
 
+ 3. Uygun **koşul kaydını** bulursa:
  + Fiyatı alır
  + Hesaplamaya dahil eder   

<br> 

| Tablo | İfadesi |  
| :--- | :--- | 
| Koşul tablosu | "NEYE göre" | 
| Erişim sırası | "HANGİ" sırayla | 
| Koşul türü | "NE tür fiyat" | 
| Hesaplama şeması | "NASIL hesaplanacak" | 
| Koşul kaydı | "KAÇ para" | 

---

# Önemli Koşul İşlem Kodları 

| İşlem Kodu | Açıklama | 
| :--- | :--- | 
| VK11 | Koşul yarat | 
| VK12 | Koşul değiştir |
| VK13 | Koşul görüntüle | 
| VK14 | Referans ile koşul yarat |
| V/LD | Koşul listesi yürüt | 
| TK11 | Koşul yaratılması (navlun giderleri) | 
| TK12 | Koşulun değiştirilmesi (navlun giderleri) | 
| TK13 | Koşulun görüntülenmesi (navlun giderleri) | 
| VBN1 | Bedelsiz ürünler - Yarat | 
| VBN2 | Bedelsiz ürünler - Değiştir | 
| VBN3 | Bedelsiz ürünler - Görüntüle | 

# Önemli Koşul Tablolar 

| Tablo | Açıklama | 
| :--- | :--- | 
| KONV | Koşullar (işlem verileri) |
| KONP | Koşullar (kalem) | 
| KOND | Koşullar (veriler) | 
| KONH | Koşullar (başlık) | 
| KONM | Koşullar (tek boyutlu miktar ölçeği) | 
| A000 | Fiyatlandırma için koşul tablosu | 

---

---

# VK11 ile PR00 Koşul Kaydı Oluşturma 

+ Yapılacak işlemlerle birlikte **VK11 işlem kodu** kullanılarak **PR00 (Liste Fiyatı)** koşul kaydının nasıl ve neden oluşturulduğu adım adım açıklanacaktır.

+ Amaç; satış belgelerinde (VA01) malzeme fiyatının **otomatik olarak gelmesini sağlamak** ve fiyatlandırma mantığını doğru şekilde kurmaktır.

+ Bu çalışmada VK11 ile **STECH firmasına ait bir malzeme için liste fiyatı (PR00) tanımlandı**.

## Neden PR00 Koşul Türü ? 

+ VK11 işlem koduna girildiğinde ilk olarak **Koşul Türü** sorulur.

+ **PR00**, standart **liste fiyatı** koşul türüdür.
  + Fiyatlandırma şemasının temelidir.
  + İndirimler, vergiler ve ek masraflar genellikle PR00 üzerinden hesaplanır.
 
+ Mantık: *"Bu malzemenin satıştaki temel fiyatını tanımlıyorum."*

<br> 

<img width="750" height="438" alt="01_VK11-01" src="https://github.com/user-attachments/assets/aa33b918-fe3c-42da-83f8-79011a472e9a" />

+ PR00 koşul türü seçildikten sonra SAP, tanımlı **koşul tablolarını** listeler.

+ Eğitim sunucusunda üç farklı koşul tablosu seçeneği görüntülenmiştir.

+ **1. Müşteri/malzeme (onay durumu ile)**
  + Aynı malzeme, farklı müşterilere farklı fiyat
  + Müşteri bazlı özel fiyatlar için kullanılır
 
+ **2. Fiyat listesi tipi/para birimi/malzeme (onay durumu ile)**
  + Temel fiyatı, fiyat listesi tipi - para birimi - malzeme kombinasyonu ile yönetebiliriz.
 
+ **3. Malzeme (onay durumu ile)**
  + Fiyat **sadece malzemeye bağlıdır**
  + Malzemenin onay durumuna göre kontrol yapılır
 
+ Bu senaryoda amaç: *"STECH Akıllı Sensör için genel bir liste fiyatı tanımlamak"*

+ Bu nedenle **Malzeme (onay durumu ile) seçilmiştir.

<br> 

<img width="1131" height="289" alt="02_VK11-02" src="https://github.com/user-attachments/assets/b386cdd2-6d82-4b06-9878-6026d00b7449" />

+ Seçim yapıldıktan sonra **Koşul Kaydı Girişi** ekranı açılır.

+ Girilen alanlar:
  + Satış Organizasyonu: Z113
  + Dağıtım Kanalı: 10
  + Malzeme: 1056 - STECH Akıllı Sensör
 
📌 Bu alanlar **koşul tablosunun anahtarıdır**.

+ SAP bu kombinasyonu satış belgesinde gördüğünde ilgili fiyatı arar.

+ *"1056 numaralı STECH Akıllı Sensör'ün 1 adet liste fiyatı = 1250 TRY'dir."*

<br> 

<img width="740" height="423" alt="03_VK11-03" src="https://github.com/user-attachments/assets/48d54c1c-26f6-4bd4-9f71-ebd009e70548" />

+ Bilgileri girip enter tuşuna bastıktan sonra, fiyat satırı üzerinde **malzeme satırına çift tıklandığında**, **ölçek (scale)** ekranı açılır.

+ Ölçek:
  + Miktara bağlı fiyat farklılaştırmasıdır
  + Toplu alım indirimleri bu yapı ile tanımlanır
 
+ Ölçek ile akıllı sensörden 10 tane alınması durumunda fiyatın 1,150 TRY fiyatına düşeceği belirlenmiştir.

+ Önceki ekrana gelip koşul kaydı kaydedilir ve aktif hale gelmiş olur.

## Genel Özet 

+ Bu çalışmada:
  + VK11 ile **PR00 liste fiyatı** tanımlandı
  + Fiyat **malzeme bazında** oluşturuldu
  + Satış organizasyonu ve dağıtım kanalı ile ilişkilendirildi
  + Geçerlilik tarihleri belirlendi
  + Satış belgelerinde otomatik fiyat gelmesi sağlandı
 
+ Sonuç olarak:  
  + **STECH firmasına ait 1056 numaralı malzeme için SD fiyatlandırma altyapısı kurulmuştur**.  












