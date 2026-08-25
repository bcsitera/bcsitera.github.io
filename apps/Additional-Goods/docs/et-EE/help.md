# Kaasnevad kaubad
Kaasnevate kaupade lahendus võimaldab:
* seadistada põhikaupade müümisel nendega koos välja minevad abitooted
* seadistada põhikaupade müümisel pandi kaasamist müügitellimuse ridadele

## Seadistamine
Lahenduse kasutamiseks tuleb esmalt teha seadistused. Seadistused võivad olla üldised ja/või kliendipõhised, kus kliendipõhine seadistus on tugevam, kui üldine
seadistus.

### Kaasnevate kaupade seadistus

Kui ettevõttel on kliente kellele kaasnevate kaupade kaasamine müügitellimusele toimub samasuguselt siis on kõige mõistlikum alustuseks luua üldine seadistus. Selleks trüki otsingusse **Kaasnevate kaupade seadistus**. Üldine kiirkaardil tuleb eraldi seadistada Lisakauba ja Pandi lisandumise käitumised.

|Lisakauba arvutamine|Selgitus|
|---|---| 
| Lisa iga toote järel | Põhitootega kaasnevad kaubad lisatakse iga kord peale müüdavat toodet uute ridadena |
| Kokkuvõte lõpus | Põhitootega kaasnevad kaubad summeeritakse kokku müügitellimuse lõppu uute ridadena |

Pandiga kaupadele saab teha seadistused järgnevalt:   

|Pandi arvutamine|Selgitus|
|---|---| 
| Lisa iga toote järel | Pant lisatakse iga põhitoote järel uue reana |
| Kokkuvõte lõpus | Pant arvutatakse kokku müügitellimuse ridade lõppu iga pandi kood eraldi |


Üldise seadistusena saab valida, kas Kaasnevad kauba ja/või pant lisatakse automaatselt dokumendi vabastamisel ning kas arvesse võetakse Ostja-klient või Maksja-klient seadistusi.


Lõpetuseks tuleb sisse lülitada millistel dokumentidel funktsionaalsust kasutada tahetakse.<br>
**Arvuta müügitellimusel** - funktsionaalsus lülitatakse sisse müügitellimustel <br>
**Arvuta müügiarvel** - funktsionaalsus lülitatakse sisse müügiarvetel <br>
**Arvuta müügikreeditil** - funktsionaalsus lülitatakse sisse müügikreeditarvetel <br>


### Seadistused Kliendikaardil

Kui aga peaks juhtuma, et konkreetsele kliendile on vaja nendekohaseid seadistusi, mis erinevad üldisest seadistusest, siis saab seda teha kliendikaardi kiirkaardilt
**Lähetamine** allpool toodud väljadel:

|Lisakauba arvutamine|Selgitus|
|---|---| 
| <tühi> | Kaasnevate kaupade lisamine võetakse üldisest seadistusest |
| Ei arvuta | Kaasnevaid kaupasid sellele kliendile ei arvutata |
| Lisa iga toote järel | Kaasnevad kaubad lisatakse iga kord peale põhitoodet uute ridadena |
| Kokkuvõte lõpus | Kaasnevad kaubad summeeritakse kokku müügitellimuse lõppu uute ridadena |

Ja pandi arvutamisel:

|Pandi arvutamine|Selgitus|
|---|---| 
| <tühi> | Pandi lisamine võetakse üldisest seadistusest |
| Pant e-tellimusel | Pant imporditakse müügitellimusele läbi EDI faili, eraldi lisa pandi arvutamist ei toimu |
| Ei arvuta | Panti sellele kliendile ei arvutata |
| Lisa iga toote järel | Pant lisatakse iga põhitoote järel uue reana |
| Kokkuvõte lõpus | Pant arvutatakse kokku müügitellimuse ridade lõppu iga kood eraldi |


### Kaasnevad tooted ja kaubad

Kaasnevad tooted lehele saab luua grupid, mille sisse defineeritakse kaasnevad kaubad mis liiguvad alati kombinatsioonis koos. Siin on võimalik luua lugematul hulgal erinevaid kombinatsioone. Selleks valige lintribal nupp **Uus > andke grupile Tähis ja Kirjeldus**. Seejärel valige menüüst **Toimingud > Kaasnevad kaubad**. Avanenud lehel kirjeldage ära millised kaasnevad kaubad antud gruppi kuuluvad. Olulised väljad on siin:
**Kauba nr** - kaasneva kauba nr<br>
**Kogus (alus)** - kogus kauba alusmõõtühiku kohta <br>
**Liik** - kaasneva kauba liik <br>
**Pant** - näitab ära milline toode on pant, seadistus ise on kaubakaardil <br>


### Seadistused Kaubakaardil

Selleks, et kaasnevad kaubad põhitootega koos välja liiguvad tuleb need aktiveerida kaubakaardil. Selleks mine põhitoote kaubakaardile ning **Kaasnevad kaubad/pant** kiirkaardil vali **Kaasnevad kaubad** väljal eelnevalt seadistatud **Kaasnevad tooted** grupp.

Kui on tegu kaubakaardiga, mis on pant siis tuleb määrata kaubakaardi järgmised parameetrid: **Liik = Mitte-varud** ja **Pant = Jah**.


### Kliendi mõõtühikud

Kui peaks juhtuma, et mõnel kaubal on klientide jaoks põhikogustest erinevad veerand-, pool- või täisaluse kogused, siis saab neid seadistada **Kliendi mõõtühikud** lehel.

|Väli|Selgitus|
|---|---| 
| Kliendi nr | Kliendi nr kellele erisus kehtib |
| Kauba nr | Kauba nr millele erisus kehtib |
| Mõõtühiku tähis | Eristav mõõtühik |

NB! Erinevad mõõtühikud ja nende seosed peavad olema eelnevalt ära defineeritud antud kauba **Kauba mõõtühikute** lehel.


# Kasutamine

## Müügidokumentidel

Kui eelnevad seadistused on tehtud, siis automaatse kaasamise puhul võetakse kaasnevad kaubad dokumendi ridadele automaatselt. Manuaalselt saab kaasnevaid kaupasid  lisada müügitellimuse ridade menüüst **Halda > Lisa kaasnevad kaubad/pant**. Avanenud aknas saad teha järgmised valikud:

|Väli|Selgitus|
|---|---| 
| Lisa/Uuenda kaasnevad kaubad | Lisab või uuendab müügitellimuse ridadel kaasnevad kaubad |
| Lisa/Uuenda pandiread | Lisab või uuendab müügitellimuse ridadel kaupadega kaasa minevad pandid |
| Klient | Võimalik valida, kas kaasnevad kaubad leitakse Maksja-klient või Ostja-klient kliendikaardi seadsituste järgi |


---

Täpsema info saamiseks, palun võtke ühendust DIGMATIX-ga:  
<a href="https://www.digmatix.com/ee/kontaktid" target="_blank">https://www.digmatix.com/ee/kontaktid</a>
