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



 ## JSON/JavaScript/XML 



#### JSON vs JavaScript
JavaScript web uygulamalarında sıklıkla kullanılan dinamik bir programlama dilidir. JSON ise bir söz dizim olarak JavaScript'in bir alt kümesi olarak düşünülebilir. Bu nedenle uygun JSON formatındaki bir içerik JavaScript ifadesine (expression) denk gelir.
 ![Ekran Görüntüsü (684)](https://user-images.githubusercontent.com/74673470/195784976-5e86147b-84a8-49f6-9d59-6bfb41444a93.png)



#### JSON vs XML
eXtensible Markup Language ifadesinin kısaltmasıdır. Veri depolamak ve iletmek için kullanılan bir script dilidir.
<br/>
https://www.w3schools.com/xml/default.asp

![Ekran Görüntüsü (685)](https://user-images.githubusercontent.com/74673470/195785823-2f0da0f6-268f-4527-8ab5-f8b85a29a975.png)
<br/>

JSON formatının XML formatına göre en büyük avantajı, doğalında bir nesne modeline sahip olmasıdır. Bu özellik sayesinde birçok programlama dili JSON verileri daha kolay bir şekilde işleyebilir.



## Postman
Postman bir API platformudur. API geliştirmek , test etmek ve/veya hazır bir API kullanımı için gerekli isteklerde bulunabileceğimiz bir uygulamadır. 
<br/>
Postman kurulumu ve kullanımı için resmi dökümantasyon: https://learning.postman.com/docs/getting-started/introduction/
<br/>


Request:  GET: https://jsonplaceholder.typicode.com/users
<br/>

Response
![Ekran Görüntüsü (686)](https://user-images.githubusercontent.com/74673470/195790189-ab26ed49-7b6b-4633-a992-b3c75b029752.png)



## SWAPI API
https://swapi.dev/

Dokümantasyonu=> https://swapi.dev/documentation

Base URL: apı nin kök adresidir. Yapacağımız tüm istekler bu adresi barındırır.
https://swapi.dev/api/
<br/>
Postman'de yapılan istekler için bu şekilde dizin kullanılabilir örnek olarak dosyalama şekli aşağıdaki gibidir.

![Ekran Görüntüsü (698)](https://user-images.githubusercontent.com/74673470/196028219-26952caf-f49a-47b2-b287-b0a75ddf2316.png)

<br/><br/>
GET ALL FILMS=> https://swapi.dev/api/films

![Ekran Görüntüsü (688)](https://user-images.githubusercontent.com/74673470/196028322-739ad566-8bf8-4494-9606-c45426ed7c66.png)
<br/>

![Ekran Görüntüsü (696)](https://user-images.githubusercontent.com/74673470/196028691-9a60c586-c001-41dc-8932-e9b495401d6c.png)
<br/><br/>
GET A FILMS=> https://swapi.dev/api/films/2/

![Ekran Görüntüsü (699)](https://user-images.githubusercontent.com/74673470/196028428-fcf422a9-5531-4b7a-ae5a-2a462c38a63c.png)
<br/><br/>

Postman da baseURL eklemek
![Ekran Görüntüsü (690)](https://user-images.githubusercontent.com/74673470/196028470-6f1216d4-e268-4d35-b56d-ee35f3e15bbd.png)
<br/><br/>

baseURL'i diğer sorgulara eklemek için{{baseURL}} kullanılır.

![Ekran Görüntüsü (691)](https://user-images.githubusercontent.com/74673470/196028515-c88b9684-595d-41c9-951a-70b1093c6fb5.png)

![Ekran Görüntüsü (692)](https://user-images.githubusercontent.com/74673470/196028517-49b1dc7b-2950-446a-93af-a0f7f0609e1d.png)
<br/><br/>

<br/><br/>
SEARCH FILM=> https://swapi.dev/api/films/?search=Hope

?search=r2
? => burda query sorgu parametresi yaptığımızı söylüyor.
search=> sorgu paremetresi key değerine denk geliyo. Yani bir şey sorgularken key=search oluyor.

![Ekran Görüntüsü (695)](https://user-images.githubusercontent.com/74673470/196028584-a63e8df8-7bf7-48db-b833-dd27c015545f.png)
<br/> <br/>


## The Movie Database API (TMDBAPI)
Öncelikle üye işlemi gerçekleştirilir.
Ayarlardan API kısmına gelip api key i oluşturmamız gerekiyor. Yapılacak işlemler için giriş anahtarı olarak düşünülebilir.
<br/>

* GET Popular Films=>https://api.themoviedb.org/3/movie/popular?api_key=<<api_key>>&language=en-US&page=1

![Ekran Görüntüsü (702)](https://user-images.githubusercontent.com/74673470/196352527-a1f78bd7-9192-4b74-a4ae-cb56b0a3b062.png)

```
{
    "status_code": 7,
    "status_message": "Invalid API key: You must be granted a valid key.",
    "success": false
}
```
Burda alınan hata api key i üye olduktan sonra api bölümünden almıştık. Aldığımız key i oraya yerleştiriyoruz. Alınan key value değerine yapıştırılır.


![Ekran Görüntüsü (703)](https://user-images.githubusercontent.com/74673470/196353097-80d3017a-6504-482d-8692-61622dc4aaf8.jpg)

<br/>

Birden fazla kimlik doğrulama seçenekleri var

![Ekran Görüntüsü (704)](https://user-images.githubusercontent.com/74673470/196354142-19f4dd67-d3a4-4814-9536-e0bf0648edc1.jpg)

<br/>
Biz api key ile kimlik doğrulamasını seçtiimizde sayfa böyle şekillenir.

![Ekran Görüntüsü (705)](https://user-images.githubusercontent.com/74673470/196354283-cd0616d8-ed87-4eb7-8f7f-1afa3efbf053.jpg)

<br/>
Ardından bizde boşluk olan yeri dokümantasyon bize nasıl diyorsa öyle doldururuz.

![Ekran Görüntüsü (706)](https://user-images.githubusercontent.com/74673470/196354518-a2ce34f5-ecb0-42ee-8d78-ae3f6b057809.jpg)

<br/>

Dokümantasyon kısmında key in query parametre olduğu yazıyor :)

![Ekran Görüntüsü (708)](https://user-images.githubusercontent.com/74673470/196354863-4b71f877-27c8-4256-be49-e370387b89d6.png)

<br/>

baseURL oluşturma ve query e ekleme

![Ekran Görüntüsü (711)](https://user-images.githubusercontent.com/74673470/196355517-1bd6b9a0-801e-4e49-8367-caa904144582.png)
s
![Ekran Görüntüsü (712)](https://user-images.githubusercontent.com/74673470/196355525-e2b9fa00-d757-4fe0-b1a6-d16040741fe4.png)

<br/>

!!! Farklı collectionlar da aynı isimde değişkenler olabilir. Biz SWAPI de baseURL kullandık burda da ama değişkenlerin scope u collection lara bağlı.
<br/>

GET A FILM DETAIL=>https://api.themoviedb.org/3/movie/{movie_id}?api_key=<<api_key>>&language=en-US

{movie_id} içinde bulunan movie_id kısmı postman da :movie_id şeklinde gösterilir.baseURL oluşturmuştuk onu da ekleyebiliriz.

![Ekran Görüntüsü (713)](https://user-images.githubusercontent.com/74673470/196359128-90c50a0c-e68c-4a4a-9ea0-415b55d26e7f.png)

Verilen hata api key inin olmaması
<br/>


Bunu düzeltmek için api key ini eklicez burda authorization kısmına geliyoruz zaten mevcut kaydedip sorgulamayı başlatıyoruz.

![Ekran Görüntüsü (715)](https://user-images.githubusercontent.com/74673470/196388664-7ce6f734-1424-4adb-b83c-470678f8b673.jpg)

<br/>

POST=>https://api.themoviedb.org/3/movie/{movie_id}/rating?api_key=<<api_key>>

baseURL api key eklendi ama hata verdi iznimiz yok filmi oylamaya

![Ekran Görüntüsü (716)](https://user-images.githubusercontent.com/74673470/196389835-56caf0a1-fa3f-4471-996a-9942fa2bd34a.jpg)
<br/>

Burda bize post metodunu kullanırken açıklama session istiyor. Ynai oturum açılması gerekiyor. Peki bunu nasıl yapıcaz dokümantasyonda detaylıca anlatılıyor. 
https://developers.themoviedb.org/3/authentication/how-do-i-generate-a-session-id

![Ekran Görüntüsü (717)](https://user-images.githubusercontent.com/74673470/196390138-09407695-8891-468e-916b-316bde58bb62.png)

<br/>

1. Create a request token

Token:Tek kullanımlık yaşam süresi olan hashlenmiş yada şifrelenmiş bir bilgi içeren metinlerdir.
Token almak için tekrar bir istekte bulunmamız gerekiyor bunun için

GET Authentication=> https://api.themoviedb.org/3/authentication/token/new?api_key=<<api_key>>

![Ekran Görüntüsü (718)](https://user-images.githubusercontent.com/74673470/196391461-48a2e555-ee50-4a7b-bf77-37b1c26d19c3.jpg)

 <br/>
 Alınan token collection a eklendi.

 ![Ekran Görüntüsü (720)](https://user-images.githubusercontent.com/74673470/196393910-7f7c4d22-ecf9-432d-9538-e0f9bc37066e.jpg)

 <br/>

2. Ask the user for permission
https://www.themoviedb.org/authenticate/{REQUEST_TOKEN} direkt url e gidilir ve izin alınır.


3. Create a session ID
POST=> https://api.themoviedb.org/3/authentication/session/new?api_key=<<api_key>>

baseURL eklendi ve sorgulama yaparken request body e token eklenmesi gerekiyorud o da eklendikten sonra session_id oluşturuldu.

![Ekran Görüntüsü (722)](https://user-images.githubusercontent.com/74673470/196395623-b0a54e4e-b45c-43f8-b143-2bc16a193466.jpg)
<br/>

Oluşturulan session id de variable a eklendi.

![Ekran Görüntüsü (724)](https://user-images.githubusercontent.com/74673470/196396411-6475ddd1-997f-4714-8b21-5c55c449b21b.jpg)
<br/>

{{session_id}} şu şekilde çünkü tmdb variable içinde tanımladık baseURL gibi :)

![Ekran Görüntüsü (725)](https://user-images.githubusercontent.com/74673470/196397668-ffc17294-9cf9-465d-8997-c6e07c7ad882.png)

<br/>


DELETE=> https://api.themoviedb.org/3/movie/{movie_id}/rating?api_key=<<api_key>>

![Ekran Görüntüsü (726)](https://user-images.githubusercontent.com/74673470/196398730-b8907b66-7593-4b4e-95c1-36ea09497828.jpg)

<br/>

Authorizatipn için api_key ya da Bearer Token kullanılabilir oda aynı şekilde Auth kısmında Bearer seçilerek oluşturulur.

![Ekran Görüntüsü (727)](https://user-images.githubusercontent.com/74673470/196400285-4f1263ce-bf56-4e9f-b37e-6758d39d3388.png)


<br/>

## FAKE API

##### Fake API Avantajları
1. Frontend (Ön yüz) tarafı hazır olan bir uygulamayı test etmek isteyebiliriz.
2. Yapmayı düşündüğümüz bir Backend (Arka yüz) çalışması için bir prototip oluşturmak isteyebiliriz.
3. Postman gibi bir API platformunda farklı HTTP metotlarına ait istekler gerçekleştirmek isteyebiliriz.
<br/>

FAKE REST API oluşturmak için json-server npm paketinden faydalanacağız. Öncelikle dosya dizinine aşağıdaki komut ile package.json dosyası oluşturacağız.

```
npm init 
```
<br/>

aşağıdaki komut ile json-server paketini indiriyoruz.
```
npm i json-server
```
<br/>

Employees adlı json dosyası oluşturuldu.

Bu json dosyasını çalıştırmak için 

```
json-server --watch employees.json
```
<br/>

Bunu script tagleri içine yazabiliriz package.json scripts start kısmını şu şekilde revize edelim.
```
  "scripts": {
    "start:server": "json-server -- watch api/employees.json"
  },
```
<br/>


Server başlatmak için aşağıdaki komut yazılır.
```
npm run start:server
```

3000 portunda çalışıyoruz. 
![Ekran Görüntüsü (730)](https://user-images.githubusercontent.com/74673470/196668836-265b4974-007a-432e-9328-0df07f200530.png)

![Ekran Görüntüsü (731)](https://user-images.githubusercontent.com/74673470/196668840-521eb8a7-46be-4a06-9d51-e588b975721d.png)

<br/>

Postman da yeni colleciton oluşturuyoruz ismi FAKE API. Burda ilk request i atıcaz çalışan portta yazan linki yazıp request i send ediyoruz.
GET ALL EMPLOYEES=>http://localhost:3000/employees

```
http://localhost:3000=> baseURL
```

![Ekran Görüntüsü (732)](https://user-images.githubusercontent.com/74673470/196669054-ffd4f68e-0eac-437b-b345-f7e2063c70b9.png)

<br/>

baseURL oluşturduk burda oluşturduğumuz baseURL'i request içine yazdık.

![Ekran Görüntüsü (733)](https://user-images.githubusercontent.com/74673470/196669059-48732f76-b766-4d1f-bd1b-3cb0d1bbaf07.png)

![Ekran Görüntüsü (734)](https://user-images.githubusercontent.com/74673470/196669072-1e462a0d-3c74-45e0-80df-4515c8036273.png)
<br/>


GET A EMPLOYEE=>http://localhost:3000/employees/:id


![Ekran Görüntüsü (735)](https://user-images.githubusercontent.com/74673470/196669267-6e3d5177-30ef-4bda-a6b4-dd849adc9b94.png)

<br/>


##### Fitreleme 
EMPLOYEES - GENDER - GET=>http://localhost:3000/employees/?gender=Male

![Ekran Görüntüsü (736)](https://user-images.githubusercontent.com/74673470/196669372-e017002c-08fa-41b6-b903-2c3508f93fc5.png)
<br/>

EMPLOYEES - roleID - GET=>http://localhost:3000/employees/?roleId=3

![Ekran Görüntüsü (737)](https://user-images.githubusercontent.com/74673470/196669347-281dc781-8c2b-401b-9bcc-1c46650e3190.png)

<br/>

iki adet filtereleme için & işareti kullanılır.
EMPLOYEES - GENDER & roleId- GET=>
http://localhost:3000/employees?gender=Female&roleId=3

![Ekran Görüntüsü (738)](https://user-images.githubusercontent.com/74673470/196669355-6962cd4c-8032-4ce1-818c-a247b53e4b5a.png)
<br/>

##### Pagination _page=1=>http://localhost:3000/employees?_page=1

1-10 arasındaki değerleri gösterir.
![Ekran Görüntüsü (739)](https://user-images.githubusercontent.com/74673470/196670803-321aaa85-4120-48d6-b7a2-fdb8975812a5.png)
<br/>

##### Sort?=>http://localhost:3000//employees/?_sort=first_name


![Ekran Görüntüsü (740)](https://user-images.githubusercontent.com/74673470/196671410-c041ab15-e15a-42da-901e-889d915ac520.png)

<br/>

##### Search=> http://localhost:3000/employees/?q=ger


![Ekran Görüntüsü (741)](https://user-images.githubusercontent.com/74673470/196671816-2c215b7c-79f0-4c24-81c1-345079a0f42a.png)
<br/>


##### Relationships
Çalışanların roleId leri var yani çalışan ve roles arasında parent-child ilişkisi var.
embed=parent a göre 
expand=child a göre
GET=>http://localhost:3000/roles?_embed=employees

![Ekran Görüntüsü (742)](https://user-images.githubusercontent.com/74673470/196676512-6fec601f-4cdb-4de4-b212-2d878bf3aab9.png)
<br/>


POST=>Bu metod ile biz employee tarafına yeni bir çalışan eklicez bunun için o verileri göndermemiz lazım Body postmandan seçip value leri yazıp isteği göndeririz. 

```
 {
      "first_name": "Aleyna",
      "last_name": "Çelik",
      "email": "ac@gmail.com",
      "gender": "Female",
      "roleId": 3
 }
```

![Ekran Görüntüsü (743)](https://user-images.githubusercontent.com/74673470/196677570-264d05f3-177a-4e8e-8e92-736cf3efa26b.png)

![Ekran Görüntüsü (745)](https://user-images.githubusercontent.com/74673470/196677854-bfd50842-9340-4301-9075-a36bed6a2cae.png)

<br/>

Delete=>Sileceğimiz çalışanın id yazarız.
http://localhost:3000/employees/:emp_id

![Ekran Görüntüsü (746)](https://user-images.githubusercontent.com/74673470/196681021-7dbf7538-3875-4825-8546-478b28994671.png)
<br/>
Patch=> Bilgileri değiştirme
http://localhost:3000/employees/:emp_id


![Ekran Görüntüsü (750)](https://user-images.githubusercontent.com/74673470/196685422-414167be-f3af-4bce-b67c-bc063f6cb649.png)

![Ekran Görüntüsü (748)](https://user-images.githubusercontent.com/74673470/196685421-f65e3f0b-9e4f-44e6-a407-af21b779fa04.png)

![Ekran Görüntüsü (751)](https://user-images.githubusercontent.com/74673470/196685423-4be32d3f-a50e-4aeb-8ed6-675f72a656ae.png)
<br/> <br/>

## cURL
URL üzerinden veri transferi yapmamızı sağlayan bir komut satırı aracıdır. REST API çerçeverinde sorgu adreslerine yapılan isteklerde sıklıkla kullanılır. HTTP, HTTPS, FTP, FTPS, GOPHER, GOPHERS, IMAP, IMAPS vs.. bir çok protokolü desteklemektedir.
https://curl.se/docs/
<br/>

##### cURL komutları
-i (--include): Çıktı içerisinde HTTP başlıklarını da gösterir.
-I (--head): Yalnızca HTTP başlıklarını görmek için kullanılır.
-o (--output) <file> : Çıktıyı bir dosyaya yazdırmak için kullanılır.
-v (--verbose): Daha fazla detay.

<br/>
gitBash içinde curl kullanılabilir ama isteğe göre ayrıca indirilebilir.

![Ekran Görüntüsü (753)](https://user-images.githubusercontent.com/74673470/196693754-2a3fb9df-f3bd-4887-b9fe-63267e67b14f.png)

![Ekran Görüntüsü (755)](https://user-images.githubusercontent.com/74673470/196696653-7713e2db-34bd-4df8-b0c5-11ff67f039ad.png)
