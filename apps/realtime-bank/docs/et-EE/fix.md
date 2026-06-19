---
---

# Kõige levinumad lahendused

- [_Maksete sobitamise žurnaali_ avades tuli hoiatus, et saldod ei ühti](#maksete-sobitamise-žurnaali-avades-tuli-hoiatus-et-saldod-ei-ühti)
- [Uusi tehinguid ei ole laekunud/tehingud on puudu](Uusi tehinguid ei ole laekunud/tehingud on puudu)
- [Väljavõte imporditi valesti, nüüd on topelt tehingud süsteemis](#väljavõte-imporditi-valesti-nüüd-on-topelt-tehingud-süsteemis)
- [Tehingud on _Maksete sobitamise žurnaalis_, aga need on sidumata](#tehingud-on-maksete-sobitamise-žurnaalis-aga-need-on-sidumata)
- [_Kõrged_ tehingud on _Maksete sobitamise žurnaalis_, aga kasutusel on automaatne konteerimine](#kõrged-tehingud-on-maksete-sobitamise-žurnaalis-aga-kasutusel-on-automaatne-konteerimine)


## _Maksete sobitamise žurnaali_ avades tuli hoiatus, et saldod ei ühti

Hoiatus võrdleb kahte väärtust: konkreetse _Pangakonto_ välja "Saldo pangas" ning viimases XML väljavõttes olnud lõppsaldot. Väli "Saldo pangas" on Business Centralis sees arvutatud väli, mis liidab ja lahutab tehingusummasid jooksvalt süsteemi sisestades. Kui pangaühenduse kaudu on mõni tehing vahele jäänud, tähendab see ka kohe, et antud saldo arvutatakse valesti.

Tuleb tuvastada, mis kuupäevast tehing puudu on. Selleks tuleb paralleelselt võrrelda internetipanka ja Business Centrali _Pangakontode_ loendit.

_Pangakontode_ loendis avada _Filtripaan_. Seejärel "Filtreeri koguväärtused järgmise alusel", valida "Kuupäevafilter" ning määrata sinna kuupäev. Sama kuupäev avada ka internetipangas ning võrrelda, kas "Saldo pangas" ja internetipanga lõppsaldo ühtivad. Sedasi saab tuvastada esimese päeva, kus saldodes tekkis erinevus ning leida puuduolev(ad) tehing(ud). Puuduolev(ad) tehing(ud) importida uuesti süsteemi järgmiste juhiste järgi.

## Uusi tehinguid ei ole laekunud/tehingud on puudu

- Kontrolli kas kõik RTB tööjärjekorra kanded töötavad. Selleks, et automaatika edaspidi töötaks tuleb tööjärjekorrad uuesti töökorda saada. Igal juhul anda konsultandile teada, kui tööd on tõrkesse läinud. Lihtsalt tööjärjekorra kande taas käivitamisest ei pruugi piisata, et automaatika taas tööle hakkaks. Tööjärjekorra logikannete alt on võimalik näha ka tõrketeate sisu. 
  - Kui panganimeline töö ei tööta
    - Tõrkekood algab 5-ga (500, 503 jt), tähendab see, et pank ei võta päringuid vastu. Enamikel juhtudel viitab see, kas tõrgetele nende keskkonnas või ka hooldustöödele.
    - On ka võimalik, et sertifikaat on aegunud
  - kui "RTB - Töötle/Seo/Konteeri" ei tööta
    - Probleem tekkis peale pangast sõnumite importimist, kas töötlemise, sidumise või konteerimise käigus. Konsultant aitab probleemi olemust selgitada.
  - kui tööjärjekorrad töötavad
    - Kontrollida lehel _Pangakonto_ tehingud, kas tehingud on puudu
    - Konsultant aitab probleemi olemust selgitada.
- Kas lehel _Sissetulevad pangasõnumid_ on uusi sõnumeid?
  - Kui minna lehele _Sissetulevad pangasõnumid_ ja seal on kohe näha read, kuupäeva(de)ga, mis süsteemist puudu, siis tähendab, et pangast on andmed kätte saadud, aga neid ei ole ära töödeldud.
    - Kui need on punased on sõnumite töötlemisel olnud tõrge, tõrke info on infopaanis kuvatud - vajadusel pöörduda konsultandi poole
    - Kui sõnumid on rasvases mustas tekstis on need töötlemata. Nende puhul käivitada toiming "Töötle" ning kustutada filtriväli tühjaks
  - Kui vastavatest kuupäevadest uued sõnumid puuduvad või ei ole kindel, kas midagi on puudu…
- Lae puudu olevad tehingud süsteemi sisse. Selleks on kaks varianti: esimene on küll pikem, aga töötab igal juhul. **Kui kasutada all olevaid variante, ei laeta ühtegi tehingut süsteemi topelt, olenemata sellest, kas tehingud juba olid varem süsteemis või mitte.**
  - Maksefaili käitsi import
    - internetipangas eksportida puudu olevad väljavõtted XML-na
    - Business Centralis avada leht _Sissetulevad pangasõnumid_
    - toiming "Impordi failist"
    - XML väljavõtte lisada sinna
    - käivitada toiming "Töötle"
    - kustutada filtriväli tühjaks
    - **OK**
  - Maksefaili import Swedbank pangaühenduse kaudu
    - lehel _Swedbank Gateway seadistus_
    - toiming "Päri kontoväljavõte"
    - valida "Aruande liik" _Varasem periood_
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

Kui tehingud said sedasi konteeritud, tulid nüüd ka _Reaalajapanga_ kaudu samad tehingud uuesti _Maksete sobitamise žurnaali_ - tähendab see, et neid ei saa enam kustutada. Kindlasti anda konsultandile teada ning koos olukorda hinnata.

Üks lahendus on app uninstallida (andmed alles jätta), topelttehingud seejärel kustutada Maksete sobitamise žurnaalist, app uuesti installida ning üle kontrollida kasutajate õigused.

## Tehingud on _Maksete sobitamise žurnaalis_, aga need on sidumata

Järelikult ühe või mitme tehingu automaatsel sidumisel tekkis tõrge ning tehinguid ei seotud.

- Võtta filtrisse tehingud, mille "Vastenduse täpsus" on _Puudub_.
- Valida need read
- Käivitada toiming "Seo valitud…"

## _Kõrged_ tehingud on _Maksete sobitamise žurnaalis_, aga kasutusel on automaatne konteerimine

Järelikult ühe või mitme tehingu automaatsel konteerimisel tekkis tõrge ning tehinguid ei konteeritud. Tuleb leida tehing(ud), millega probleem tekkis, need lahendada ning seejärel käsitsi konteerida.