# Oturum Komutları

PHP'deki oturum desteği, belli bir veriyi sonraki erişimlerden korumak için kullanılır. Böylece daha özelleştirilmiş uygulamalar oluşturabilir ve sitenizin çekiciliğini arttırabilirsiniz.

Sitenize gelen her ziyaretçiye eşsiz bir kimlik atanır, buna oturum kimliği diyoruz. Bu kimlik istemci tarafında bir çerezde ya da doğrudan URL üzerinde saklanır.

Oturum desteği, $_SESSION dizisindeki istekler arasında veri saklamanızı sağlar. PHP özdevinimli olarak sizin tarafınızdan (session_start() üzerinden örtük olarak ya da session_register() üzerinden doğrudan) veya sitenize bir ziyaretçi geldiğinde karşı taraftan (session.auto_start 1 ise) istekle beraber oturuma özgü bir oturum kimliği gönderilip gönderilmediğine bakar. Gönderilmişse evvelce o oturum adına saklanmış ortam yeniden oluşturulur. 

Oturum modülü bir oturumda sakladığınız verinin sadece oturumu oluşturduğunuz kullanıcı tarafından görüldüğünü garanti edemez. Oturumun bütünlüğünü etkin olarak korumak için oturumun önemine bağlı olarak ek tedbirler almanız gerekir.

Oturumlarınız tarafından taşınan verinin önemine ve konuşlandırdığınız ek korumalara bağlı olarak ki, bunun bir fiyatı vardır, kullanıcının rahatı azalır. Örneğin, kullanıcılarınızı basit sosyal mühendislik taktiklerinden korumak isterseniz session.use_only_cookies yönergesini etkin kılmanız gerekir. Bu durumda, çerezler kullanıcı tarafında koşulsuz olarak etkin kılınmalıdır yoksa oturum çalışmayacaktır.

Bir mevcut oturum kimliğinin üçüncü şahıslara ifşa edilmesinin çeşitli yolları vardır. İfşa edilmiş bir oturum kimliği, üçüncü tarafın o kimlik ile ilişkilendirilmiş tüm özkaynaklara erişmesini mümkün kılar. İlk olarak oturum kimliğini taşıyan URL'ler ifşa olur. Harici bir siteye bir bağ verirseniz oturum kimliğini içeren URL harici sitenin günlük kayıtlarına geçebilir. İkinci olarak, daha etkin bir saldırgan ağ trafiğini dinleyebilir. Eğer şifreleme yapılmıyorsa oturum kimlikleri ağ üzerinden salt metin olarak akacaktır. Bu noktada çözüm, sunucunuzun SSL bağlantılar kurmasını sağlamak ve bunu kullanıcılarınız için zorunlu kılmaktır. 

## Komut Listesi
Komut |Anlamı|
------------|-------------|
```session_abort``` | Discard session array changes and finish session
```session_cache_expire``` | Önbelleğe alınan oturumun ömrünü döndürür
```session_cache_limiter``` | Geçerli önbellek sınırlayıcısını döndürür ve/veya tanımlar
```session_commit``` | session_write_close işlevinin takma adıdır
```session_create_id``` | Create new session id
```session_decode``` | Oturum verisini bir dizgeden elde eder
```session_destroy``` | Bir oturumla ilişkilendirilmiş tüm veriyi yokeder
```session_encode``` | Geçerli oturum verisini bir dizge olarak kodlar
```session_gc``` | Perform session data garbage collection
```session_get_cookie_params``` | Oturum çerezi değiştirgelerini döndürür
```session_id``` | Geçerli oturum kimliğini döndürür ve/veya tanımlar
```session_is_registered``` | Bir küresel değişkenin oturumda kayıtlı olup olmadığına bakar
```session_module_name``` | Geçerli oturum modülünü döndürür ve/veya tanımlar
```session_name``` | Geçerli oturum ismini döndürür ve/veya tanımlar
```session_regenerate_id``` | Geçerli oturum kimliğini yenisiyle değiştirir
```session_register_shutdown``` | Session shutdown function
```session_register``` | Geçerli oturuma bir veya daha fazla küresel değişkeni kaydeder
```session_reset``` | Re-initialize session array with original values
```session_save_path``` | Geçerli oturum kayıt yolunu tanımlar ve/veya döndürür
```session_set_cookie_params``` | Oturum çerezi değiştirgelerini tanımlar
```session_set_save_handler``` | Kullanıcı seviyesi oturum saklama işlevlerini bildirir
```session_start``` | Oturum verisini ilklendirir
```session_status``` | Returns the current session status
```session_unregister``` | Geçerli oturumdaki bir küresel değişkeni kayıtdışı yapar
```session_unset``` | Free all session variables
```session_write_close``` | Oturum verisini yazıp oturumu kapatır
