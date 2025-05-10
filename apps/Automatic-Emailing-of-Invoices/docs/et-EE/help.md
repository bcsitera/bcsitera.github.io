# Automaatne arvete saatmine meilile
Automaatne arvete saatmine meilile lahendus võimaldab järgmist: 
- Määra kliendile dokumendi saatmise profiil, saatmaks automaatselt arveid kliendi meilile peale konteerimist
- Saa ülevaade saatmise olekutest ning saatmise ajast konteeritud arvete loendis
- Halda ühe tööjärjekorra kande käivitusega saadetavate arvete mahtu (vältimaks meiliserveri sattumist musta spämmi nimekirja)
- Saada arve maksja või saaja või mõlema meiliaadressile
<br>


### Eeltingimused ning seadistus:
- Konteeritud müügiarvete ja müügi kreeditarvete edukaks meilitsi saatmiseks tuleb "Aruandevalik - Müük" lehel linnukesega märkida "Kasuta meilisõnumi manuses" (Kasutus vastavalt Arve või Kreeditarve).
  - Vajadusel kasutajat teavitatakse nimetatud määrangu tegemise vajadusest, kui kasutaja "Dokumendi saatmise profiil" lehel aktiveerib valiku "Saada müügiarve meiliga automaatselt".
- Tööjärjekorra tööd on vajalikud saatmaks arveid, mille meiliga saatmise olekuks on "Ootab saatmist"
  - Lahendus loob vajalikud tööjärjekorra tööd, kui kasutaja "Dokumendi saatmise profiil" lehel aktiveerib valiku "Saada müügiarve meiliga automaatselt" ning kasutajat teavitatakse tööjärjekorra seadistamise ning aktiveerimise vajadusest.
<br>
  
**Tööjärjekorra kande mainimist väärivad seaded:**
  
|Väli|Kirjeldus|
|---|---|
|Käivitatava objekti liik|Aruanne|
|Käivitatava objekti liik|70405500 Müügiarve ja 70405501 Kreeditarve puhul|
|Aruande päringuakna valikud|Määra sobiv "Max saadetavaid arveid ühe tööga"<br>Vaikimisi (määrangu väärtus 0) saadetakse 100 arvet ühe käivitumisega.<br>Määratav väärtus peaks vastama Teie meiliserveri limiitidele (küsi oma IT administraatorilt) ning üldteada spämmifiltrite lävenditele.<br>Sobiva määrangu tegemiseks tuleb arusaadavalt arvestada ka määrangut "Minutite arv käivitamiste vahel". |

<br>
  
### Kasutusstsenaariumid:
- **Saada arve kliendile meilitsi automaatselt peale konteerimist**
  - Loo dokumendi saatmise profiil ning tee valik "Saada müügiarve meiliga automaatselt". Vajadusel määra samas "Meiliaadressi allikas" (vaike ning soovituslikuks väärtuseks on Maksja meiliaadress).
  - Määra loodud dokumendi saatmise profiil kliendi kaardile.
  - Täida kliendikaardi väli "Meil" või kliendi "Dokumendi kujundused" lehel "Saada meilile".
    - Soovitatav on luua sobiva sisuga "Meilisõnumi sisu kujunduse kirjeldus" ning teha valik "Kasuta meilisõnumi sisus".
  - Peale arve konteerimist saab arve meiliga saatmise olekuks "Ootab saatmist".
  - Tööjärjekorra kanne "Konteeritud müügiarvete meiliga saatmine" käivitub ja saadab ära vastavas olekus olevad arved ning märgib meiliga saatmise olekuks "Saadetud" ja täidab välja "Meiliga saatmise aeg".
- **Saada arve käsitsi meiliga**
  - Saates arve meilitsi toimingu "Saada meilisõnumiga" abil märgitakse samuti meiliga saatmise olekuks "Saadetud" ja täidetakse väli "Meiliga saatmise aeg".
  - Saaja meiliaadress võetakse vastavalt "Dokumendi saatmise profiil" lehel määrangule "Meiliaadressi allikas" (kas maksja kliendilt või saaja kliendilt või lisatakse mõlemad).
- **Käsitsi "Meiliga saatmise olek" muutmine**
  - Vali konteeritud müügiarve/kreeditarve ning vali Protsess -> "Uuenda dokument".
  - Sektsioonis "Meiliga saatmine" vali uus "Meiliga saatmise olek" väärtus.
    - Märkus! Oleku muutmise korral tühjendatakse väli "Meiliga saatmise aeg".
- **Vaata saaja meiliaadressi või tõrke põhjust**
  - Vali konteeritud müügiarve/kreeditarve ning vali Toimingud -> Tegevuse logi.  
<br>
  
#### Märkused:
- Kui loodud meilisõnumid on edukalt meiliserverile (_vastavalt saatmiseks kasutatavale meilikontole_) üle antud, siis nende arvete saatmise olekusks määratakse "Saadetud".
  - Seega kui meiliserveril ei õnnestu toimetada meilisõnumit saajale, siis see info ei jõua tagasi Business Centrali.
    - Lahenduseks on kontrollida meilikonto sõnumeid, mida kasutati meiliserveri poolt meilisõnumite saatmiseks.
- Kui Business Centralil ei õnnestu meilisõnumeid üle anda meiliserverile, siis määratakse olekuks "Tõrge" ning vastavad meilisõnumid leiab "Nurjunud meilid väljundkaustast".
  - Kui tõrke põhjuseks on Saaja meiliaadressi puudumine, siis määratakse olekuks "Tõrge" ning meilisõnumit ei üritata meiliserverile üle anda.
    - Tõrke põhjuse väljaselgitamiseks vali Toimingud -> Tegevuse logi.  


  
  
---

Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:
<a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>
