---
---
# Liitumine

## Taotluse esitamine
Business Central kasutab liidestamisel otsekanalit. Liitumiseks võtke ühendust oma kliendihalduriga või esitage taotlus panga kodulehel.

Võimalik on seadistada pangaühendused järgmiste pankadega:
1. [Swedbank Gateway](https://www.swedbank.ee/business/d2d/ebanking/gateway)
2. [LHV Connect](https://www.lhv.ee/et/connect)
3. [SEB Baltic Gateway](https://www.seb.ee/ariklient/igapaevapangandus/elektroonilised-kanalid/baltic-gateway)
4. [Coop Pank Gateway](https://www.cooppank.ee/gateway)
5. [Luminor Web Service](https://luminor.ee/ari/web-services)

## Toetatud teenused
### Teenuste kirjeldused
 - **Maksete edastamine panka** – ootel ehk allkirjastamata maksed.
 - **Regulaarne konto väljavõte** ehk camt.053* – panga poolt automaatselt saadetav eelneva päeva väljavõte.

 - **Kiirteavitused** ehk camt.054* – panga poolt automaatselt saadetav teavitus iga tehingu kohta, mis vastab kehtestatud tingimustele (sisse/välja, valuuta, alates summast).

 - **Jooksva päeva kontoväljavõtte päring** ehk camt.053* – asendab kiirteavitusi teatud juhtudel.
 - **LinkPay**** – lisab arvetele ja arve e-kirjadele makselingi.

*Teenuse nimetus Luminoris, vajalik lepingu sõlmimisel.
**Meie reaalajamajanduse paketis sees, kuid pankade vaates on tegu täiesti eraldi seiseva lahendusega. Kasutamiseks vaja sõlmida pangaga eraldi leping. Lisainformatsiooni leiab [meie LinkPay juhendist](linkpay.md).

### Toetatud teenuste loetelu pankade lõikes
    

 Teenused | Swedbank | LHV | SEB | Coop Pank | Luminor | 
--|--|--|--|--|--
Maksete edastamine panka| ✅ | ✅ | ✅ | ✅ | ✅ |
Regulaarne konto väljavõte | ✅ | ✅ | ✅ | ✅ | ✅ |
Kiirteavitused | ✅ |✅ | | ✅ |✅ |
Jooksva päeva kontoväljavõtte päring | ✅ | |✅ | | ✅ |
LinkPay* | ✅ |✅ |✅ | | |


*Lisainformatsiooni leiate [meie LinkPay juhendist](linkpay.md).

### Hinnakiri pankade lõikes
Coop Pank on omalt poolt loonud hea võrdlustabeli hinnakirja erinevuste kajastamiseks pnakade lõikes. See asub jaotise all [Hinnakiri > Hinnakirja võrdlus teiste pankadega (otsekanal)](https://www.cooppank.ee/ariklient/igapaevapangandus/liidestused).

## Turvasertifikaat
Kõigi pankade puhul tuleb lahenduses seadistada turvasertifikaat. Liitumisel annab pank teile sellekohased juhised. Kuna tegemist on üsna tehniliste sammudega, siis soovitav on pöörduda oma BC partneri poole, kes aitab need teha.

Kokkuvõtvalt on vajalik:
- Sertifikaadipäringu koostamine, sertifikaadi tellimiseks.
- Sertifikaadi- ja privaatvõtmefaili liitmine pfx/p12 failiks ja parooli genereerimine.
- pfx/p12 faili ja parooli seadistamine BC-s.

Swedbank juhendid:  
[http://dev.swedbankgateway.net/content/general-info/doc/How-to-generate-CSR-and-convert-private-key-to-p12.pdf](http://dev.swedbankgateway.net/content/general-info/doc/How-to-generate-CSR-and-convert-private-key-to-p12.pdf)  
[https://www.swedbank.com/openbanking/swedbank-gateway-go-live.html](https://www.swedbank.com/openbanking/swedbank-gateway-go-live.html)  

LHV juhend:  
[https://partners.lhv.ee/en/connect/#certificates](https://partners.lhv.ee/en/connect/#certificates)

SEB juhend:  
[https://developer.baltics.sebgroup.com/bgw/documentation/authentication](https://developer.baltics.sebgroup.com/bgw/documentation/authentication)

Coop Pank juhend:  
[https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf](https://www.cooppank.ee/s3fs-public/juhendid/Gateway_votmete_genereerimise_juhend.pdf)
