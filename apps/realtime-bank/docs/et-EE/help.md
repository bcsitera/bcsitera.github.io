---
---

# Reaalajapank: kasutusjuhend

## Sisukord

- [Seadistused](#seadistused)
- [Rollikeskus](#rollikeskus)
  - [Kuhi Reaalajapank](#kuhi-reaalajapank)
- [Leht Maksežurnaal](#leht-maksežurnaal)
  - [Maksete panka saatmine](#maksete-panka-saatmine)
- [Leht Pangakontod](#leht-pangakontod)
- [Leht Maksete sobitamise žurnaalid](#leht-maksete-sobitamise-žurnaalid)
- [Kas midagi valesti/puudu?](#kas-midagi-valestiuudu)

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
Lepingu ja/või kliendi id-d | Andmed panga lepingust.

### Pangakonto seadistused
_Pangakonto_ kaardi väljal "Pangaühendus" määrake millist pangaühendust kasutate. Juhul, kui kontol jätta pangaühendus määramata, siis selle konto tehinguinfot Business Centralisse ei laeta.

_Pangakonto_ kaardil on nupp "Sea pangaühenduse alguskuupäev", kus tuleb reaalajapangale ümberlülitamise päeval määrata kuupäev ning pangas olev algsaldo antud päeval. 

### Reaalajapanga seadistused
Lehel _Reaalajapanga seadistus_ täitke väli "Konteeritud tehingu nr." määrates vastava numbriseeria. Kui internetipangas on arvelduskontosid, mida ei soovita Business Centralis kajastada, siis on võimalik sisse laadida vaid pangasõnumid, mis puudutavad Business Centralisse salvestatud kontosid. Selleks tuleb sisse lülitada funktsionaalsus "Filtreeri sissetulevad sõnumid". "Eemalda sissetulev tundlik sisu" kustutab ära tundlikud andmed nagu töötaja isikule viitavad andmed, kui sisselaetud pangasõnum sisaldab koondmakse tehinguid.

Pangasõnumite töötlemist puudutavatest seadistustes on võimalik _Maksete sobitamise žurnaalis_ kajastada teenustasusid eraldi ridadel. Selleks tuleb sisse lülitada "Teenustasud eraldi real". Kui sisse lülitada "Nimi konteerimise kirjelduses", siis lisatakse pangast alla laetud tehingu tekstile ette ka seotud osapoole nimi. 

Väljal _Sidumise loogika_ valige "Maksete sobitamise žurnaal". Teised sidumisviisid ei ole tulevikus toetatud ning eemaldatakse.  

"Vastandkannete sobitamine" tähendab, et sidumisel otsib sobivaid kirjeid ka erimärgiliste avatud kannete seast. Nt kasutatakse nii arvete kui ka krediitarvete kandeid. Kui makse on tehtud Business Centrali kaudu, siis "Maksekorralduste registritega sobitamine" vastendab tehingud automaatselt maksekorraldus registris olevate andmetega. Kui sisse lülitada "Vastenda Klient/Hankija" ning tehingut ei seota ühegi avatud kandega, siis seotakse tehing Kliendi/hankija kontoga registrikoodi alusel. 

"Dimensioonid seotud kandelt" - kui tehing seotakse avatud kandega, millele on avarasemast dimensioonid määratud, siis tehingule lähevad samad dimensioonid. "Dimensioonid tekst-kontoks vastendamisest" võimaldab funktsionaalsuses lisada ka dimensioone. 

### Allkirjastatud maksete seadistused

Allkirjastatud maksete edastamiseks tuleb BC-s seadistada igale pangakontole, millelt makseid sooritatakse, nõutud kinnitajad. Kinnitajaid võib olla üks või mitu. Pangakontole saab määrata nõutud allkirjastajad nii _Pangakontode_ loendis kui ka igalt _Pangakonto_ kaardilt eraldi. Kõik määratud kinnitajad on makse edastamiseks ka kohustuslikud - makset ei edastata panka juhul, kui kellegi allkiri on puudu.

Kõik kasutajad, kes määratakse kinnitajaks, peavad olema ka Smart-ID seadistuses kasutajateks määratud - abiks on **[Smart-ID kasutusjuhend](../../../smart-id/docs/et-EE/help.md)**. Business Centralis on võimalik allkirjastada ainult Smart-ID kaudu - teised allkirjastamise lahendused ei ole toetatud Business Centralis. Meiliteavitused kinnitusnõudega edastab süsteem sellele emaili aadressile, mis on BC-s _Kasutaja_ kaardil määratud “Kontaktmeiliks”.


## Rollikeskus

### Kuhi _Reaalajapank_  

#### Tagasilükatud maksed

Siia jõuab info tagasilükatud maksete kohta. Kui pank tuvastas vea peale makse panka saatmist _Maksežunraalist_, siis jõuab see tehing siia. Igal tehingul on kirjas, milles tõrge seisnes. Üleval on toiming "Peida/Kuva", millega saab tehingud antud kuhjast eemaldada.

#### Ootel maksed

Siia jõuab info maksete kohta, mis on panka edastatud ning on seal ootel maksete nimekirjas. Need tuleb pangas kinnitada.

## Leht _Maksežurnaal_

Siin tuleb makseread luua. Saab teha ka maksed tulevikku - ülekanne toimub sellel kuupäeval, mis on märgitud "Konteermiskuupäevaks".

### Maksete panka saatmine

Ilma _Reaalajapanga_ äpita tuleb vajutada "Ekspordi…" vahelehel _Pank_ - tekib XML fail, mis tuleb internetipangas importida. Reaalajapanga äpiga tuleb vajutada "Edasta panka…". 

#### Oota töötlemise tulemust

Kui "Oota töötlemise tulemust" on sisse lülitatud, siis toimub makse käsitlus kohe ning saadakse esimene tagasiside, kas kõik tehingud olid korrektsed. Kui tagasiside ütleb "Aksepteeritud" olid kõik read korrektsed.

Kui tagasiside ütleb "Tagasi lükatud" oli kogu maksefail tagasi lükatud. Kui tagasiside ütleb "Osaliselt aksepteeritud", siis vähemalt üks makserida oli failis probleemne.

Selleks, et näha, milles probleem on, tuleb samas _Maksežurnaalis_, vahelehel _Pank_ vajutada "Maksekorralduste registrid". Seal on kõige ülemine rida just eksporditud maksefail ning vajutades väljal "Ülekannete arv", avaneb detailne vaade, kus on kõik tehingud. Seal on ka märgitud read, mis olid probleemsed ning ei läbinud pangapoolset kontrolli ega salvestunud panka.

#### Allkirjastamata maksed

Kui "Allkirjasta maksed" on väljas - panka saadetakse allkirjastamata maksed ning need tuleb pangas kinnitada. Pangas saab allkirjastamisel kasutada kõiki variante - ID-kaart, Smart-ID ja Mobiil-ID.

#### Allkirjastatud maksed

Kui "Allkirjasta maksed" on sees - taustal luuakse XML, mis ootab Smart-ID allkirjasid volitatud isikutelt. Lahenduse kasutuseks peab olema installitud Smart-ID äpp, kasutajatele isikukoodid seadistatud ning pangakontodel määratud volitatud isikud.

**Kui makseridade looja on ka volitatud kinnitaja:**

Avaneb tal kohe Smart-ID allkirjastamise aken ning ta saab kohe allkirjastada.

**Kui volitatud kinnitajaid on veel/makseridade looja ei ole volitatud kinnitaja:**

Edastab süsteem emaili kinnitaja(te)le. Emailis on link, mis viitab Business Centrali lehele _Maksekorralduse reg. kanded_ ning seal on kuvatud kõik tehingud, mis ühe maksefailina lähevad panka. Business Centralis saab tehingud üle vaadata ning siis allkirjastada Smart-ID-ga. Selleks on üleval toiming "Allkirjasta kõik".

**Kust leiab allkirjastamist vajavad tehingud Business Centralis?**

Kõik maksefailid asuvad lehel _Maksekorralduste registrid_. Sinna saab, kui minna _Maksežurnaali_ ning vahelehele _Pank_. Samuti leiab lehe, kui see otsingusse sisestada. 

Allkirjastamist ootavatel maksefailidel on väljal "Allkirjastamise staatus" kirjas _Allkirjastamine pooleli_. Kui avada väli "Allkirjastajad", siis seal on kuvatud kõik nõutud allkirjastajad ning kas nad on allkirjastanud juba ja millal. Samuti saab sealt uuesti välja saata meiliteavitused.

Selleks, et näha kõiki tehinguid, mis maksefailis on ning nendega tutvuda enne allkirjastamist, tuleb avada väli "Ülekannete arv". Kasutades toimingut "Allkirjasta kõik" saab read Smart-ID-ga kinnitada.

**Millal makse panka liigub?**

Kohe kui kõik volitatud isikud on oma allkirjaga maksefaili kinnitanud, liigub maksefail panka. _Maksekorralduste registris_ on ka väljal "Allkirjastamise staatus" kirjas _Saadetud_. Enam ei ole vaja internetipangas midagi kinnitada ning tehingud jäävad ootama oma ülekande kuupäeva.

#### Maksed panka edastatud

Soovitame konteerida tehingud alles siis, kui need on väljavõttega hiljem sisse imporditud. Sedasi on kindlus, et tehing reaalselt ka pangas läbi läks. Kui siiski vaja ette konteerida või tegite kogemata - leiate vastuse alt.

_Maksežurnaal_ tuleb peale maksete panka saatmist tühjaks kustutada. Kõik avatud kanded on siin žurnaali töölehel juba seotud maksetega - imporditud väljavõtte pealt ei tuvastata siduvusi samade kannetega. _Maksežurnaal_ tuleb teha tühjaks.

## Leht _Pangakontod_

Kõikidel pangakontodel on uued väljad: "Saldo pangas" ja "Konteerimata summa". Kui pangakonto on seadistatud pangaäpi ühendusega, siis klikkides väljadel asuvatel summadel, avanevad täpsemad vaated.

### Saldo pangas

"Saldo pangas" väärtus kuvab reaalselt seisus internetipangas. Seda arvutatakse iga tehinguga ümber ning on sama värske kui kõige uuem sõnum, mis pangaühenduse kaudu on laekunud.

Klikkides väljal "Saldo pangas" olevad summal, avanevad antud pangakonto kõik tehingud üks-ühele kujul, täpselt nii nagu need on ka internetipangas. Punasega on väljaminekud, rohelisega sissetulekud. Siia salvestub ka logi - kas tehing on pearaamatusse konteeritud või mitte, mis oli "Vastenduse täpsus" konteerimise hetkel. Kui kasutusel on automaatne konteerimine, siis automaatikaga konteeritud tehingute puhul on "Vastenduse täpsus" märgitud _Kõrge_.

### Konteerimata summa

Väli "Konteerimata summa" on väljade "Saldo pangas" ja "Saldo" (ehk pearaamatusse konteeritud summa) erinevus.

Väljal "Konteerimata summa" klikkides avaneb antud pangakonto _Maksete sobitamise žurnaal_. Siit leiab antud pangakonto tehingud, mis on _Reaalajapanga_ ühenduse kaudu laekunud ning vajavad veel raamatupidaja üle vaatamist enne konteerimist. Samad tehingud saab kätte kui otsida _Maksete sobitamise žurnaale_.

### _Pangakonto_ kaart

Siin saab määrata antud pangakontole nõutud allkirjastajaid, et kasutada allkirjastatud maksete edastamist. Kõik kasutajad, kes on määratud nõutud allkirjastajaks, peavad oma allkirjaga kinnitama maksefaili, et see panka läheks. Kasutajaid saab määrata toiminguga "Allkirjastajad".

## Leht _Maksete sobitamise žurnaalid_

Siin on nimekiri pangakontodest, mis on seni kasutanud _Reaalajapanga_ ühendust tehingute importimisel. Neid avades saab üle vaadata tehingud, mis on veel konteerimata pearaamatusse. Siin ridu kustutada ei saa.

Kõik tehingud olenemata kuupäevast on ühes vaates. Samuti ei ole võimalik tehinguid kustutada. Võimalik kuupäeva alusel filtreerida neid. Selleks, et tehingu saaks ära konteerida, siis tuleb kindlasti veenduda, et veerus "Erinevus" ei oleks ühtegi punast summat. See tähendab, et tegu on rahaga, mis on üles jäänud ning tuleb enne konteerimist ära siduda.

**Kuidas viia punane summa "Erinevus" eraldi reale?**

Tee aktiivseks rida, mille "Erinevust" soovid uuele reale viia. Mine vahelehele "Käsitsi sidumine" ning seal vali "Vii erinevus üle kontole". Vali kas Kliendi, Hankija või PR konto ning vajuta OK.

Kui on vaja tekkinud rida siduda konkreetse Kliendi/Hankija avatud kandega, siis tee aktiivseks lisandunud rida ning vajuta "Eemalda sidumised". Nüüd ava käsitsi sidumise aken - kas vajuta väärtusele, mis asub lahtris "Vastenduse täpsus" või mine vahelehele _Käsitsi sidumine_ ning seal vali "Seo käsitsi…". Nüüd saad valida konkreetse avatud kande, millega tehing siduda.

"Erinevust" saab uutele ridadele viia nii mitu korda kui vaja.

**Sidumise kinnitamine**

Tehingud, mis on üle vaadatud tasub märkida ära - kasuta selleks toimingut "Kinnita sidumised". Sedasi on lihtsam hallata, millised tehingud on üle kontrollitud ning kinnitatud. See on ka abiks kui on soov vahepeal žurnaalis tehinguid vähendada ning osaliselt konteerida neid.

**Kuidas osaliselt konteerida?**

Kui oled valmis osad tehingud ära konteerima, siis vajuta nuppu "Konteeri…". Nüüd avaneb hüpikaken. Automaatselt on täidetud samad filtrid, mis žurnaali töölehe vaateski olid. Lisaks saab märkida, mis "Vastenduse täpsus" olema peab, et konteerida tehingud ära. Kui filtriväljad tühjaks jätta, konteeritakse kõik vaates olnud tehingud ära.

Samamoodi saab filtreid valida ka konteerimise eelvaates.

**Vastenda tekst kontoks**

Siin saab määrata tehingu teksti osasid ning millisele kontole süsteem need peaks automaatselt siduma. Nt tehingu, mis sisaldavad teksti "teenustasu" saab määrata konkreetsele PR kontodele.

Täiendused. Väljas "Vastendamise tekst" saab kasutada \*, et veel täpsemini määrata tehingu vastendamise teksti. Lisaks PR kontodele saab tehinguid määrata ka konkreetsetele Kliendi, Hankija või Pangakonto kontodele (nt kaarditerminalid).

Igal real saab määrata ka dimensioone. Selleks kasutada toimingu "Dimensioonid". Sinna saab panna ühe või mitu dimensiooni ning määrata kontreetsed Dimensiooniväärtused.

Lisatud on ka väli "Vastendamise seotud osapoole liik", kus saab määrata, kas vastendus käivitub ainult _Organisatsioonide_ või ainult _Eraisikute_ puhul. Kui väli tühjaks jätta käivitub vastendmaine olenemata maksja liigist.


---

### Kontaktinfo
Täpsema info saamiseks, palun võtke ühendust DIGMATIX Estonia AS-ga:
<a href="https://www.digmatix.com/ee" target="_blank">https://www.digmatix.com/ee</a>