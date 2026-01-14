# Organizasyonel Yapı 

**1. Şirket Kodu (Company Code)**
  - Mali muhasebenin en küçük birimidir.
  
  - Kendi başına bilanço ve kar/zarar tablosu üretebilen yasal bir işletmeyi temsil eder.
 
  - SD modülündeki satış işlemleri, finansal boyut için mutlaka bir şirket koduna bağlanır. 

**2. Satış Organizasyonu (Sales Organization)**
  - Ürün ve hizmetlerin satışından, yasal sorumluluğundan ve fiyatlandırılmasından sorumlu olan en üst düzey SD birimidir.

  - Bir şirket koduna birden fazla satış organizasyonu bağlanabilir. 

**3. Dağıtım Kanalı (Distribution Channel)**

  - Ürünlerin veya hizmetlerin müşteriye ulaşma yoludur.

  - Örn: Toptan satış, Perakende satış, İnternet satışı

**4. Bölüm (Division)**
  - Ürün gruplarını veya hizmet kategorilerini temsil eder.

  - Örneğin bir teknoloji şirketinde donanım ve yazılım iki ayrı bölüm olabilir.

  - Müşteri bazlı özel anlaşmalar genellikle bölüm bazında yapılır.

**5. Satış Bürosu (Sales Office)**

  - Satış bürosu bünyesinde çalışan, belirli ürünlerden veya müşteri segmentlerinden sorumlu personel grubudur.

  - Performans takibi ve raporlama için kullanılır.


**6. Müşteri Grubu (Customer Group)** 

  - Müşterileri benzer özelliklerine göre sınıflandırmak için kullanılır.

  - Örneğin "Zincir Marketler", "Küçük Esnaf" veya "Kamu Kurumları".

  - Bu sınıflandırma genellikle raporlama ve özel indirim tanımlamak için kritiktir.

:pushpin: Bu yapıda **Satış Organizasyonu + Dağıtım Kanalı + Bölüm** üçlüsü bir araya gelerek **"Satış Alanı" (Sales Area)** denen kavramı oluşturur ki bu, SD modülünün kalbidir. 


---

# Satış Organizasyonu Oluşturma - SPRO 

<img width="658" height="408" alt="spro-1" src="https://github.com/user-attachments/assets/8748152d-11ca-41ff-bb9a-ab3e495f56f7" />

+ **SPRO** işlem koduna girilir ve sol üstte bulunan **SAP referans IMG** butonuna basılır.

---

<img width="696" height="580" alt="spro-2" src="https://github.com/user-attachments/assets/cd3beba0-193a-4af5-9b41-85a5beadf1d8" />

+ Burada İşletme Yapısı -> Tanım -> Satış ve Dağıtım -> Satış org. tanımlanması yolu izlenir.

---

<img width="1032" height="556" alt="spro-3" src="https://github.com/user-attachments/assets/55465b68-1058-479a-8108-8395fa1ce8de" />

+ Çıkan ekranda ilk seçenek seçilir.

--- 

<img width="1171" height="760" alt="spro-4" src="https://github.com/user-attachments/assets/07c4365d-a974-4513-bba5-c9c9963ff705" />

+ Eğitim sunucumda bulunan 1000 kodlu organizasyon kopyalanıp ekrandaki bilgilerle değiştirilerek **Z113** kodlu **STECH Domestic Sales** satış organizasyonu oluşturulmuştur.

---
---

# Dağıtım Kanalı Oluşturma - SPRO

<img width="1117" height="598" alt="dagitim-kanali-1" src="https://github.com/user-attachments/assets/bd0e0cd9-22ed-4eea-8a7d-aa966c6160df" />

+ Burada İşletme Yapısı -> Tanım -> Satış ve Dağıtım -> Dağıtım kanalı tanımlanması yolu izlenerek çıkan ekranda ilk seçenek seçilir. 

---

<img width="591" height="584" alt="dagitim-kanali-2" src="https://github.com/user-attachments/assets/046bc578-d53a-4ca9-8c53-d8df39cb3e58" />

+ Eğitim sunucumda bulunan ve klasik tanımlama ile tanımlanmış **10** kodlu **Yurtiçi dağıtım** kanalı kullanılacaktır.

+ Yeni bir kanal oluşturmak için sol üstte bulunan **yeni giriş** butonu kullanılabilir.

---
---

# Bölüm Tanımlama 

<img width="1139" height="624" alt="bolum-1" src="https://github.com/user-attachments/assets/5b308774-04dc-497e-bcc2-77d16422eb23" />

+ Burada İşletme Yapısı -> Tanım -> Genel Lojistik -> Bölüm tanımlanması yolu izlenerek çıkan ekranda ilk seçenek seçilir.

---

<img width="520" height="340" alt="bolum-2" src="https://github.com/user-attachments/assets/f123a96c-4c99-4cdf-ab7b-4350a745839e" />

+ İlgili bilgiler doldurularak **14** kodlu **Tech Products** bölümü oluşturulmuştur. 

---
---

# Tayin İşlemleri 

## Satış Organizasyonuna Şirket Kodunu Ata 

<img width="539" height="625" alt="01_satis org - sirket kodu" src="https://github.com/user-attachments/assets/6a2cf2e7-9a31-44ca-959a-22ab14f398ca" />

+ Burada İşletme Yapısı -> Tayin -> Satış ve Dağıtım -> Şirket koduna satış organizasyonu tayini yolu seçilir.

---

<img width="683" height="327" alt="02_satis org - sirket kodu-atama" src="https://github.com/user-attachments/assets/de4b3442-86f6-4a85-89c2-41b42bf47bde" />

+ Eğitim sunucumda kullanılan şirket kodu **TR03** satış organizasyonuna atanır. 

<br> 

## Satış Organizasyonunu Dağıtım Kanalına Atama 

<img width="572" height="340" alt="03_satis-org-dagitim-kanali" src="https://github.com/user-attachments/assets/633996c2-b540-4eeb-9713-46becae367bb" />

+ İşletme Yapısı -> Tayin -> Satış ve Dağıtım -> Satış organizasyonuna dağıtım kanalı tayini yolu izlenir ve **yeni giriş** butonu kullanılır. 

---

<img width="686" height="315" alt="04_satis-org-dagitim-kanali-2" src="https://github.com/user-attachments/assets/dee98d70-6a6b-4247-877d-7672865c5824" />

+ Satış organizasyonu (Z113), Yurtiçi Dağıtım Kanalına (10) bağlanır.

---

<img width="677" height="326" alt="05_satis-org-dagitim-kanali-3" src="https://github.com/user-attachments/assets/4f1a05ba-d4ea-4879-b2b4-a0a8ffa38f4f" />

<br>

## Satış Organizasyonunu Bölüme Atama 

<img width="540" height="516" alt="06_satis-org-bolum" src="https://github.com/user-attachments/assets/4d74e45e-04dd-4876-b08c-6aa385ace5d4" />

+ Burada İşletme Yapısı -> Tayin -> Satış ve Dağıtım -> Satış organizasyonuna bölüm tayini yolu izlenerek **yeni giriş** butonuna basılır.

---

<img width="678" height="186" alt="07_satis-org-bolum-2" src="https://github.com/user-attachments/assets/d9c02113-eb47-428a-bdcd-94a920a18ebb" />

+ Satış Organizasyonu (Z113), Bölüme (14) bağlanır.

--- 

<img width="647" height="210" alt="08_satis-org-bolum-3" src="https://github.com/user-attachments/assets/df8ba818-5633-445e-a3eb-b0f7fbf6d93d" />

<br>

## Satış Organizasyonunu SD Alanına Bağla 

<img width="529" height="339" alt="09_satis-org-sd-alani" src="https://github.com/user-attachments/assets/93e4bb9f-e6fc-41d5-bf4b-108a987ae5be" />

+ Burada İşletme Yapısı -> Tayin -> Satış ve Dağıtım -> SD Alanının Oluşturulması yolu izlenir ve **yeni giriş** butonuna basılır.

---

<img width="881" height="213" alt="10_satis-org-sd-alani-2" src="https://github.com/user-attachments/assets/2db25369-128a-405e-8d2d-617cf7bad043" />

+ Daha önceden oluşturulan satış organizasyonu, dağıtım kanalı ve bölüm kodları sırayla girilir.

---

<img width="874" height="391" alt="11_satis-org-sd-alani-3" src="https://github.com/user-attachments/assets/a9184c9e-c745-43ea-bdc6-74bd2da771ef" />

<br>

## Üretim Yeri Tayini 

<img width="579" height="337" alt="12_uretim-yeri-tayin" src="https://github.com/user-attachments/assets/8c6bd557-96c4-40c1-9016-2f21c7e3b5c1" />

+ Burada İşletme Yapısı -> Tayin -> Satış ve Dağıtım -> Üretim yeri tayin et yolu izlenerek **yeni giriş** butonuna basılır.

---

<img width="967" height="210" alt="13_uretim-yeri-tayin-2" src="https://github.com/user-attachments/assets/7de828f3-a77c-4ab2-901a-bf120c6cd0c8" />

+ Satış organizasyonu, dağıtım kanalı ve eğitim sunucumda kullanılan **ZAKD** üretim yeri bilgileri girilir.

---

<img width="984" height="232" alt="14_uretim-yeri-tayin-3" src="https://github.com/user-attachments/assets/25175939-490f-4f7c-ba37-0172ac822071" />





