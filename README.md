# SMS Spam Detection | Preprocessing & Five Classifier Model

## Description

Dataset: [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)

The SMS Spam Collection is a set of SMS tagged messages that have been 
collected for SMS Spam research. It contains one set of SMS 
messages in English of 5,574 messages, tagged acording being ham (legitimate) or spam.

### Data Understanding

Dataset: [Airplane Price Prediction](https://www.kaggle.com/datasets/asinow/airplane-price-dataset)
| Column Name                  | Description                                                                 |
|----------------------------|-------------------------------------------------------------------------|
| **v1**                  | Spam or ham, label-target. |
| **v2**                  | Text of SMS. |

## Analyze (EDA)

<img src="https://github.com/gokhanmutlu/surface_temperature_EDA/blob/main/images/Average%20Surface%20Temperature%20by%20Year.png" width="60%">

- Farklı modellerin farklı bölgelerdeki satış fiyatlarında gözle 
görülür bir fark yok. Boeing 777'nin 
Avrupadaki satışında aykırı veri noktaları içeriyor.
<br/>

<img src="https://github.com/gokhanmutlu/surface_temperature_EDA/blob/main/images/Hottest-Coldest%20Countries.png" width="60%">

- Genel ve doğal olarak uçağın yaşı arttıkça fiyatı aynı 
şekilde düşme eğilimi gösteriyor. Fakat bu düşüş bazı modeller için daha hızlı 
olurken bazı modeller için daha hafif bir şekilde gerçekleşmiş.
<br/>

<img src="https://github.com/gokhanmutlu/surface_temperature_EDA/blob/main/images/Hottest-Coldest-Boxplot.png" width="60%">

- Cessna 172 modeli için yakıt tüketimi arttıkça fiyatında herhangi 
bir değişim olmadığı gözükmekte. Bu uçak modelinin daha az kapasiteli olmasından dolayı 
kaynaklanıyor olabilir.
<br/>

<img src="https://github.com/gokhanmutlu/surface_temperature_EDA/blob/main/images/Monthly%20Average%20Temperature.png" width="60%">

- When examining the general temperature averages, it is evident that the average temperature during the summer season is higher compared to other seasons.
<br/>


<p float="left">
    <img src="https://github.com/gokhanmutlu/surface_temperature_EDA/blob/main/images/Linear%20Regression.png" width="49%">
    <img src="https://github.com/gokhanmutlu/surface_temperature_EDA/blob/main/images/Temperature%20Forecast.png" width="49%">

</p>

<br/>

- ``Üretim yılı`` ve `yaş` negatif korelasyon gösteriyor
- ``Kapasite`` ``Menzil`` birbirleri arasında yüksek korelasyon gösteriyor. Multicollinearity oluşturuyor.
- `Fiyat` ile yüksek korelasyon gösteren `Kapasite` `Menzil` özelliklerinden biri kullanılacak modele göre çıkarılabilir.

<br/>

## Construct

## Summary

1. Kapasite, doğrudan uçağın büyüklüğü ve taşıma kapasitesi ile ilgili olduğu için fiyat üzerinde belirleyici bir etkiye sahip.
2. Üretim Yılı ise uçakların yaşını gösterdiği için, genellikle yaşlanan uçaklar daha düşük fiyatlara sahip olur. Bu yüzden üretim yılı, modeldeki en etkili faktörlerden biri olabiliyor.
3. XGBRegression fiyatları tahminlerken yaklaşık %98 bir başarı sağlıyor. Ayrıca RMSE için de diğer modellere göre daha az sapma gösteriyor.