#   Faktooringu lahendus | Kasutusjuhend
Faktooringu lahendus lisab Business Central-i faktooringusse müügiarvete loovutatamise ja faktooringust laekuvate summade töötlemise funktsionaalsust.

Lahenduses toetatud järgmised Eesti pangad:

Müügiarvete edastamine
* Swedbank 
* SEB
* Luminor
* LHV

Laekumiste töötlemine
* Swedbank 


### Põhilised funktsioonid:
*   Faktooringulepingu paindlik seadistamine.
*   Müügiarvete koondloetelu genereerimine vastavalt iga panga failiformaadile. 
*   Ülevaade loovutatud ja loovutamata müügiarvetest ja nende tasumistest. 
*   Regressiooniõigusega ja regressiooniõiguseta lepingud. 
*   Faktooringu märge müügiarvetele kliendi keeles. 
*   Loovutatud müügiarvete tasumise kohta väljastatava faili import ja selle alusel kannete automaatne genereerimine, sh 
    *   avansi ja reservi laekumise kajastamine; 
    *   komisjonitasude ja teenustasude automaatne kandmine seadistatud pearaamatu kontodele.
*   Kliendipõhised ja lepingupõhised limiidid. 
## Seadistamine
Lahenduse esmakordsel kasutamisel tuleb alustada faktooringulepingu loomisest süsteemis. Selleks peab avama lehe **Faktooringlepingud** ja looma uue lepingu vajutades nupule **+Uus**.  

Avaneval lepingu kaardil täita **muudetavad** väljad:  

|Väli| Selgitus|Muudetav / Informatiivne| 
|---|---|---|
|Nr.:**|Faktooringlepingu number|Muudetav|
|Kirjeldus|Faktooringlepingu kirjeldus|Muudetav|
|Faktooringu tekst arvele***|Müügiarvel kajastuv märge selle loovutamise kohta faktoorile|Muudetav|
|Lisa faktooringu tekst konteerimisel|Lisab märkuse müügiarve loovutamise kohta müügiarve ridadele|Muudetav|
|Limiit|Faktooringulepingu limiit|
|Klientide arv|Antud faktooringulepinguga seotud klientide arv|Informatiivne|
|Klientide liimit|Väljal kuvatakse kliendikaardil väljal **Faktooringulepingu limiit** olevate limiitide koondsumma|Informatiivne|
|Loovutamata arvete arv|Kliendile väljastatud, kuid faktoorile loovutamata müügiarvete arv|Informatiivne|
|Loovutamata arvete summa|Kliendile väljastatud, kuid faktoorile loovutamata müügiarvete summa|Informatiivne|
|Avatud kannete arv|Antud faktooringulepinguga seotud müügiarvete arv|Informatiivne|
|Faktooringulepingu tüüp|Valikus regressita ja regressiga lepingute tüübid|Muudetav|
|Faktooringu hankija nr:****|Faktooringu hankija, kellele kantakse regressiga lepingu alusel laekunud avanss lühiajalise kohustuse näol|Muudetav|
|Faktooringu kliendi nr:****|Faktooringu klient, kellele kantakse faktoorile loovutatud müügivõlgnevus|Muudetav|
|Komisjonitasude PR konto:|Konto, millele konteeritakse tasumisele kuuluv komisjonitasu|Muudetav| 
|Intresside PR konto:|Konto, millele konteeritakse tasumisele kuuluv intress faktoorilt reservi laekumisel|Muudetav|
|Pangakonto:|Faktooringulepinguga seotud pangakonto Business Central-s|Muudetav|
|Loovutamiste numbriseeria:|Müügiarvete loovutamise numbriseeria |Muudetav|  

** Kohustuslik väli  
** Lehel **Standardteksti tähised** on võimalik hallata tekste müügiarve loovutamise kohta kliendi keeles, sõltuvalt kliendikaardil märgitud keele tähisest.  
*** Faktooringu kliendi täitmine on vajalik regressita lepingu puhul. Faktooringu hankija on kohustuslik regressiga lepingu korral. Nii faktooringu klient kui faktooringu hankija võivad olla mõlemad täidetud, kuid süsteem kasutab ühte vastavalt lepingu tüübile.
##  Faktooringulepingute leht
Lehel asuvad tegevusnupud **Loovuta** ja **Loovutatud arve** ja tabeli väljad  
* **Loo loovutamine**  - käivitab müügiarvete pangale loovutamise protsessi. Etapi tulemusena luuakse loovutamise read.

* **Loovutamised**- faktoorile müügiarvete edastuse read.

Faktooringlepingute lehe väljadele selgitused:  

|Väli | Selgitus|
|--- |--- |
|Nr.:|Faktooringulepingu number|
|Kirjeldus|Faktooringulepingu kirjelduse väli|
|Klientide arv| Klientide arv, kellel on kliendi kaardil märgitud vastav faktooringulepingu number|
|Loovutamata arvete arv| Kliendile esitaud ja faktoorile edastamata müügiarvete arv |
|Loovutamata arvete summa| Kliendile esitatud ja faktoorile edastamata müügiarvete koondsumma |
|Avatud kannete arv | Faktoorile edastatud ja tasumata jäänud arvete arv |
|Limiit | Lepingu limiidi summa faktooringulepingu kaardilt|

## Loovutamised  
Lehel kuvatakse loovutamise read ehk panka edastatud müügiarvete komplektid.   

Lehel asuvad tegevusnupud **Kanna žurnaali** ja **Ekspordi faili** ja tabeli väljad.

* **Kanna žurnaali** - funktsiooni kasutamiseks tuleb valida loovutamise rida ja  vajutada nuppu **Kanna žurnaali**. Enne žurnaali ridade loomist küsitakse, millist žurnaali ja töölehte kasutada soovitakse. Seejärel luuakse žurnaaliread, mis sulgevad loovutamise komplektis olevate kliendi võlgnevused ja kannavad need faktooringu kliendile. Sealjuures tekib faktooringu kliendil esialgse müügiarvele analoogne kanne. St kannetel ühtivad dokumendi nr, kuupäev, maksetähtaeg jne.   

* **Ekspordi faili** - genereerub Excel-formaadis müügiarvete koondloetelu, mis vastab Swedbanki nõuetele.\
*NB! Faili panka edastamiseks tuleb see  manuaalselt edastada faktooriga kokkulepitud viisil.*

### Loovutamiste ridade väljade selgitused  

|Väli | Selgitus|  
|--- | --- |  
|Nr. | Faktooringu lepingu kirjeldus |  
|Loovutamise kuupäev |Kuupäev, mil loovutamise rida loodi |
|Arvete arv |Loovutatud müügiarvete arv |
|Arvete summa |Loovutatud müügiarvete summa |
|Avatud kannete arv |Tasumata arved on staatuses "Avatud"|  

## Faktooringu lahenduse kasutamine
*   **Faktooringu lepingu kaardi seadistamine**  
Lahenduse korrektseks töötamiseks peavad olema täidetud muudetavad väljad faktooringulepingu [kaardil](#Seadistamine).
*   **Faktooringulepingu ja limiidi lisamine kliendi kaardile.**\
    Faktooringulepingu kliendiga sidumiseks tuleb valida faktooringuleping kliendi kaardil asuval kiirkaardil **Maksed**. Lisaks on võimalik märkida kliendipõhist limiiti. Väljal kajastuvad limiidid kuvatakse summeritult faktooringu lepingu kaardil.\
*NB! Müügiarvet või müügitellimust koostades saab valida teist lepingut, mis on seotud antud konkreetse müütehinguga.*   
*   **Müügiarvete koondloetelu edastamine panka**\
Seda etapi on kirjeldatud **Ekspordi faili** nupu kirjeldamises. Tegevus on vajalik müügiarvete koondloetelu genereerimiseks.
*   **Müügiarveete sulgemine ja kandmine Faktooringu kliendile**\
Tegevus on vajalik ainult regressita lepingu puhul. Seda etapi on kirjeldatud **Kanna žurnaali** osas. Etapi eesmärgiks on loovutatud müügiarvete tasutuks märkimine ja müügivõla kandmine faktooringu kliendile. 

*   **Laekumiste süsteemi sisse lugemine**\
XML-formaadis faili süsteemi lugemiseks peab kasutaja valima lepingu tüübi, vajutades nuppu **Laekumise import** (Protsess -> Laekumise import) laekumisžurnaalis. Avanevas aknas valitakse faktooringlepingu number ja seejärel imporditakse XML-formaadis fail, mis sisaldab infot laekumise kohta. Kui faili sisselugemine ei toimu kronoloogilises järjekorras, siis tuleb esmalt sisse lugeda avansi sisaldavat fail ja seejärel XML fail reservi laekumisega.\

Konteerimata kanded tekivad automaatselt, summad saadakse XML failist. Allpool on ülevaade tekkivatest finantskannetest.

 **Avansi laekumine regressiooniõiguseta lepingu alusel**  

|Laekumisžurnaali rida|Deebet/Kreedit|Selgitus|
|---|---|---|
|Faktooringu kliendi võlg|Kreedit|Faktooringu klient faktooringulepingu kaardilt|
|Pangakonto|Deebet|Pangakonto faktooringulepingu kaardilt|
|Komisjonitasu|Deebet|Komisjonitasude konto faktooringulepingu kaardilt|
|Komisjonitasu KM|Deebet|Komisjonitasude konto faktooringulepingu kaardilt|  

**Reservi laekumine regressiooniõiguseta lepingu alusel**  

|Laekumisžurnaali rida | Deebet/Kreedit| Selgitus|
|---|---|---|
|Faktooringu kliendi võlg| Kreedit| Faktooringu klient faktooringulepingu kaardilt|
|Pangakonto|Deebet| Pangakonto faktooringulepingu kaardilt|
|Komisjonitasu|Deebet| Komisjonitasude konto faktooringulepingu kaardilt|  

**Avansi laekumine regressiooniõigusega lepingu alusel**  

|Laekumisžurnaali rida| Deebet/Kreedit| Selgitus|
|---|---|---|
|Faktooringu hankija kohustus| Kreedit| Faktooringu klient faktooringulepingu kaardilt|
|Pangakonto|Deebet| Pangakonto faktooringulepingu kaardilt|
|Komisjonitasu|Deebet| Komisjonitasude konto faktooringulepingu kaardilt|
|Komisjonitasu KM|Deebet|Komisjonitasude konto faktooringulepingu kaardilt|  

**Reservi laekumine regressiooniõigusega lepingu alusel**  

|Laekumisžurnaali rida | Deebet/Kreedit| Selgitus|
|---|---|---|
|Faktooringu hankija kohustus| Deebet| Faktooringu klient faktooringulepingu kaardilt|
|Pangakonto|Deebet| Pangakonto faktooringulepingu kaardilt|
|Intress|Deebet| Intressikulu konto faktooringulepingu kaardilt|
|Kliendi müügivõlg|Kreedit|Loovutatud müügiarve summa*|  

*NB! Peale reservi laekumist regressita lepingu alusel toimub müügiarve ja faktooringu hankija kohustuse sidumine, mille tulemusena võrduvad nii hankija kliendi kohustuse ja müügivõla jääksumma nulliga. 

---
Täpsema info saamiseks, palun võtke ühendust:  
[https://www.itera.ee](https://www.itera.ee)
