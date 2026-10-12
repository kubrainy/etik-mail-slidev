# Türkçe Kurumsal E-Postalarda Etik Dışı Dil Tespiti

**Detecting Unethical Language in Turkish Corporate Emails**

> Bu çalışma **IDAP'26** kapsamında **Marmara Üniversitesi**'nde sunulmuştur.
> Makale **IEEE Xplore**'da yayınlanma sürecindedir.

Bu depo, çalışmanın konferans sunumunun [Slidev](https://sli.dev) ile hazırlanmış kaynak kodunu içerir.

**Yazarlar:** Kübra Çetinkaya, Sezi Güngörmüş, Şerif Ali Sadık
**Kurum:** Kütahya Dumlupınar Üniversitesi

## Bağlantılar

| | |
|---|---|
| Canlı demo | [etikmail.kubrainy.me](https://etikmail.kubrainy.me/) |
| Uygulama kodu | [github.com/kubrainy/etik-mail](https://github.com/kubrainy/etik-mail) |
| Model | [huggingface.co/kubrainy/etik-mail-toxic-model](https://huggingface.co/kubrainy/etik-mail-toxic-model) |
| Veri seti | [huggingface.co/datasets/kubrainy/etik-mail-dataset](https://huggingface.co/datasets/kubrainy/etik-mail-dataset) |
| Sunum (PDF) | [slides-export.pdf](./slides-export.pdf) |

## Çalışma Hakkında

Kurumsal e-postalarda etik dışı dil her zaman açık hakaret veya küfür olarak ortaya çıkmaz; baskılayıcı, küçümseyici ya da pasif-agresif ifadeler de karşı tarafta rahatsızlık yaratabilir. Literatürdeki çalışmalar çoğunlukla toksik dil tespitine veya spam/phishing gibi güvenlik problemlerine odaklanırken, bu çalışma farklı bir soru soruyor:

> *“Bu e-posta, çalışanlar arasındaki etik kurumsal iletişime uygun mu?”*

### Veri Seti

- **3.222** benzersiz Türkçe kurumsal iletişim metni; **etik** ve **etik dışı** olmak üzere dengeli iki sınıf
- Etik dışı örnekler hiyerarşik baskı, küçümseyici ifadeler, pasif-agresif söylemler, tehditkâr dil ve mobbing niteliği taşıyan iletişimi kapsar
- Metinlerin üretiminde büyük dil modellerinden (Claude, ChatGPT) yararlanılmış; her metin araştırmacılar tarafından tek tek incelenip elle etiketlenmiştir

### Model

[BERTürk](https://huggingface.co/dbmdz/bert-base-turkish-cased) (`dbmdz/bert-base-turkish-cased`), ikili etik dil sınıflandırması için fine-tune edilmiştir (`BertForSequenceClassification`).

### Sonuçlar

Eğitimden ayrılan 645 örneklik dengeli değerlendirme kümesinde:

| Doğruluk | Kesinlik | Duyarlılık | F1 |
|:---:|:---:|:---:|:---:|
| %99,845 | %100 | %99,690 | %99,845 |

Model 645 örneğin 644'ünü doğru sınıflandırmıştır. Modelin daha önce görmediği 30 örnekle yapılan stres testinde 30 örneğin 27'si doğru sınıflandırılmış, pasif-agresif kategorideki 10 örneğin tamamı etik dışı olarak tespit edilmiştir.

### Prototip

FastAPI tabanlı bir backend, e-posta istemcisine bağlanır. Kullanıcı gönder butonuna bastığında mesaj metin temizleme, tokenizasyon ve çıkarım adımlarından geçer; etik dışı sınıfın olasılığı **0,60** eşiğini aşarsa gönderim durdurulur ve kullanıcıya mesajını düzenlemesi için geri bildirim verilir.

## Sunumu Çalıştırma

```bash
pnpm install
pnpm dev      # http://localhost:3030 adresinde açılır
pnpm build    # statik çıktıyı dist/ klasörüne üretir
pnpm export   # sunumu PDF olarak dışa aktarır
```

Slayt akışı ve konuşmacı notları [slides.md](./slides.md) dosyasındadır; her slaydın içeriği [components/](./components/) altındaki `Page0.vue` … `Page13.vue` bileşenlerinde yer alır.

## Destek

Bu çalışma **TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma Projeleri Destekleme Programı** kapsamında desteklenmiştir.

## Atıf

Makale IEEE Xplore'da yayınlandığında atıf bilgisi buraya eklenecektir.
