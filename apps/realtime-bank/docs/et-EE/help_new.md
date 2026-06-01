---
---

# Reaalajapank: kasutusjuhend

## Sisukord

- [Rollikeskus](#rollikeskus)
  - [Kuhi Reaalajapank](#kuhi-reaalajapank)
- [Leht Maksežurnaal](#leht-maksežurnaal)
  - [Maksete panka saatmine](#maksete-panka-saatmine)
- [Leht Pangakontod](#leht-pangakontod)
- [Leht Maksete sobitamise žurnaalid](#leht-maksete-sobitamise-žurnaalid)
- [Kas midagi valesti/puudu?](#kas-midagi-valestiuudu)

# Rollikeskus

## Kuhi _Reaalajapank_  

### Tagasilükatud maksed

Siia jõuab info tagasilükatud maksete kohta. Kui pank tuvastas vea peale makse panka saatmist _Maksežunraalist_, siis jõuab see tehing siia. Igal tehingul on kirjas, milles tõrge seisnes. Üleval on toiming "Peida/Kuva", millega saab tehingud antud kuhjast eemaldada.

### Ootel maksed

Siia jõuab info maksete kohta, mis on panka edastatud ning on seal ootel maksete nimekirjas. Need tuleb pangas kinnitada.

# Leht _Maksežurnaal_

Siin tuleb makseread luua. Saab teha ka maksed tulevikku - ülekanne toimub sellel kuupäeval, mis on märgitud "Konteermiskuupäevaks".

## Maksete panka saatmine

Ilma _Reaalajapanga_ äpita tuleb vajutada "Ekspordi…" vahelehel _Pank_ - tekib XML fail, mis tuleb internetipangas importida. Reaalajapanga äpiga tuleb vajutada "Edasta panka…". 

### Oota töötlemise tulemust

Kui "Oota töötlemise tulemust" on sisse lülitatud, siis toimub makse käsitlus kohe ning saadakse esimene tagasiside, kas kõik tehingud olid korrektsed. Kui tagasiside ütleb "Aksepteeritud" olid kõik read korrektsed.

Kui tagasiside ütleb "Tagasi lükatud" oli kogu maksefail tagasi lükatud. Kui tagasiside ütleb "Osaliselt aksepteeritud", siis vähemalt üks makserida oli failis probleemne.

Selleks, et näha, milles probleem on, tuleb samas _Maksežurnaalis_, vahelehel _Pank_ vajutada "Maksekorralduste registrid". Seal on kõige ülemine rida just eksporditud maksefail ning vajutades väljal "Ülekannete arv", avaneb detailne vaade, kus on kõik tehingud. Seal on ka märgitud read, mis olid probleemsed ning ei läbinud pangapoolset kontrolli ega salvestunud panka.

### Allkirjastamata maksed

Kui "Allkirjasta maksed" on väljas - panka saadetakse allkirjastamata maksed ning need tuleb pangas kinnitada. Pangas saab allkirjastamisel kasutada kõiki variante - ID-kaart, Smart-ID ja Mobiil-ID.

### Allkirjastatud maksed

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

### Maksed panka edastatud

Soovitame konteerida tehingud alles siis, kui need on väljavõttega hiljem sisse imporditud. Sedasi on kindlus, et tehing reaalselt ka pangas läbi läks. Kui siiski vaja ette konteerida või tegite kogemata - leiate vastuse alt.

_Maksežurnaal_ tuleb peale maksete panka saatmist tühjaks kustutada. Kõik avatud kanded on siin žurnaali töölehel juba seotud maksetega - imporditud väljavõtte pealt ei tuvastata siduvusi samade kannetega. _Maksežurnaal_ tuleb teha tühjaks.

# Leht _Pangakontod_

Kõikidel pangakontodel on uued väljad: "Saldo pangas" ja "Konteerimata summa". Kui pangakonto on seadistatud pangaäpi ühendusega, siis klikkides väljadel asuvatel summadel, avanevad täpsemad vaated.

## Saldo pangas

"Saldo pangas" väärtus kuvab reaalselt seisus internetipangas. Seda arvutatakse iga tehinguga ümber ning on sama värske kui kõige uuem sõnum, mis pangaühenduse kaudu on laekunud.

Klikkides väljal "Saldo pangas" olevad summal, avanevad antud pangakonto kõik tehingud üks-ühele kujul, täpselt nii nagu need on ka internetipangas. Punasega on väljaminekud, rohelisega sissetulekud. Siia salvestub ka logi - kas tehing on pearaamatusse konteeritud või mitte, mis oli "Vastenduse täpsus" konteerimise hetkel. Kui kasutusel on automaatne konteerimine, siis automaatikaga konteeritud tehingute puhul on "Vastenduse täpsus" märgitud _Kõrge_.

## Konteerimata summa

Väli "Konteerimata summa" on väljade "Saldo pangas" ja "Saldo" (ehk pearaamatusse konteeritud summa) erinevus.

Väljal "Konteerimata summa" klikkides avaneb antud pangakonto _Maksete sobitamise žurnaal_. Siit leiab antud pangakonto tehingud, mis on _Reaalajapanga_ ühenduse kaudu laekunud ning vajavad veel raamatupidaja üle vaatamist enne konteerimist. Samad tehingud saab kätte kui otsida _Maksete sobitamise žurnaale_.

## _Pangakonto_ kaart

Siin saab määrata antud pangakontole nõutud allkirjastajaid, et kasutada allkirjastatud maksete edastamist. Kõik kasutajad, kes on määratud nõutud allkirjastajaks, peavad oma allkirjaga kinnitama maksefaili, et see panka läheks. Kasutajaid saab määrata toiminguga "Allkirjastajad".

# Leht _Maksete sobitamise žurnaalid_

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

# Kas midagi valesti/puudu?

## Maksežurnaalis konteeriti tehingud ette

Sellised makseread sulgevad Hankijaandmiku kanded, kuid loovad uued pangakontoandmiku kanded, mis jäävad avatuks. Selleks, et need saaksid suletud tuleb oodata, kuni väljavõtte laekub süsteemi. Süsteem tuvastab ise ära maksed, mis said varem konteeritud ning sobitab need olemasolevate Pangakontoandmiku kannetega.

Kui varasemalt konteeritud tehing on _Maksete sobitamise žurnaalis_ sobitatud Pangakontoandmiku kandega, siis on veerus "Konto liik" märgitud _Pangakonto_. Nende tehingute "Vastenduse täpsus" on _Kõrge_. Nendele võib ka käivitada "Konteerimise eelvaate" ning seal tuleb teade, et ühtegi uut kannet ei looda. Seejärel võib tehingud ära konteerida - sellega vaid suletakse eelnevalt loodud Pangakontoandmiku kanded.

Kui hakkategi ette konteerima teadlikult kõiki makseid hankijatele, siis võib lehel _Maksete sidumise seadistus_ välja lülitada "Luba hankijaandmiku kannete sidumine".

Kui see oli ühekordne juhus, siis tasub lehel _Maksete sidumise seadistus_ välja lülitada "Luba hankijaandmiku kannete sidumine" ajutiselt. _Maksete sobitamise žurnaalis_ üles leida tehingud, mis said eelnevalt konteeritud, need valida ning käivitada "Eemalda sidumised". Seejärel käivitada "Seo valitud…". Nüüd saab tehingud konteerida ning seejärel uuesti sisse lülitada lehel _Maksete sidumise seadistus_ välja lülitada "Luba hankijaandmiku kannete sidumine".

## _Maksete sobitamise žurnaali_ avades tuli hoiatus, et saldod ei ühti

Hoiatus võrdleb kahte väärtust: konkreetse _Pangakonto_ välja "Saldo pangas" ning viimases XML väljavõttes olnud lõppsaldot. Väli "Saldo pangas" on Business Centralis sees arvutatud väli, mis liidab ja lahutab tehingusummasid jooksvalt süsteemi sisestades. Kui pangaühenduse kaudu on mõni tehing vahele jäänud, tähendab see ka kohe, et antud saldo arvutatakse valesti.

Tuleb tuvastada, mis kuupäevast tehing puudu on. Selleks tuleb paralleelselt võrrelda internetipanka ja Business Centrali _Pangakontode_ loendit.

_Pangakontode_ loendis avada _Filtripaan_. Seejärel "Filtreeri koguväärtused järgmise alusel", valida "Kuupäevafilter" ning määrata sinna kuupäev. Sama kuupäev avada ka internetipangas ning võrrelda, kas "Saldo pangas" ja internetipanga lõppsaldo ühtivad. Sedasi saab tuvastada esimese päeva, kus saldodes tekkis erinevus ning leida puuduolev(ad) tehing(ud). Puuduolev(ad) tehing(ud) importida uuesti süsteemi järgmiste juhiste järgi.

## Uusi tehinguid ei ole laekunud/tehingud on puudu

- Kontrolli kas kõik RTB tööjärjekorra kanded töötavad. Selleks, et automaatika edaspidi töötaks tuleb tööjärjekorrad uuesti töökorda saada. Igal juhul anda konsultandile teada, kui tööd on tõrkesse läinud. Lihtsalt tööjärjekorra kande taas käivitamisest ei pruugi piisata, et automaatika taas tööle hakkaks.
  - kui panga nimeline töö ei tööta
    - suure tõenäosusega oli pangas teenus maas, ühendus katkes ing tööjärjekord ei õnnestunud süsteemi automaatselt taastada
    - on ka võimalik, et sertifikaat on aegunud
    - muu probleem
  - kui "RTB - Töötle/Seo/Konteeri" ei tööta
    - konsultant selgitab välja probleemi olemuse
  - kui tööjärjekorrad töötavad
    - kontrollida lehel _Pangakonto_ tehingud, kas tehingud on tõesti puudu
    - anda konsultandile teada
- Kas lehel _Sissetulevad pangasõnumid_ on uusi sõnumeid?
  - kui lehele minna ja seal on kohe näha read, kuupäeva(de)ga, mis süsteemist puudu, siis tähendab, et pangast on andmed kätte saadud, aga neid ei ole ära töödeldud.
    - kui need on punased on sõnumite töötlemisel olnud tõrge, tõrke info on infopaanis kuvatud - vajadusel pöörduda konsultandi poole
    - kui sõnumid on rasvases mustaas tekstis on need töötlemata. nende puhul käivitada toiming "Töötle" ning kustutada filtriväli tühjaks
  - kui vastavatest kuupäevadest uued sõnumid puuduvad või ei ole kindel, kas midagi on puudu…
- Lae puudu olevad tehingud süsteemi sisse. Selleks on kaks varianti: esimene on küll pikem, aga töötab igal juhul. **Kui kasutada all olevaid variante, ei laeta ühtegi tehingut süsteemi topelt, olenemata sellest, kas tehingud juba olid varem süsteemis või mitte.**
  - Maksefaili käitsi import
    - internetipangas eksportida puudu olevad väljavõtted XML-na
    - Business Centralis avada leht _Sissetulevad pangasõnumid_
    - seal on toiming "Impordi failist"
    - XML väljavõtte lisada sinna
    - uu(te)l sõnumi(te)l käivitada toiming "Töötle"
    - kustutada filtriväli tühjaks
    - **OK**
  - Maksefaili import Swedbank pangaühenduse kaudu
    - lehel _Swedbank Gateway seadistus_
    - toiming "Päri kontoväljavõte"
    - valida "Aruande liik" Varasem periood
    - märkida periood, kus tehingud on (potentsiaalelt) puudu  
       **NB!** kui perioodi jääb ka jooksev päev ehk tänane kuupäev, rakendub teenustasu 0,50€
    - **OK**
    - käivitada toiming "Võta uued pangasõnumid"
    - lehel _Sissetulevad pangasõnumid_
    - käivitada toiming "Töötle"
    - kustutada filtriväli tühjaks
    - **OK**
  - Maksefaili import SEB pangaühenduse kaudu (kui puudu olevad tehingud on viimase 21 päeva sees)
    - lehel _SEB Baltic Gateway seadistus_
    - toiming "Võta lõpetatud päeva tehingud"
    - märkida (potentsiaalselt) puuduolevate tehingutega kuupäev  
       **NB!** tuleb iga kuupäevaga eraldi teha
    - **OK**
    - lehel _Sissetulevad pangasõnumid_
    - käivitada toiming "Töötle"
    - kustutada filtriväli tühjaks
    - **OK**
- Nüüd on tehingud _Maksete sobitamise žurnaalis_ ning nende "Vastenduse täpsus" on _Puudub_

## Väljavõtete imporditi valesti, nüüd on topelt tehingud süsteemis

Valesti importimine tähendab otse Maksete sobitamise žurnaali - seda ei tohi teha.

Kui tehingud said sedasi konteeritud, tulid nüüd ka _Reaalajapanga_ kaudu samad tehingud uuesti _Maksete sobitamise žurnaali_ - tähendab see, et neid ei saa enam kustutada. Kindlasti teada anda konsultandile teada ning koos olukorda hinnata.

Lahenduseks saab proovida, kas süsteem laseb need tehingud konteerida mõnele vahekontole nt _Raha teel_. Seejärel teha käsitsi vastandkanded, et need tagasi pöörata.

Kui süsteem seda ei võimalda, siis tuleb:

- üles kirjutada, millistel kasutajatel on seni kasutuses _Reaalajapanga_ õiguste komplektid BGW REALTIMEBANKFULL ja BGW REALTIMEBANKLITE
- Reaalajapanga äpp uninstallida (**mitte** kustutada andmed)
- tehingud _Maksete sobitamise žurnaalis_ kustutada
- äpp uuesti installida
- kasutajatel taastada _Reaalajapanga_ õiguste komplektid BGW REALTIMEBANKFULL ja BGW REALTIMEBANKLITE

## Tehingud on _Maksete sobitamise žurnaalis_, aga need on sidumata

Järelikult ühe või mitme tehingu automaatsel sidumisel tekkis tõrge ning tehinguid ei seotud.

- Võtta filtrisse tehingud, mille "Vastenduse täpsus" on _Puudub_.
- Valida need read
- Käivitada toiming "Seo valitud…"

## _Kõrged_ tehingud on _Maksete sobitamise žurnaalis_, aga kasutusel on automaatne konteerimine

Järelikult ühe või mitme tehingu automaatsel konteerimisel tekkis tõrge ning tehinguid ei konteeritud. Tuleb leida tehing(ud), millega probleem tekkis, need lahendada ning seejärel käsitsi konteerida.

---

### Kontaktinfo
Täpsema info saamiseks, palun võtke ühendust DIGMATIX Estonia AS-ga:
<a href="https://www.digmatix.com/ee" target="_blank">https://www.digmatix.com/ee</a>