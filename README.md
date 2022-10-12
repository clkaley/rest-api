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




# REST (Representational State Transfer) API Nedir?
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