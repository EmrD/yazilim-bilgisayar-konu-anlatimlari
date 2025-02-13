# Linked List (bağlı liste) Nedir? 

Bağlı listeler 4 ana grupta incelenebilir:

- Singly Linked List (Tek Yönlü Bağlı Liste)
- Doubly Linked List (Çift Yönlü Bağlı Liste)
- Circular Linked List (dairesel bağlı liste anlamına gelir, tek veya çift yönlü olabilir)

Temel olarak bellek üzerinde birden fazla veriyi bir arada tutup gerekli yerlere gerekli elemanların referanslarını alarak buradan veri arama, sıralama, araya ekleme, silme gibi işlemleri yapar.

## Singly Linked List

Tek yönlü bağlı liste, bağlı listeler içerisindeki en sık kullanılan ve diğerlerine göre daha temel bir yapı içerir. Temelde, 1 index içinde 2 düğüm tutularak bir tanesinde o index üzerindeki verinin kendi değerini, bir diğer düğümünde ise bir sonraki index üzerinde bulunan değeri referans verir. Eğer ilgili index son index ise next değeri NULL olarak atanır. Görselleştirilmiş halini bulabilirsiniz; 

![image](https://github.com/user-attachments/assets/99cee3d8-a059-4afd-9648-0c22866f9098)

## Doubly Linked List

Çift yönlü bağlı liste, tek yönlü bağlı listeye kıyasla ufak bir farklılık içerir. Tek yönlü bağlı listeden farklı olarak, bir index içerisinde 3 farklı düğüm bulunur. Bunlar sırasıyla; 

- Prev
- Value
- Next

şeklindedir. Buradaki prev, bir önceki düğümün adresini tutar. Value kısmı o index üzerindeki değeri, next kısmı ise tek yönlü bağlı listedeki gibi bir sonraki index'in value kısmını referans verir. Eğer ilgili index 0 ise prev değeri NULL olarak, eğer son index ise next değeri NULL olarak atanır. Görselleştirilmiş hali; 
![image](https://github.com/user-attachments/assets/96315fb7-c2b3-43a2-a1e5-2bdbbf459727)

## Circular Linked List

Dairesel bağlı listelerde son düğümün (tail) next pointer'ı, listenin başındaki (head) düğüme işaret eder. Örneğin index değeri 0 olan bir çift yönlü bağlı listede prev değeri normal şartlar altında NULL olması gerekiyorken, dairesel bağlı listede index 0'ın prev değeri son index'in value değerinin referansını verir. Aynı şekilde son index üzerindeki next değeri de index 0'ın value değerinin referansını alır. Tek yönlü dairesel bağlı listede ise tek fark yalnızca PREV kısmının olmamasıdır. Görselleştirilmiş hali; 
![image](https://github.com/user-attachments/assets/f85e2167-9e1b-478a-b4b0-e4df84f2acbd)

## Bağlı Listeler Nerelerde Kullanılır? 

Bağlı listeler özellikle bir önceki / sonraki işlemin tutulması gereken yerlerde kullanılır. İnternet tarayıcılarda bulunan ileri ve geri butonları genelde bu temeli kullanırlar. 
