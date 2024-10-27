# Amazon Yorumları Sentiment Analizi Projesi 🛍️📊

Bu proje, Amazon üzerindeki müşteri yorumlarının duygu analizi yapmak amacıyla tasarlanmıştır. Proje, metin ön işleme, metin görselleştirme, duygu analizi, özellik mühendisliği, duygu modelleme ve hiperparametre optimizasyonu gibi adımlardan oluşmaktadır. Aşağıda, her bir adımın detayları verilmiştir:

## 1. Metin Ön İşleme 🧹

Metin verileri analiz edilmeden önce, çeşitli ön işleme adımlarından geçirilir:

- **Normalleştirme**: Metinler küçük harflere dönüştürülür ve gereksiz boşluklar temizlenir.
- **Noktalama İşaretleri Kaldırma**: Metinlerdeki noktalama işaretleri (noktalama işaretleri, soru işaretleri, ünlem işaretleri vb.) kaldırılır.
- **Sayıları Kaldırma**: Metinlerdeki sayılar temizlenir.
- **Durma Kelimelerini Kaldırma**: "ve", "veya", "ama" gibi durma kelimeleri metinden çıkarılır.
- **Nadir Kelimeleri Kaldırma**: Sık kullanılmayan ve analize katkısı olmayan kelimeler kaldırılır.
- **Terim Frekanslarını Hesaplama**: Her bir kelimenin metin içindeki frekansı hesaplanır.
- **Tokenizasyon**: Metinler kelimelere ayrılır.
- **Lemmatizasyon**: Kelimeler köklerine indirgenir.

## 2. Metin Görselleştirme 📊

Ön işleme adımlarından geçirilen metinler, görselleştirme ile daha anlaşılır hale getirilir:

- **Terim Frekanslarının Hesaplanması ve Görselleştirilmesi**: Kelimelerin frekansları bar plot ile görselleştirilir.
- **Wordcloud Oluşturma**: Kelimelerin frekanslarına göre wordcloud oluşturulur. Wordcloud'lar, standart, belirli bir şekilde (örneğin, Türk bayrağı 🇹🇷 veya PlayStation simgesi 🎮) özelleştirilebilir.

## 3. Duygu Analizi 😊😐😠

Metinlerin duygu analizi yapılması için `SentimentIntensityAnalyzer` kullanılır:

- **Duygu Yoğunluğu Hesaplama**: Her bir yorumun olumlu, olumsuz veya nötr olma durumu hesaplanır.
- **Duygu Etiketleme**: Duygu yoğunluğuna göre yorumlar "pos" (olumlu) veya "neg" (olumsuz) olarak etiketlenir.

## 4. Özellik Mühendisliği 🛠️

Etiketlenmiş verilerin sayısal temsili için özellik mühendisliği adımları uygulanır:

- **CountVectorizer**: Kelimelerin frekanslarına göre sayısal temsil oluşturulur.
- **TF-IDF**: Kelimelerin önemine göre ağırlıklandırılmış sayısal temsil oluşturulur.

## 5. Duygu Modelleme 🤖

İki farklı modelleme yaklaşımı kullanılır:

- **Logistic Regression**: Doğrusal bir modelleme yaklaşımıdır.
- **Random Forests**: Karar ağacı tabanlı bir modelleme yaklaşımıdır.

Her bir model, farklı veri temsilleri (Count Vectors, TF-IDF Word veya TF-IDF N-gram) üzerinde eğitilir. Ardından, çapraz doğrulama kullanılarak modellerin performansı değerlendirilir.

## 6. Hiperparametre Optimizasyonu ⚙️

`Random Forests` modeli için `GridSearchCV` kullanılarak en iyi hiperparametreler belirlenir:

- **GridSearchCV**: Farklı hiperparametre kombinasyonları denenerek en iyi performansı veren parametreler seçilir.
- **Model İyileştirme**: Seçilen hiperparametrelerle modelin performansı artırılır.

Bu proje, Amazon yorumlarının duygu analizi için kapsamlı bir yaklaşım sunar ve farklı modelleme teknikleriyle müşteri yorumlarının duygu durumunu tahmin etmeyi amaçlar. 🚀
