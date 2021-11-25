# HW2 | House Prices Project

* **Variable** - Variable name.

* **Type** - Değişkenlerin tipinin tanımlanması. Bu alan için iki değer kullanıldı: `sayısal` veya `kategorik`.

* **Segment** - Değişkenlerin segmentinin tanımlanması. Üç olası segment tanımlandı: `building`, `space` veya `location`. `Building`, binanın fiziksel özellikleriyle ilgili bir değişkeni kastediyor (örneğin, 'OverallQual'). `Space`, evin alan özelliklerini bildiren bir değişkeni kastediyor (örneğin, 'TotalBsmtSF'). `Location`, evin bulunduğu yer hakkında bilgi veren bir değişkeni kastediyor (örneğin, 'Neighborhood').

* **Expectation** - `SalePrice` değişken etkisi hakkındaki beklenti. Olası değerler olarak `Yüksek`, `Orta` ve `Düşük` olan kategorik bir ölçek kullanıldı.

* **Conclusion** - Verilere hızlı bir bakış attıktan sonra, değişkenin önemi hakkındaki sonuçlar. `Expectation` ile aynı kategorik ölçekte devam edildi.

* **Comments** - Değişkenler hakkında genel yorum.


## Veri üzerinde yapılan işlemler:

* Sezgisel analiz kısmını tamamlayabilmek adına, tablo formatının oluşturulması.

* Benzerliği yüksek veriler, modelin anlamlılığında fazladan etki edebileceği için, veri içindeki değişkenlerden benzerliği yüksek verilerin gruplanması veya kullanılacak verinin seçilmesi.

    - Bu maddede korelasyon coef katsayıları üzerinden ilerlendi. Benzerliği yüksek verilerin tek bir değişken haline getirilip getirilemeyeceğini değerlendirildi. Eğer tek bir değişken haline getiremiyorsak benzer verilerden hangisini seçmemiz gerektiği üzerinde konuşuldu.
    
* Veri setinde anlamlı olabilecek yeni kolonlar oluşturulması.

    - Bu madde için, birbirleriyle sayısal veya anlamsal ilişkisi olan değişkenlerden matematiksel hesaplamalar veya gruplandırmalar yaparak veri seti büyütüldü.
 
 
* Outlierları temizleyip, bağımlı değişken üzerinde verileri normalleştirmeye çalışılması.

