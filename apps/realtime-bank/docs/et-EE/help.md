---
---
# Reaalaja pank - Kasutusjuhend
## Sisukord

- [Seadistused](#seadistused)
- [Maksete edastamine panka](#maksete-edastamine-panka)  
- [Sissetulevad pangasõnumid](#sissetulevad-pangasõnumid)
- [Pangatehingute ülevaade, sidumine ja konteerimine](#pangatehingute-ülevaade-sidumine-ja-konteerimine)
- [LinkPay kasutusjuhend](linkpay.md)

## Seadistused

### Pangaühenduste seadistused

Võimalik on seadistada pangaühendused järgmiste pankadega:
1. Swedbank Gateway
2. SEB Baltic Gateway
3. LHV Connect
4. Coop Pank Gateway
5. Luminor Web Service

Liitumisjuhiseid leiab [siit](join.md).

Iga pangaühenduse kohta on seadistuse leht (n. "Swedbank Gateway seadistus"), kus tuleb täita järgmised väljad:

Väli |  Selgitus | 
-- | --
Teenuse URL | Sisestage panga teenuse aadress: <br> Swedbank - https://psd2.api.swedbank.com/partner/v1/sgw/ <br> SEB - https://api.bgw.baltics.sebgroup.com/ <br> LHV - https://connect.lhv.eu/ <br> Coop Pank - https://cpgw.cooppank.ee/ <br> Luminor - https://ftc.luminoropenbanking.com/v1/ft-services/CorporateFileService  
Seadme- või autentimissertifikaadi failinimi | Importige sertifikaadi fail (pfx/p12 formaat). Sertifikaadi saate pangast.
Seadme- või autentimissertifikaadi parool | Sisestage sertifikaadi parool.
Krüpteermissertifikaat (Swedbank-i puhul) | Sertifikaadi saab laadida siit: http://dev.swedbankgateway.net/info#certificates
Lepingu ja/või kliendi id-d | Andmed panga lepingust.

### Pangakonto seadistused
_Pangakonto_ kaardi väljal "Pangaühendus" määrake millist pangaühendust kasutate. Juhul, kui kontol jätta pangaühendus määramata, siis selle konto tehinguinfot Business Centralisse ei laeta.

_Pangakonto_ kaardil on nupp "Sea pangaühenduse alguskuupäev", kus tuleb reaalajapangale ümberlülitamise päeval määrata kuupäev ning pangas olev algsaldo antud päeval. 

### Reaalajas panga seadistused
Lehel _Reaalajas panga seadistus_ täitke väli "Konteeritud tehingu nr." määrates vastava numbriseeria.

Väljal _Sidumise loogika_ valige "Maksete sobitamise žurnaal". Teised sidumisviisid ei ole tulevikus toetatud ning eemaldatakse.

### Allkirjastatud maksete seadistused

Allkirjastatud maksete edastamiseks tuleb BC-s seadistada igale pangakontole, millelt makseid sooritatakse, nõutud kinnitajad. Pangakontole saab määrata nõutud allkirjastajad nii _Pangakontode_ loendis kui ka iaglt _Pangakonto_ kaardilt eraldi. Kõik määratud kinnitajad on makse edastamiseks ka kohustuslikud - makset ei edastata panka juhul, kui kellegi allkiri on puudu.

Kõik kasutajad, kes määratakse kinnitajaks, peavad olema ka Smart-ID seadistuses kasutajateks määratud - abiks on **[Smart-ID ksutusjuhend](../../../smart-id/docs/et-EE/help.md)**. Meiliteavitused edastab süsteem sellele emaili aadressile, mis on BC-s _Kasutaja_ kaardil määratud “Kontaktmeiliks”.

Kui allkirjastatud maksete edastamine on algatatud, on võimalik maksekorralduste registrite alt jälgida makse allkirja staatust. Selleks tuleb valida õige makse ning välja “Allkirjastajad“ kaudu saab vaadata nõutud allkirjastajaid antud maksel. Samuti on võimalik näha, kes nõutud kinnitajatest on oma allkirja andnud ja millal ning ka informatsiooni saadetud meiliteavituste kohta. Samal lehel on võimalik uuesti meiliteavitused välja saata kasutajatele, kelle allkiri on endiselt puudu.

## Maksete edastamine panka

Lehel _Maksežurnaal_ saab luua panka saadetavad maksed. Vajutades vahelehel _Pank_ nupule "Edasta panka..." avaneb aruande päringuaken. Siin on võimalus sisse lülitada funktsioon _Oota töötlemise tulemust_. Sellisel juhul jääb süsteem ootama, pangast esimest maksestaatust. Kõik maksed, mis on žurnaalis, kombineeritakse üheks maksekorralduse registriks ning edastatakse panka allkirjastamata kujul ehk panka salvestuvad need kui ootel maksed.

Võimalik on maksed ka BC-s ära allkirjastada ning siis ei ole neid enam vaja pangas kinnitada, ent selleks tuleb teha vajalikud seadistused, mille kohta leiate lisainfot **[siit](#allkirjastatud-maksete-seadistused)**. Allkirjastatud kujul maksete edastamiseks tuleb sisse lülitada funktsioon _Allkirjasta maksed_. Kui maksete edastaja on ka nõutud kinnitaja, siis on temal kohe võimalus maksed allkirjastada, teistele nõutud allkirjastajatele edastatakse kinnitusnõue meili teel.  

**Microsofti soovitus**: Pärast maksežurnaali panka edastamist, tuleks kõik read _Maksežurnaalist_ kustutada. Konteerima peaks alles _Maksete sobitamise žurnaalis_, kui pangast on juba saabunud kinnitus väljaminekute korrektsuse osas.

Eksporditud maksefailid leiad samalt lehelt nupu alt, või otsides vaadet, _Maksekorralduste registrid_. Välja alla _Ülekannete arv_ on salvestatud kõik žurnaali tehingud eraldi ning iga tehingu kohta ka maksestaatus.

Kui kasutaja roll on _Raamatupidaja_, tekib talle avalehele _Reaalajas pank_ kuhi. Sinna tuleb sisse informatsioon tagasilükatud ning ootel maksete kohta. Avades leht _Tagasilükatud maksed_ on võimalik iga makse eraldi märkida peidetuks, kasutades nuppu "Peida/kuva" - see eemaldab probleemse makse rollikeskuse ülevaatest.

## Sissetulevad pangasõnumid

### Pangasõnumite laadimine pangast

Iga pangaühenduse seadistamise lehel (n. _Swedbank Gateway seadistus)_ on nupp "Võta uued pangasõnumid", mida saab kasutada pangasõnumite impordiks.
    
Vajutades nupule "Tööjärjekorra kanded", avatakse leht _Tööjärjekorra kanded_, kus on võimalik seadistada kaks automaattööd: 
- pangasõnumite võtmine pangast ja 
- pangasõnumite töötlemine (sh. tehingute sidumine ning konteerimine). 

Soovitud töötlemise sammud määrake töötlemise automaattöö nupu all _Aruande päringuaken_.

Imporditud pangasõnumid kuvatakse lehel _Sissetulevad pangasõnumid_. Vaikimisi kuvatakse kirjed, mis on veel töötlemata. Kõikide sõnumite nägemiseks vajutage nupule "Näita kõiki sõnumeid".


### Pangasõnumite import failist

Lehel _Sissetulevad pangasõnumid_ on tegevus "Impordi failist". Seda saab kasutada juhuks, kui pangaühendus ei ole seadistatud ja sõnumeid pangast automaatselt ei tule.

### Pangasõnumite töötlemine
Pangsõnumi(te) töötlemiseks vajutage nupule "Töötle", mis loeb XML vormingus pangasõnumist välja  tehingute info ning salvestab need tabelitesse _Pangakonto tehingud_ ning _Maksete sobitamise žurnaal_.

Peale sõnumi edukat töötlemist saate vajutada nupule "Näita kõiki sõnumeid" - sõnumil on nüüd Olek _Töödeldud_. Paremal olevas kiirinfos on näha _Salvestatud tehingute arv_. Sellele numbrile vajutades on võimalik liikuda lehele _Pangakonto tehingud_.

## Pangatehingute ülevaade, sidumine ja konteerimine

### Pangatehingud

Pangakonto kaardil on uus väli "Saldo pangas". Selles summas kajastuvad kõik pangast imporditud tehingud, ka need, mis on veel sidumata ja/või konteerimata. Seetõttu võib väljal "Saldo pangas" olev summa erineda väljal "Saldo" kuvatavast summast. 

Väljal "Saldo pangas" summale vajutades avatakse leht _Pangakonto tehingud_, millel on näha kõik tehingud nii nagu need on pangakontol pangas.

### Pangatehingute sidumine ja konteerimine
Sidumiseks ja konteerimiseks kasutatakse püsivat "RTB" nimelist _Maksete sobitamise žurnaali_.  
  
Juhul, kui pangasõnumite töötlemise tööjärjekorra automaattööl on aktiveeritud ka "Sidumine" ja "Konteerimine" - siis jäävad "RTB" žurnaali alles ainult need read, mis vajavad kästisi töötlemist ehk read, mida automaatselt siduda ei õnnestunud.

---

### Kontaktinfo
Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:
<a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>
