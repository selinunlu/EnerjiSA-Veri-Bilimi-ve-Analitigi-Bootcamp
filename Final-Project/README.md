# Final Project | Theft & Loss 

Projenin amacı tesisata bağlı, nitelikli kaçak yapan müşterileri tespit etmektir. Bunun için 24 aylık tüketim verileri, 12 aylık demand ve sayaçla ilgili bir takım veriler var.Train setindeki NK_FLAG alanı target değişken olup, bir classification modelidir. NK_Flag=1 olması kaçağın olduğu, 0 olması kaçağın olmadığını ifade etmektedir.

* 24 aylık tüketim verilerinin oldukça önemli olduğunu düşünüldü. Birbirini izleyen aylar arasındaki ekstrem tüketim farkları, mevsimlik olarak gruplandığında elde edebilen değerler, belirli bir ay ile onun 12 ay sonraki değeri arasındaki farklar, aylık değerlerin birbiri arasındaki korelasyonları gibi faktörlerin nekadar etkili olabileceğini araştırıldı ve sonuçta bu tarz yeni veri elde etmektense bulunan halinin daha yararlı olacağına karar verildi.

* Tüketim değişkeninde NaN verilerin bulunması, müşterinin kaçak yapmasından kaynaklanacağı düşünüldü ve ‘TUKETIM_NAN’ isimli yeni bir kolon oluşturuldu.

* Demand değişkeni ise anlık olarak çekilen en yüksek elektrik miktarını göstermektedir. Buradaki önemli nokta ise anlık olarak çekilen bu değerin yüksek olması, o ay içerisinde yüksek miktarda elektrik kullandığını göstermemektedir. Burdan çıkarılan sonuç, tüketim miktarı ile demand miktarı arasında mantıksal bir ilişki kurmanın mümkün olmadığı.

* Tarih verisi içeren 'SAYAC_BASLANGIC_TARIHI', 'SAYAC_TAKILMA_TARIHI', 'SAYAC_BITIS_TARIHI' kolonlarının ve 'SAYAC_MALZEME_ID' kolonunun hedefe götürecek bir yarar sağlamadığı görüldü ve bu kolonlar kullanılmama kararı alındı.

* Dağılımları görülen sayaç özellikleri ile ilgili değişkenlere bakıldığında incelenen sayacın bir ticarethane ya da mesken kullanımında olması kaçak durumunda fark yaratacağı düşünülmekte. Aynı zamanda kullanımın ticarethane ve meskende olmasının sayaç faz tipi, sayaç ölçüm türünde fark yarattığı görüldü. Ticarethanede daha çok trifaze görülürken, meskende monofaze çoğunlukta görülüyor. Ticarethanede kombi ölçümü fazla görülürken, meskende aktif ölçüm fazla görülüyor. Bu durum eksik verileri doldurmada işe yaradı.

* 'SOKAK_RISK_SKORU' , 'MAHALLE_RISK_SKORU, 'SOB_RİSK_SKORU' değişkenleri incelediğinde sokak risk skorunun mahalle ya da sob risk skorundan yüksek olması durumlarının 1'e götürdüğünü farkedildi. Öncelikle buna göre yeni bir değişken üretme denense de bu değişkenlerin tek başlarına da anlamlı olduğunu modelleme aşamasında görüldü ve ayrı kolonlar olarak bulundurmaya karar verildi.

* Dağılımları görülen sayaç özellikleri ile ilgili değişkenlere bakıldığında incelenen sayacın bir ticarethane ya da mesken kullanımında olmasının kaçak durumunda fark yaratacağı düşünüldü. Aynı zamanda kullanımın ticarethane ve meskende olmasının sayaç faz tipi, sayaç ölçüm türünde fark yarattığı görüldü. Ticarethanede daha çok trifaze görülürken, meskende monofaze çoğunlukta görülüyor. Ticarethanede kombi ölçümü fazla görülürken, meskende aktif ölçüm fazla görülüyor. Bu durum eksik verileri doldurmada işe yaradı. ‘SAYAC_FAZ_N’ deki eksik verileri ticarethane ise trifaze olarak, mesken ise monofaze olarak dolduruldu.

* Kaçak tahmini yaparken yakalanan müşteri sayısının önemli olduğunu biliniyor. Fakat bu yakalanan müşterinin ticarethane-sanayi’de olması meskende olmasından daha iyi bir avantaj olabilir. Çünkü ticarethaneler meskenlere göre oldukça fazla elektrik çekiyorlar.

* ‘SAYAC_OLCUM_TURU’ndeki verilerin çoğunluğunun kombi olması sebebiyle eksik veriler ‘Kombi’ olarak dolduruldu.

* Sayaç marka ve model değişkenlerinin tek kolona indirilip indirilmeyeceği analizi yapıldığında her iki değişkeni de bulundurmanın hedefe giderken yararlı olacağına karar verildi. Bu değişkenlerde bulunan eksik verilerin MISSING olarak doldurulmasına karar verildi. Ancak dengesiz şekilde kategorilere dağılan bu değişkenleri gruplayarak kullanmak daha doğru olacaktı. Gruplarken de verilerdeki 0-1 dağılımlarını göz önünde bulundurarak gerçekleştirildi.

* Tarih verisi içeren 'SAYAC_BASLANGIC_TARIHI', 'SAYAC_TAKILMA_TARIHI', 'SAYAC_BITIS_TARIHI' kolonlarının ve 'SAYAC_MALZEME_ID' kolonunun bizi hedefimize götürecek bir yarar sağlamadığı görüldü ve bu kolonlar kullanılmama kararı alındı.

* 'SAYAC_YAPIM_YILI' kolonunda 0-1 dağılımlarına göre gruplama yapıldı.

* Yeni kolonlar oluşturuldu. 'SAYAC_YAPIM_YILI' ile 'SAYAC_TAKILMA_TARIHI' arasındaki fark alınarak 'SAYAC_YAS' kolonu oluşturuldu. 

* Risk Skorlarının hedefe götürmede etkili olacağı belirtilmişti. Bu sebeple sokak risk skorunun mahalle risk skorundan büyük olduğu ve sayaç ölçüm türünün kombi olduğu verilerden yeni bir kolon oluşturuldu.

* Kaçak veriler ararken aslında yaptığımız iş outlier tespiti. Bu sebeple IQR kullanarak tüketim verileri üzerinden ‘TUKETIM_OUTLIER’ kolonunu oluşturuldu.


Değişkenleri inceleyerek kullanılacaklara karar verme ve yeni değişkenler üretme aşamasından sonra gerekli veri doldurma, gruplama ve encoding işlemleri sonrası veri modelleme için hazır hale geldi. Bu aşamada kontrollü gitmek adına yüzde 80 ve 20 olacak şekilde train ve test veri setleri ayrıldı. Oversampling ve scalling işlemleri ardından validation veri setine aynı işlemler uygulanarak model deneme kısmına geçildi.

Veri keşif kısmında detaylı çalışıldığı için öncelik çeşitli modelleme yöntemleri deneyerek en uygun olanı bulmak oldu. Random Forest Classifier, Support Vector Classifier , CatBoost Classifier, Logistic Regression, AdaBoost Classifier, XGB Classifier gibi yöntemler deneyerek en başarılı sonuçları SVC ve catboostta alındığı görüldü. Ancak f1 skor tahminini yeterli bulunmayarak veri setinde iyileştirmeye gidildi. Bu aşamada tüketim değişkenlerindeki nan verilerin hedefe yaklaştırabileceği görüldü. Skordaki artışa da en çok bu durum yarar sağladı.
