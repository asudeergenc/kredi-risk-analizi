\# Kredi Risk Analizi ve Dashboard



Müşterilerin 2 yıl içinde kredisini geri ödememe (temerrüt) ihtimalini tahmin eden ve sonuçları Power BI dashboard'unda gösteren bir bankacılık odaklı veri analizi projesi.



!\[Dashboard](dashboard/dashboard.png)



\## Veri Seti

Kaggle "Give Me Some Credit" veri seti (cs-training.csv). Ham veri Kaggle'a ait olduğu için bu depoda yer almaz. Temizlenmiş hali `data/cs-training-clean.csv` dosyasındadır.



\## Yapılanlar

1\. \*\*Veri temizleme ve keşif (EDA):\*\* Eksik gelir ve bağımlı sayısı değerleri medyan ile dolduruldu, eksik gelir için işaretleyici sütun eklendi, 18 yaş altı ve hatalı kodlu (96/98) satırlar çıkarıldı, uç değerler 99. yüzdelikte kırpıldı. Temizlik sonrası 149.730 satır kaldı.

2\. \*\*Modelleme:\*\* İki model karşılaştırıldı.

&#x20;  - Lojistik Regresyon (temel model): ROC-AUC 0,848

&#x20;  - HistGradientBoosting: ROC-AUC 0,858 (daha başarılı)

3\. \*\*Risk grupları:\*\* Model olasılıkları Düşük, Orta ve Yüksek risk gruplarına ayrıldı.

4\. \*\*Dashboard:\*\* Sonuçlar Power BI ile görselleştirildi.



\## Bulgular

\- Test setinde 29.946 müşteri var, genel temerrüt oranı %6,60.

\- Gerçek temerrüt oranı risk grubuna göre: Düşük %1,3, Orta %6,2, Yüksek %26. Model, riskli müşterileri ayırt edebiliyor.

\- Temerrüt oranı yaşla birlikte düşüyor: 30 yaş ve altında %11,35, 60 yaş üstünde %3,00.



\## Proje Yapısı

\- `notebooks/01\_eda.ipynb`: veri temizleme ve keşif

\- `02\_modelleme.ipynb`: modelleme

\- `data/`: temizlenmiş veri ve model sonuçları

\- `dashboard/`: Power BI dosyası ve ekran görüntüsü



\## Kullanılan Araçlar

Python (pandas, scikit-learn), Jupyter Notebook, Power BI, Git/GitHub

