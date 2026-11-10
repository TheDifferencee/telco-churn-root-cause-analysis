# telco-churn-root-cause-analysis


#  Telekom Müşteri Kaybı (Churn) Kök Neden Analizi ve Hipotez Testleri

IBM Telco Müşteri Kaybı veri seti üzerinde gerçekleştirilmiş; operasyonel aksaklıkları, fiyatlama baskılarını ve müşteri sadakat dinamiklerini ortaya koyan uçtan uca Keşifçi Veri Analizi (EDA) ve parametrik olmayan istatistiksel hipotez testi çalışması.

---

##  Temel Bulgular ve İstatistiksel Kanıtlar

| Etken Değişken | Kullanılan Test / Metrik | Temel Gözlem | İş Dünyası Çıkarımı |
| :--- | :--- | :--- | :--- |
| **Abonelik Süresi (`tenure`)** | Mann-Whitney U ($p < 0.001$) | Ayrılmalar ilk 1–5 ayda zirve yapıyor (Erken Dönem Terki) | En kritik elde tutma penceresi ilk 90 gündür |
| **Sözleşme Türü (`Contract`)** | Ki-Kare Testi ($\chi^2$, $p < 0.001$) | Aylık sözleşmede kayıp %42.7 iken 2 yıllıkta <%3 | Uzun vadeli taahhütler en güçlü müşteri kalkanıdır |
| **Aylık Fatura (`MonthlyCharges`)** | Mann-Whitney U ($p < 0.001$) | Terk edenlerin medyanı ~$79, kalanların ~$64 | Yüksek fiyat segmentindeki aboneler en yüksek kaçış riskine sahiptir |
| **Teknik Destek & Fiber Altyapı** | Ki-Kare Testi ($\chi^2$, $p < 0.001$) | Fiber kullananların %72'sinde teknik destek paketi yok | Destek almayan fiber abonelerinde kayıp %41.9'a ulaşıyor |

---

##  Kullanılan Teknolojiler ve Metodoloji

* **Veri İşleme ve Analiz:** Python, Pandas, NumPy
* **İstatistiksel Çıkarım:** SciPy (`stats.mannwhitneyu`, `stats.chi2_contingency`, `stats.shapiro`)
* **Veri Görselleştirme:** Seaborn, Matplotlib
