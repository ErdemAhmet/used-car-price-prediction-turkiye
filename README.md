# Türkiye İkinci El Araç Fiyat Tahmini

Türkiye'deki ikinci el araç ilanlarının özelliklerinden ilan fiyatını tahmin etmeyi amaçlayan bir makine öğrenmesi ders projesi. Veri temizleme, keşif, model eğitimi ve değerlendirme adımları Jupyter Notebook içinde yer alır.

[![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-Gradient%20Boosting-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)

## Proje hakkında

Bu çalışmada `GradientBoostingRegressor` kullanılarak araç fiyatı tahmini yapılır. Notebook; fiyat ve kilometre alanlarını sayısallaştırır, eksik değerleri kaldırır, fiyat uç değerlerini IQR yöntemiyle filtreler, kategorik alanları `LabelEncoder` ile dönüştürür ve veriyi eğitim/test kümelerine ayırır.

### Kayıtlı notebook sonuçları

| Metrik | Değer |
| --- | ---: |
| R² | 0,951 |
| MAE | 58.003 TL |
| RMSE | 82.105 TL |

Bu değerler notebook'a kaydedilmiş son çalıştırmanın çıktılarıdır. Notebook yeniden çalıştırıldığında veri veya paket sürümlerine bağlı olarak sonuçlar değişebilir. 

## Depo içeriği

| Dosya | Açıklama |
| --- | --- |
| `Used_Car_Price_Prediction.ipynb` | Veri hazırlama, modelleme ve görselleştirme adımları |
| `araba.csv` | Notebook'un kullandığı araç ilanı verisi |
| `requirements.txt` | Python paketleri |


## Çalıştırma

Python 3.9 veya üzeri ve Jupyter gerekir. Depoyu klonladıktan sonra proje klasöründe:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
jupyter notebook Used_Car_Price_Prediction.ipynb
```

macOS veya Linux:

```bash
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook Used_Car_Price_Prediction.ipynb
```

Notebook hücrelerini sırayla çalıştırın. `araba.csv` dosyası notebook ile aynı dizinde olmalıdır.

## Google Colab

Projenin Colab sürümü: [Notebook'u Google Colab'de aç](https://colab.research.google.com/drive/1P86bA6mJVU4T4YZBiXxTqIwCRN1YWeOW?usp=sharing).

Colab'de çalıştırmak için `araba.csv` dosyasını oturumun dosyalar bölümüne yükleyin.

## Veri kaynağı

Veri seti: [Used Car Price 2025 Turkiye All Brands — Kaggle](https://www.kaggle.com/datasets/aiwithcagri/used-car-price-2025-turkiye-all-brands).

Veri setinin lisans ve yeniden dağıtım koşullarını Kaggle kaynak sayfasından kontrol edin. Depoda ayrı bir veri lisansı tanımlanmamıştır.

## Sınırlamalar

- Veri, ilan fiyatlarını içerir; gerçekleşmiş satış fiyatlarını temsil ettiği garanti edilmez.
- Kategorik sütunlar veri bölünmeden önce tüm veri üzerinde kodlandığı için değerlendirmede veri sızıntısı riski vardır. Daha sağlam bir akış için kodlayıcıları eğitim verisine yalnızca `fit` eden bir `Pipeline`/`ColumnTransformer` kullanılabilir.
- Tek bir eğitim/test bölmesi ve tek model kullanılmıştır; sonuçlar farklı bölmelerde değişebilir.
- Bu proje eğitim amaçlıdır ve gerçek araç alım satımında tek başına fiyat belirleme aracı olarak değerlendirilmemelidir.

## Lisans

Bu depodaki kaynak kod için ayrıca bir yazılım lisansı belirtilmemiştir. Yeniden kullanım için veri setinin Kaggle koşullarını ve kaynak kod sahibinden alınması gereken izinleri kontrol edin.
