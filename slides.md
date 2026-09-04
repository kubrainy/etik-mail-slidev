---
theme: seriph
title: Türkçe Kurumsal E-Postalarda Etik Dışı Dil Tespiti
info: |
  IDAP'26 Sunumu
  Kübra Çetinkaya, Sezi Güngörmüş, Şerif Ali Sadık
class: text-center
layout: center
drawings:
  persist: false
transition: fade-out
mdc: true
---

<Page0 />

<!--
Merhaba ben Kübra Çetinkaya. Kütahya Dumlupınar Üniversitesi Yazılım Mühendisliği
bölümünden mezunum. Bugün sizlere Türkçe kurumsal e-postalarda etik dışı dil
kullanımının yapay zekâ ile otomatik olarak tespit edilmesine yönelik
gerçekleştirdiğimiz çalışmayı sunacağım.

-->

---
layout: center
class: text-center
---

## Etik Dışı Dil Nedir ?

<br>

<Page1 />

<!--
Etik dışı dil dediğimizde genellikle aklımıza hakaret, küfür, nefret söylemi
veya açık saldırganlık ifade eden iletişim biçimleri geliyor.

Fakat kurumsal iletişimde problem her zaman bu kadar açık değil.

Örneğin bu mailde doğrudan bir hakaret bulunmuyor. Ancak kullanılan dil
baskılayıcı ve pasif-agresif ifadeler barındırıyor.

[click] Bu ifadeler çoğu zaman doğrudan hakaret içermesede karşı tarafta rahatsızlık hissi oluşturabilir.
Dolayısıyla problem yalnızca kötü kelimeleri tespit etmek değil;
asıl mesele iletişim biçimini ve bağlamı anlayabilmek.
-->

---
layout: center
class: text-center
---

## İletişim Dijitalleşti, Ama İnsan Faktörü Kaybolmadı

<Page2 />

<!--
Dijitalleşmeyle birlikte kurum içi iletişim de önemli ölçüde dijital
kanallara taşındı.

Yüz yüze iletişimde ses tonu, mimik ve beden dili gibi unsurlarla
karşımızdaki kişinin bağlamını kolayca kurabiliyoruz. Ancak e-postalarda
bu mümkün olmuyor; elimizde sadece yazılan kelimeler kalıyor, bu yüzden
mesajın nasıl yazıldığı çok daha kritik hâle geliyor.

[click] Peki bu kelimeler etik dışı olduğunda bunu insan gözüyle mi,
yapay zekâyla mı tespit edeceğiz? İşte çalışmamız tam olarak bu
soruya cevap arıyor.
-->

---
layout: center
class: text-center
---

## 

<Page3 />

<!--
Literatürü incelediğimizde, e-posta ve dijital iletişim alanındaki çalışmaların genel olarak üç farklı eğilim etrafında toplandığını görüyoruz.

İlk eğilim, özellikle sosyal medya platformlarında toksik, saldırgan, hakaret içeren veya nefret söylemi barındıran ifadelerin tespitine yönelik çalışmalar. Bu çalışmalarda temel soru genellikle **“Bu dil zararlı mı?”** şeklinde karşımıza çıkıyor. Yani iletişimin toksik olup olmadığı, saldırganlık düzeyi veya nefret söylemi içerip içermediği sınıflandırılmaya çalışılıyor.

İkinci eğilim ise kurumsal e-postalar üzerinde gerçekleştirilen NLP ve makine öğrenmesi çalışmaları. Burada e-postalar; spam, phishing, dolandırıcılık, insider threat ve benzeri güvenlik problemlerinin tespiti için analiz ediliyor. Dolayısıyla temel odak, iletişimin **güvenli olup olmadığı veya bir tehdit içerip içermediği** üzerine kuruluyor.

[click] Üçüncü ve bizim çalışmamıza en yakın alan ise **Enron e-posta veri seti üzerinden gerçekleştirilen çalışmalar**. Bu çalışmalarda kurumsal iletişim ile etik arasındaki ilişkiyi farklı açılardan inceleniyor. Ancak burada amaç, e-postaları doğrudan **“etik” veya “etik dışı”** şeklinde sınıflandırmak değil. Daha çok şirket içerisindeki iletişim biçimlerinden hareketle yöneticilerin davranışları, güven, şeffaflık, kontrol ve kurumsal ilişkiler gibi kavramlar dolaylı olarak analiz ediliyor. Örneğin temel soru, şirket içerisinde etik açıdan problemli durumlar yaşanırken yöneticilerin e-posta iletişimlerinde nasıl bir dil kullandığı şeklinde ele alınıyor.

Dolayısıyla literatürde önemli bir boşluk ortaya çıkıyor: **Bir e-postanın güvenlik açısından tehdit oluşturup oluşturmadığını veya toksik olup olmadığını tespit etmeye yönelik çalışmalar bulunmasına rağmen, kurumsal iletişim bağlamında kullanılan dilin etik iletişim ilkelerine uygun olup olmadığını doğrudan sınıflandıran çalışmalar oldukça sınırlı.**

Biz bu noktada farklı bir soru soruyoruz:

[click] **“Bu e-posta dolandırıcılık mı?” değil.
“Bu e-posta toksik mi?” de değil.
Bizim sorumuz: “Bu e-posta, çalışanlar arasındaki etik kurumsal iletişime uygun mu?”**

Literatürde Türkçe kurumsal e-postalar üzerinde bu problemi doğrudan ele alan hazır ve yeterli bir veri setinin bulunmaması nedeniyle de veri setimizi kendimiz oluşturduk. Veri setimizde etik ve etik dışı iletişim örneklerini dengeli şekilde oluşturduk ve her bir örneği insan gözetiminden geçirerek veri setine dahil ettik.

[click] Böylece çalışmamızın amacı yalnızca **“e-postayı sınıflandırmak”** değil; yapay zekâ kullanarak **kurumsal iletişimde etik dışı dilin otomatik olarak tespit edilebilmesine yönelik bir temel oluşturmaktır.**
-->

---
layout: center
class: text-center
---

## Biz Ne Yaptık?

<br>

<Page4 />

<!--
Bu boşluğu ele almak amacıyla Türkçe kurumsal iletişime özgü bir veri
seti oluşturduk.

[click] Bu veri seti üzerinde önceden eğitilmiş BERTürk modelini
fine-tune ederek ikili bir etik dil sınıflandırıcısı geliştirdik.

[click] Son aşamada da modeli çalışan bir web tabanlı prototip sisteme
entegre ettik.
-->

---
layout: center
class: text-center
---

## Veri Seti

<Page5 />

<!--
Çalışmanın önemli bileşenlerinden biri probleme özgü veri setimiz.

[click] Toplam 3.222 benzersiz Türkçe kurumsal iletişim metni
oluşturduk ve bunları etik ve etik dışı olmak üzere iki sınıfa
ayırdık. Dengeli bir dağılım oluşturulmasına özen gösterdik.

[click] Etik dışı örneklerde hiyerarşik baskı, küçümseyici ifadeler,
pasif-agresif söylemler, tehditkâr dil ve mobbing niteliği taşıyan
iletişim biçimlerini temsil etmeyi hedefledik.
-->

---
layout: center
class: text-center
clicks: 3
---

## Verilerin Oluşturulması ve Güvenliği 

<Page6 />

<!--
[click] Metinlerin oluşturulmasında Claude ve ChatGPT gibi büyük dil
modellerinden yararlandık; ancak oluşturulan içerikleri doğrudan veri
setine aktarmadık.

[click] Her metin araştırmacılar tarafından tek tek incelendi. Metnin
kurumsal bağlama uygunluğu, doğal ve gerçekçi olması, anlamsal
tutarlılığı ve daha önce kullanılan bir örnekle birebir aynı olmaması
kontrol edildi. Sonrasında tüm örnekler yine araştırmacılar tarafından etik
veya etik dışı olarak etiketlendi. 

[click] Dolayısıyla model, BDM'nin verdiği etikete doğrudan eğitilmedi.
Üretim ile kabul arasında her zaman bir insan denetimi katmanı vardı.
-->

---
layout: center
class: text-center
---

## 

<Page7 />

<!--
Model tarafında ise BERTürk'ü tercih ettik.

[click] BERTürk, Türkçe için önceden eğitilmiş bir BERT modelidir ve
çalışmamızda kurumsal iletişim metinlerinin etik veya etik dışı olarak
sınıflandırılması için fine-tune edilmiştir.

BERTürk'ü tercih etmemizdeki önemli noktalardan biri, modelin yalnızca
belirli kelimeleri aramak yerine metni bağlama göre
değerlendirebilmesidir.
-->

---
layout: center
class: text-center
clicks: 3
---

## Eğitim + Doğrulama → Performans Değerlendirmesi

<Page8 />

<!--
Model eğitim ve doğrulama sürecinden geçirildikten sonra, performansını
eğitim sürecinden ayrılan 645 örneklik dengeli değerlendirme kümesi
üzerinde ölçtük.

[click] Burada doğruluk, kesinlik, duyarlılık ve F1 skorlarını kullandık.

Model seçiminde temel ölçüt olarak ise kesinlik ve duyarlılıkı birlikte
değerlendiren F1 skorunu esas aldık.

Sonuçlara baktığımızda modelimiz değerlendirme kümesinde
yüzde 99,84 doğruluk ve yüzde 99,845 F1 skoruna ulaştı. 

[click] Modelin hangi sınıflarda nasıl tahmin yaptığını daha ayrıntılı görmek için 
karmaşıklık matrisini oluşturduk.
Matrise baktığımızda 322 etik örneğin tamamının
doğru sınıflandırıldığını görüyoruz. 323 etik dışı örneğin ise 322'si
doğru sınıflandırılırken yalnızca bir örnek etik olarak tahmin edilmiş.

[click] Yani modelimiz bu değerlendirme kümesinde 645 örneğin 644'ünü doğru sınıflandırmış 
ve yalnızca 1 örnekte hata yapmıştır.

(Bu cümleden sonra bir saniye durun.)
-->

---
layout: center
class: text-center
---

## Peki Gerçek Hayatta?

<Page9 />

<!--
Ancak yüksek bir test skoru tek başına yeterli değil. Çünkü veri
setimiz kontrollü bir ortamda oluşturuldu.

Bu nedenle modelin daha önce görmediği 30 örnekten oluşan ek bir
stres testi gerçekleştirdik. Testte sert ama profesyonel iletişim,
pasif-agresif ve iğneleyici iletişim ve nötr iş mesajlarını
karşılaştırdık.

[click] Model 30 örneğin 27'sini doğru sınıflandırdı.

[click] Özellikle bizim için önemli olan, pasif-agresif kategorideki
10 örneğin tamamını etik dışı olarak tespit etti.

[click] Bununla birlikte modelin sert ama profesyonel iletişim ile
etik dışı iletişim arasındaki sınırda zaman zaman aşırı hassas
davrandığını da gördük.
-->

---
layout: center
class: text-center
---

## Örnek Etik Dışı Mail

<br>
<br>


<Page10 />

<!--
Konuşmanın başındaki maile geri dönelim. Malimizde baskılayıcı ve küçümseyici 
ifadelerin olduğunu konuşmuştuk. Gelin bu maili birlikte bizim web arayüzümüzde test edelim. 
-->

---
layout: center
class: text-center
clicks: 5
---


<Page11 />

<!--
Sistemimiz FastAPI tabanlı bir backend ile e-posta istemcisi arasında
bağlantı kuruyor.

[click] Kullanıcı gönder butonuna bastığında mesaj metin temizleme,
tokenizasyon ve çıkarım adımlarından geçerek analiz ediliyor.

[click] Etik dışı sınıfın olasılığı belirlediğimiz 0,60 eşik değerinin
üzerine çıkarsa,

[click] sistem gönderimi durduruyor ve kullanıcıya mesajını
düzenlemesi için geri bildirim veriyor.

-->


---
layout: center
class: text-center
---

## Katkımız

<Page12 />

<!--
Sonuç olarak bu çalışmada üç temel katkı sunduk.

[click] İlk olarak Türkçe kurumsal iletişim bağlamına özgü bir veri
seti oluşturduk.

[click] İkinci olarak bu veri üzerinde BERTürk tabanlı bir etik dil
sınıflandırma modeli geliştirdik.

[click] Üçüncü olarak modeli gerçek kullanım senaryosuna yaklaştıran
çalışan bir prototip sisteme entegre ettik.

[click] Elbette mevcut sonuçların oluşturduğumuz veri seti ve
gerçekleştirdiğimiz deneyler kapsamında değerlendirilmesi gerekiyor.
Bir sonraki aşamada farklı sektörlerden gerçek dünya verileriyle
veri setini genişletmek ve bağımsız veri kümeleri üzerinde doğrulama
yapmak istiyoruz.

Sonuç olarak bu çalışmayla amacımız yalnızca etik dışı bir e-postayı
sınıflandırmak değil.

[click] Kurumsal iletişimde problemli dilin, iletişim gerçekleşmeden
önce fark edilebildiği proaktif bir yapı ortaya koymak.

[click] Bu çalışmanın Türkçe kurumsal iletişimde etik dil
farkındalığının artırılmasına katkı sağlayabileceğini düşünüyoruz.
-->

---
layout: center
class: text-center
---

<Page13 />

<!--
Sunum sonunda modeli kendiniz de deneyebilirsiniz — QR kodu okutarak
canlı sisteme ulaşabilirsiniz.

Beni dinlediğiniz için teşekkür ederiz. Sorularınız varsa
memnuniyetle yanıtlarım.
-->



