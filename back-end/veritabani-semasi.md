# 🏗️ Veritabanı Şeması

![](../.gitbook/assets/untitled-diagram.png)

{% file src="../.gitbook/assets/db.pdf" caption="👀 DB Şeması" %}

## 🎤 Açıklama

* 🏗️ Yapı temel iki kısımdan oluşmakta
  * 👤 User \(ve ona bağlı yapılar\)
  * 📦 Object
* 👮‍♀️ Object yapısı ve fonksiyonelliği User, Quiz ve Tip yapılarından tamamen bağımsızdır
* 🗃️ Kullanıcının yaptığı quizler solvedQuiz tablosu \(ara tablo olarak\) aracıyla tutulmakta
* 🗃️ Kullanıcının gördüğü tip'ler seenTip tablosu \(ara tablo olarak\) aracıyla tutulmakta

 

## 📝 Notlar

* 👮‍♂️ Şıklara özgü işlem yapılmayacağı için `Şık` tablosu kurulmamıştır
* ⚙️ Şıklar, `options` alanından çıkarılacak
  * ✨ String Parsing işlemi sorgulardan daha az külfetlidir

