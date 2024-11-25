# Hash Tablosu

**Hash Tablosu**, key-value pair (anahtar-değer) eşleyen bir veri yapısıdır. Hash tabloları, özellikle arama sorgularında hızlı olmaları dolayısıyla sıkça kullanılır. Bir **temel hash fonksiyonu** kullanarak, anahtarları bir dizi içerisindeki indekslere dönüştürür ve değerler bu indekslerde saklanır.

## Hash Tablosunun Çalışma Mantığı
1. Bir anahtar tanımlanan **temel hash fonksiyonuna** gönderilir.
2. Hash fonksiyonu, anahtarı bir dizi içinde bir indekse dönüştürür.
3. Değer, hesaplanan indekse kaydedilir.
4. Birden fazla anahtar aynı indeksi oluşturduğunda (çakışma), **ayrık zincirleme (seperate chaining)** veya **lineer probing** gibi teknikler kullanılır.

## Hash Table Üzerinde Index Çakışması (Index Collision) Durumunda Yapılabilecekler
1. Ayrık zincirleme (seperate chaining)
2. Lineer Probing
3. Quadratic Probing
4. Double Hashing
5. Plus 3<br>
...

## Ayrık Zincirleme (Separate Chaining)
Bu collision solution yönteminde temel amaç, çakışan index üzerinde bir linked-list oluşturarak 2 veya daha fazla veriyi value => next şeklinde tutmaktır. Örneğin; 4 sayısı 4. index üzerinde konumlanmak istiyor. Ancak daha sonra 14 sayısı da 10 boyutlu bir dizi üzerinde 4. index değerini alacak. Bu durumda şöyle bir yapı oluşur; 

```4 - 14 => 14 - NULL```

## Lineer Probing
Bu yöntemde, çakışan index değeri belirli bir oranda artırılarak çıkan sonuç yeni index değeri olur. Örneğin 10 boyutlu bir dizide;

```h(x) = x % 10```

temel fonksiyon olsun. Bu durumda **4** ve **14** sayıları aynı index değerinde olacaklardır. Bu durumda sonradan eklenmek sayının index hesaplaması için; 

```f(index) = index + 1``` 

gibi bir fonksiyon kullanılır. Buradaki artırma miktarı; kullanılan veri yapılarına ve projede kullanılan algoritmalara göre değişiklik gösterir. Örneğin, 14 sayısı için;

```f(h(14)) = 5```

sonucunu verir. Dolayısıyla 14 sayısı, 5. index üzerinde konumlanır. Bu durum boş yer bulunana kadar artırılmaya devam eder. 

# Lineer Probing Dezavantajları
Lineer Probing yapısının en büyük dezavantajlarından biri, hash table üzerinde belirli index değerlerine yığılma yaparak önceki evya aradaki index değerlerine hiçbir veri yazamamasıdır. Bu durum verilerin verimli şekilde yerleşmemesine yol açar.

## Quadratic Probing
Bu yapıda amaç Lineer Probing yapısının yol açtığı belirli index'ler üzerindeki yığılmayı bir nebze dağıtmaktır. Bunu ise i gibi bir değişken ile lineer olarak artırılarak yapılır. Örneğin; 4 sayısı 4. index üzerinde. 14 sayısı da 10 boyutlu bir dizide 4. index üzerinde gelmeye çalışıyor. Bu durumda şöyle bir fonksiyon ortya çıkar; 

```f(pre_index) = (pre_index + i^2) mod 10```

dolayısıyla; 

```f(4) = (4 + 1.1) mod 10 = 5```

(i değeri, çoğu durumda 1'den başlayarak lineer olarak artış gösterir. Bir sonraki iterasyonda 2 olarak güncellenir.)

## Double Hashing
Bu yapıdaki amaç Quadratic Probing gibi verileri düzenli şekilde dağıtmaya çalışır. Ancak bunu kullanıcı tanımlı ekstra bir fonksiyondan geçirerek yapar. 4 ve 14 için temel fonksiyon şu olsun; 

```h(x) = x mod size```

10 boyut için; 

```h(4) = 4 mod 10 = 4```. index'e yerleşir. 

14 için; 

```h(14) = 14 mod 10 = 4```. index'e yerleşmek ***ister***.

bu durumda kullanıcı tanımlı şöyle bir fonksiyondan geçirilip yeni index alınabilir; 

```f(x) = ((x + x) - (x/2)) mod size```

14 için yeni index;

```f(14) = (14 + 14) - (14/2) mod 10 = 21 mod 10 = 1```. index; 14 sayısı için yeni index değeri olur. 

## Plus 3
Bu yapıda, eğer bir index üzerinde bir çakışma olursa yeni eklenmek istenen değerin index değerine 3 eklenir ve o index'e yerleşir. 4 ve 14 için; 

4 sayısı 4. index'e yerleşir. 
14 sayısı **normal şartlar altında** 4. index'e yerleşir. Ancak dolu olduğunda ```4 + 3 = 7```. index'e yerleştirilir. Buradaki 3 sayısı, index yığılmalarını bir nebze önlemek için ortlama bir değer olarak verilmiştir. **Ancak standart terminoloji içinde yer almaz.**
