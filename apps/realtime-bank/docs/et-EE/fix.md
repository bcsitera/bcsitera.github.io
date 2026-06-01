---
---

# Kas midagi valesti/puudu?

- [_Maksežurnaalis_ konteeriti tehingud ette](#maksežurnaalis-konteeriti-tehingud-ette)
- [_Maksete sobitamise žurnaali_ avades tuli hoiatus, et saldod ei ühti](#maksete-sobitamise-žurnaali-avades-tuli-hoiatus-et-saldod-ei-ühti)
- [Uusi tehinguid ei ole laekunud/tehingud on puudu](Uusi tehinguid ei ole laekunud/tehingud on puudu)
- [Väljavõte imporditi valesti, nüüd on topelt tehingud süsteemis](#väljavõte-imporditi-valesti-nüüd-on-topelt-tehingud-süsteemis)
- [Tehingud on _Maksete sobitamise žurnaalis_, aga need on sidumata](#tehingud-on-maksete-sobitamise-žurnaalis-aga-need-on-sidumata)
- [_Kõrged_ tehingud on _Maksete sobitamise žurnaalis_, aga kasutusel on automaatne konteerimine](#kõrged-tehingud-on-maksete-sobitamise-žurnaalis-aga-kasutusel-on-automaatne-konteerimine)

## _Maksežurnaalis_ konteeriti tehingud ette

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

## Väljavõte imporditi valesti, nüüd on topelt tehingud süsteemis

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