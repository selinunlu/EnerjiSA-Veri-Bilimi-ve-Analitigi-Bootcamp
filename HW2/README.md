# HW2 | House Prices Project

* **Variable** - Variable name.

* **Type** - Değişkenlerin tipinin tanımlanması. Bu alan için iki olası değer kullanabiliriz: 'sayısal' veya 'kategorik'

* **Segment** - Değişkenlerin segmentinin tanımlanması. Üç olası segment tanımlayabiliriz: building, space veya location. 'Building' dediğimizde, binanın fiziksel özellikleriyle ilgili bir değişkeni kastediyoruz (örneğin, 'OverallQual'). 'Space' dediğimizde, evin alan özelliklerini bildiren bir değişkeni kastediyoruz (ör. 'TotalBsmtSF'). Son olarak 'Location' dediğimizde evin bulunduğu yer hakkında bilgi veren bir değişkeni kastediyoruz (örneğin 'Neighborhood').

* **Expectation** - 'SalePrice' değişken etkisi hakkındaki beklentimiz. Olası değerler olarak 'Yüksek', 'Orta' ve 'Düşük' olan kategorik bir ölçek kullanabiliriz.

* **Conclusion** - Verilere hızlı bir bakış attıktan sonra, değişkenin önemi hakkındaki sonuçlarımız. 'Expectation' ile aynı kategorik ölçekte devam edebiliriz.

* **Comments** - Değişkenler hakkında genel yorumumuzu buraya yazabiliriz.


**Veri üzerinde yapılan işlemler:**

* Sezgisel analiz kısmını tamamlayabilmek adına, tablo formatının oluşturulması.
* Benzerliği yüksek veriler, modelin anlamlılığında fazladan etki edebileceği için, veri içindeki değişkenlerden benzerliği yüksek verilerin gruplanması veya kullanılacak verinin seçilmesi.
    *Bu maddede korelasyon coef katsayıları üzerinden ilerleyebiliriz. Benzerliği yüksek verilerin tek bir değişken haline getirilip getirilemeyeceğini değerlendirebilir. Eğer tek bir değişken haline getiremiyorsak benzer verilerden hangisini seçmemiz gerektiği üzerinde bir konuşabiliriz.
* Veri setimizde anlamlı olabilecek yeni kolonlar oluşturulması.
    *Bu madde için, birbirleriyle sayısal veya anlamsal ilişkisi olan değişkenlerden matematiksel hesaplamalar veya gruplandırmalar yaparak veri setimizi büyütebiliriz.
* Outlierları temizleyip, bağımlı değişken üzerinde verileri normalleştirmeye çalışıyor olacağız.

