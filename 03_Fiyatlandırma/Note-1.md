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
 
+ Yani SAP'ye diyoruz ki: *"Fiyatı hesaplarken bu alanlara bak"

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
 
+ 📌 **Bulunca durur, devam etmez

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













