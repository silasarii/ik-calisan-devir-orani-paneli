# İK & Çalışan Devir Oranı (Turnover) Paneli

Bu proje, bir şirketin insan kaynakları verilerini, çalışan sirkülasyonunu, devir hızını ve departman bazlı iş gücü dağılımını analiz etmek amacıyla Power BI ile uçtan uca geliştirilmiş etkileşimli bir analitik panelidir.

---

## 🎯 Proje Hedefleri & İş Soruları

* **İş Gücü Durumu:** Toplam aktif çalışan sayısı ve dönem içinde işten ayrılan çalışan sayısı ne seviyede?
* **Personel Devir Hızı:** Şirketin genel turnover (devir hızı) oranı nedir ve aylık bazda nasıl bir seyir izlemektedir?
* **Zaman Serisi & Trend:** Personel devir hızı yıl içinde hangi dönemlerde (örneğin yıl sonu veya belirli aylarda) ani dalgalanmalar veya zirveler göstermektedir?
* **Departman Kırılımı:** Hangi departmanlar en yüksek aktif çalışan hacmine ve yoğunluğuna sahiptir?

---

## 🛠️ Teknik Yetkinlikler & Yöntem

* **Power Query (ETL & Veri Temizleme):**
  * Tüm veri setine yönelik detaylı veri hazırlığı ve veri tipi düzenlemeleri yapıldı.
  * Eksik veya hatalı değerler kontrol edilerek analiz için en uygun formata getirildi.

* **Veri Modelleme (Star Schema Mantığı):**
  * Merkezde Fact tablosu (`Çalışan Aylık Durumları`), etrafında ise Dimension tabloları (`Çalışan Bilgileri`, `Departmanlar`, `Tarih`) olacak şekilde optimize edilmiş bir Star Schema kurgulandı.
  * Tablolar arasında 1:* (Bire Çok) ilişkiler kuruldu.

* **DAX & Ölçü Mimarisi (Measure Branching):**
  * Tüm temel hesaplamalar düzen ve sürdürülebilirlik için ayrı bir **Ölçüler** tablosunda toplandı:
    * `Aktif Çalışan Sayısı`
    * `İşten Ayrılan Çalışan Sayısı`
    * `Personel Devir Hızı % = DIVIDE([İşten Ayrılan Çalışan Sayısı], [Aktif Çalışan Sayısı], 0)`
    * `Ortalama Performans = AVERAGE('Çalışan Aylık Durumları'[Performans Puanı])`

* **Görselleştirme & Dashboard Mimarisi:**
  * Üst alanda kritik metrikleri özetleyen 4 adet profesyonel KPI kartı konumlandırıldı.
  * Zamansal değişimi takip etmek için aylık trendi gösteren çizgi grafik ve büyükten küçüğe sıralı departman dağılım sütun grafiği kullanıldı.

---

## 💡 Öne Çıkan Analitik Çıkarımlar

* **Devir Hızı Trendi:** Yıl içerisinde personel devir hızının belirli aylar itibarıyla (özellikle yıl sonuna doğru) belirgin dalgalanmalar ve zirveler yaşadığı görülmektedir.
* **Departman Yoğunluğu:** Aktif çalışan sayısının departmanlar bazında dağılımında Finans ve Pazarlama ön planda yer alırken, tüm departmanlar dengeli bir kurumsal dağılım sergilemektedir.

---

## Kullanılan Teknolojiler
* **İş Zekası & Görselleştirme:** Microsoft Power BI Desktop
* **Veri Hazırlığı & Modelleme:** Power Query, DAX, Star Schema
* **Veri Kaynakları:** Microsoft Excel / İlişkisel Veri Setleri
---

## Proje Yapısı

```text
├── assets/
│   └── dashboard.png               
├── data/
│   ├── calisan_aylik_durumlari.xlsx                   
│   ├── calisan_bilgileri.xlsx                   
│   ├── departmanlar.xlsx                   
│   └── tarih.xlsx                   
├── ik_calisan_devir_orani_paneli.pbix          
└── README.md

```

<div align="center">

### 👤 Sıla Sarı
🎓 **Dokuz Eylül Üniversitesi - Ekonometri**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sıla-sarı)
