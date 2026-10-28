\# Lab 01: Statik ve OSPF Hibrit Yönlendirme Senaryosu



Bu laboratuvar, kurumsal ağlarda yaygın olarak kullanılan statik rota ile dinamik yönlendirme protokollerinin (OSPF) birlikte çalışabilirliğini simüle etmek amacıyla oluşturulmuştur.



Static Routing : Manuel kontrol demektir Sade ve ssiz bir şekilde işini yapar verimlilik bant değeri boşa harcanmamış olur ağ büyüdükçe router fazlalaştıkça kontrol etmemiz zorlaşır.



Dynamic Routing : Ağ büyükse tercih edilir otonom sistem (AS) tek bir yönetm altında ortak yönlendirme politikasına sahip ıp ağları topluluğudur. Ağ üzerinde bir sorun olursa veya yeni bir hat eklenirse bunu anlar ve trafiği otomatik olarak çalışan diğer alternatif yola yönlendirir.



OSPF : Ağ dünyasıdna en çok kullanılan bağlantı durumlu dinamik yönlendirme protokollerinden biridir. Ağ üzerindeki bağlantıların hızını ve maliyetini hesaplayarak her zaman için en kısa ve en hızlı yolu seçer , büyük ağları küçük parçalara bölerek yönlendiricileirn işlemci yükünü azaltır ve performansı arttırır ağda bir değişiklik olursa bunu haber vererek rotaları anında günceller. 



Bu topolojideki cihazların bilgileri şunlardır :

|PC0|İÇ AĞ|192.168.1.10|255.255.255.0|192.168.1.1 R1|
|-|-|-|-|-|
|PC1|UZAK AĞ|172.16.1.10|255.255.255.0|172.16.1.1  R3|
|R1|OSPF|192.168.1.1 (Gig0/0/0)<br /><br /><br />10.10.12.1 (R2 Bağlantısı)|255.255.255.0<br />255.255.255.252||
|R2|OMURGA|10.10.12.2 (R1 Bağlantısı)<br /><br /><br />10.10.23.1 (R3 Bağlantısı)|255.255.255.252<br />255.255.255.252||
|R3|DIŞ AĞ|10.10.23.2 (R2 Bağlantısı)<br /><br /><br />172.16.1.1 (Gig0/0/1)|255.255.255.252<br />255.255.255.0||



PC0 (192.168.1.10) komut istemcisinden (CMD), uzak uçtaki PC1 (172.16.1.10) adresine başarıyla ping atılarak hibrit yönlendirmenin sorunsuz çalıştığı teyit edildi.







