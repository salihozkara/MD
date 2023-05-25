Şuan modalda lazy load script varsa çalışmıyor.

Çözüm önerisi:

https://github.com/salihozkara/Volo.Abp.SecurityHeaderTest/commit/67e4ef138db76c5cdfd2361562c8dd5012ea7db7

[Global script tag helper](https://github.com/abpframework/abp/pull/16496/files#diff-780060cc19621243a4f319661074649ca9aee2a608604b22e69d21b7b46e80c8) yazdığımız için bu özelliği kullanmayacak kişilerde etkilenecek ve altta verilen benzeri bir kod varsa çalışmayacaktır.
Kod : 
```cs
<script @(1 == 1 ? "Test" : "")>
    alert('Index page!')
</script>
```

![image](https://github.com/salihozkara/MD/assets/58659931/70bde62b-e965-476c-976e-cf2c9cf0d73f)


Bu hatayı verecektir.

Çözüm :
Bu hatanın yaşandığı scriptleri tekrar düzenleyin.


Yada breaking change oluşturmamak için bu tag helperi farklı bir namespace taşıyalım. Dokümanda nasıl ekleyeceklerini gösterelim. Bu durumda bizim kodlarımızdaki script taglarını düzenlememiz gerekir.

Nonce ifadesi sıkıntı çıkarmayacak şekilde. 

Bu noktada abp-script tag helperi belki normalde script tag helperinin görevlerini yapacak şekilde düzenlenebilir ve tüm kod larımızda bunu kullanırız yada farklı bir tag helper yazılır ve onu kullanırız.


Bu noktada karar veremedim.
abp-script in içeriğini bilmediğim için bu yapıya uygun mu bunuda bilemiyorum.

Örnek proje linki : https://github.com/salihozkara/Volo.Abp.SecurityHeaderTest

Bu projede WrongPage de html sonradan eklenen script çalışmıyor. Index sayfasındaki script global script tag helper sayesinde çalışıyor.
Layoutu ezme sebebim leptonx paket referans olduğu için o Layout şuan benim yazdığım tag helperi tanımıyor.
