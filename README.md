#  Çoklu Doğrusal Regresyon — Girişim Kârını Tahmin Etme

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Model-Doğrusal_Regresyon-blue?style=flat-square" alt="Model" />
  <img src="https://img.shields.io/badge/Lisans-MIT-lightgrey?style=flat-square" alt="Lisans" />
</p>

---

## 📌 Proje Hakkında

> **Amaç:** Bir girişimin harcamalarına ve konumuna dayanarak elde edeceği **karı** tahmin etmek.

Bu proje, **`Startups.csv`** veri seti üzerinde bir **Çoklu Doğrusal Regresyon** modeli kurar. Dört bağımsız değişken — *AR-GE Harcaması*, *Yönetim Harcaması*, *Pazarlama Harcaması* ve *Eyalet* — kullanılarak, model iş yatırımları ile ortaya çıkan **Kar** arasındaki ilişkiyi öğrenir.

İş akışı, eksiksiz bir makine öğrenmesi hattını kapsar:

- 📊 **Veri yükleme ve keşfi** — dağılımların ve öznitelik–hedef ilişkilerinin anlaşılması.
- 🔤 **Kategorik kodlama** — `State` (Eyalet) sütununun **One-Hot Encoding** ile sayısal forma dönüştürülmesi.
- ✂️ **Eğitim/Test ayrımı** — genellemeyi dürüstçe değerlendirmek için verinin ayrılması.
- 🤖 **Model eğitimi** — bir `LinearRegression` tahmincisinin eğitilmesi.
- 📈 **Değerlendirme** — performansın **R-Kare** ve **Ortalama Kareli Hata (MSE)** ile ölçülmesi.

---

## 📂 Veri Seti

Veri seti (**`Startups.csv`**), farklı girişimleri tanımlayan kayıtlar içerir. Her satır, şirketin üç kategorideki harcamalarını, faaliyet gösterdiği eyaleti ve elde ettiği karı barındırır.

| Sütun               | Tip         | Açıklama                                                     |
| :------------------ | :---------- | :----------------------------------------------------------- |
| 🧪 **R&D Spend**       | `float`     | Araştırma & Geliştirme'ye yatırılan tutar.                   |
| 🏢 **Administration**  | `float`     | Yönetim operasyonlarına harcanan tutar.                      |
| 📣 **Marketing Spend** | `float`     | Pazarlama ve reklama harcanan tutar.                         |
| 📍 **State**           | `category`  | Girişimin faaliyet gösterdiği ABD eyaleti *(New York, California, Florida)*. |
| 💰 **Profit**          | `float`     | **Hedef değişken** — girişimin elde ettiği kar.              |

> 💡 **Not:** `Profit` (Kar) tahmin etmek istediğimiz bağımlı değişkendir; kalan dört sütun ise bağımsız (tahmin edici) değişkenlerdir.

---

## 🛠️ Kullanılan Teknolojiler

| Teknoloji        | Amaç                                                 |
| :--------------- | :--------------------------------------------------- |
| 🐍 **Python**       | Temel programlama dili.                              |
| 🐼 **Pandas**       | Veri yükleme, inceleme ve işleme.                    |
| 🔢 **NumPy**        | Sayısal işlemler ve dizi yönetimi.                   |
| 🤖 **Scikit-Learn** | Kodlama, eğitim/test ayrımı, modelleme ve metrikler. |
| 📓 **Jupyter**      | Etkileşimli geliştirme ve analiz not defteri.        |

---

## ⚙️ Nasıl Çalıştırılır

Sonuçları yerel olarak yeniden üretmek için bu adımları izleyin.

**1️⃣ Depoyu klonlayın**

```bash
git clone https://github.com/<your-username>/multiple_linear_regression.git
cd multiple_linear_regression
```

**2️⃣ (İsteğe bağlı) Bir sanal ortam oluşturun ve etkinleştirin**

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

**3️⃣ Bağımlılıkları yükleyin**

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

**4️⃣ Not defterini başlatın**

```bash
jupyter notebook multiple_linear_regressions.ipynb
```

> ▶️ Veriyi yüklemek, modeli eğitmek ve değerlendirme metriklerini görmek için hücreleri yukarıdan aşağıya doğru çalıştırın.

---

## 🔬 Model Performansı & Sonuçlar

Model, verinin bir bölümü üzerinde eğitildi ve görülmemiş test seti üzerinde değerlendirildi. Performans, aşağıdaki metrikler aracılığıyla raporlanır:

| Metrik                          | Yorum                                                        |
| :------------------------------ | :----------------------------------------------------------- |
| 🎯 **R-Kare (R²)**                | Modelin, girişim karındaki varyansın ne kadarını açıkladığını gösterir. |
| 📉 **Ortalama Kareli Hata (MSE)** | Tahminler ile gerçek değerler arasındaki ortalama kareli farkı ölçer. |

> ✅ **Önemli çıkarım:** Model, kardaki değişkenliğin büyük çoğunluğunu yakalayarak güçlü bir uyum sergiliyor. Analiz, **AR-GE Harcaması**'nın bir girişimin karlılığındaki en etkili faktör olduğunu doğruluyor.

### 📋 Tahminler vs. Gerçek (Test Seti)

Not defteri, modelin tahmin ettiği kar ile gerçek değerleri yan yana karşılaştıran bir tablo üretir. Tahminlerin gerçek karı yakından takip etmesi, modelin güvenilirliğini pekiştirir.

> 🔍 Güncel metrikleri ve karşılaştırma tablosunu görmek için not defterindeki hücreleri çalıştırın.

---

<p align="center">
  <i>⭐ Bu projeyi faydalı bulduysanız, bir yıldız vermeyi düşünün!</i>
</p>
