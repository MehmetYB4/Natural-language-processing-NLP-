Amazon yorumları sentiment analizi.
Metin Ön İşleme: Metin verileri normalleştirme, noktalama işaretlerini kaldırma, sayıları kaldırma, durma kelimelerini kaldırma, nadir kelimeleri kaldırma, belirli bir metin için terim frekanslarını hesaplama, tokenizasyon ve lemmatizasyon gibi ön işlemlerden geçirilir.
Metin Görselleştirme: Terim frekanslarının hesaplanması ve bar plot ile görselleştirilmesi, wordcloud oluşturma (standart, belirli bir şekilde ve Türk bayrağı veya PlayStation simgesine göre özelleştirilmiş).
Duygu Analizi: Metinlerin duygu analizi yapılması için SentimentIntensityAnalyzer kullanılır. Her bir yorumun duygu yoğunluğu (olumlu, olumsuz veya nötr) hesaplanır.
Özellik Mühendisliği: Duygu yoğunluğu temel alınarak "pos" veya "neg" olarak etiketlenen bir duygu etiketi oluşturulur. Etiketlenmiş verilerin sayısal temsili için CountVectorizer veya TF-IDF kullanılır.
Duygu Modelleme: İki farklı modelleme yaklaşımı kullanılır: Logistic Regression ve Random Forests. Her bir model, farklı veri temsilleri (Count Vectors, TF-IDF Word veya TF-IDF N-gram) üzerinde eğitilir. Ardından, çapraz doğrulama kullanılarak modellerin performansı değerlendirilir.
Hiperparametre Optimizasyonu: Random Forests modeli için GridSearchCV kullanılarak en iyi hiperparametrelerin belirlenmesi ve modelin iyileştirilmesi sağlanır.
