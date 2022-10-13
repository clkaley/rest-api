# API (Application Programming Interface) Nedir?

Bir yazılımın gerçekleştirebildiği işlemlere belirli koşullar dahilinde dışarıdan erişilip bu işlemlerin kullanılmasını sağlayan arayüzdür. Kısaca, bir uygulamada gerçekleştirmek istediğimiz ek bir işlemi, o işlemi sağlayan başka bir uygulamadan API kullanarak gerçekleştirebiliriz.

##### Interface: telefonu açtığımızda youtube girdik uygulamanın bize sağladığı arayüzden istediğimiz videoya erişebiliyoruz. Arka planını bilmediğimiz uygulamanın arayüzünü kullanarak ulaşabiliriz.

##### Application Programming: İki yazılımın kodun birbiriyle iletişime geçmesidir.
</br>

* API Örnekleri
1. OOP Public Methods
2. Node.js FS Modülü, Go(lang) FMT Paketi
</br></br>

* Neden API Kullanırız?
1. API kullanımı bizi ilgili işlemin gerektireceği iş yükünden kurtarır. “API hayatı kolaylaştırır”.
2. API lar özel kullanıcı kitlelerine yönelik hazırlanırlar ve ilgili verileri hızlı bir şekilde oluşturmamızı sağlarlar. ( IMDB API, GitHub API ..)
3. Platform bağımsız çalışırlar.
4. Güncelleme durumunda bizim yapmamız gereken işlemler sınırlıdır.

</br>

API 'yi tanımlayan en iyi örnek-> garson bizle mutfak arasındaki api dir. 
https://www.youtube.com/watch?v=s7wmiS2mSXY



Müşteri menüye bakar garsona siparişi söyler.
![Ekran Görüntüsü (675)](https://user-images.githubusercontent.com/74673470/195401791-7c50aa94-4d2e-4aa0-bab6-848a9b2dccea.png)

Garson verilen siparişi (request'i) mutfağa iletir.
![Ekran Görüntüsü (676)](https://user-images.githubusercontent.com/74673470/195401792-b7f6f1b7-1e92-4a16-8559-2db5ac3d947e.png)

Garson mutfaktan gelen yemeği (response'u) müşteriye verir.
![Ekran Görüntüsü (677)](https://user-images.githubusercontent.com/74673470/195401797-89bbabb5-b712-4c79-b6c7-b6dc37896d54.png)




## REST (Representational State Transfer) API Nedir?
İlgili isteğe karşılık gelen verinin JSON / XML gibi dosya formatlarında gönderilmesidir.REST API, REST mimarisinin prensiplerine taşıyan API’lardır.
Rest dediğimiz şey aslında api nin son güncel durumundaki bilgileri kaynaktan alıp göndermesidir.

https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa/related?hl=tr (JSON Formatter) eklentisi
<br/> 

{JSON} Placeholder
Free fake API for testing and prototyping.
<br/> <br/> 

https://jsonplaceholder.typicode.com/users
http isteğiyle rest api json formatında veri döndü.
![Ekran Görüntüsü (678)](https://user-images.githubusercontent.com/74673470/195405665-054809fb-9a81-48e9-89f9-9dafeb46b990.png)

<br/> 

![Ekran Görüntüsü (679)](https://user-images.githubusercontent.com/74673470/195405668-f171f5df-e02d-4e14-808c-4abf5d80c270.png)

<br/><br/>


* REST Prensipleri
1. Client – Server
2. Uniform Interface
3. Statelessness
4. Cacheable
5. Layered System
6. Code On Demand - Optional



## REST Prensipleri
<br/>

#### Client-Server
İstemci isteği gönderen, sunucu da ilgili cevabı veren durumundadır. Birbirlerinin sorumluluk alanlarına girmezler. Birbirlerinden bağımsız programlama dilleri ve teknolojiler kullanabilirler.
<br/>

![client-server](https://user-images.githubusercontent.com/74673470/195564057-392bee01-69c9-474c-92d1-9ef33adea43a.jpg)
<br/><br/>

#### Uniform Interface
Aynı kaynağa yönelik olan tüm istekler, isteğin nereden geldiğinden bağımsız olarak aynı şekilde görünmelidir. Bu aynı zamanda istemci – sunucu bağımsızlığını da destekler. 4 temel özelliği bulunmaktadır.
<br/>

1. Identification of resources: kaynakların tanımlanması, bir kaynak için sunucuya yapılan istek benzersiz bir URI adresi ile tanımlanmalıdır.
 ```
  http://example.com/users(GET)
  http://example.com/users/11/posts(GET)
 ```
<br/>

 2. Manipulation of resources through representations

<br/>

 3. Self-descriptive messages
```
 Sunucu-> Content Type (JSON, XML)
 İstemci-> Aynı URI farklı methodlar ve farklı sonuçalar 
 (GET /users=>amaç kullanıcıları almaktır.) 
 (PUT /users=> amaç yeni kullanıcı eklemektir) 
```
<br/>


4. HATEOAS (Hypermedia As The Engine Of Application State)
Sunucu tarafından gönderilen cevap istenilen verinin yanında bazı ek aksiyonlar da içerebilir.
Ek bilgiler için:https://en.wikipedia.org/wiki/HATEOAS
<br/><br/>

#### Statelessness
State: Söz konusu veriyi veya durumu belirtir. React te düşünürsek herhangi bir component in o anki durumunu ifade eder.
Statefull(durum bilgisi olan)
Stateless(durum bilgisi olmayan).
Gerçek hayattan bir örnek vererek konuyu hayata uyarlayalım. Örneğin hep gittiğimiz bir kafe var ve bu kafade durmadan aynı siparişi mesela tiramisuyu söylüyoruz 1,2,3....15 artık ne olucak garson biz sipariş vermeden tatlımızı getirebilir. Burda garsonun artık durum hakkında bilgisi var yani (Statefull) dur. Ama ben her gittiğimde tekrar tekrar siparişi veriyorsam bu durum (Stateless) dur.

<br/><br/>

#### Cacheable
Sunucu gelen isteklere verilen cevapların önbelleklenebilir olup olmadığını belirtmelidir.
İhtiyacımız olan şeyin daha yakına alınması gibi.
Bir web sayfasına ilk girdiğimiz yükleme uzun sürer ama ondan sonra tekrar girdiğimizde sayfanın bilgileri cache klasöründe vardır ve bize onu getirir hemde öncekine göre daha kısa sürede(tabi güncelleme varsa bu bilgiyi yeniden çeker.) Performans artışını sağlar.
Örneğin “Cache-Control”, “Expires” gibi HTTP başlıkları önbellek ile ilgili bilgiler taşır.

<br/><br/>



#### Layered System 
İstemci – sunucu arasındaki ilişki katmanlara ayrılabilir, ve bileşenler sadece ilişkili oldukları katmanlara karşı sorumlu olurlar.
<br/>

![layered-system](https://user-images.githubusercontent.com/74673470/195564054-dd5dc18c-b7e3-4a2d-85f4-ce80b9d57550.jpeg)
<br/><br/>

#### Code On Demand - Optional
Sunucu, istemci tarafına istemcinin işlevini genişletecek ek kodlar gönderebilir. Bu özellik istemci tarafında yapılması gereken işlemleri hafifletir.
Örneğin sunucu, istemci tarafına döneceği HTML dökümanın içerisine JavaScript kodları ekleyebilir.
<br/><br/>