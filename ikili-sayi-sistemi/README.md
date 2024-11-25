# Bilgisayarların Çalışması Ve İkili Sayı Sistemi 

Bilgisayarlar günümüzde pek çok alanda kullanılmaktadır. Bu yazıda aslında bilgisayarların bir işlemi yaparken nasıl bir yol izlediklerini, bunları yaparken nasıl bir yol kullandıklarını bulabilirsiniz.

## İkili Sayı Sistemi (Binary)

Bilgisayarlar, çoğunlukla çalışırken ikili sayı sistemi üzerinden ilerlerler. Tabii ki burada kuantum bilgisayarlar gibi istisnaları yoksaymak gerekiyor. Bilgisayarlar, tüm işlemleri 0 ve 1 değerleriyle ifade edilen binary formatına dönüştürerek işler. Bunun kaynağı; bilgisayarlardaki işlemcilerin transistör denilen devre elemanlarıyla işlem yapmasıdır. Bunun daha detaylı ayrıntısını transistörler ile ilgili yazıda bulabilirsiniz. 

## Onlu Sayı Sistemi (Decimal) 

Decimal ifadesi; günümüzde kullandığımız sayıları söylediğimiz sayı sistemidir. Aslında biz farkında olmadan günlük hayatta 10'lu sayı sistemini kullanırız. Ancak bunun bilgisayarların işlemcilerinde bir karşılığı olmadığı için bu sayıları dönüştürmemiz gerekli.

## Binary => Decimal Dönüşümleri

Bir ikili sayı sistemindeki sayıyı bizim anlayacağımız yani decimal tabana dönüştürmek için sırasıyla şunu yaparız; 

- Sayının sonundan başlayarak 2'nin kuvvetlerini her bir sola kaymada 1 artacak şekilde yazarız. Burada kuvveti 0'dan başlatırız.
- Daha sonra her basamak için onun altındaki değeri o sayı ile çarparız
- Daha sonra bulduğumuz bütün sonuçların toplamı bize o ikili tabandaki sayının onluk sistemdeki karşılığını verir.

Daha anlaşılır olması açısından görseli aşağıda bulabilirsiniz. Örnek olarak burada 0111 gibi bir ifade kullanılmıştır ancak bu tam bir byte örneği değil, yarım byte örneğidir. Bunun ile ilgili detayları bit ve byte'larla ilgili olan yazıda bulabilirsiniz. 

![image](https://github.com/user-attachments/assets/beb9a5f4-0cfd-49fe-9a75-09e74d9c718f)

## Decimal => Binary Dönüşümleri

Bir onlu sistemdeki sayıyı ikili sisteme dönüştürmek için ise sayının 2'nin hangi kuvvetlerinin toplamı şeklinde yazılacağına bakıp buna göre aynı yöntemi kullanarak kontrolünü yapabiliriz.

## Bilgisayarlar Bunu Nasıl Kullanırlar

Bilgisayarların işlemcileri, yukarıda belirtilen dönüşümleri saniyede çok fazla kez yaparlar. Bunu yaparken de 0 ve 1 sayılarını, bir transistörden akım geçip geçmeyeceğini anlatmak için yaparlar. Bunları ise farklı türlerde girdi olarak kullanıcıdan alıp bilgisayarlar tarafından anlaşılan sayılara dönüştürürler. Bu dönüşümlerden bazıları şunlardır; 

- Decimal => Binary
- Text => Binary (ASCII Tablosu yardımıyla)
- Image => Binary (base64 gibi kodlamalar yardımıyla)
- Audio => Binary (sesin bazı parametrelerine bakarak. Örneğin; ses düzeyi, duraklama yerleri vs.)

Kısacası bilgisayarlar, herhangi bir medyayı bize gösterirken 0 ve 1'leri kullanırlar. Aslınnda her işi yapmak için kullandıklarını da söyleyebiliriz. Örneğin şu anda bu yazıyı düzgün şekilde okuyabilmemizin kaynağı 0 ve 1 sayıları.
