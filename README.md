# House Classification Project

Bu proje, İstanbul Arnavutköy ilçesindeki emlak ilanlarından elde edilen verilerle, evlerin **“sıfır” (yeni) mi yoksa “ikinci el” mi** olduğunu tahmin etmek amacıyla geliştirilmiş bir makine öğrenmesi sınıflandırma projesidir. (Bina yaşı 5 yıldan küçük olan binalar **Sıfır**, 5 yıldan büyük olan binalar ise **İkinci El** olarak değerlendirilmiştir.)

## Proje Hakkında 

- **Amaç**: Belirtilen özelliklere sahip bir evin “sıfır” mı yoksa “ikinci el” mi olduğunu tahmin etmek.  
- **Kapsam**: Proje kapsamında toplanan veriler yalnızca Arnavutköy (İstanbul) bölgesine aittir.

## Veri Açıklaması

Veri seti şu sütunları içermektedir:

- `Room Count` – Evin oda sayısı  
- `Price` – Evin kira fiyatı   
- `Area (m²)` – Net kullanım alanı (m²)    
- `Building Age` – Bina inşa edildiğinden bu yana geçen yıl sayısı  
- `Condition` – Hedef değişken: `Sıfır` veya `İkinci El`

## Veri Ön İşleme 

- Eksik veriler tespit edilip, uygun strateji ile dolduruldu. 
- Kategorik değişkenler (condition) sayısal formatlara dönüştürüldü (Label Encoding).  
- Aykırı değerler tespit edilip temizlendi.

## Keşifsel Veri Analizi (EDA) 

- `seaborn`/`matplotlib` kullanılarak:
  - Fiyat–metrekare, fiyat–bina yaşı gibi birçok ilişki çizildi.

## Modelleme

Aşağıdaki sınıflandırma algoritmaları kullanıldı:

1. **Lojistik Regresyon**  
2. **Support Vector Machine**  
3. **Gaussian Naive Bayes**  
4. **Decision Tree**  
5. **KNN**
6. **Random Forest**
7. **XGBoost**
8. **AdaBoost**
9. **MLP**

Her model için:
- Train/Test setlerine ayırma (örneğin %80–20)
- Cross-validation uygulandı 
- Doğruluk, precision, recall, F1 score gibi metrikler hesaplandı
- Karışıklık matrisleri görselleştirildi

## Değerlendirme ve Sonuçlar 

- Model performanslarına göre en iyi sonuçları veren classification method bulundu. 
- XGBoost metoduyla en iyi değerlere ulaşıldı. 

![XGBoost sonuçları](https://i.imgur.com/o4tmJlq.jpeg)
