# Tokenizer Benchmark

### Bu klasör bir tokenizer benchmarkı oluşturma ve bu yolla tokenizer standartları oluşturma amaçlı çalışmaları içerir.

## Benchmark Kriterleri 

1. Verilen metnin kaç tokene dönüştürüldüğü. 
2. Ne kadar hızlı dönüştürüldüğü.
3. Dönüştürülen tokenlerin kaçının anlamlı tokenler olduğu. 
4. Dönüştürülen tokenlerin kaçının anlam kaybı olmadan daha küçük tokenlerle ifade edilebileceği.
5. Token sözlüğünün boyutu.

## Kriterlerin Amaçları 

- Token Sayısı: Train aşamasında kullanılacak corpusun daha az tokene ayrılması demek hem kelimelerin daha kapsamlı tokenleştirildiği hem de daha hızlı süreceği anlamına gelir. 
- Anlamlı Token Oranı: Tokenlerin anlamlı olması demek embedding matrisinde de tokenlerin gerçekten ifade ettikleri anlamlara daha yakın şekilde temsil edilebilmesi demektir. 
- Tokenlerin Özlük Oranı: Birden fazla tokenin aynı anlamı ifade etmesi hem o anlamın bulanıklaşmasına ve eğitim aşamasında bu anlamı oluşturmak çok daha zor olacak, eldeki corpusun değeri düşecek. Bu sebeple tokenlerin özlük oranı (bir tokenin aynı veya benzer anlama sahip alt tokenlere bölünemiyor oluşu) önemli bir kıstastır. Bu ölçüt dildeki anlam desenlerinin tokenizer tarafından ne kadar iyi yakalanabildiği ile ilgili bir ölçüttür.
- Sözlük Boyutu: Sözlük boyutunun büyümesi demek toplam model boyutunun da büyümesi demek olduğundan hem train aşamasında daha çok tokeni eğitmek hem de tahmin aşamasında daha çok token arasından seçim yapmak göz önünde bulundurulunca aynı dil için kullanılacak daha küçük bir sözlük daha verimli olabilir.
- Hız: Yine hem train aşamasında corpusun tokenleştirilmesinde hem de son kullanıcı büyük metinlerle işlem yaparken önemli bir kriter.

### *Bu başlık bitmedi.*

## Maddelerin Uygulanması

*İlgili maddelerin uygulanması ile ilgili fikirler.*

- Tokenlerin anlamlı olup olmadığı isTurkish() fonksiyonu ile kontrol edilebilir. 
- Eğer token bir predefined_word ise isTurkish() fonksiyonunu çalıştırmaya gerek yok.
