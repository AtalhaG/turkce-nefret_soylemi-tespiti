# Türkçe Nefret Söylemi Tespiti (Turkish Hate Speech Detection)

Türkçe metinlerde nefret söylemi / saldırgan içerik tespiti yapan bir doğal dil işleme (NLP) projesi. Klasik bir makine öğrenmesi baseline'ı ile transformer tabanlı bir derin öğrenme modeli karşılaştırılmış, en iyi model Hugging Face Spaces üzerinde canlıya alınmıştır.

🔗 **Canlı Demo:** [Hugging Face Spaces üzerinde dene]
https://huggingface.co/spaces/AtalhaG/turkce-nefret-soylemi-tespiti

---

## 📋 Proje Özeti

Bu proje, bir metnin **nefret söylemi içerip içermediğini** (ikili sınıflandırma: 0 = nötr, 1 = nefret söylemi) tahmin eden bir model geliştirmeyi amaçlamaktadır. İki farklı yaklaşım denenmiş ve karşılaştırılmıştır:

1. **Baseline Model:** TF-IDF vektörleştirme + Logistic Regression
2. **Final Model:** BERTurk (`dbmdz/bert-base-turkish-cased`) fine-tuning

## 🗂️ Veri Seti

- Ana veri seti: [`manueltonneau/turkish-hate-speech-superset`](https://huggingface.co/datasets/manueltonneau/turkish-hate-speech-superset) (Hugging Face Hub)
- İki ek Türkçe nefret söylemi veri seti denenmiş, ancak etiketleme tutarsızlıkları nedeniyle model performansını düşürdüğü görülmüş ve süreçten çıkarılmıştır. Bu deneme `01_model_egitimi.ipynb` dosyasında belgelenmiştir.

## 🛠️ Kullanılan Teknolojiler

- Python, pandas, numpy
- scikit-learn (TF-IDF, Logistic Regression)
- Hugging Face Transformers (BERTurk fine-tuning)
- Gradio (arayüz)
- Hugging Face Hub & Spaces (model barındırma ve dağıtım)

## ⚠️ Sınırlılıklar

- Model, eğitim verisindeki etiketleme kalitesine bağımlıdır; veri setindeki olası önyargılar (bias) model tahminlerine yansıyabilir.
- Bu model bir karar verme aracı değil, içerik moderasyonuna **yardımcı** bir araç olarak değerlendirilmelidir.
