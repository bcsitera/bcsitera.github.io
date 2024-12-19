---
---
##### Versioon 21.0.24352.0
- Lisandus Swedbank Gateway uue API tugi.
- Lisandus makselingi funktsionaalsus [LinkPay](https://support.every-pay.com/et/merchant-support/linkpay-makselink/)

##### Versioon 21.0.24242.0
- Maksete edastamisel panka maksefaili töötlemistulemuste kohene tagaside kasutajale (Swedbank, LHV, Coop).

##### Versioon 21.0.24105.0
- Coop Pank Gateway on nüüd kasutatav ka BC pilveklientidel.

##### Versioon 21.0.24085.0
- Lisandus Luminor Bank AS ühendus (Luminor WebService teenus).

##### Versioon 21.0.24017.0
- Lisandus Swedbank jooksva päeva kontoväljavõtte päring. Seda on hea kasutada juhul, kui tehinguid on palju ja kiirteavitus ei ole otstarbekas.

##### Versioon 21.0.24017.0
- Lisandus Coop Pank Gateway
- Imporditakse mitte kõigi vaid ainult BC-s seadistatud pangakontode sõnumid. Vajalik juhul, kui on pangakontosid, mille tehinguinfot BC-sse ei soovita.

##### Versioon 21.0.23153.1
RTB makste sobitamise žurnaalis saab nüüd üht pangatehingu rida jagada mitmeks kasutades nuppu "Vii erinevus üle kontole". Konteerimine kontrollib, et jagatud ridade summa vastaks pangatehingu summale.

##### Versioon 21.2.23145.0
Pangatehingute sidumiseks ja konteerimiseks saab nüüd kasutada "Maksete sobitamise žurnaali".
 
Sellisel juhul imporditakse pangatehingud **RTB** nimelisse maksete sobitamise žurnaali. Tegu on püsiva žurnaaliga, mis ei kustu konteerimisel ning millest on lubatud ka osaline konteerimine. Žurnaalirea konteerimisel märgitakse pangatehingute aknas tehing konteerituks.

Maksete sobitamise žurnaali kasutamise saab aktiveerida reaalaja panga seadistuse "Sidumise loogika" valikus.  

##### Versioon 20.2.23046.0
- Lisandus vaikedimensioonide määramise võimalus tekst kontoks vastendamisele.
- Parandus: kasutaja sisestatud konteerimise kirjeldus ei läinud vahel konteerimisel kaasa.

##### Versioon 20.2.23035.0
- Lisandus maksete otseedastamine Swedpanka (lisaks LHV-le, SEB-le).

##### Versioon 20.2.23015.0
- Lisatud event OnBeforeMatchBankPayments, millega saab asendada sidumise koodiploki 1255 "Match Bank Payments" enda versiooniga.
  
##### Versioon 20.2.23014.0
- Sobitamise parandused:
  - Käsitsi sobitamisel puhul ei sulgunud pangakontondmiku kanne.
  - Sobitamise muutmisel tavasidumiseks ei tekkinud konteerimisel kandeid.
  
##### Versioon 20.2.22358.0
- Maksežurnaali tegevusega "Edasta panka" saab makseid edastada nüüd ka SEB panka.
- SEB Baltic Gateway seadistuse lehele lisandus tegevus "Võta lõpetatud päeva tehingud", mis lubab pärida lõpetatud pangapäevade väljavõtte (kuni 20p tagasi). Funktsionaalsus on vajalik juhuks kui päevasisene laadimine jäi mingil põhjusel poolikuks või seisis. Sel juhul saab laadida puuduvad tehingud lõpetatud pangapäeva tervikväljavõttest.
- Reaalajapanga seadistuse lehele lisandus "Kliendi viitenumbri väli". Seadistus aitab tuvastada klienti, juhul kui seotavad arved puuduvad. Varasemalt toimus tuvastus juba registreerimisnumbri ja IBAN-i põhjal.

##### Versioon 20.2.22351.0
- Maksežurnaali lisandus tegevus "Edasta panka", millega saab maksed edastada otse LHV panka.

##### Versioon 20.2.22189.0
- Täiendatud on makse sidumise reeglitest lähtuvat sidumisloogikat:
  - Lisatud on sidumistäpsuse tunnus Keskmine, kuna maksete sidumisreeglites on kasutusel.
  - Tekst kontoks vastendamine toetab filtri kujul sisestusi (n. @pangateenus*).
  - Sidumine seob ümber ka juba seotud kanded juhul, kui need ei ole käsitsi seotud.
- Tekst kontoks vastendamise aknasse on lisatud vaikedimensioonide seadistamise võimalus.

##### Versioon 16.0.22179.0
- Lisaks senisele sisseehitatud sidumisloogikale on nüüd võimalik kasutada standardil baseeruvat (makse sidumise reeglitest lähtuvat) sidumisloogikat. Valiku saab teha lahenduse seadistuses.  Loogika vastab täpselt standardile, kuid kui standard arvega seost ei lea, siis lisaloogika leiab teise osapoole reg nr või IBAN-i järgi.

##### Versioon 16.0.22157.0
- Nüüd on ka pilveversioonis toetatud kõik kolm panka: Swedbank, SEB ja LHV.


