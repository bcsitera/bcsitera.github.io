---
---
# Liitumine

## Sisukord

- [Taotluse esitamine](#taotluse-esitamine)
- [Otsekanal vs operaatorkanal](#otsekanal-vs-operaatorkanal)
- [Toetatud teenused](#toetatud-teenused)
- [Turvasertifikaat](#turvasertifikaat)
- [Seadistused](#seadistused)


## Taotluse esitamine
Business Central kasutab liidestamisel nii otsekanalit kui ka operaatorkanalit - pankade lõikes erinev. Liitumiseks võtke ühendust oma kliendihalduriga või esitage taotlus panga kodulehel.

Võimalik on seadistada pangaühendused järgmiste pankadega:
1. [Swedbank Gateway - otse- ja operaatorkanal](https://www.swedbank.ee/business/d2d/ebanking/gateway)
2. [LHV Connect - otsekanal](https://www.lhv.ee/et/connect)
3. [SEB Baltic Gateway - otse- ja operaatorkanal](https://www.seb.ee/ariklient/igapaevapangandus/elektroonilised-kanalid/baltic-gateway)
4. [Coop Pank Gateway - otse- ja operaatorkanal](https://www.cooppank.ee/gateway)
5. [Luminor Web Service - otsekanal](https://luminor.ee/ari/web-services)

## Otsekanal vs operaatorkanal

Pangad | Otsekanal | Operaatorkanal |
--|--|--
Swedbank Gateway | ✅ | ✅ |
LHV Connect | ✅ | ⏳ | 
SEB Baltic Gateway | ✅ | ✅ |
Coop Pank Gateway | ✅ | ✅ | 
Luminor Web Service | ✅ | ⏳ | 

Otsekanali puhul on Teie majandustarkvara ühendatud otse pangaga. See lahendus on saadval kõikides pankades üle Baltikumi. Andmete vahendamiseks tuleb luua turvasertifikaat. Sertifikaadi loomise juhendi edastab pank Teile ning on osa lepingu sõlmimise prostessist. Sektsioonis [Turvasertifikaat](#turvasertifikaat) saate tutvuda antud sammuga. Soovitus on lasta DIGMATIX Estonial ära teha antud tegevused.
**NB!** Swedbank edastab ka juhendi Swedbank Developer Portaalis tegevuste läbimiseks. Palume need sammud läbi teha - küsimuste tekkimisel abistab konsultant.

Operaatorkanali puhul on DIGMATIX Estonia andmete vahendaja. See tähendab, et Teie majandustarkavara edastab andmeid meile ning meie omakorda edastame need panka ja vastupidi. Kõik ühendused andmete vahendamise protsessis on kaitstud turvasertifikaatidega. Siin lahenduses loob ja haldab kõiki vajalikke sertifikaate DIGMATIX Estonia. Operaatorkanali kasutajatele on pangalepingud üldjuhul soodsamatel tingimusel. See lahnedus on saadval hetkel läbi Swedbank, SEB ja Coop Panga ning ainult Eestis.
**NB!** Kui olete Business Centrali Pilve lahenduse kasutaja, on Coop Pank Gateway teile saadaval ainult operaatorkanalina.

Siit leite ka **Swedbank Gateway operaatorkanali kiirtaotluse lingi**: https://www.swedbank.ee/business/d2d/ebanking/gateway/conclude?operatorId=47540


## Toetatud teenused
### Teenuste kirjeldused
 - **Maksete edastamine panka** – ootel ehk allkirjastamata maksed või ka Smart-ID-ga allkirjastatud maksed.  
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
Coop Pank on omalt poolt loonud hea võrdlustabeli hinnakirja erinevuste kajastamiseks pankade lõikes. See asub Coop Panga Gateway liidese lehel.  

Otsekanali hinnakirja erinevused [leiate siit](https://www.cooppank.ee/ariklient/igapaevapangandus/liidestused#?tab=tab-4&accordionItem=otsekanal).  

Operaatorkanali hinnakirja erinevused [leiate siit](https://www.cooppank.ee/ariklient/igapaevapangandus/liidestused#?tab=tab-4&accordionItem=otsekanal). **NB!** Operaatorkanalit toetame vaid Swedbank, SEB ning Coop Pank Gateway-ga.

## Turvasertifikaat (otsekanal)
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

## Seadistused

### Pangaühenduste seadistused

Võimalik on seadistada pangaühendused järgmiste pankadega:
1. Swedbank Gateway
2. SEB Baltic Gateway
3. LHV Connect
4. Coop Pank Gateway
5. Luminor Web Service


Iga pangaühenduse kohta on seadistuse leht (n. _Swedbank Gateway seadistus_), kus tuleb täita järgmised väljad:

Väli |  Selgitus | 
-- | --
Teenuse URL | Sisestage panga teenuse aadress: <br> Swedbank - https://psd2.api.swedbank.com/partner/v1/sgw/ <br> SEB - https://api.bgw.baltics.sebgroup.com/ <br> LHV - https://connect.lhv.eu/ <br> Coop Pank - https://cpgw.cooppank.ee/ <br> Luminor - https://ftc.luminoropenbanking.com/v1/ft-services/CorporateFileService  
Seadme- või autentimissertifikaadi failinimi | Importige sertifikaadi fail (pfx/p12 formaat). Sertifikaadi saate pangast.
Seadme- või autentimissertifikaadi parool | Sisestage sertifikaadi parool.
Lepingu ja/või kliendi id-d | Andmed panga lepingust.
Operaatorkanali režiim | Lülitada sisse kui sõlmisite operaatorkanali lepingu.

Samal lehel toiminguga "Tööjärjekorra kanded", luuakse kõik antud panga jaoks vajalikud tööjärjekorra kanded. Need tuleb seadistada vastavalt soovitud sagedusele. 

### Pangakonto seadistused
_Pangakonto_ kaardi väljal "Pangaühendus" määrake millist pangaühendust kasutate. Juhul, kui kontol jätta pangaühendus määramata, siis selle konto tehinguinfot Business Centralisse ei laeta.

_Pangakonto_ kaardil on nupp "Sea pangaühenduse alguskuupäev", kus tuleb reaalajapangale ümberlülitamise päeval määrata kuupäev ning pangas olev algsaldo antud päeval. 

### Reaalajapanga seadistused
Lehel _Reaalajapanga seadistus_ täitke väli "Konteeritud tehingu nr." määrates vastava numbriseeria. Kui internetipangas on arvelduskontosid, mida ei soovita Business Centralis kajastada, siis on võimalik sisse laadida vaid pangasõnumid, mis puudutavad Business Centralisse salvestatud kontosid. Selleks tuleb sisse lülitada funktsionaalsus "Filtreeri sissetulevad sõnumid". "Eemalda sissetulev tundlik sisu" kustutab ära tundlikud andmed nagu töötaja isikule viitavad andmed, kui sisselaetud pangasõnum sisaldab koondmakse tehinguid.

Pangasõnumite töötlemist puudutavatest seadistustes on võimalik _Maksete sobitamise žurnaalis_ kajastada teenustasusid eraldi ridadel. Selleks tuleb sisse lülitada "Teenustasud eraldi real". Kui sisse lülitada "Nimi konteerimise kirjelduses", siis lisatakse pangast alla laetud tehingu tekstile ette ka seotud osapoole nimi. 

Väljal _Sidumise loogika_ valige "Maksete sobitamise žurnaal". Teised sidumisviisid ei ole tulevikus toetatud ning eemaldatakse.  

"Vastandkannete sobitamine" tähendab, et sidumisel otsib sobivaid kirjeid ka erimärgiliste avatud kannete seast. Nt kasutatakse nii arvete kui ka krediitarvete kandeid. Kui makse on tehtud Business Centrali kaudu, siis "Maksekorralduste registritega sobitamine" vastendab tehingud automaatselt maksekorraldus registris olevate andmetega. Kui sisse lülitada "Vastenda Klient/Hankija" ning tehingut ei seota ühegi avatud kandega, siis seotakse tehing Kliendi/hankija kontoga registrikoodi alusel. 

"Dimensioonid seotud kandelt" - kui tehing seotakse avatud kandega, millele on avarasemast dimensioonid määratud, siis tehingule lähevad samad dimensioonid. "Dimensioonid tekst-kontoks vastendamisest" võimaldab funktsionaalsuses lisada ka dimensioone. 

"Maksehälve mitme seotud kandega" võimaldab tuvastada maksehälbeid, nii nagu need Pearaamatu seadistuses määratud on, ka siis, kui tehing on seotud mitme avatud kandega.
**NB!** Pea meeles, et iga tehingu puhul “Lubatud maksehälbe summa (PR seadistus)” korrutatakse seotud kannete arvuga. Nt tehingul, mis on seotud 4 avatud kandega, uus Lubatud maksehälbe summa = 4 × “Lubatud maksehälbe summa (PR seadistus)”. Ei tasu muretsede, kuna tehing tuleb alati üle vaadata, sest selliste tehingute "Vastenduse täpsus" on _Kõrge_.

### Allkirjastatud maksete seadistused

Allkirjastatud maksete edastamiseks tuleb BC-s seadistada igale pangakontole, millelt makseid sooritatakse, nõutud kinnitajad. Kinnitajaid võib olla üks või mitu. Pangakontole saab määrata nõutud allkirjastajad nii _Pangakontode_ loendis kui ka igalt _Pangakonto_ kaardilt eraldi. Kõik määratud kinnitajad on makse edastamiseks ka kohustuslikud - makset ei edastata panka juhul, kui kellegi allkiri on puudu.

Kõik kasutajad, kes määratakse kinnitajaks, peavad olema ka Smart-ID seadistuses kasutajateks määratud - abiks on **[Smart-ID kasutusjuhend](../../../smart-id/docs/et-EE/help.md)**. Business Centralis on võimalik allkirjastada ainult Smart-ID kaudu - teised allkirjastamise lahendused ei ole toetatud Business Centralis. Meiliteavitused kinnitusnõudega edastab süsteem sellele emaili aadressile, mis on BC-s _Kasutaja_ kaardil määratud “Kontaktmeiliks”.

### Ostuarvete ja maksete integratsiooni lahenduse seadistused

Lahenduse kasutamiseks tuleb lehel Reaalajapanga seadistus sisse lülitada funktsioon “Allkirjasta makse arve kinnitamisel”. Seejärel tuleb kuupäeva valemiga määrata väljale “Maksetähtaja arvutamine”, mitu päeva enne arve maksetähtaega tehing pangas sooritatakse. Pangakonto, mis määratakse _Reaalajapanga seadistuses_ väljale “Vaikimisi pangakonto nr.“ on vaike arvelduskonto, millelt ostuarvete eest tasuma hakatakse. Ostuarve peal on olemas väli “Reaalajas pangakonto nr.”, kus algselt läheb vaikekonto, ent seda saab igal ostuarvel muuta enne kinnitusnõude saatmist. *Vt ka lähemalt, kuidas seadistada pangakontodele nõutud allkirjastajaid*.




