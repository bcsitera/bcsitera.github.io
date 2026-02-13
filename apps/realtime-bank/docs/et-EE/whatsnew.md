---
---

##### Versioon 24.0.26022.0 (_saadaval al. 22.01.2026_)
- Täiendused funktsioonile _Vastenda tekst kontoks_ 
  - "Vastendamise tekst" väljal saab kasutada *
  - ridadele saab määrata dimensioone
  - ridu saab siduda Pangakontodega.
- Koondmakses tundlikke andmete kustutamise funktsionaalsuse kasutamiseks tuleb see sisse lülitada lehel _Reaalajapanga seadistus_.
- Täiendatud on saldode erinevuse hoiatuse loogika - hoiatus oli varem eksitav.
- Lehele _Pangakonto tehingud_ salvestub logi, kust saab jälgida, mis oli konteerimise hetkel "Vastenduse täpsus" tehingul.
- Veaparandus Citadele pangakonto väljavõtete Swedbank Gateway kaudu importimisel.


##### Versioon 24.0.25316.0 (_saadaval al. 12.11.2025_)
- Koondmakse (palgamakse) puhul, kui see laetakse pangast alla, siis töötlemisel kustutakse töötaja isikule viitavad andmed
- Juhul kui pangast saadud väljavõttel olev lõppsaldo ei klapi sellega, mis on BC-s arvutatud, teavitab BC sellest kasutajat _Maksete sobitamise žurnaalis_ - olukord võib tekkida, kui panga poolelt on teenus maas ning kõik tehingud ei ole sisse laetud
- Kui _Maksete sobitamise žurnaalis_ ei seota tehingut ühegi avatud kandega ning _Vastenduse täpsus_ jääb "Puudub", käivitub järeltegevus, mis määrab tehingu osapoolele märgitud registrikoodi alusel tehingule _Kliendi/Hankija_
- Kui tehing seotakse _Maksete sobitamise žurnaalis_ dokumendiga, millele varasemalt määrati _Dimensioonid_, siis lähevad ka tehingule külge samad _Dimensioonid_
- Swedbank väljavõtet pärides on võimalik pärida nüüd lisaks tänasele ning varasemale perioodile ka eilset päeva. Saab seadistada automaatikana tööle igal hommikul käivituma - nt Citadele, Urbo ja Šiauliai (Artea) pankade väljavõtteid ei genereerita eelneva päeva kohta automaatselt.
- Tehingul on nüüd kuvatud _Maksete sobitamise žurnaalis_ ka "Välise dokumendi nr." - varasemalt oli hankijatele tasutud ostuarvete siduvuse kontrollimine keerulisem, kuna tehingukirjelduses oli hankija arve nr märgitud, ent _Maksete sobitamise žurnaalis_ oli seotud kannete kohta info vaid BC siseste dokumendi numbritega kajastatud.
- Parandatud on kaks bug'i: 
  - Makseid edastades on võimalus oodata töötlemise esmast tulemust, et näha, kas makse salvestus panka ehk oli korrektne. Teatud juhtudel tagasiside kuvades tekkis teavitusaknas tõrge, mida enam ei teki.
  - Seadistust "Maksekorralduse registriga vastendamine" kasutades tekkis avatud kandeid sidudes tõrge, mis sai lahendatud. 

##### Versioon 24.0.25248.0 (_saadaval al. 05.09.2025_)
- Võimalik edastada pankadesse ka allkirjastatud kujul makseid, seda läbi Smart-ID.
- Võimalik sisse lülitada sidumine vastandlike kannetega sobitamise žurnaalis. Süsteem seob tehinguid ka vastandmärgiliste kannetega ehk nt nii arvete kui ka kreeditarvetega.
- Võimalik sisse lülitada sidumise loogika, mis sobitamise žurnaalis vastendab tehingud dokumentidega maksekorralduse registrisse salvestatud andmete põhjal.
- BC27 ühilduv (2025 wave 2)

##### Versioon 21.0.25143.0 (_saadaval al. 23.05.2025_)
- Tööjärjekorra automaatika seob ainult uued sissetulnud tehingud ega muuda olemasolevaid ridu maksete sobitamise žurnaalis.
- Lisandus võimalus maksete sobitamise žurnaalis siduda automaatselt vaid valitud read.
- _Maksete sobitamise žurnaalis_ on kasutajale kuvatud väljavõtte lõppsaldo kõige hiljutisemast XML väljavõtte failist

##### Versioon 21.0.25024.0 (_saadaval al. 24.01.2025_)
- Lisandus ebaõnnestunud maksete ülevaade rollikeskuses ning konkreetne tagaside tekkinud tõrgete kohta.
- Pangakonto kaardile lisandus tegevus "Sea pangaühenduse alguskuupäev". Läbi selle tuleb määrata, mis kuupäeval hakatakse lahendust kasutama ning mis on konto algsaldo selleks kuupäevaks.

##### Versioon 21.0.24352.0 (_saadaval al. 17.12.2024_)
- Lisandus Swedbank Gateway uue API tugi.
- Lisandus makselingi funktsionaalsus [LinkPay](https://support.every-pay.com/et/merchant-support/linkpay-makselink/)

##### Versioon 21.0.24242.0 (_saadaval al. 29.08.2024_)
- Maksete edastamisel panka maksefaili töötlemistulemuste kohene tagaside kasutajale (Swedbank, LHV, Coop).

##### Versioon 21.0.24105.0 (_saadaval al. 14.04.2024_)
- Coop Pank Gateway on nüüd kasutatav ka BC pilveklientidel.

##### Versioon 21.0.24085.0 (_saadaval al. 25.03.2024_)
- Lisandus Luminor Bank AS ühendus (Luminor WebService teenus).

##### Versioon 21.0.24028.0 (_saadaval al. 28.01.2024_)
- Lisandus Swedbank jooksva päeva kontoväljavõtte päring. Seda on hea kasutada juhul, kui tehinguid on palju ja kiirteavitus ei ole otstarbekas.

##### Versioon 21.0.24017.0 (_saadaval al. 17.01.2024_)
- Lisandus Coop Pank Gateway
- Imporditakse mitte kõigi vaid ainult BC-s seadistatud pangakontode sõnumid. Vajalik juhul, kui on pangakontosid, mille tehinguinfot BC-sse ei soovita.

##### Versioon 21.0.23153.1
RTB makste sobitamise žurnaalis saab nüüd üht pangatehingu rida jagada mitmeks kasutades nuppu "Vii erinevus üle kontole". Konteerimine kontrollib, et jagatud ridade summa vastaks pangatehingu summale.

##### Versioon 21.2.23145.0
Pangatehingute sidumiseks ja konteerimiseks saab nüüd kasutada "Maksete sobitamise žurnaali".
 
Sellisel juhul imporditakse pangatehingud **RTB** nimelisse maksete sobitamise žurnaali. Tegu on püsiva žurnaaliga, mis ei kustu konteerimisel ning millest on lubatud ka osaline konteerimine. Žurnaalirea konteerimisel märgitakse pangatehingute aknas tehing konteerituks.

Maksete sobitamise žurnaali kasutamise saab aktiveerida reaalajapanga seadistuse "Sidumise loogika" valikus.  

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


