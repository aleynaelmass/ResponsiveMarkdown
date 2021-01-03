# RESPONSIVE DESIGN-CSS

Web dizaynın ilk zamanlarında ,sayfalar belirli bir ekran boyutunu hedefleyerek oluşturulurdu. Kullanıcı ,tasarımcının belirlediği ekran boyutundan büyük veya küçük bir ekrana sahipse ,sonuçlar istenmeyen kaydırma çubuklarından aşırı uzun satır uzunluklarına ve yetersiz alan kullanımına kadar değişiyordu. Daha çeşitli ekran boyutları mevcut hale geldikçe , web sayfalarının düzenini ve görünümünü farklı ekran genişliklerine , çözünürlüklerine vb. uygun olacak şekilde değiştirmesine izin veren bir dizi uygulama olan **Responsive Web Design (RWD)** kavramı ortaya çıktı. Multi cihazlı bir web için tasarlama  şeklini ve bu konuyu anlamak için bilmemiz gereken ana tekniklere yer verilecektir.


## Tarihi Web Site Düzenleri
Eskiden , bir web sitesi tasarlarken iki seçeneğimiz mevcuttu:
- Tarayıcı penceresini dolduracak şekilde genişleyen akıcı bir site oluşturabilirsiniz.
- veya piksel cinsinden sabit boyutta olacak sabit genişlikte bir site.
   >**not** : Örnekteki basit akıcı düzene bakın:[exapmle](https://mdn.github.io/css-examples/learn/rwd/liquid-width.html),
 ,  [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/liquid-width.html).
 Farklı boyutlarda nasıl göründüğünü görmek için tarayıcı pencerenizi farklı şekilde sürükleyin.
  >**not**:Basit genişlikli örneğe bakın :[exapmle](https://mdn.github.io/css-examples/learn/rwd/fixed-width.html),[source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/fixed-width.html)
 
Mobil web, ilk özellikli telefonlar olmaya başladığında, mobili benimsemek isteyen şirketler genellikle sitelerinin özel bir mobil sürümünü farklı bir URL ile (genellikle _m.example.com_ veya _example.mobi_ gibi bir şey oluştururlardı. ) Bu, sitenin iki ayrı versiyonunun geliştirilmesi ve güncel tutulması gerektiği anlamına geliyordu.

Ek olarak, bu mobil siteler genellikle çok kısaltılmış bir deneyim sunuyordu. Mobil cihazlar daha güçlü hale geldikçe ve tam web sitelerini görüntüleyebildikçe,  kendilerini sitenin mobil sürümünde mahsur bulan ve sitenin tam özellikli masaüstü sürümünde olduğunu bildikleri bilgilere erişemeyen mobil kullanıcılar için sinir bozucuydu. 
 


## Responsive Design'dan Önce Flexible Layout
2004'te Cameron Adams , farklı ekran çözünürlüklerine uyarlanabilen bir tasarım oluşturma yöntemini açıklayan [[Resolution dependent layout(Çözünürlüğe bağlı düzen)](http://www.themaninblue.com/writing/perspective/2004/09/21/) başlıklı bir yazı yazdı . Bu yaklaşım, ekran çözünürlüğünü tespit etmek ve doğru CSS'yi yüklemek için JavaScript gerektiriyordu.
Zoe Mickley Gillenwater, flexible  sitelerin yaratılabileceği farklı yolları tanımlama ve resmileştirme [çalışmalarında](http://zomigi.com/blog/voices-that-matter-slides-available/) etkili oldu , ekranı doldurmakla boyut olarak tamamen sabitlenmek arasında uygun bir ortam bulmaya çalışıyordu.




# Responsive Web Design
Responsive Design terimi [ 2010 yılında Ethan Marcotte tarafından icat edildi](https://alistapart.com/article/responsive-web-design/) ve üç tekniğin kombinasyon halinde kullanımını tanımladı.
<ol><li> lki, Gillenwater tarafından zaten araştırılan ve Marcotte'nin Fluid Grids (2009'da A List Apart'ta yayınlandı.) makalesinde okunabilen fluid grids fikriydi.</li>
<li>1.  İkinci teknik, Fluid Imagesfikriydi . Ayarı çok basit bir teknik kullanarak max-width özelliğini  100%,  Bu, bir görüntünün,  taşması yerine, esnek boyutlu bir sütuna sığacak şekilde küçültülmesini sağlar, ancak sütun görüntüden daha geniş olursa, büyüyemez ve pikselli hale gelmez.  </li>
<li> 1.  Üçüncü anahtar bileşen, Media query . Media Queries, Cameron Adams'ın yalnızca CSS ,JavaScript kullanarak keşfettiği düzen anahtarı türünü etkinleştirmesi. Tüm ekran boyutları için tek bir düzene sahip olmak yerine, düzen değiştirilebilir halde, daha küçük ekran için kenar çubukları yeniden konumlandırılabilir veya alternatif gezinme görüntülenebilir.</li>
    </ol>
    
  **Responsive Web Design ayrı bir teknoloji değildir.** Web tasarımına yönelik bir yaklaşımı vey bir dizini en iyi uygulamak için kullanılan bir terimdir ve görüntülemek için kullanılan cihaza yanıt verebilecek bir düzen oluşturmak için kullanılır. Modern Css  layout metotlarına doğası gereği duyarlıdır ve sitelerin tasarlanmasını kolaylaştırmak için vardır.
  


## Media Queries

Responsive design yalnızca media queries ile ortaya çıkabildi.The Media Queries Level 3 spesifikasyonu, 2009 yılında bir Candidate Recommendation ( Aday Öneri) haline geldi,yani tarayıcılarda uygulamaya hazır olduğu kabul edildi.
> Örneğin, aşağıdaki media query , geçerli web sayfasının ekran medyası (dolayısıyla basılı bir belge değil) olarak görüntülenip görüntülenmediğini ve görünüm alanının en az 800 piksel genişliğinde olup olmadığını test eder. `.container`selector için CSS , yalnızca bu iki şey doğruysa uygulanacaktır.


 > - @media screen and (min-width: 800px) {
  .container {
    margin: 1em 2em;
  }
} 

Bir stylesheet'e birden çok media queries ekleyebilir, tüm düzeninizi veya bölümlerini çeşitli ekran boyutlarına en iyi şekilde uyacak şekilde değiştirebilirsiniz.
Media Queries  kullanırken yaygın bir yaklaşım, dar ekranlı cihazlar (ör. Cep telefonları) için basit bir tek sütunlu düzen oluşturmak, ardından daha büyük ekranları kontrol etmek ve işlemek için yeterli ekran genişliğine sahip olduğunuzu bildiğinden çok sütunlu bir düzen uygulamaktır.  Bu genellikle **mobile first** tasarım olarak tanımlanır .
- Media Queries ile ilgili daha fazlası için [MDN Dökümantasyonu](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)

 ## Flexible Grids
Responsive siteler, yalnızca breakpoints arasındaki düzenlerini değiştirmekle kalmaz, aynı zamanda flexible grids üzerine inşa edilir. Flexible grid, var olan her olası cihaz boyutunu hedeflemenize ve bunun için mükemmel bir piksel düzeni oluşturmanıza gerek olmadığı anlamına gelir.
 Fleixible grid kullanarak, içeriğin kötü görünmeye başladığı noktada yalnızca breakpoint eklemeniz ve tasarımı değiştirmeniz gerekir. Örneğin, ekran boyutu büyüdükçe satır uzunlukları okunamayacak kadar uzun hale gelirse veya bir kutu daraldıkça her satırda iki sözcükle sıkıştırılırsa.
 Responsive design'ın ilk günlerinde, düzeni gerçekleştirmek için tek seçeneğimiz [floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats) kullanmaktı .
 Marcotte, fluid grids ile  ilgili orijinal çalışmasında, pikseller kullanılarak tasarlanan bir düzeni alıp yüzdelere dönüştürmek için bir formül ayrıntılı olarak açıkladı.
```
target / context = result 
```
Örneğin, hedef sütun boyutumuz 60 piksel ise ve  context (veya container) 960 piksel ise, ondalık noktayı iki haneye taşıdıktan sonra CSS'mizde kullanabileceğimiz bir değer elde etmek için 60'ı 960'a böleriz. 
```
.col {
  width: 6.25%; /* 60 / 960 = 0.0625 */
}
```
Bu yaklaşım günümüzde bir çok web üzerinde bulunmakta.
>Aşağıdaki örnek, Media Queries ve fluid grids kullanan basit ve duyarlı bir tasarımı göstermektedir. Dar ekranlarda düzen, kutuları üst üste dizilmiş olarak görüntüler.
- **Note**: Burda bulabilirsin: [live example](https://mdn.github.io/css-examples/learn/rwd/float-based-rwd.html) ve  [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/float-based-rwd.html)  GitHub'ta.



# [Modern Layout Technologies](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#Modern_layout_technologies )
[Multiple-column layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout), [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox), ve [Grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids) modern düzen yöntemleri varsayılan olarak responsivedir. Hepsi fluid grids oluşturmaya çalıştığınızı varsayar ve bunu yapmanın daha kolay yollarını sunar.


### [Multicol](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#Multicol "Multicol için kalıcı bağlantı")

- Bu düzen yöntemlerinden en eskisidir.`column-count`, içeriğinizin kaç sütuna bölünmesini istediğinizi belirtir. Tarayıcı daha sonra ekran boyutuna göre değişecek bir boyut olan bunların boyutunu hesaplar.
```
.container {
  column-count: 3;
} 
```
`column-width`, _minimum_ genişlik belirlemiş olursunuz . Tarayıcı, container'a rahatça sığacak kadar bu genişlikte sütun oluşturacak ve ardından kalan alanı tüm sütunlar arasında paylaştıracaktır. Bu nedenle sütun sayısı ne kadar boşluk olduğuna göre değişecektir.
```
.container {
  column-width: 10em;
} 
```

 

### [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#Flexbox "Permalink to Flexbox")

Containerlardaki boşluğa göre öğeler arasındaki  alanı küçültür ve dağıtır. Değerlerini değiştirerek `flex-grow`ve `flex-shrink`etrafındaki fazla veya daha az yer karşılaştığınızda davranır öğeleri istediğiniz gibi gösterebilir.
> Aşağıdaki örnekte, flex öğelerin her biri,[Flexbox: Flexible sizing of flex items](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#Flexible_sizing_of_flex_items),
> `flex: 1` flex containerda eşit miktarda yer kaplayacaktır .
```
.container {
  display: flex;
}

.item {
  flex: 1;
} 
```
>**Not** : Örnek olarak, yukarıdaki simple responsive layoutu bu sefer flexbox kullanarak yeniden oluşturduk. Sütunların boyutunu hesaplamak için artık garip yüzde değerleri kullanmamıza gerek kalmadığını görebilirsiniz: [example](https://mdn.github.io/css-examples/learn/rwd/flex-based-rwd.html) , [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/flex-based-rwd.html) .
### [CSS grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#CSS_grid "Permalink to CSS grid")
CSS Grid Layout `fr`birim, mevcut alanın grid tracks arasında dağıtımına izin verir. Sonraki örnek, boyutunda üç yol içeren bir column tracks oluşturur `1fr`. Bu, her biri container için  kullanılabilir alanın bir bölümünü kaplayan üç sütun izi oluşturacaktır.
>Daha fazlası için [Flexible grids with the fr unit](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#Flexible_grids_with_the_fr_unit).
```
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
} 
```
>**Not** : Wrapper'da sütunları tanımlayabildiğimiz için grid layout sürümü daha da basittir:[example](https://mdn.github.io/css-examples/learn/rwd/grid-based-rwd.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/grid-based-rwd.html).

### [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#Responsive_images "Permalink to Responsive images")

Responsive images en basit yaklaşım, Marcotte'nin responsive design hakkındaki ilk makalelerinde anlatıldığı gibiydi. Temel olarak, ihtiyaç duyulabilecek en büyük boyutta bir görüntü alır ve onu küçültürdünüz. Bu, günümüzde hala kullanılan bir yaklaşımdır ve çoğu stil sayfasında aşağıdaki CSS'yi bir yerlerde bulacaksınız:
```
img {
  max-width: 100%;
} 
```
>Bu yaklaşımın açık dezavantajları var. Görüntü, gerçek boyutundan çok daha küçük görüntülenebilir, bu da bant genişliği israfıdır . Bir mobil kullanıcı, tarayıcı penceresinde gerçekte gördüklerinin birkaç katı boyutunda bir görüntü indiriyor olabilir. Ek olarak, mobil cihazlarda masaüstü ile aynı görüntü en boy oranını istemeyebilirsiniz. Örneğin, mobil cihazlar için kare bir resme sahip olmak güzel olabilir, ancak aynı sahneyi masaüstünde bir yatay resim olarak göstermek. Veya, mobil cihazlarda bir görüntünün daha küçük boyutta olduğunu kabul ederek, tamamen farklı bir görüntü göstermek isteyebilirsiniz; bu, küçük bir ekran boyutunda daha kolay anlaşılır. Bunlar, bir görüntüyü küçültmekle başarılamaz.
>
>>Responsive Images, [`<picture>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)öğeyi ve ve özelliklerini kullanarak bu iki sorunu da çözer. 
>- "İpuçları" (görüntünün en uygun olduğu ekran boyutu ve çözünürlüğü tanımlayan meta veriler) ile birlikte birden çok boyut sağlayabilirsiniz ve tarayıcı, her cihaz için en uygun görüntüyü seçecek ve kullanıcının bir görüntü boyutunu indirmesini sağlayacaktır. kullandıkları cihaza uygun.[`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)  `srcset``sizes`

>>>Ayrıca farklı boyutlarda kullanılan _doğrudan_ görüntüleri de yapabilirsiniz , böylece farklı ekran boyutlarına farklı bir kırpma veya tamamen farklı bir görüntü sağlayabilirsiniz.
MDN'de buradaki [  Responsive Images  HTML section](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) için ayrıntılı bir [kılavuz](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) bulabilirsiniz .


### [Responsive Typography](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#Responsive_typography "Permalink to Responsive typography")
>Bu örnekte, seviye 1 başlığımızı `4rem`, yani temel yazı tipi boyutumuzun dört katı olacak şekilde ayarlamak istiyoruz .Bu jumbo başlığını yalnızca daha büyük ekran boyutlarında istiyoruz, bu nedenle önce daha küçük bir başlık oluşturuyoruz, ardından kullanıcının en az bir ekran boyutuna sahip olduğunu biliyorsak daha büyük boyutun üzerine yazmak için **media queries** kullanıyoruz `1200px`.
```
html {
  font-size: 1em;
}

h1 {
  font-size: 2rem;
}

@media (min-width: 1200px) {
  h1 {
    font-size: 4rem;
  }
} 
```
Responsive grid örneğimizi, özetlenen yöntemi kullanarak responsive type de içerecek şekilde düzenledik. Düzen iki sütunlu versiyona giderken başlığın boyutları nasıl değiştirdiğini görebilirsiniz.

>Mobil cihazlarda başlık daha küçüktür
>Ancak masaüstünde daha büyük başlık boyutunu görüyoruz:
>**Not:** Bu örneğe uygulamalı bakın:[example](https://mdn.github.io/css-examples/learn/rwd/type-rwd.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/type-rwd.html).
>>>Media queries, yalnızca sayfanın düzenini değiştirmekle sınırlamanıza gerek yoktur. Farklı ekran boyutlarında daha kullanışlı veya çekici hale getirmek için herhangi bir öğeyi ince ayar yapmak için kullanılabilirler.


### [Using viewport units for responsive typography](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#Using_viewport_units_for_responsive_typography "Permalink to Using viewport units for responsive typography")
İlginç bir yaklaşım, `vw`responsive typography etkinleştirmek için görüntü alanı birimini kullanmaktır . `1vw`viewport genişliğinin yüzde birine eşittir, yani yazı tipi boyutunuzu kullanarak ayarlarsanız `vw`, her zaman viewport boyutuyla ilişkili olacaktır.
```
h1 {
  font-size: 6vw;
}
```
Yukarıdakileri yapmanın sorunu, kullanıcının `vw`birimi kullanarak herhangi bir text seti yakınlaştırma yeteneğini kaybetmesidir , çünkü bu metin her zaman görünüm penceresinin boyutuyla ilgilidir. **Bu nedenle, metni yalnızca viewport birimlerini kullanarak asla ayarlamamalısınız** .
Bir çözüm var ve [calc() ](https://developer.mozilla.org/en-US/docs/Web/CSS/calc) kullanmayı içeriyor.`vw` üniteyi `em`s veya `rem`s gibi fixed size kullanarak bir değer kümesine eklerseniz, metin yine de yakınlaştırılabilir olacaktır. Esasen, `vw`birim bu yakınlaştırılmış değerin üstüne ekler:
```
h1 {
  font-size: calc(1.5rem + 3vw);
}
```
>Bu, başlığın yazı tipi boyutunu mobil için ayarlamak ve media queriesi yeniden tanımlamak yerine yalnızca bir kez belirtmemiz gerektiği anlamına gelir.  Viewport boyutunu artırdıkça yazı tipi kademeli olarak artar.
>>>[example](https://mdn.github.io/css-examples/learn/rwd/type-vw.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/type-vw.html).


### [The viewport meta tag](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#The_viewport_meta_tag "Permalink to The viewport meta tag")
Responsive page'in HTML kaynağına bakarsanız, genellikle belgede aşağıdaki  `<head>` içinde [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta)etiketi görürsünüz.
 ```
<meta name="viewport" content="width=device-width,initial-scale=1">
```

Meta tag, mobil tarayıcılara görüntü alanının genişliğini cihaz genişliğine ayarlamaları ve belgeyi hedeflenen boyutunun% 100'üne ölçeklendirmeleri gerektiğini söyler;  belgeyi mobil cihazlar için optimize edilmiş şekilde amaçladığınız boyutta gösterir.
**Bu neden gerekli? Çünkü mobil tarayıcılar viewport genişlikleri hakkında yalan söyleme eğilimindedir.**
>>Meta tag, Orijinal iPhone piyasaya sürüldüğünde ve insanlar web sitelerini küçük bir telefon ekranında görüntülemeye başladığında, çoğu sitenin mobil cihazlar için optimize edilmemiş olması nedeniyle mevcuttur.
>
Viewport meta tag ile  kullanabileceğiniz başka ayarlar da vardır,

-   `initial-scale`: 1 olarak ayarladığımız sayfanın ilk yakınlaştırmasını ayarlar.
-   `height       ` : Görüntü alanı için belirli bir yükseklik ayarlar.
-   `minimum-scale`: Minimum yakınlaştırma seviyesini ayarlar.
-   `maximum-scale`: Maksimum yakınlaştırma seviyesini ayarlar.
-   `user-scalable`: Olarak ayarlanırsa yakınlaştırmayı engeller .

 `minimum-scale`, `maximum-scale`ve özellikle ortamda `user-scalable` `no`etmekten kaçınmalısın. Kullanıcıların ihtiyaç duydukları kadar çok veya az yakınlaştırmalarına izin verilmelidir; bunun engellenmesi erişilebilirlik sorunlarına neden olur.

>**Not** : Viewport Meta tag ( [@viewport)](https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport) değiştirmek için tasarlanmış bir CSS @ kuralı vardır, ancak tarayıcı desteği zayıftır. Her ikisi de kullanıldığında, meta etiket @viewport'u geçersiz kılar.
