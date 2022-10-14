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

<br/>

#### Cacheable
Sunucu gelen isteklere verilen cevapların önbelleklenebilir olup olmadığını belirtmelidir.
İhtiyacımız olan şeyin daha yakına alınması gibi.
Bir web sayfasına ilk girdiğimiz yükleme uzun sürer ama ondan sonra tekrar girdiğimizde sayfanın bilgileri cache klasöründe vardır ve bize onu getirir hemde öncekine göre daha kısa sürede(tabi güncelleme varsa bu bilgiyi yeniden çeker.) Performans artışını sağlar.
Örneğin “Cache-Control”, “Expires” gibi HTTP başlıkları önbellek ile ilgili bilgiler taşır.

<br/>



#### Layered System 
İstemci – sunucu arasındaki ilişki katmanlara ayrılabilir, ve bileşenler sadece ilişkili oldukları katmanlara karşı sorumlu olurlar.
<br/>

![layered-system](https://user-images.githubusercontent.com/74673470/195564054-dd5dc18c-b7e3-4a2d-85f4-ce80b9d57550.jpeg)
<br/>

#### Code On Demand - Optional
Sunucu, istemci tarafına istemcinin işlevini genişletecek ek kodlar gönderebilir. Bu özellik istemci tarafında yapılması gereken işlemleri hafifletir.
Örneğin sunucu, istemci tarafına döneceği HTML dökümanın içerisine JavaScript kodları ekleyebilir.
<br/><br/><br/>





## HTTP (Hyper Text Transfer Protocol) Nedir? 
İstemci ile sunucu arasındaki veri akışının kurallarını belirleyen protokoldür. Request, Response modeline göre çalışır. Burdaki isteğin ve cevabın belirli bir formatta olması gerekir.

<br/>

![HTTP](https://user-images.githubusercontent.com/74673470/195684275-ce929192-c609-4b52-b9bc-dfffb9e7a90b.jpeg)



##### REST Mimarisinde HTTP'nin Rolü
REST mimarisinin prensiplerinde istemci - sunucu çalışma modelidir. Biz bir istekte bulunuruz ve sunucu isteğimize karşılık olan durumu (state) bize bir sunum (presentation) olarak gönderir. HTTP protokolü burada bu sunum transferi için kurulan iletişimin kurallarını belirler. REST mimarisine uygun API'ların neredeyse tamamında HTTP protokolü kullanılır.


#### HTTP Request
İstek (Request) yapısını belirtir. 4 bölümden oluşur.
<br/>

![Request](https://user-images.githubusercontent.com/74673470/195685107-7cdc0219-f5dd-4ccf-9249-a5ec7ae96206.png)

https://developer.mozilla.org/en-US/docs/Web/HTTP

Request Line: Kullanılacak http metodu ve gidilecek olan path ve http versiyon belirtilir.
<br/>
Request Headers: Yapılan isteğin özelliklerini belirtir. (Content-Length:gönderilen başlığın uzunluğu)
<br/>
Blank Line: Header özellikleri ile msaj body' yi ayırmak
<br/>
Request Message Body:Bu istekte ne yapmak istediğimizi belirtir.
<br/>

#### HTTP Response

![Response](https://user-images.githubusercontent.com/74673470/195685113-fc5b8a02-bb60-4635-812f-3dbcb402216a.png)

<br/>

Status Line: protokol versiyonu http status kod döner. İsteğin başarılı olup olmadığına dair bilgiler döner.
<br/>
Response Headers:Cevaba ait özellikler taşır.
<br/>
Blank Line:Header özellikleri ile msaj body' yi ayırmak
<br/>
Response Message Body: Cevabın html sayfası
<br/>

![Ekran Görüntüsü (681)](https://user-images.githubusercontent.com/74673470/195694977-b7435c11-94e0-48d9-9c9f-0ad0da50de1c.png)

<br/><br/>

## HTTP Status Codes
Sunucu tarafından ilgili isteğin sonucunu belirten, 3 rakamdan oluşan sayısal ifadelerdir.


![Ekran Görüntüsü (682)](https://user-images.githubusercontent.com/74673470/195696624-e105562f-4d52-4c63-85e8-d61171621da5.png)

<br/>

https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information_responses

<br/>

1. Informational Responses
100: Continue
102: Processing
<br/>

2. Successful Responses
200 OK 
201 Created
204 No Content
<br/>

3. Redirections 
300 Multiple Choice
301 Moved Permanently (kaynak adresi kalıcı olarak değiştirildi)
304 Not Modified (değişiklik yok)
<br/>

4. Client Errors
400 Bad Request
401 Unauthorized (istemci istekte bulunurken gerekli kimlik doğrulaması yapılmamıştır.)
403 Forbidden (Yetkinin olmadığı işlem yapmak)
404 Not Found (bulunmayan kaynağa istek bulunmak)
405 Method Not Allowed (get requeste put request göndermek)
<br/>

5. Server Errors
500 Internal Server Error (istemci tarafından istek başarılı sunucu tarafından cevap dönmüyor)
503 Service Unavailable (Server tarafında bakım varsa)
<br/>



## HTTP Methods

https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods
<br/>
<br/>

##### Get 
Verileri almak ve listelemek için kullanılan istek metot.

```
GET
http://example.com/users
```
<br/>



##### Post 
Belirli bir kaynağa veri göndermek için kullanılır.

```
POST
http://example.com/users
```
<br/>

##### Put 
Belirli bir kaynaktaki verinin tamamının değiştirilmesi için kullanılan metot. Gönderdiğimizde verinin body sinde bulunan her şeyi göndermemiz gerekiyor :)

```
PUT
http://example.com/users/1
{ “name": "Ali", "surname": "Ezer"}
```
<br/>


##### Patch 
Belirli bir kaynaktaki verilerin bir kısmının değiştirilmesi için kullanılan metot.

```
PATCH
http://example.com/users/1
{ "name": "Ahmet"}
```
<br/>


##### Delete 
Belirli bir kaynaktaki verilerin silinmesi için kullanılan metot.

```
DELETE
http://example.com/users/1
```
<br/>

##### Connect 

##### Options 
İlgili URL de izin verilen metotları içerir.
<br/>

##### Trace 
Genelde debug metotları için kullanılır
<br/>

##### Head 
Get metoduna benziyor ama yalnızca header bilgisini alabiliyoruz.

<br/>

#### Safe Metodlar
GET, HEAD, OPTIONS: Sunucu "state" tarafında değişiklik oluşturmazlar. "Read-Only" yapısındadır.
<br/>

#### IDEMPOTENT (etkisiz) Metotlar
GET – HEAD - OPTIONS – DELETE – PUT – TRACE : Tekrar durumunda sunucu state yapısında herhangi bir yan etki bırakmazlar. Safe metodlar, idempotent'tır. 
<br/><br/>


### Endpoint (Sorgu Adresi)
REST API kullanımında gönderilen istek ile verilen cevap için belirlenen buluşma noktasıdır.
<br/>
Root(Base) /Path yapısından oluşur, isimler kullanılır, fiil ilgili HTTP metodu ile belirtilir. Dökümantasyon tarafından belirtilir.

```
https://jsonplaceholder.typicode.com/posts
.com a kadar base root
/posts ise resource verir
```


<br/>

Değişen değer için genelde (:) kullanılır.
```
https://jsonplaceholder.typicode.com/posts/1 =>
/posts/:id veya /posts/{{id}}
```

<br/>
Sorgu parametreleri için (?) kullanılır.

```
http://example.com/articles?sort=author
```
<br/><br/>



## JSON (JavaScript Object Notation) Nedir?
Veri depolamak veya veri iletmek için kullanılan metin tabanlı söz dizimidir.

https://www.json.org/json-en.html
<br/>

#### JSON Veri Tipleri

String: "String", 
<br/>
Number: 7, 3.2, 
<br/>
Boolean: true, false
<br/>
Null: null
<br/>
Array: ["İstanbul", "Ankara", "Malatya"] Array içerisinde kullanılan değerler sıralı olarak listelenebilir.
<br/>
Object { "name": "Ali", "age":24 } JSON nesneleri verileri key-value çiftleri olarak tanımlar.
<br/>

 JSON dosyaları bir array, nesne ve/veya bunların iç içe geçmiş formlarından oluşur.