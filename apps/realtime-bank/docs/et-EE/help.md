---
---
# Reaalaja pank - Kasutusjuhend
## Sisukord

- [Seadistused](#seadistused)
- [Sissetulevad pangasõnumid](#sissetulevad-pangasõnumid)
- [Pangatehingute ülevaade, sidumine ja konteerimine](#pangatehingute-ülevaade-sidumine-ja-konteerimine)

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
Teenuse URL | Sisestage panga teenuse aadress: <br> Swedbank - https://swedbankgateway.net/ <br> SEB - https://api.bgw.baltics.sebgroup.com/ <br> LHV - https://connect.lhv.eu/ <br> Coop Pank - https://cpgw.cooppank.ee/ <br> Luminor - https://ftc.luminoropenbanking.com/v1/ft-services/CorporateFileService  
Seadme- või autentimissertifikaadi failinimi | Importige sertifikaadi fail (pfx/p12 formaat). Sertifikaadi saate pangast.
Seadme- või autentimissertifikaadi parool | Sisestage sertifikaadi parool.
Krüpteermissertifikaat (Swedbank-i puhul) | Sertifikaadi saab laadida siit: http://dev.swedbankgateway.net/info#certificates
Lepingu ja/või kliendi id-d | Andmed panga lepingust

### Pangakonto seadistused
_Pangakonto_ kaardi väljal "Pangaühendus" määrake millist pangaühendust kasutate. Juhul, kui kontol jätta pangaühendus määramata, siis selle konto tehinguinfot Business Centralisse ei laeta.

### Reaalajas panga seadistused
Lehel _Reaalajas panga seadistus_ täitke väli "Konteeritud tehingu nr." määrates vastava numbriseeria.

Väljal _Sidumise loogika_ valige "Maksete sobitamise žurnaal". Teised sidumisviisid ei ole tulevikus toetatud ning eemaldatakse.

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
Panagsõnumi(te) töötlemiseks vajutage nupule "Töötle", mis loeb XML vormingus pangasõnumist välja  tehingute info ning salvestab need tabelitesse _Pangakonto tehingud_ ning _Maksete sobitamise žurnaal_.

Peale sõnumi edukat töötlemist saate vajutada nupule "Näita kõiki sõnumeid" - sõnumil on nüüd Olek _Töödeldud_. Paremal olevas kiirinfos on näha _Salvestatud tehingute arv_. Sellele numbrile vajutades on võimalik liikuda lehele _Pangakonto tehingud_.

## Pangatehingute ülevaade, sidumine ja konteerimine

### Pangatehingud

Pangakonto kaardil on uus väli "Saldo pangas". Selles summas kajastuvad kõik pangast imporditud tehingud, ka need, mis on veel sidumata ning konteerimata. Seetõttu võib väljal "Saldo pangas" olev summa erineda väljal "Saldo" kuvatavast summast. 
Väljal "Saldo pangas" summale vajutades avatakse leht _Pangakonto tehingud_, milles on näha kõik tehingud nii nagu need on pangakontol pangas.

### Pangatehingute sidumine ja konteerimine
Sidumiseks ja konteerimiseks kasutatakse püsivat "RTB" nimelist _Maksete sobitamise žurnaali_.  
  
Juhul, kui panagsõnumite töötlemise tööjärjekorra automaattööl on aktiveeritud ka "Sidumine" ja "Konteerimine" - siis jäävad "RTB" žurnaali alles ainult need read, mis vajavad kästisi töötlemist ehk read, mida automaatselt siduda ei õnnestunud.

---

### Kontaktinfo
Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:
<a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>
