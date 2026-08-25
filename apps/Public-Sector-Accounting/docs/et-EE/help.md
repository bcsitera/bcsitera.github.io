# Avaliku sektori finantsarvestuse lahendus
Avaliku sektori finantsarvestuse lahendus Business Centralis võimaldab järgmist:
- Riigi kontode haldust
- Riigi tehingupartnerite haldust
- Saldoandmike haldust
- Saldoandmiku esitamist XML failiga Saldoandmike infosüsteemis
- Makseandmike haldust
- Makseandmiku esitamist XML failiga Saldoandmike infosüsteemis
<br><br>

## Seadistamine
### Dimensioonid
Lahendus kasutab saldoandmike loomiseks pearaamatu kannete dimensioone, seega on vaja luua dimensioonid järgmise info tarbeks:
 - Tehingupartner
 - Tegevusala
 - Allikas
 - Rahavoog
 <br><br>

### Riigi raamatupidamise seadistus
Sektsioonis **Dimensioonid** määratleme lahenduse toimimiseks vajalikud dimensioonid:

|Väli|Selgitus|
|---|---| 
| Tehingupartneri dimensiooni tähis | Dimensiooni tähis, mis vastab dimensioonile **Tehingupartner**. |
| Tegevusala dimensiooni tähis| Dimensiooni tähis, mis vastab dimensioonile **Tegevusala**. |
| Allika dimensiooni tähis | Dimensiooni tähis, mis vastab dimensioonile **Allikas**. |
| Rahavoo dimensiooni tähis | Dimensiooni tähis, mis vastab dimensioonile **Rahavoog**. |
| Tingimuslik rahavoo dimensiooni väärtus | Määrab rahavoogude dimensiooni väärtuse (tavaliselt **01**), mis käivitab saldoandmiku koostamisel tingimusliku rahavoogude loogika lähtuvalt Riigi kontoplaani määratlustest. |

Lisainfot võimalike dimensiooniväärtuste osas saab <a href="https://saldo.rtk.ee/saldo-app/" target="_blank">Saldoandmike infosüsteemist</a>.
<br><br>

Sektsioonis **Üldine** määratletakse:

|Väli|Selgitus|
|---|---| 
| Tehingupartnerite numbrid | Määrab **tehingupartnerite** numbriseeria. Väärtuse saab valida **Numbriseeriate loendist**. |
| Riigi saldoandmiku numbrid | Määrab **saldoandmike** numbriseeria. Väärtuse saab valida **Numbriseeriate loendist**. |
| Riigi makseandmiku numbrid | Määrab **makseandmike** numbriseeria. Väärtuse saab valida **Numbriseeriate loendist**. <br>*(Nähtaval ainult juhul, kui ettevõtte tehingupartneri kood on määramata või kui tehingupartneri kood algab numbritega 0 kuni 6 ja neljas number on null kuni 3)* |
| Ettevõtte tehingupartneri kood | Määrab **ettevõtte enda tehingupartneri koodi**i, mida kasutatakse saldoandmiku XML failis.<br> *(Kui sobivat väärtust ei ole valikus, siis tuleb vastav dimensiooniväärtus tehingupartneri dimensiooniväärtustesse lisada.)* |
| Ettevõtte tegevusala kood | Määrab **ettevõtte enda tegevusala kood**i. Siin määratud väärtus lisatakse automaatselt vastavale PR kontole, kus Tegevusala dimensioon on nõutud, vaikedimensiooni väärtuseks. <br>*(Kui sobivat väärtust ei ole valikus, siis tuleb vastav dimensiooniväärtus tehingupartneri dimensiooniväärtustesse lisada.)* |
| Eemalda makseandmikust TP | Määrab **makseandmikust välistatud tehingupartnerid**. Näiteks maksuameti ja eraisikute välistamiseks tuleks sisestada 014001 ning 800699 püstkriipsuga eraldatuna. <br>*(Nähtaval ainult juhul, kui ettevõtte tehingupartneri kood on määramata või kui tehingupartneri kood algab numbritega 0 kuni 6 ja neljas number on null kuni 3)* |
| Kajasta makseandmikus maksed summast | Määrab **summa, millest alates kajastub makse makseandmikus**. Tavaliselt on väärtuseks 100 <br>*(Nähtaval ainult juhul, kui ettevõtte tehingupartneri kood on määramata või kui tehingupartneri kood algab numbritega 0 kuni 6 ja neljas number on null kuni 3)* |

<br><br>

### Riigi kontod
Esmase installeerimise käigus täidab lahendus riigi kontode tabeli vaikeväärtustega. *(Kontod seisuga juuli 2022.)*<br>
Riigi kontode tabel koosneb kontodest, millel on number, nimetus ning vastavate dimensioonide kohustuslikkuse määratlused vaadeldava konto osas.<br>
**Tehingupartner ja/või Tegevusala dimensioon võivad olla tingimuslikult kohustuslik**ud - st vastav dimensioon on ainult siis kohustuslik lisada, kui tehingu rahavoo dimensioon on ettemääratud väärtusega (tavaliselt 01).

Seadista järgnevad väljad parema kasutajakogemuse ning täpsema saldoandmiku saamiseks:

|Väli|Selgitus|
|---|---| 
| Konstantne TP dimensioon | Määrab konstantse tehingupartneri dimensiooni väärtuse riigi kontole. **Riigi kontole määratud väärtus prevalveerib pearaamatu kandel oleva väärtuse üle**. Kasutatakse tavaliselt maksu kontodel, sest maksude tehingupartner saab olla vaid üks (Maksu- ja Tolliamet). <br> ***Märkus!** Kui siin on tehingupartneri kood määratud, siis puudub vajadus vastaval PR kontol Tähis kohustuslik vaikedimensiooni määratlemiseks.*|
| Kasuta konstantset TP dimensiooni pangakonto kaardilt | Määrab **kas lahendus kasutab saldoandmiku loomisel pangakonto kaardil määratud konstantset riigi tehingupartneri dimensiooniväärtust** pearaamatu kandel oleva tehingupartneri dimensiooniväärtuse asemel. Kasutatakse tavaliselt Arvelduskontod pankades kontol. <br> ***Märkus!** Kasutades pangakonto kaardil Konstantne riigi TP dimensioon väärtust ei tohiks pangakontol tehingupartneri vaikedimensiooni kasutada, sest võivad tekkida dimensioonikonfliktid laekumiste/maksete sobitamisel.*|
| Riigi kontoklassi määrang | Määrab **riigi kontole vasava kontoklassi** Näiteks laovarude soetamisel saab siin märkida kontoklassiks 55. Kui kontoklass on määramata, siis võetakse kontoklassiks riigi konto kaks esimest numbrit. <br> *Välja kasutatakse ainult makseandmiku koostamisel.*|
| Lukus | Lukus olevat riigi kontot ei saa valida PR kontole, riigi saldoandmikule ja riigi makseandmikule.<br> _Ühtlasi ei kuvata lukus olevat kontot riigi kontode valikus (filtriga peidus)._|

Kasutaja saab taastada riigi kontode tabeli vaikeväärtused nupust "**Lähtesta riigi kontod**". <br>
**Hoiatus!** Lähtestamine kaotab kõik Kasutaja tehtud muudatused riigi kontodes.
<br><br>

### Kontoplaan
Igale PR kontole tuleb määrata vastav riigi konto number. *Väli on saadaval nii kontoplaanis, kui konto kaardil.*

Peale riigi konto lisamist kontrollib lahendus kohustuslike dimensioonide nõuet antud riigi konto osas. **Kui dimensioon on kohustuslik või tingimuslik, siis lahendus lisab riigi konto poolt nõutud vaikedimensioonide kohustuslikkuse** käesolevale PR kontole *(Väärtuse konteerimine määratluseks Tähis kohustuslik)*.<br>
***Märkus!** Kui Kasutaja hindab, et vastavale PR kontole ei tehta kunagi tehinguid rahavoo tingimusliku väärtusega (01), siis Kasutaja peaks eemaldama vastava PR konto vaikedimensioonidest "Tähis kohustuslik" nõude tehingupartneri ja/või tegevusala dimensiooni osas.*
<br><br>

### Riigi tehingupartnerid
Esmase seadistuse käigus peaks Kasutja looma tehingupartnerite loetelu.
Kasutaja saab **laadida alla tehingupartnerite XML fail**i Saldoandmike infosüsteemist nupuga "Lae alla partnerite XML".<br>
Kasutaja saab importida/uuendada tehingupartnerid XML failist nupuga "Impordi partnerid XML failist".<br>
***Märkus!** Kuna riigi poolt loodud tehingupartnerite XML failis puudub unikaalsuse tunnus, siis uuendamine õnnestub vaid kirjetega, milledel on olnud muutumatu kombinatsioon Kood + Nimetus + Kehtiv alates. Vastasel juhul luuakse uus kirje.*
<br><br>

### Kliendid/Hankijad
Iga **Kliendi/Hankija kaardile tuleb määrata vastav riigi tehingupartner**. *Seda saab teha sektisoonis Riigi raamatupidamise info.*<br>
Kui tehingupartneri id valitakse, siis lahendus lisab vastava tehingupartneri koodi tehingupartneri dimensiooni üheks väärtuseks ning ühtlasi lisatakse tehingupartneri kood Kliendi/Hankija vaikedimensiooniks (Väärtuse konteerimine määratluseks Sama tähis).
<br><br>

### Pangakontod
Kasutaja peaks igale pangakontole **määratlema Konstantne riigi TP dimensioon väärtuse**. Seda saab teha pangakonto kaardil. *Nii toimides **puudub vajadus pangakontole vaikedimensiooni määramiseks**.*  <br>
Määratlust kasutatakse riigi saldoandmiku koostamisel, kui riigi kontoplaanis on märgitud väli "Kasuta konstantset pangakonto TP dimensiooni pangakonto kaardilt".<br>  

**Märkus!Kui väli Konstantne riigi TP dimensioon on kasutusel, siis tuleks vastavalt PR kontolt (leitav pangakonto konteeringurühma kaudu) eemaldada Tähis kohustuslik vaikedimensiooni nõue Tehingupartneri dimensiooni osas.**
<br>

**Kajasta makseandmikus** määrab kas pangakontolt toimunud maksed võetakse arvesse riigi makseandmiku koostamisel.

<br><br>

## Kasutamine
### Pearaamatu kanded
Kontoplaanis määratud kohustuslikud vaikedimensioonid tuleb lisada igale PR kandele. Lisaks salvestatakse kandele riigi konto number. Vastava info abil loob lahendus riigile esitatava saldoandmiku.  
_Riigi konto numbrit on võimalik pearaamatu kannetes muuta, kasutades "Redigeeri loendit" toimingut._  
<br><br>

### Riigi saldoandmikud
Uue saldoandmiku loomiseks tuleb Kasutajal määratleda aruandeperioodi aasta ning kuu (lõpu kuu). Saldoandmik arvutatakse kumuleeruvalt alates aruandeperioodi kalendriaasta algusest kuni lõpu kuu viimase päevani.<br>
Saldoandmiku **ridade loomiseks tuleb Kasutajal vajutada nuppu "Arvuta read"**. *Read luuakse iga riigikonto tarbeks kombinatsioonis tehingupartner, tegevusala, allikas ning rahavoog.*

Kontrollimaks, millistest pearaamatu kannetest on saldoandmiku rida loodud tuleb kasutada nuppu "**Näita aluskandeid**" *(nupu leiab Ridadest, Halda nupu alt)*. Kõikide dimensioonidega kannete vaatamiseks tuleb avanenud pearaamatu kannetest vajutada Kanne -> PR Dimensiooni ülevaade ning seejärel juba Kuva maatriks.
<br><br>
Kui mõnel saldoandmiku real on ebatäpsed väärtused tänud ekslikult määratud dimensioonile, siis kannete korrigeerimiseks saab kasutada <a href="http://apps.itera.ee/apps/dimension-correction-tool/docs/et-EE/app.html" target="_blank">Dimensiooniparandaja</a> lahendust.
Peale paranduste tegemist kannetes, tuleb Kasutajal uuesti vajutada nuppu "Arvuta read", mis seejärel arvutab uuesti saldoandmiku read.
<br><br>
Vabastatud saldoandmiku korral saab nupust "**Loo XML fail**" luua ning salvestada saldoandmiku XML kujul, mille saab importida saldoandmike infosüsteemi.
<br><br>

### Riigi makseandmikud
Uue makseandmiku loomiseks tuleb Kasutajal määratleda aruandeperioodi aasta ning kuu (lõpu kuu).
<br>
Makseandmiku **ridade loomiseks tuleb Kasutajal vajutada nuppu "Arvuta read"**.

Ridade loomisel vaatab süsteem kõikide Kajasta makseandmikus märkega pangakontode pangakontoandmiku kandeid ning leiab maksed, mis on suurem/võrdsed riigi seadistuses määratud algsummast ning mille tehingupartner pole riigi seadistustes märgitud eemaldamiseks.  
**Märkus!** Riigisaladuse all olevaid makseid saab makseandmikust eemaldada tehes vastava määratluse vastavatel pearaamatu kannetetel nupu **Eemalda kanne makseandmikust** abil.
<br><br>
Süsteem leiab iga maksega seotud ostuarve(d) ning käib läbi kõik read, leidmaks tehtud makse kuluklassid.  
Kui tehti osaline makse, siis arvutatakse summad kontoklasside lõikes vastavalt tasutud summa proportsioonile.  
Kui makse pole seotud arvega vaid otse PR kontoga, siis Pearaamatu kandelt vaadatakse tehingupartner ning riigi konto nr., mille alusel leitakse kontoklass.
<br><br>
Vabastatud makseandmiku korral saab nupust "**Loo XML fail**" luua ning salvestada makseandmiku XML kujul, mille saab importida saldoandmike infosüsteemi.

---

Täpsema info saamiseks, palun võtke ühendust DIGMATIX-ga:   <a href="https://www.digmatix.com/ee/kontaktid" target="_blank">https://www.digmatix.com/ee/kontaktid</a>
