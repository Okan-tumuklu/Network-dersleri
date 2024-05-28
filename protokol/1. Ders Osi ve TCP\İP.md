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

<h3>Application Layer(Uygulama Katmanı)</h3>

Uygulama katmanı, kullanıcıları network ile bir araya getiren ve iletişimlerini sağlayan önemli bir katmandır. Bu katmanda, genellikle uygulamalar bulunur ve kullanıcılar bu uygulamalar aracılığıyla ağ üzerinde etkileşim kurarlar. Örneğin, bir kullanıcı mesaj göndermek, e-posta göndermek veya dosya paylaşmak istediğinde, bu işlemleri gerçekleştirmek için bir uygulamaya ihtiyaç duyar. Bu uygulamalar, arka planda çalışan bir ağ protokolü vasıtasıyla iletişimi sağlar ve iletim için veriyi hazırlamaya başlar. Daha sonra, bu veri, iletim için bir alt katmana iletilir.

Uygulama katmanı, ağın en üst katmanını oluşturur ve kullanıcıların ağa erişmesini sağlar. Ancak, bu katman yalnızca kullanıcı etkileşimini değil, aynı zamanda ağ üzerindeki veri akışını da yönetir. Bu sayede, kullanıcılar istedikleri uygulamalara sorunsuz bir şekilde erişebilir ve iletişim kurabilirler. Bu katman ayrıca, uygulama düzeyindeki hataları ele alır ve kullanıcıya geri bildirim sağlar, böylece kullanıcılar işlemlerini daha güvenilir bir şekilde gerçekleştirebilirler.

</p>


Devam edecem haaa
