# Objektihaldus ja arveldus
Objektihalduse lahendus Business Centralis võimaldab:
- Hallata objekte (objekti infot)
- Haldada objektiga seotud teenuseid ja kaupu
- Teostada arveldamist

## Seaded
Lahenduse kasutamiseks tuleb avada **Objektihalduse seadistus** ja täita järgmised väljad:

|Väli|Selgitus|
|---|---|
| Objekti numbrid | Määrab objektide loomisel kasutatava numbriseeria. |
| Objekti lepingu numbrid | Määrab lepingute loomisel kasutatava numbriseeria. |
| Objekti finantsaruanne | Määrab objekti kaardilt avaneva finantsaruande (nt eelarve vs tegelik), kui objekti kaardil kasutatakse toimingut "Finantsaruanne". |
| Objekti eelarve finantsaruanne | Määrab millist finantsaruannet kasutatakse objekti eelarve lehel, Prindi eelarve toimingu puhul. |
| Töötaja allikas | Määrab töötajate lähte-/allikatabeli (vajalik juhul kui ) |
| Hinnaarvutuse viis | Määrab objektide ja müügiarvete hinnaarvutuse viisi. Selleks et objektilahendus kuvaks ning kasutaks objektil määratud hindu korrektselt, tuleks valida **Objekti hind**. |
| Ei loo marginaali hinda kui kliendi hind olemas | Määrab, et ostuarvelt ei looda hinnakirja rida kauba või objekti marginaali alusel, kui kliendi hind on juba hinnakirjas olemas. |
| Luba seotud isikute filter ostu- ja müügidokumentidel | Määrab, kas seotud isikute filter (kasutajale on nähtav ainult temaga seotud objektide info) kehtib lisaks objektide registrile ka järgmistel lehtedel: Ostuarved ja ostu kreeditarved (sh konteeritud), Osturead (sh konteeritud), Müügiarved ja müügi kreeditarved (sh konteeritud). |
| Delegeeri kinnituskanne automaatselt | Määrab, kas reapõhised kinnituskanded delegeeritakse automaatselt asendajale (kui viimane leitakse). |

<br>
Dimensioonide sektsioonis:

|Väli|Selgitus|
|---|---|
| Objekti dimensiooni tähis | Määrab mõõtmekoodi, mida kasutatakse objektide jaoks. Süsteem kasutab seda ka vaikimisi dimensiooni automaatseks loomiseks objektile. |
| Eelarve teise dimensiooni tähis | Määrab teise dimensiooni väärtuse, mida kasutatakse eelarve avamisel objekti kaardilt. (Eeldatakse, et Global dimension 1 on objektidimensioon). |
| Dimensioonide uuendamise filter | Määrab dimensioonid, mida uuendatakse kirjetele (G/L, FA, Budget, Analysis View kirjed), kui need muutuvad objektil. Mitme dimensiooni lisamiseks kasuta vertikaalset toru (nt OBJECT|MANAGER). |
| Kauba vaikedimensioon | Määrab vaikimisi dimensiooni artiklite jaoks, nii et süsteem saab automaatselt luua vastava uue dimensiooniväärtuse, kui luuakse uus artikkel. |
| Kaubakategooria vaikedimensioon | Määrab vaikimisi dimensiooni artiklikategooriate jaoks, nii et süsteem saab automaatselt luua vastava dimensiooniväärtuse, kui luuakse uus artiklikategooria. Kui artiklikategooria valitakse artiklile, lisatakse artiklile vastav vaikimisi dimensiooniväärtus. |
| Kaubakategooria nõutud | Määrab, et süsteem kontrollib kas loodud kaupadel on kaubakategooria kui dimensioon lisatud või mitte. |

Samuti on võimalik määrata kuni 8 objekti atribuuti, mis kuvatakse lehel **Objektid ja atribuudid** veergudena.

Toimingut **Isiku rolli vaikedimensioonid** kasutatakse, et määrata dimensioonid isikurollidele nii, et need lisatakse objektile automaatselt vastava rolliga isku pealt.

## Kasutamine

### Objektid

Objekti tabel on lahenduse keskne osa. Seal saab sisestada erinevat infot järgmistes sektsioonides:

- Objekti info (nt nimi, tüüp, seotud põhivarad jne)
  - Kui vajalik, määrake **Osturidade kinnituse mall**, et objektiga seotud osturidade kinnitamine, toimiks vastavalt mallile.
- Objekti märkused (tekst, tabel või graafika objekti kirjeldamiseks)
- Aadressiinfo (sh täpse asukoha jaoks saab sisestada geolokatsiooni koordinaadid)
- Seotud isikud (enda töötajad, kliendi kontaktid, kolmanda osapoole kontaktid jm)
- Arveldamisega seotud info (sh objekti globaaldimensioonid)
- Objekti müügiridad (korduvad kuu-põhised arveldatavad teenused antud objektil)
  - Hinda saab sisestada välja **Kehtiv hind** kaudu
  - Erinevatel ridadel võivad olla erinevad lepingud
  - Teenused võivad olla hooajalised (_nt muru niitmine või lume lükkamine_)
- Kaubad/Töövahendid — kaubad mis kokku lepitud objektil kasutamiseks ning mida kasutatakse koos arveldatavate teenustega
  - Määrake, kas kaubad on teenuse hinna sees või lisatakse müügiarvele kui edasimüügi kaup.

### Objekti lepingud

Objekti leping on vajalik finantsiliste kokkulepete (_nt maksetähtaeg_) rakendamiseks arve loomisel.
_Ei ole kohustuslik, kuid väga soovitatav._
Kasutaja saab valida, kas kõik ühe lepingu objektid kogutakse ühele arvele (**Lepingu objektid ühele arvele**) või luua eraldi arve iga objekti kohta.

### Arveldamine

Korduva kuu-arvelduse loomiseks kasutage toimingut **Loo objektide arved**.
Lahendus loob arved kõigi nende objektide jaoks, millel on kehtivad objekti müügiread antud arveldusperioodi jaoks.


---

Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga: <a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>
