# Finance Pro
Finance Pro lahendus laiendab standardset finantsfunktsionaalsust rakenduses Microsoft Dynamics 365 Business Central järgmiste funktsionaalsustega:
- [Seotud dimensioonid](#seotud-dimensioonid)
- [Automaatsed vaikedimensioonid](#automaatsed-vaikedimensioonid)
- [Perioodiseerimiskanded sisaldavad rohkem teavet](#perioodiseerimiskanded-sisaldavad-rohkem-teavet)
- [Partnerite kohesed saldod](#partnerite-kohesed-saldod)
- [PR kannete lisateave](#pr-kannete-lisateave)
- [Põhivarade kohene ülevaade](#põhivarade-kohene-ülevaade)
- [Erisoodustus](#erisoodustus-eesti-ettevõtetele)
- [Kinnitamise tingimus ostudokumentidel](#kinnitamise-tingimus-ostudokumentidel)

<br>

# Funktsioonid
## Seotud dimensioonid
See funktsionaalsus võimaldab siduda teiste dimensioonide väärtuseid soovitud globaaldimensiooni väärtusega (_nii et on võimalik luua nn dimensioonipuu_).  
Pärast seadistamist, kui kasutaja valib kannetele globaaldimensiooni väärtuse (_millel on seotud dimensioonid_), lisatakse automaatselt ka kõik vastavad seotud dimensioonid.

Seotud dimensioone on võimalik kasutada järgmistel kirjetel:
- Müügidokumendi päis ja read (sh müügitellimus, müügiarve ja müügi kreeditarve)
- Ostudokumendi päis ja read (sh ostutellimus, ostiarve ja ostu kreeditarve)
- Peažurnaal
- Põhivara PR žurnaal ja põhivara žurnaal
- Maksete žurnaal ja maksete vastavustamine žurnaal
- Kaupade žurnaal

### Seadistamine
Seotud dimensioonide kasutamiseks peate globaaldimensiooni väärtusega siduma soovitud teiste dimensioonide väärtused. Selleks:
1. Navigeerige **Dimensioonid** lehele
2. Olles **globaaldimensiooniks** oleva dimensiooni peal valige toiming **Seotud dimensioonid**
   1. _Või avage globaaldimensiooni dimensiooniväärtused ning valige seal toiming "Seotud dimensioonid"._
3. Lisage soovitud dimensioonide dimensiooniväärtused, mis antud globaaldimensiooni väärtusega peavad olema seotud.

**Seadistamise märkused:**
- Kasutaja ei saa valida **sama** dimensiooni seotud dimensiooniks.
- Kasutaja ei saa valida dimensiooni seotud dimensiooniks, kui see dimensioon on **juba määratud** selle praeguse dimensiooni seotud dimensiooniks.
- Kui kasutaja valib dimensiooni, mis on **juba määratud** alus-dimensiooni seotud dimensiooniks, siis teavitatakse kasutajat ja palutakse tal kinnitada, kas ta soovib jätkata.
- Kui muuta **Alus dimensiooniväärtuse nimi** väärtus lehel **Seotud dimensioonid**, siis nüüd muutuvad kõik sama dimensiooniväärtuse nimetused.
- Kui muuta **Dimensiooniväärtuse nimi** lehel **Dimensiooniväärtused**, siis muutuvad vastavad **Alus dimensiooniväärtuse nimi** väärtused
- Toiming **Seotud dimensioonid** on **aktiivne** ainult siis, kui ollakse dimensiooni peal, mis on kas Globaaldimensioon 1 või 2.
<br>

## Automaatsed Vaikedimensioonid
See funktsionaalsus võimaldab automaatselt lisada vaikedimensioone erinevatele tabelitele.
Näiteks seadistades vaikedimensioonid kliendi tabelile, lisatakse automaatselt kliendi number iga loodud kliendi vaikedimensiooniks, mis seejärel liigub kõikidele kliendiga seotud kannetele kaasa ja seeläbi hõlbustab aruandlust.

Automaatseid vaikedimensioone on võimalik seadistada põhiandmete tabelitele, mis toetavad vaikedimensioone ja millel on üks unikaalne identifikaator (nn liht primaarvõti) nt:
- Klient
- Hankija
- Töötaja
- Põhivara
- Ressurss
- Projekt
- Asukoht
- jne _(sh vaikedimensioonide toega arendatud tabelid)_  

### Seadistamine
Automaatsete vaikedimensioonide kasutamiseks tuleb:
1. Luua vastavale põhiandmete tabelile **Dimensioon** _(kuhu siis dimensiooniväärtuseid automaatselt saab lahendus lisama hakata)_
2. Avada leht **Automaatseid vaikedimensioonid** ning valida soovitav sobilik põhiandmete tabel
3. Valida millistelt tabeli välja(de)lt võetakse **Dimensiooniväärtuse nimetus** _(valides mitu välja, tuleb kasutada eraldajaks sümbolit "&")_
4. **Siduda** põhiandmete tabel punktis 1. loodud **Dimensiooniga**
5. Vajutada nuppu **Sünkroniseeri**, selleks et luua või uuendada valitud tabeli dimensiooniväärtused ja vaikedimensioonid _(sh dim.väärtuse nimetus)_  

**Seadistamise märkused:**
- Kasutaja saab vajadusel seadistada samale tabelile külge **mitu vaikedimensiooni**, kuid see ei ole soovitatav.
  - _nt sidudes Töötaja tabeliga nii ISIK, kui TÖÖTAJA dimensioonid ja kuigi tegu oleks lihtsalt dubleeriva vaikedimensiooniga, siis ei saa välistada selle vajalikkust teatud olukordades._
- **Dimensiooniväärtuse nimetuse** allikaks olevad tabeliväljad leitakse võimalusel automaatselt. Kasutaja saab seda muuta.

### Kasutamine
Peale seadistust sh nupu **Sünkroniseeri** vajutamist on kõikidele vastava tabeli kirjetele lisatud vastavad vaikedimensioonid.  
Kui nüüd süsteemis **luuakse uus kirje**, siis süsteem **loob automaatselt** määratud dimensioonile **uue vaikedimensiooni väärtuse** ning **lisab** vastava väärtuse automaatselt selle kirje **vaikedimensiooniks**.

**Kasutamise märkused:**
- Kui kasutaja **muudab** nüüd põhitabelis primaarvõtme välja (_nt Töötaja nr., Kauba nr., Kliendi nr. jne_), siis süsteem **automaatselt muudab** ka vastava dimensiooniväärtuse väärtust.
  - _Märkus! Kui põhiandmete tabel on seotud **Globaaldimensiooniga**, siis automaatne dimensiooniväärtuse muutmine ei ole hetkel tehniliselt võimalik. Kasutajale kuvatakse vastav teade._
- Kui kasutaja **muudab** põhitabelis **Dimensiooniväärtuse nimetuse** allikaks olevaid tabeliväljasid, siis automaatselt muudetakse ka dimensiooniväärtuse nimetus.  
<br>

## Perioodiseerimiskanded sisaldavad rohkem teavet
See funktsionaalsus lisab vastava alus-rea kirjelduse perioodiseerimisgraafiku ridade kirjeldusele (ja sealt lähevad need pearaamatu kannete kirjelduseks).
- Perioodiseerimiskannete kirjeldused saavad sisaldada rea kirjeldust seotud:
  - Müügirealt
  - Osturealt
  - Žurnaalirealt

  Märkus! Müügi-/ostudokumentides lisatakse rea kirjeldus perioodiseerimisgraafiku ridade kirjeldusele ainult juhul, kui rida on liigiga „PR konto", sest neid ei koondata PR kannete loomisel (_erinevalt näiteks kaup liigiga ridadest_).

### Seadistamine
Müügi-/ostudokumentide rea kirjelduste kasutamiseks perioodiseerimiskannetel navigeerige „Müügi ja müügivõlgade seadistus" lehele ja/või „Ostude ja ostuv. seadistus" lehele ning lubage:
- „Kopeeri rea kirjeldus PR kandele" (_see muudab järgneva välja nähtavaks_)
- „Lisa rea kirjeldus periodiseerimise kannetele"

Märkus! Peažurnaali kasutamisel ei ole seadistamist vaja (_st peažurnaali rea kirjeldus lisatakse alati perioodiseerimisgraafiku ridade kirjeldusele_).  
<br>

## Partnerite kohesed saldod
See funktsionaalsus võimaldab saada partneri saldo mis tahes kuupäeva seisuga kiiresti, kasutades ainult kuupäevafiltrit kliendi/hankija loendis.
Lisage loendis kuupäevafilter ja uus väli „Saldo kuupäevaks (KV)" näitab saldot lõppkuupäeval, mis sai kuupäevafiltris määratud.  
<br>

## PR kannete lisateave
Pearaamatu kannetele lisatakse järgmine teave:
- Allika nimi ja Korr. konto nimetus
  - Sõltuvalt liigist võib see olla:
    - Kliendi nimi
    - Hankija nimi
    - Töötaja nimi
    - Põhivara nimi
    - Pangakonto nimi  
<br>  

## Põhivarade kohene ülevaade
- Põhivara loendisse lisatud väljad:
  - Jääkväärtus
  - Soetusmaksumus
  - Soetuse kuupäev
  - Kulum %
  - Kulumiraamat
  - Kulumi alguse kuupäev
  - Kulumi lõpu kuupäev
  - Kulumiaastate arv
  - Järelejäänud kulumi aeg
  - Likvideerimiskuupäev
  - Järgmise hoolduse kuupäev
  - Garantii kuupäev
  - Seerianumber
  - Hankija nimi
  - Hooldushankija nimi

**Märkused:**
- Kui PV loendisse lisada **PV konteerimise kuupäevafilter**, siis arvutatakse **Jääkväärtus** ning **Soetusmaksumus** lähtuvalt sellest määrangust.
  - _Nii saab kiiresti nt eelmise aasta lõpu seisuga PV seisu otse loendist kätte._
- Kui loendis on tuhandeid põhivarasid, võib loendi avamine olla aeglane (_kuna paljud neist väljadest on arvutatud ehk flowfieldid_). Sellisel juhul palun peidke väljad, mida te ei vaja.  
<br>
  

## Erisoodustus (Eesti ettevõtetele)
### Seadistamine
See on aktiveeritud ainult siis, kui ettevõtte andmetes on "Riigi/regiooni tähis" väärtuseks "EE".  
Kui funktsionaalsus on aktiveeritud, siis PR kontode kaardil on võimalik märkida kontot kui "Erisoodustuse konto" (jaotises "Erisoodustus").  
Kui "Erisoodustuse konto" on märgitud, siis on võimalik määrata PR kontod, kuhu erisoodustusega seotud maksud arvutatakse, genereerides vastavasisulised lisaread ostudokumentidel.

### Kasutamine
Kui ostudokumendil kasutatud konto on "Erisoodustuse konto", siis konteeringu eelvaate või konteerimise tulemusena tekivad erisoodustusmaksudega seotud read.  
Märkus! Maksudega seotud nn. arveldusread on hallid ning neid ridu ei saa kustutada. Kui kustutada rida, millelon "Erisoodustuse konto", siis kustuvad ka maksudega seotud read.  
_Kui luuakse konteeritud ostuarve pealt parandav kreeditarve ja muudetakse kulukontodel summasid, siis konteeringu eelvaade arvutab ümber maksusummad._  
<br>
  
## Kinnitamise tingimus ostudokumentidel
### Kasutamine
Ostudokumentide päisesse on lisatud väli "Kinnitamise tingimus".  
Väljale saab valida väärtuse tabelist "Kinnitamise tingimused", kuhu saab ise luua tähised, mille alusel siis seadistada sobiv ostudokumendi kinnitamise töövoog.


---

Täpsema info saamiseks, palun võtke ühendust DIGMATIX-ga:  
<a href="https://www.digmatix.com/ee/kontaktid" target="_blank">https://www.digmatix.com/ee/kontaktid</a>
