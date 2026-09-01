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

# Detecting Unethical Language
# in Turkish Corporate Emails

### Türkçe Kurumsal E-Postalarda
### Etik Dışı Dil Tespiti

<br>

**Kübra Çetinkaya** · **Sezi Güngörmüş** · **Şerif Ali Sadık**

Kütahya Dumlupınar Üniversitesi

<br>

IDAP'26 · 2026

<!--
Merhaba, bugün sizlere Türkçe kurumsal e-postalarda etik dışı dil
kullanımının yapay zekâ ile otomatik olarak tespit edilmesine yönelik
gerçekleştirdiğimiz çalışmayı sunacağım.

Çalışmamızda özellikle kurumsal iletişimde karşımıza çıkabilen
pasif-agresif, küçümseyici, baskılayıcı ve benzeri etik dışı dil
örüntülerine odaklandık.
-->

---
layout: center
class: text-center
---

## 

<Page1 />

<!--
Etik dışı dil dediğimizde genellikle aklımıza hakaret, küfür, nefret söylemi
veya açık saldırganlık geliyor.

Fakat kurumsal iletişimde problem her zaman bu kadar açık değil.

Örneğin burada doğrudan bir hakaret bulunmuyor. Ancak kullanılan dil
baskılayıcı ve pasif-agresif bir iletişim biçimi oluşturabiliyor.

[click] Pasif-agresif, baskılayıcı, küçümseyici — bunlar hakaret gibi
sözlükte aranan kelimeler değil.

[click] Dolayısıyla problem yalnızca kötü kelimeleri tespit etmek değil;
iletişim biçimini ve bağlamı anlayabilmek.
-->

---
layout: center
class: text-center
---

## Neden Kurumsal E-Posta?

<Page2 />

<!--
Dijitalleşmeyle birlikte kurum içi iletişim de önemli ölçüde dijital
kanallara taşındı.

[click] Özellikle e-posta gibi yazılı iletişim kanallarında tonlama ve
beden dili gibi bağlam sağlayan unsurlar ortadan kalktığı için, mesajın
nasıl algılandığı daha kritik hâle geliyor.

[click] Bu nedenle kurumsal iletişimde etik dışı dilin tespiti, yalnızca
bir NLP problemi değil, aynı zamanda çalışma ortamının iletişim
kalitesiyle ilişkili bir problem.
-->

---
layout: center
class: text-center
---

## Literatürdeki Boşluk

<Page3 />

<!--
Literatürü incelediğimizde burada iki farklı eğilim görüyoruz.

Bir tarafta sosyal medya ve çevrim içi platformlarda toksik, saldırgan
ve hakaret içeren dilin tespitine yönelik çalışmalar var.

Diğer tarafta kurumsal e-postalar üzerinde NLP çalışmaları bulunuyor;
ancak bunların önemli bir bölümü dolandırıcılık, phishing veya insider
threat gibi güvenlik problemlerine odaklanıyor.

[click] Bizim çalışmamız ise bu ikisinin arasında kalan, ancak doğrudan
hedeflenmemiş bir probleme odaklanıyor: kurum içerisindeki gündelik
etik dışı iletişim.

[click] Yani bizim sorumuz "Bu e-posta dolandırıcılık mı?" değil;
"Bu e-posta çalışanlar arası etik iletişime uygun mu?"
-->

---
layout: center
class: text-center
---

## Biz Ne Yaptık?

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
ayırdık. Dengeli bir dağılım oluşturulmasına özen gösterildi.

[click] Etik dışı örneklerde hiyerarşik baskı, küçümseyici ifadeler,
pasif-agresif söylemler, tehditkâr dil ve mobbing niteliği taşıyan
iletişim biçimlerini temsil etmeyi hedefledik.
-->

---
layout: center
class: text-center
---

## Veriyi Nasıl Güvenilir Hale Getirdik?

<Page6 />

<!--
Burada özellikle veri setinin oluşturulma sürecini vurgulamak istiyoruz.

[click] Metinlerin oluşturulmasında Claude ve ChatGPT gibi büyük dil
modellerinden yararlandık; ancak oluşturulan içerikleri doğrudan veri
setine aktarmadık.

[click] Her metin araştırmacılar tarafından tek tek incelendi. Metnin
kurumsal bağlama uygunluğu, doğal ve gerçekçi olması, anlamsal
tutarlılığı ve daha önce kullanılan bir örnekle birebir aynı olmaması
kontrol edildi. Sonrasında tüm örnekler yine insan gözetiminde etik
veya etik dışı olarak etiketlendi.

[click] Dolayısıyla model, BDM'nin verdiği etikete doğrudan eğitilmedi.
Üretim ile kabul arasında her zaman bir insan denetimi katmanı vardı.
-->

---
layout: center
class: text-center
---

## Neden BERTürk?

<Page7 />

<!--
Model tarafında ise BERTürk'ü tercih ettik.

[click] BERTürk, Türkçe için önceden eğitilmiş bir BERT modelidir ve
çalışmamızda kurumsal iletişim metinlerinin etik veya etik dışı olarak
sınıflandırılması için fine-tune edilmiştir.

[click] Buradaki önemli nokta, modelin yalnızca belirli kelimeleri
aramak yerine metni bağlamsal olarak temsil etmesidir.
-->

---
layout: center
class: text-center
---

## Eğitim → Değerlendirme

<Page8 />

<!--
Model eğitim ve doğrulama sürecinden geçirildikten sonra, performansını
eğitim sürecinden ayrılan 645 örneklik dengeli değerlendirme kümesi
üzerinde ölçtük.

[click] Burada accuracy, precision, recall ve F1 skorlarını kullandık.

Model seçiminde temel ölçüt olarak ise precision ve recall'u birlikte
değerlendiren F1 skorunu esas aldık.

[click] Sonuçlara baktığımızda modelimiz değerlendirme kümesinde
yüzde 99,84 doğruluk ve yüzde 99,845 F1 skoruna ulaştı. Burada
accuracy, precision, recall ve F1 skorlarını kullandık; model
seçiminde temel ölçüt olarak precision ve recall'u birlikte
değerlendiren F1 skorunu esas aldık.

[click] Karmaşıklık matrisine baktığımızda 322 etik örneğin tamamının
doğru sınıflandırıldığını görüyoruz. 323 etik dışı örneğin ise 322'si
doğru sınıflandırılırken yalnızca bir örnek etik olarak tahmin edilmiş.

[click] Yani bu değerlendirme kümesinde yalnızca bir yanlış negatifimiz
var ve hiç yanlış pozitifimiz yok.

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

(Bu, sadece başarıyı anlatıp geçmediğimiz, dürüst bir bulgu —
makale de tam olarak bu sınırlılığı belirtiyor.)
-->

---
layout: center
class: text-center
---

## Modeli Gerçek Sisteme Dönüştürdük

<Page10 />

<!--
Çalışmayı yalnızca bir sınıflandırma modeli olarak bırakmadık.

Modeli bir e-posta istemcisi prototipine entegre ettik. Sistem
FastAPI tabanlı bir backend ile e-posta istemcisi arasında bağlantı
kuruyor.

[click] Kullanıcı gönder butonuna bastığında mesaj metin temizleme,
tokenizasyon ve çıkarım adımlarından geçerek analiz ediliyor.

[click] Etik dışı sınıfın olasılığı belirlediğimiz 0,60 eşik değerinin
üzerine çıkarsa,

[click] sistem gönderimi durduruyor ve kullanıcıya mesajını
düzenlemesi için geri bildirim veriyor.

(Şimdi gerçek sistemden canlı bir demo göstereceğim — 45-60 saniye
sürecek. Önce etik bir mesaj: "Toplantı notlarını müsait olduğunuzda
paylaşabilir misiniz?" → gönderilebilir. Sonra etik dışı bir mesaj:
"Bu raporu hâlâ göndermemiş olmanız kabul edilebilir değil..." →
gönderim engellenir.)
-->

---
layout: center
class: text-center
---

## Ne Kazandık?

<Page11 />

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
-->

---
layout: center
class: text-center
---

<Page12 />

<!--
Sonuç olarak bu çalışmayla amacımız yalnızca etik dışı bir e-postayı
sınıflandırmak değil.

[click] Kurumsal iletişimde problemli dilin, iletişim gerçekleşmeden
önce fark edilebildiği proaktif bir yapı ortaya koymak.

[click] Bu çalışmanın Türkçe kurumsal iletişimde etik dil
farkındalığının artırılmasına katkı sağlayabileceğini düşünüyoruz.

[click] Bizi dinlediğiniz için teşekkür ederiz. Sorularınızı
memnuniyetle yanıtlarız.
-->

---
layout: center
class: text-center
---

## Modeli Deneyin

<Page13 />

<!--
Sunum sonunda modeli kendiniz de deneyebilirsiniz — QR kodu okutarak
canlı sisteme ulaşabilirsiniz.
-->
