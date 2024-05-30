<h1 align='center'>protokol Nedir?</h1>

<p>
  Protokol: Kurallar bütünüdür denebilir. Şöyle düşünelim: İki insan aralarında konuşuyor, yani bir iletişim halindeler. Bu sohbet sırasında iki kişinin de birbirlerini anlaması için bazı hususlar vardır. Bunlar örnek olarak, aynı dili konuşmaları, aynı konuyu konuşmaları vb. şeklinde sıralanabilir. Aynı şekilde, aralarından birinin bir cümle kurması için kişinin de kendi içinde bazı sıralamaları vardır. Örneğin, beynin düşünmesi, sonra kas ve sinir sistemini kullanarak düşündüğü cümleyi bir ses dalgası olarak çıkarması gibi.

İşte networkde de protokol budur. İki cihazın birbirini anlaması için bazı kurallar vardır; biz bunlara network protokolleri diyoruz. Aynı şekilde, iletişim sırasında bir cihazın diğer bir cihaza veri yollaması için bazı sıralamalar vardır; işte bunlara da protokol yığınları diyoruz.

İlk önce protokol yığınları anlamak ile başlayalım, sonrasında protokoller için özel olarak çalışma yaparız. 
</p>

<h2 align='center'>OSİ Modeli</h2>

<p>
 OSİ Modeli: Bir protokol yığınıdır, yani bir iletişim sırasında verinin oluşturulmasından iletimine kadar ve iletildikten sonra verinin alınmasından okunmasına kadar geçen yolu bize anlatır. 7 adet katmandan oluşur ve her katmanda veri, farklı bir adımdan geçerek en alt katmandan iletime başlar. Aynı şekilde, veri alındıktan sonra her katmanda farklı bir işleme tabi tutularak en üst katmanda kullanıcının veriyi görmesi sağlanır.

 <div align="center">
    <img src="https://github.com/Okan-tumuklu/Network-dersleri/assets/117488504/45009d97-ab1b-4962-ad4f-66340c801568" alt="Network Image">
</div>

Gelin beraber bu katmanları tek tek inceleyerek çalışma prensibini anlayalım.

---
<h3>Application Layer(Uygulama Katmanı)</h3>

Uygulama katmanı, kullanıcıları network ile bir araya getiren ve iletişimlerini sağlayan önemli bir katmandır. Bu katmanda, genellikle uygulamalar bulunur ve kullanıcılar bu uygulamalar aracılığıyla ağ üzerinde etkileşim kurarlar. Örneğin, bir kullanıcı mesaj göndermek, e-posta göndermek veya dosya paylaşmak istediğinde, bu işlemleri gerçekleştirmek için bir uygulamaya ihtiyaç duyar. Bu uygulamalar, arka planda çalışan bir ağ protokolü vasıtasıyla iletişimi sağlar ve iletim için veriyi hazırlamaya başlar. Daha sonra, bu veri, iletim için bir alt katmana iletilir.

Uygulama katmanı, ağın en üst katmanını oluşturur ve kullanıcıların ağa erişmesini sağlar. Ancak, bu katman yalnızca kullanıcı etkileşimini değil, aynı zamanda ağ üzerindeki veri akışını da yönetir. Bu sayede, kullanıcılar istedikleri uygulamalara sorunsuz bir şekilde erişebilir ve iletişim kurabilirler. Bu katman ayrıca, uygulama düzeyindeki hataları ele alır ve kullanıcıya geri bildirim sağlar, böylece kullanıcılar işlemlerini daha güvenilir bir şekilde gerçekleştirebilirler.

-
<h3>Presentation Layer(Sunum Katmanı)</h3>

Sunum katmanı, uygulama katmanından aldığı veriyi sıkıştırarak veya şifreleyerek bir alt katmana iletir. Bu şifreleme, verinin güvenliğini sağlamak, sıkıştırma ise veri iletim verimliliğini artırmak içindir. Sunum katmanı, verinin hedef cihazda anlaşılabilir olmasını sağlar. Veri, farklı sistemler arasında uyumlu ve güvenli bir şekilde çalışarak iletişimi sağlar.

Bir kaç işlevi bulunmaktadır sunum katmanının. gelin ufak örnekler ile bahsedelim.

Veri Temsilinin Standardizasyonu

Bir web tarayıcısı (client) ve bir web sunucusu (server) arasında veri alışverişi yapıldığını düşünelim. Web tarayıcısı, sunucudan bir resim dosyası (JPEG formatında) talep eder. Sunum katmanı, bu JPEG dosyasının istemci ve sunucu arasında doğru formatta temsil edilmesini sağlar. Böylece tarayıcı, sunucudan gelen resim dosyasını doğru bir şekilde görüntüleyebilir.

Veri Şifreleme

Bir bankanın web sitesi üzerinden çevrimiçi bankacılık işlemi yaparken, girdiğiniz kullanıcı adı ve şifre bilgilerinin güvenli bir şekilde sunucuya iletilmesi gerekir. Bu veriler, sunum katmanında şifrelenir (örneğin, TLS/SSL kullanılarak). Şifrelenmiş veri, ağ üzerinden güvenli bir şekilde iletilir ve sunucu tarafında yine sunum katmanında çözülerek orijinal haline getirilir.

Veri Sıkıştırma

Büyük boyutlu bir dosyanın (örneğin, bir video dosyası) e-posta ile gönderilmesi gerektiğinde, bu dosyanın boyutunu azaltmak için sıkıştırılması gerekir. Sunum katmanı, dosyanın sıkıştırılmasını (örneğin, ZIP formatına dönüştürülmesini) sağlar. Alıcı tarafında, bu dosya sunum katmanında sıkıştırılmış formatından çıkarılır ve orijinal boyutuna döndürülür.

Veri Dönüştürme

Farklı karakter kodlama sistemleri kullanan iki bilgisayar arasında veri aktarımı yapıldığını düşünelim. Örneğin, bir bilgisayar ASCII karakter setini, diğeri ise EBCDIC karakter setini kullanıyor olabilir. Sunum katmanı, ASCII'den EBCDIC'e ve EBCDIC'den ASCII'ye karakter kodlama dönüşümlerini gerçekleştirir. Bu sayede, iki bilgisayar arasında doğru ve anlaşılır veri alışverişi sağlanır.

--
<h3>Session Layer(Sunum Katmanı)</h3>



</p>


Devam edecem haaa
