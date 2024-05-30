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

___
<h3>Application Layer(Uygulama Katmanı)</h3>

Uygulama katmanı, kullanıcıları network ile bir araya getiren ve iletişimlerini sağlayan önemli bir katmandır. Bu katmanda, genellikle uygulamalar bulunur ve kullanıcılar bu uygulamalar aracılığıyla ağ üzerinde etkileşim kurarlar. Örneğin, bir kullanıcı mesaj göndermek, e-posta göndermek veya dosya paylaşmak istediğinde, bu işlemleri gerçekleştirmek için bir uygulamaya ihtiyaç duyar. Bu uygulamalar, arka planda çalışan bir ağ protokolü vasıtasıyla iletişimi sağlar ve iletim için veriyi hazırlamaya başlar. Daha sonra, bu veri, iletim için bir alt katmana iletilir.

Uygulama katmanı, ağın en üst katmanını oluşturur ve kullanıcıların ağa erişmesini sağlar. Ancak, bu katman yalnızca kullanıcı etkileşimini değil, aynı zamanda ağ üzerindeki veri akışını da yönetir. Bu sayede, kullanıcılar istedikleri uygulamalara sorunsuz bir şekilde erişebilir ve iletişim kurabilirler. Bu katman ayrıca, uygulama düzeyindeki hataları ele alır ve kullanıcıya geri bildirim sağlar, böylece kullanıcılar işlemlerini daha güvenilir bir şekilde gerçekleştirebilirler.

___
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

___
<h3>Session Layer(Sunum Katmanı)</h3>

İki cihaz arasındaki iletişimin kurulması, yönetilmesi ve sonlandırılmasından sorumlu olan katman, oturum katmanıdır. Bu katman, Sunum katmanından aldığı veriye herhangi bir müdahalede bulunmadan oturum işlemlerini yerine getirir ve veriyi bir alt katmana iletir.

Oturum işlemleri şunlardır:

Oturumu başlatır: Hedef cihaz ile kaynak cihaz arasında bir oturum başlatarak veri alışverişine hazır hale getirir.
Oturumu yönetir: Sağlamış olduğu oturumu sürdürür, gerekirse durdurur ve hataları önler. Böylece iki cihaz arasındaki iletişim düzgün bir şekilde sağlanır.
Oturumu sonlandırır: Kurmuş olduğu oturumu iki cihazın veri alışverişi bittiğinde sonlandırır.
Senkronizasyon: Veri akışının kesintisiz ve düzenli olmasını sağlamak için veri akışında kontrol noktaları oluşturur. Bu kontrol noktaları sayesinde veri transferinde bir hata olduğunda, belirli bir noktadan itibaren veri yeniden gönderilebilir.
Diyalog Kontrolü: İki cihaz arasındaki iletişim yönünü (tek yönlü, iki yönlü, yarı çift yönlü) ve iletişim modunu (örneğin, full-duplex) yönetir.


Anlamadığınız terimleri ileride daha iyi anlayacağız, merak etmeyin dostlarım.

___

<h3>Trasnport Layer(Taşıma Katmanı)</h3>

Taşıma katmanı, bir üst katmandan aldığı verileri segmentlere bölerek bir alt katmana gönderir ve gelen verideki parçaları birleştirerek bir üst katmana iletilir. Bu segmentlere önemli bilgiler eklenir, örneğin port numaraları.

Port numarası nedir diye sorarsanız: Bir cihaza veri gönderdiğimizi düşünelim, peki bu veri hangi uygulamada gösterileceğini nasıl anlar? İşte bunu sağlayan port numarasıdır. Taşıma katmanında kullanılan protokoller, segmentlere port numaraları ekler. Bu port numaraları sayesinde bir cihazda çalışan farklı uygulamalar aynı anda gösterilebilir. Örneğin, bir bilgisayarda web sitesini çalıştıran port numarası 80'dir. Benzer şekilde, bir veri tabanı uygulamasını çalıştıran port numarası 3306'dır. Bu sayede hangi uygulamada verinin gösterileceğine karar verir.

 <div align="center">
    <img src="https://github.com/Okan-tumuklu/Network-dersleri/assets/117488504/831e7afb-d5ff-493c-9d5f-4a3ff3834756" alt="Network Image">
</div>

Yalnız şöyle bir durum var: Server-client iletişimi sağlandığında, server sabit olarak uygulama için bir port numarası kullanır, ancak client tarafı dinamik olarak o iletişim için bir port açar. Örneğin, bir web sitesine bağlanırken hedef server 80 numaralı portu kullanırken, benim tarafımda random olarak 52300 numaralı bir port açılabilir. Aynı anda farklı bir web sitesine gittiğimde yine hedef 80 numaralı portu kullanırken, benim veriyi gönderdiğim port numarası 48305 olabilir. Gönderilen her verinin cevabı, bizim açmış olduğumuz random porttan bize gelir.

 <div align="center">
    <img src="https://github.com/Okan-tumuklu/Network-dersleri/assets/117488504/bfcfa4ca-9ea3-4368-9525-98eb67565840" alt="Network Image">
</div>

Bu katmanda genellikle iki farklı protokol kullanılır TCP veya UDP bunları ileride anlicaz.

___


<h3>Network Layer(Ağ Katmanı)</h3>

Network katmanı, taşıma katmanından aldığı verileri paketler haline getirir. Bu paketlere hangi cihaza gidecekse, o cihazın IP adresini ve kendi kaynak IP adresini ekler. Bu sayede veri, hangi cihaza gideceğini bilir ve hedef cihazda yanıtı hangi cihaza ileteceğini bilir. Network katmanında iki önemli özellik öne çıkar: adresleme ve yönlendirme. Adresleme, IP adresini pakete eklemektir; yönlendirme ise veriyi hedef cihaza doğru ve hızlı bir şekilde iletmek için doğru yolu bulmaktır.

 <div align="center">
    <img src="https://github.com/Okan-tumuklu/Network-dersleri/assets/117488504/58e5d695-53e1-4095-a7cd-22a17720ca3d" alt="Network Image">
</div>

Yukarıdaki resimde gördüğünüz gibi, en doğru yolu bulup hedefe yönlendiriyor.

Tabiki bu katmanın Bir kaç görevi daha var bu ileriki konular içindir, ileride beraber öğreneceğiz.

<h3>Data-Link Layer(Veri-Bağ Katmanı)</h3>

Data Link katmanı, bilgisayar ağlarında verilerin fiziksel ortamda taşınabilir hale getirilmesinden sorumlu olan katmandır. üst katmanlardan aldığı verileri, fiziksel ortamda taşınabilir çerçevelere dönüştürür.

Bu sırada, iletişimde bulunan cihazlar arasında doğrudan bağlantıyı sağlar. Bu katman, çerçeveleri oluştururken her bir çerçeveye hedef ve kaynak MAC adresleri ekler. MAC adresleri, ağdaki her bir cihazın benzersiz kimliğini temsil eder. Dolayısıyla, iletişimde gönderici ve alıcı cihazların belirlenmesini ve iletilen verinin doğru adrese ulaştırılmasını sağlar.

Data Link katmanı, genellikle ağ kartları (network interface cards - NICs) ve Ethernet gibi fiziksel ağ teknolojileri tarafından desteklenir. Bu katman, aynı yerel ağdaki cihazlar arasında iletişimi yönetirken, aynı zamanda veri bütünlüğünü sağlayarak iletişim hatasını en aza indirir.

<h3>Physical Layer(Fiziksel Katmanı)</h3>

Fiziksel katman, üstten aldığı verileri kablolar ve cihazlar yardımıyla ileten katmandır. Bu katmanın sadece görevi, veriyi kablo, ışık veya radyo sinyali aracılığıyla iletmektir.

</p>


<h2 align='center'>Kapsülleme</h2>

