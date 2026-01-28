# 🏦 BDDK Verileriyle Türk Bankacılık Sektörü Finansal Analiz Otomasyonu

Bu proje, **BDDK (Bankacılık Düzenleme ve Denetleme Kurumu)** tarafından yayınlanan resmi mizan verilerini kullanarak; kümülatif finansal tabloları otomatik olarak aylık performans verilerine dönüştüren, risk metriklerini hesaplayan ve interaktif raporlar sunan uçtan uca bir **Veri Hattı (Data Pipeline)** çalışmasıdır.
<img width="1303" height="730" alt="image" src="https://github.com/user-attachments/assets/48f98d25-f81a-496d-b0ee-a4839916a3fc" />
<img width="1283" height="717" alt="image" src="https://github.com/user-attachments/assets/ce2ba205-128c-4a2e-8f81-e034d6da92a6" />




## 🎯 Proje Amacı ve Otomasyon Mantığı
Bankacılık sektöründe veriler genellikle yıl başından itibaren toplanarak (kümülatif) yayınlanır. Bu proje, manuel hesaplama süreçlerini ortadan kaldırarak şu katma değerleri sağlar:
* **Toplu Veri İşleme:** 35+ farklı Excel dosyasını (mizanı) `glob` ve `regex` otomasyonu ile saniyeler içinde tarar.
* **Akıllı Dönüşüm:** Kümülatif rakamlardan `diff()` ve `fillna()` algoritmalarıyla "Gerçek Aylık" kâr/zarar ve performans verilerini türetir.
* **Gelişmiş Analitik:** SQL üzerinde **Window Functions** kullanarak büyüme oranlarını, hareketli ortalamaları ve risk ağırlıklarını otomatik hesaplar.

---

## 🛠 Teknik Yetenekler (Technical Stack)

| Aşama | Kullanılan Araçlar | Uygulanan Teknikler |
| :--- | :--- | :--- |
| **ETL (Veri İşleme)** | Python (Pandas) | Regex ile dosya ayıklama, Glob otomasyonu, Veri temizleme. |
| **İleri Analitik** | SQL Server (T-SQL) | Window Functions, **Reporting Views (BI Entegrasyonu)**, Pareto Analizi. |
| **Görselleştirme** | Power BI | Dinamik KPI Dashboards, Trend Takibi, Hareketli Ortalamalar. |

---

## 🚀 Kullanım Rehberi (Tak-Çalıştır / Plug-and-Play)

Bu proje, karmaşık kurulum ve yapılandırma süreçlerini ortadan kaldıran **"Plug-and-Play"** mimarisiyle tasarlanmıştır.

1.  **Veri Hazırlığı ve Yerleşimi:** Analizde kullanılan **ham BDDK mizan verileri, notebook dosyalarıyla aynı dizinde hazır olarak sunulmuştur.** Ayrıca kendi verilerinizi eklemek isterseniz, Excel dosyalarını ana dizine kopyalamanız yeterlidir.
    * **Kritik Not:** Kod yapısı `path = "."` (mevcut dizin) olarak kurgulandığı için veriler ve notebooklar aynı klasörde olduğu sürece sistem dosyaları otomatik olarak tanır. Ek bir dosya yolu düzenlemesine gerek kalmadan analizler doğrudan başlatılabilir.
2.  **Python ETL Süreci:** `faz1.ipynb` dosyasından başlayarak sırasıyla notebook'ları çalıştırın. Bu otomasyon süreci sonunda tüm verileriniz konsolide edilerek `Proje_Final_Master_Data.xlsx` dosyanız otomatik olarak oluşturulacaktır.
3.  **SQL Analitik Katmanı:** Oluşan master veriyi SQL Server tablonuza aktarın ve `Banka_Finansal_Analiz_Projesi.sql` script'ini çalıştırın. 
    * **Reporting Views:** SQL içerisinde Power BI için optimize edilmiş özel görünümler (Views) oluşturulur. Bu sayede hesaplama yükü veritabanı seviyesinde tutularak rapor performansı maksimize edilir.
4.  **Power BI Dashboard:** `BANKA PROJESİ RAPORU.pbix` dosyasını açarak SQL veritabanınıza bağlayın. Tüm hesaplanan metrikler dashboard üzerinde anlık olarak güncellenecektir.

---

## 📂 Proje Hiyerarşisi
* **`/Notebooks`**: Veri madenciliği ve kümülatiften aylığa geçiş motorları (`faz1.ipynb`, `faz2.ipynb`, `faz3.ipynb`, `merge.ipynb`).
* **`/SQL`**: Analitik sorgular ve **Power BI Reporting Views** (`Banka_Finansal_Analiz_Projesi.sql`).
* **`/Reports`**: Karar vericiler için hazırlanan interaktif dashboard (`BANKA PROJESİ RAPORU.pbix`).
* **`Proje_Final_Master_Data.xlsx`**: Tüm süreçlerin sonunda oluşan, analize hazır nihai veri seti.



---

## 📈 Öne Çıkan Analitik Göstergeler
1. **Net Faiz Marjı (NIM):** Aylık faiz gelir/gider dengesinin takibi.
2. **Operasyonel Yük Analizi:** Diğer risklerin kârlılık üzerindeki baskısının ölçülmesi.
3. **Pareto (80/20) Sınıflandırması:** Toplam kârın %80'ini getiren "Yıldız Ay"ların SQL ile tespiti.
4. **3 Aylık Hareketli Ortalama:** Mevsimsellikten arındırılmış finansal trend takibi.

---

### 
Bu proje, manuel finansal süreçlerin otomasyonu üzerine geliştirilmiş bir portfolyo çalışmasıdır.

