# Notes
- Label Encoding, Target Encoding, Frekans Encoding yaptıktan sonra lineer modellerin büyük sayılı etiket alanın fiyatınında daha büyük olması gerekir gibi bir mantık kurma riski vardır
- bunun için bu encode yöntemleri ile birlikte ağaç tabanlı modeller kullanılır. lineer modeller ve yapay sinir ağları tercih edilmez
- line item value çok yüksek korelasyon(0.96) nedeniyle kaldırılmıştır.(neredeyse hedef değişkenle aynı şeyi ifade ediyor)
- KNN Imputerla eksik verileri dolduramayız çünkü kategorik verileri dolduramaz ve Label encoderla çalışamaz random forest classifier kullanarak bu eksik değerleri dolduracağız
- Outlier Detect için IQR yöntemi aykırı gibi gözüken ama sektörde normal olan bu değerleri outlier olarak işaretler çünkü veriler sağa çarpık bu yüzden en güvenilir yöntem izolasyon ağaçlarını kullanmaktır
- Encoder olarak label encoder birden fazla feature kullandığında bozulacağı için ordinal encoder kullandım.
- Lineer modeller verinin yapısı ve önişleme adımlarından sonra düzgün sonuçlar üretemez.
- Adaboost hiperparametre ayarlarından sonra gözle görülür bir biçimde iyileşmiştir ama hala çok yetersiz kalmaktadır. zayıf öğrenciler gürültüyü çözmekte etkisiz kalmıştır.
- Daha önce yaptığım *"line item value"* kolonunu kaldırmadığım Eğitim sonuçlarında xgb eğitim sırasında 0.97 gibi bir r2 skoru verirken test verisetinde 0.92 ye kadar düşmüştür.Yani bu durum overfitting'e sebep olmuştur.buna karşın random forest istikrarlı bir çizgide ilerlemiş ve sonuçları tutarlıdır overfiting'e yatkınlığı düşüktür. fakat sonradan fark etmem üzerine bu kolon kaldırılmıştır
