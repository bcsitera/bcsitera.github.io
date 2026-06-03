# Lepingute haldus
Lepingute funktsionaalsus võimaldab BC-s järgmist:

- Müügi- ja ostulepingute haldus
- Müügipäise ja müügiridade summade jälgimist lepingu numbri alusel
- Ostupäise ja osturidade summade jälgimist lepingu numbri alusel
- Lepingute tugi projekti kaardil projekti müügiarvet loomiseks
- Partneri ja lepingute tugi projekti plaanimisridadel planeerimise eesmärgil 
- Vaikedimensioonide kasutamine lepingtel
- Lepingu arvelduse ridade loomine
- Perioodiliste müügiarvete loomine lepingu arvelduse ridade alusel

## Sisukord
  - [Seadistamine](#seadistamine)
    - [Lepingu kategooriad](#lepingu-kategooriad)
  - [Kasutamine](#kasutamine)
    - [Lepingu loomine](#lepingu-loomine)
      - [Lepingu kopeerimine](#lepingu-kopeerimine)  
    - [Lepingu kasutamine ostu- ja müügidokumentidel](#lepingu-kasutamine-ostu--ja-müügidokumentidel)
    - [Lepingu täituvuse jälgimine](#lepingu-täituvuse-jälgimine)
    - [Lepingute kasutamine projektides](#lepingute-kasutamine-projektides)
  - [Arveldamine](#arveldamine)
    - [Lepingu arvelduse ridade loomine](#lepingu-arvelduse-ridade-loomine)
    - [Müügiarvete loomine](#müügiarvete-loomine)
  - [Tagatiste haldus](#tagatiste-haldus)
    - [Seadistused](#seadistused)
    - [Kasutamine (Kinnipidamised)](#kasutamine-kinnipidamised)
    - [Kasutamine (Tagatised)](#kasutamine-tagatised)

## Seadistamine
Funktsionaalsuse kasutamiseks tuleb **Lepingute seadistuses** seadistada järgmised väljad:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManSetupEE.png" target="_blank"><img src="ContManSetupEE.png" alt="Lepingute Seadistus" width="800"/></a>

| Väli | Selgitus |
| --- | --- | 
| **_Lepingute numbrid_** | Antud väljal määratakse ära lepingute numbriseeria. Väärtus on valitav **Numbriseeriate** loendist.|
| **_Lepingu täitmise kontod_** | Tuleb ära määrata PR kontode filter mille pealt hakatakse lugema lepingu täitmist. Näiteks tulu ja kulukontod, kuhu tekib lepingu kandeid. Kindlast võiks välja jätta käibemaksu ja reskontroga seotud kontod. Võib sisestada konkreetsed kontod ja/või kontode vahemiku (näiteks vahemik 30000..90000).|
|**_Vaikimis lepingu tüüp_**|Määrab ära uute lpingute vaikimisi lepingu tüübi.
|**_Vaikimisi lepingu kategooria müügi jaoks_**|Määrab uute müügilepingute vaikimisi kategooria.
|**_Vaikimisi lepingu kategooria ostu jaoks_**|Määrab uute ostulepingute vaikimisi kategooria.
|**_Lepingu aruande ID_**|Määrab vaikimisi aruande ID lepingu väljatrüki jaoks, vaikimisi kantakse see edasi uutele Lepingu kategooriatele.

_Arveldamisega seotud seadistused_

|Väli|Selgitus|
|---|---| 
|**_Näita arvelduse infot_**|Määrab kas **_Arveldamise info_** vahekaart on müügilepingutel nähtav või mitte.
|**_Lepingu arvelduse ridade loomise kuupäevavalem_**|Määrab vaikimisi kuupäevavalemi **_Järgmise arvelduse kuupäeva_** jaoks kui kasutatakse funtksiooni **Lepingu arvelduse ridade loomine (CM)**.
|**_Müügiarvete loomise kuupäevavalem_**|Määrab vaikimisi kuupäevavalemi **_Konteerimiskuupäeva_** jaoks kui kasutatakse funtksiooni **Müügiarvete loomine (CM)**.

_Projektidega seotud seadistused_

|Väli|Selgitus|
|---|---| 
|**_Kanna lepingu nr. projekti arve päisesse_** |Võimaldab projekti kaardile valitud lepingu numbri kaasa võtta projekti arve loomisel ning lisada selle loodud projekti arve päissesse.


_Kontaktidega seotud algseadistus kui kontaktimoodul pole kasutuses_

|Väli|Selgitus|
|---|---| 
|**_Ava turunduse seadistus ja täida automaatselt kliendi ja hankija ärisuhte tähised, kontaktide numbriseeria_** |Avab turunduse seadistuse ja täidab automaatselt Kliendi ja Hnakija ärisuhete tähised kui need on tühjad. Lisaks loob ja täidab kontaktide numbriseeria kui see väli on tühi.
|**_Käivita masstöö "Loo klientidest kontaktid_** |Runs BC batchjob that creates Contacts from Customers.
|**_Käivita masstöö "Loo hankijatest kontaktid_** |Runs BC batchjob that creates Contacts from Vendors.

----

### Lepingu kategooriad

Lepingu kategooriad võimaldavad teil kirjeldada erienvat tüüpi kategooriaid, et lepinguid oleks lihtsam grupeerida.

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManContCategoriesEE.png" target="_blank"><img src="ContManContCategoriesEE.png" alt="Lepingu kategooriad" width="800"/></a>

|Väli|Selgitus|
|---|---| 
| **_Lepingu kategooria tähis_** | Võimaldab määrata lepingu kategooria tähise.|
| **_Lepingu kategooria kirjeldus_** | Võimaldab määrata lepingu kategooria kirjelduse.|
|**_Müük, Ost, Muu_**| Müük tuleks märkida juhul kui kategooriat peaks saama valida müügilepingutele (Tüüp **Müük**), Ost tuleks märkdia juhul kui kategooriat peaks saama valida ostulepingutele (Tüüp **Ost**), Muu tuleks märkida juhul kui kategooriat peaks saama valida ka muudele lepingutele (Tüüp **Muu**).
|**_Müügilepingute arv_** ja **_Ostulepingute arv_**| Kuvab müügi/ostulepingute arvu antud kategoorias.|
|**_Kanna Välise lepingu nr. müügipäisesse_**| Määrab vaikeväärtuse, selle kategooria uute lepingute jaoks, kandmaks Välise lepingu nr.-t edasi müügipäisesse.|
| **_Lepingu Aruande ID_** | Määrab vaikeväärtuse, selle kategooria uute lepingute jaoks, lepingu aruande ID jaoks mis on leingu väljatrüki aluseks.|
| **_Lepingu kujunduse kirjeldus_** | Määrab vaikeväärtuse, selle kategooria uute lepingute jaoks, lepingu kujunduse kirjelduse - valitakse kliendi poolt sellele aruande ID-le määratletud Kohandatud aruannete kujunduste hulgast.|

_Arveldamisega seotud seadistused_

|Väli|Selgitus|
|---|---| 
| **_Vaikimisi arveldusperioodi valik_** | Võimaldab antud kategooriasse kuuluvate lepingute jaoks määrata vaikimis arveldusperioodi valiku.|
| **_Vaikimisi arveldusperiood_** | Võimaldab antud kategooriasse kuuluvate lepingute jaoks määrata vaikimis arveldusperioodi.|
| **_Vaikimisi liik_** | Võimaldab antud kategooriasse kuuluvate lepingute lepingu ridade jaoks määrata vaikimisi liigi.|
| **_Vaikimisi nr._** | Võimaldab antud kategooriasse kuuluvate lepingute lepingu ridade jaoks määrata vaikimisi nr.|

---
 
## Kasutamine
### Lepingu loomine

Lepingute lahenduse puhul on võimalik hallata nii ostu-, müügi- kui ka muid lepinguid. Uue lepingu sisestamiseks tuleb avada **Lepingud** ning luua uus kirje kasutades nuppu **+Uus**.

Avaneval lepingu kaardil on võimalik täita ja jälgida järgenvaid välju:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManContractCardEE.png" target="_blank"><img src="ContManContractCardEE.png" alt="Lepingu kaart" width="800"/></a>

| Väli | Selgitus |
| --- | --- | 
| Lepingu nr.* | Täitub automaatselt vastavalt **Lepingute seadistuses** määratud numbriseeriale.|
| Lepingu tüüp* | Määratakse ära kas tegemist on ostu, müügi või mõne muu lepinguga. Valik määrab ühtlasi ära ka selle kas leping on valitav ostuarvele (**Ost**) või müügiarvele (**Müük**).|
| Lepingu kategooria** | Lepingu liigitamiseks ja kategooriapõhiste vaikeväärtuste toomiseks lepingu kaardile saab valida lepingu kategooria. Valik Lepingu kategooriate loendist.|
| Nimetus ja Kirjeldus** | Lepingu nimetuse ja lühikirjelduse sisestamiseks.|
| Partneri nr.* | Võimaldab määrata lepingu osapoole, valik toimub **Kontaktide loendist**. Kui kontakt on seotud ka mõne **Kliendi** või **Hankijaga** siis kuvatakse vastavad andmed väljadel _Kliendi nr ja nimi_ ning _Hankija nr ja nimi_. |
|Pealepingu nr. | Võimaldab lepingute grupeerimist ühise tunnuse (pealepingu) alla, väljalt avaneb valik **Lepingute loendisse**. Vaikimisi täidetakse lepingu enda numbriga.|
|Välise lepingu nr. | Võimaldab sisestada partneripoolse lepingu numbri.|
|Kanna Välise lepingu nr. müügipäisesse | Võimaldab valida kas soovitakse arvele lepingu numbri valimisel kaasa tuua ka Välise lepingu nr. mis lisatakse Välise dokumendi nr. väljale.|
| Algus- ja Lõpukuupäev** | Määratakse ära mis on lepingu kehtivusaeg. Väli on informatiivse tähendusega|
| Maksetingimused | Võimaldab määrata lepingus kokkulepitud maksetingimused. Väärtus kantakse üle müügi/ostu päisesse peale lepingu nr valimist dokumendi päises.|
|Müügiisiku/Sisseostja tähis| Võimaldab määrata müügiisiku/sisseostja kes on vastava lepingu eest vastutav. Väärtus kantakse üle müügi/ostu päisesse peale lepingu nr valimist dokumendi päises.
| Lukus | Võimaldab lepingu märkida lukus olevaks. Lepingut ei kuvata enam lepingu valiku juures ost- ja müügidokumentidel ega projektide valikutes.|

Vahekaardil **Finants** on võimalik täita ja jälgida järgenvaid välju:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManContractCardFinEE.png" target="_blank"><img src="ContManContractCardFinEE.png" alt="Lepingu kaart" width="800"/></a>

| Väli | Selgitus |
| --- | --- | 
| Summa** | Võimaldab määrata lepingu summa, mille alusel hakatakse kuvama ka lepingu jääki.|
| Summa KM-ga | Võimaldab sisestada lepingu summa koos käibemaksuga.|
| Täitmine (KV) | Kuvab lepinguga seotud summasid **Pearaamatu kannete alusel**. Kannetele on summa arvutamiseks rakendatud **Lepingute seadistuses** määratud filtrit.
| Täitmise % | Kuvab täitmise protsenti mida arvutatske vastavalt väljadele **_Summa_** ja **_Täitmine (KV)_**.
| Jääk (KV) | Kuvab lepingu jääki mis leitakse väljade **_Summa_** ja **_Täitmine (KV)_** alusel
| Alamlepingute arv | Kuvab alamlepingute arvu ehk lepinguid millele on pealepinguks valitud antud leping. Pealeping ise ei lähe arvesse.|
| Alamlepingute täitmine (KV) | Kuvab alamlepingute **_Täitmine (KV)_** summat. Pealeping täitmist siia ei liideta.|

Vahekaardil **Seosed** on võimalik täita ja jälgida järgenvaid välju:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManContractCardRelationsEE.png" target="_blank"><img src="ContManContractCardRelationsEE.png" alt="Lepingu kaart" width="800"/></a>

Vahekaardil **Seosed** kuvatavad väljad (Kliendi nr. ja nimi ning Hankija nr. ja nimi) täituvad automaatselt peale partneri valimist. Väljad täituvad ainult juhul kui partneriks valitud **Kontakt** on seotud kliendi ja/või hankijaga. Kui seos luuakse hiljem, siis tuleb lepingu päises kasutada tegevust **Uuenda kliendi/hankija seos**, mis uuendab Kontaktiga (Partneri nr.) seotud Kliendi ja Hankija seosed ka lepingul.

| Väli | Selgitus |
| --- | --- | 
| Lepingu Aruande ID | Määrab millist aruande ID-d kasutatakse antud lepingu väljatrükki aluseks.|
| Lepingu kujunduse kirjeldus | Määrab millist lepingu kujunduse kirjeldust kasutatakse antud lepingu väljatrükiks - valitakse kliendi poolt sellele aruande ID-le määratletud Kohandatud aruannete kujunduste hulgast.|

*_Väljad mis tuleb kndlasti täita_
**_Väljad mis on soovituslikud täita_

#### Lepingu kopeerimine

Ava **Lepingute loend** või **Lepingu kaart** ja kasutage nuppu **Kopeeri leping**.
Avaneb järgnev vaade:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManCopyContractEE.png" target="_blank"><img src="ContManCopyContractEE.png" alt="Lepingu kopeerimine" width="500"/></a>

Täitke ära **Uue lepingu nr.**, kui soovite lepingule numbri käsitsi määrata, või märkige linnukes **Kasuta numbriseeriat**, kui soovite, et uue lepingu number võetakse numbriseeriast. Täiendavalt saate valida ka seda kas kopeeritakse ka lepingu read - **Kopeeri lepingu read* 
* Vaikimisi täidetakse **Lepingu nr.** ja **Lepingu nimi** selle lepingu infoga mida kopeeritakse. 

Vajutage **OK**.

Avaneb **Lepingu kaart** uue lepingu andmetega, millelt kopeerimisel eemaldati dimensioonide ja summade info.
 
### Lepingu kasutamine ostu- ja müügidokumentidel
Müügi- ja ostudokumentidel on võimalus valida päisesse väljale **_Lepingu number_** sobiv leping **Lepingute loendist**. Kui dokumendi päisesse on lepingu number valitud siis lisatakse see automaatselt ka igale dokumendi reale. Dokumendi ridadel on võimalik lepingu numbrit muuta. 


#### _Tähtis_
---
_Dokumentidele valitavate lepingute valik on piiratud järgnevate tunnuste alusel:_
- _Lepingu liigiga ehk müügidokumentidele saab valida lepinguid liigiga **Müük** ja ostudokumentidele liigiga **Ost**._
- _Ostja või müüja numbriga ehk müügidokumentidel **Ostja-kliendi number** ning ostudokumentidel **Müüja-Hankija number**._
- _Valikust jäävad välja ka **Lukus** lepingud._

_Kui tingimustele vastavat lepingut siiski valikus ei kuvata võib asi olla selles, et lepingul on uuendamata Kliendi/Hankija seos. Uuendamiseks tuleb **Lepingu kaardil** vajutada nuppu **Uuenda kliendi/hankija seos**, mis uuendab **Kontaktiga** (Partneri nr.) seotud **Kliendi** ja **Hankija** väärtused lepingul._

---

Dokumendi konteerimisel kantakse lepingu number edasi konteeritud dokumentidele, pearaamatusse, kliendi- ja hankijareskontrosse ning projektiandmiku kannetesse. 


#### _Tähtis_

--- 
_Arvestama peab sellega, et kliendi- ja hankijareskontrosse liigub lepingu number mis on valitud dokumendi päisesse. Kui ridadel on kasutatud ka teisi lepingu numbreid siis need liiguvad edasi vastavatele tulu ja kulukannetele._

---

### Lepingu täituvuse jälgimine

Lepingu täituvust ning jääki on võimalik jälgida **Lepingute loendist** või **Lepingu kaardilt** järgnevatelt väljadelt:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManCompletionTrackingEE.png" target="_blank"><img src="ContManCompletionTrackingEE.png" alt="Lepingu täituvuse jälgimine" width="1000"/></a>

- Täitmine (KV) - kuvab lepinguga seotud summasid **Pearaamatu kannete alusel**. Kannetele on summa arvutamiseks rakendatud **Lepingute seadistuses** määratud filtrit.
- Jääk (KV) - kuvab lepingu jääki mis leitakse väljade **_Summa_** ja **_Täitmine (KV)_** alusel

Lisaks on nii loendist kui kaardilt võimalik avada ka seotud **Pearaamatu kanded** kasutades selleks nuppu **Täitmise kanded**.
 

### Lepingute kasutamine projektides
Lepinguid on võimalik kasutada ka projektimoodulis nii **Projekti kaardil** kui ka **Projekti plaanimisridadel**.


**Projekti kaardile** on võimalik sisestada projektiga seotud müügileping. 

Lepingu valimisel rakenduvad järgnevad filtrid:
- Lepingu liik ehk projektile saab valida lepinguid liigiga **_Müük_**.
- Klient ehk projektile saab valida lepinguid mis on seotud projektil märgitud **_Maksja-kliendi nr._**-ga.
- Valikust jäävad välja ka **_Lukus_** lepingud.

Projekti müügiarve loomisel kantakse leping üle ka loodavale **Müügiarvele**.

**Projekti plaanimisridadele** on võimalik sisestada **_Partneri nr._** ning temaga seotud ostu- või müügileping. See võimaldab jälgida seda kas näiteks allhanke puhul on partneriga juba leping sõlmitud või mitte ning hiljem jälgida ka lepingu täituvust.

Lepingu valimisel rakenduvad järgnevad filtrid:
- Partner ehk projekti plaanimisreale saab valida lepinguid mis on seotud projekti plaanimisreale märgitud **_Partneri nr._**-ga.
- Valikust jäävad välja ka **_Lukus_** lepingud.

---

## Arveldamine

Funktsionaalsus võimaldab sisestada arvldamise infot lepingu kaardile ning seejärel lepingu ridadele. Peale seda saate luua lepingu arvelduse ridu, et kontrollida õigsust ning kõrvalekaldeid, ning seejärel saate nende ridade alusel luua müügidokumente.

#### _Tähtis_

--- 
_**Arvelduse info** vahekaart on nähtav ainult juhul kui **Lepingute seadistuses** on see lubatud ja lepingu tüüp on **Müük**! **Lepingu read** vahekaart muutub nähtavaks peale seda kui arveldus info kuupäevaväljad on täidetud ning on klikatud **Lisa lepingu read**!_

---

**Arvelduse info** vahekaardil on võimalik täita järgenvad väljad:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManBillingInfoEE.png" target="_blank"><img src="ContManBillingInfoEE.png" alt="Arvelduse info" width="1000"/></a>

|Väli|Selgitus|
|---|---| 
| **_Maksja kliendi nr._** | Võimaldab määrata maksja kliendi numbri. Kui väli pole täidetud siis kasutatakse müügidokumendi loomsiel kliendi vaikeväärtust.|
| **_Saaja-aadressi tähis_** | Võimaldab määrata saaja-aadressi. Kui väli pole täidetud siis kasutatakse müügidokumendi loomsiel kliendi vaikeväärtust.|
| **_Arveldusperioodi valik_** | Võimaldab määrata vaikimisi arvldusperioodi valiku lepingu ridade jaoks.|
| **_Arveldusperiood_** | Võimaldab määrata vaikimisi arvldusperioodi lepingu ridade jaoks. Vaikimisi on väli peidetud.|
| **_Arvelduse alguskuupäev_** | Võimaldab määrata vaikimisi arvelduse alguskuupeäva lepingu ridade jaoks.|
| **_Esimese perioodi lõppkuupäev_** | Võimaldab määrata vaikimisi esimese perioodi lõppkuupäeva lepingu ridade jaoks. See väli võmaldab mängida esimese perioodi pikkusega, et sättida tuelvikuperioodid täiskuude peale.|
| **_Arvelduse lõppkuupäev_** | Võimaldab määrata vaikimisi arvelduse lõppkuupäeva lepingu ridade jaoks|
| **_Lisa lepingu read_** | Aktiveerib vahekaardi **Lepingu read** ja sisestab esimese lepingu rea vaikeväärtustega **Lepingu kategoorialt** ja **Arvelduse info** vahekaardilt.|

**Lepingu read** vahekaardil on võimalik täita järgenvad väljad:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManContLinesEE.png" target="_blank"><img src="ContManContLinesEE.png" alt="Lepingu read" width="800"/></a>

|Väli|Selgitus|
|---|---| 
| **_Liik_** | Võimldab määrata liiki. Vaikeväärtus võetakse **Lepingu kategooria** alusel.|
| **_Nr._** | Võimaldab määrata nr. mida hakatakse arveldama. Esimese rea vaikeväärtus võetakse **Lepingu kategooria** alusel|
| **_Kirjeldus_** | Võimaldab määrata rea kirjelduse.|
| **_Kogus_** | Võimaldab määrata arveldatavat kogust.|
| **_Mõõtühik_** | Võimaldab määrata arveldatavat mõõtühikut. Vaikimsi on väli peidetud.|
| **_Ühiku hind KM-ta_** | Võimaldab määrata arveldatavat ühiku hinda.|
| **_Rea summa KM-ta_** | Kuvab arvutatud rea summat. Väli ei ole muudetav.|
| **_Kehtiv_** | Võimaldab määrata kas rida on kehtiv või mitte. Vaikeväärtus on Kehtiv.|
| **_Lisa perioodi tekst_** | Võimaldab määrata kas uus perioodi infoga tekstirida lisatakse peale antud rida kui luuakse lepingu arvelduse ridu.|
| **_Arveldusperioodi valik_** | Võimaldab määrata arveldusperioodi valiku antud reale. Vaikeväärtus võetakse **Arvelduse info** vahekaardilt.|
| **_Arvelduse alguskuupäev_** | Võimaldab määrata arvelduse alguskuupäeva antud reale. Vaikeväärtus võetakse **Arvelduse info** vahekaardilt.|
| **_Esimese perioodi lõppkuupäev_** | Võimaldab määrata arveldusperioodi valiku antud reale. Vaikeväärtus võetakse **Arvelduse info** vahekaardilt.|
| **_Järgmsie arvelduse kuupäev_** | Kuvab antud rea **Järgmsie arvelduse kuupäeva** (järgmsie perioodi alguskuupäev), väli täidetakse automaatselt peale tegevuse [Lepingu arvelduse ridade loomine](#lepingu-arvelduse-ridade-loomine) käivitamist. Väli ei ole muudetav.|
| **_Arvelduse lõppkuupäev_** | Võimaldab määrata arvelduse lõppkuupäeva antud reale. Vaikeväärtus võetakse **Arvelduse info** vahekaardilt.|

Lepingu ridade põhine müügidokumentide loomine koosneb kahest sammust: Lepingu arvelduse ridade loomine ja Müügiarvete loomine.

### Lepingu arvelduse ridade loomine
Esimene samma on luua **Lepingu arvelduse read**.

Ava **Lepingute loend** või **Lepingu kaart** ja kasutage nuppu **Lepingu arvelduse ridade loomine (CM)**.
Avaneb järgnev vaade:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManCreateContInvLinesEE.png" target="_blank"><img src="ContManCreateContInvLinesEE.png" alt="Lepingu arvelduse ridade loomine" width="500"/></a>

Täitke ära **Järgmise arvelduse kuupäev**, seda kuupeäva rakendatakse lõpu filtrina vaheimikule mida rakendatakse **Kehtivatele** lepingu ridadele. Seda rakendatakse väljale **Järgmine arvelduse kuupäev** või **Arvelduse alguskuupeäv** (kui eelnev väli on veel tühi) ning seejärel luuakse **Lepingu arvelduse read** iga **Lepingu rea** kohta mis vastav filtri kriteeriumitele. 
* Vaikimisi täidetakse see Täna + kuupäevavalem  **Lepingute seadistuse** väljalt **_Lepingu arvelduse ridade loomise kuupäevavalem_**.
* Täiendavalt on võimalik valida filtreid ka **Lepingu** ja **Lepingu ridade** tabelitest.
* Kui nuppu klõpsatakse **Lepingu kaardilt** siis vaikimisi rakendatakse **_Lepingu nr._** filtrit. 

Vajutage **OK**.

Kasutage **Lepingu kaardilt** nuppu  **Lepingu arvelduse read**, et avada loend. Kontrollige kas arvleudse read loodi ning kas need paistavad korrektsed, et nende alusel müügidokumendid luua. _Loend ei ole redigeeritav_.

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManContInvLinesEE.png" target="_blank"><img src="ContManContInvLinesEE.png" alt="Lepingu arvelduse read" width="800"/></a>

Mõned väljad selgitust ei vaja, kuid mõnele on selgitused lisatud allpool.

|Väli|Selgitus|
|---|---| 
| **_Konteerimiskuupäev_** | Vaikimisi **Perioodi alguskuupäev**.|
| **_Perioodi alguskuupäev_** ja **_Perioodi lõppkuupäev_**  | Kuvavad tegelikku arvelduse perioodi.|
| **_Olek_** | Kuvab antud rea olekut. **Uus** - Esimene olek kõikidel loodud ridadel. Samuti taastatakse selline oleks ridadel mis müügidokumendilt eemaldatakse või kui kogu müügodokument eemaldatakse. **Tellimus** - Kui ridade alusel on loodud **Müügitellimus**. **Arve** - Kui ridade alsuel on loodud **Müügiarve**. **Konteeritud** - seotud müügidokument on konteeritud. **Tühistatud** - rida on tühistatud kasutades nuppu **Tühista**. Tühistada saab ainult ridu mille olek on **Uus**.|
| **_Dokumendi nr._** | Kuvab seotud dokeumdni numbrit (tellimus, arve, konteeritud arve).|

---

### Müügiarvete loomine
Teien samm on **Müügitellimuste** või **Müügiarvete** loomine.

Avage **Lepingute loend** või **Lepingu kaart** ja kasutage nuppu **Müügiarvete loomine (CM)**.
Avaneb järgnev vaade:

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManCreateSalesInvEE.png" target="_blank"><img src="ContManCreateSalesInvEE.png" alt="Lepingu müügiarvete loomine" width="500"/></a>

Täitke ära **Konteerimiskuupäev**, seda kuupeäva rakendatakse lõpu filtrina vaheimikule mida rakendatakse **Lepingu arvelduse ridadele** mille olek on **Uus**. Seda rakendatakse väljale **Konteerimiskuupäev** ning seejärel luuakse **Müügairved/Tellimsued** kõikide lepingu arvelduse ridadega mis vastavad filtrite kriteeriumitele ning need grupeeritakse vastavalt **Arvete loomise alusele**.
* By default it is filled with Today + date formula from **_Create Sales Invoices Date Formula_** in **Contract Setup**.
* Additonal filters can be applied from **Contracts** or **Contract Invoice Lines**.
* If clicked from **Contract Card** then **_Contrat No_** filter will be entered automatically. 

|Väli|Selgitus|
|---|---| 
| **_Asenda konteerimiskuupäev_** | Võimaldab loodavatel müügidokumentidel asendada **Konteerimiskuupäeva**. Vaikimisi võetakse müügidokumendi konteerimiskuupäev esimeselt sellele dokumendile lisati lepingu arvelduse realt. |
| **_Arvete loomise alus_** | Võimaldab määrata mille alusel ridadest dokumendid luuakse. **Leping** - üks arve/tellimus iga lepingu kohta. Ainult ühe lepinguga seotud read lisatakse ühele arvele/tellimsuele. **Klient** - üks arve/tellimuse kliendi kohta. Read erinevatest sama kliendi lepingutest koondatakse kokku ühele arvele/tellimusele. **Pealeping** - üks arve/tellimus pealepingu kohta. Read erienvatest lepingutest millel on sama pealepingu number koondatakse kokku ühele arvele/tellimusele.|
| **_Loo kui_** | Võimaldab määrata millist tüüpi müügidokumendid luuakse: **Arved** (vaikimisi) või **Tellimsued**.|

Vajutage **OK**.

# Tagatiste haldus

Tagatiste haldust saab hallata kahte moodi, seadistatav lepingute seadistuses millist lahendust ja kus (Ost, Müük) kasutatakse.

### Tagatised

Tagatiste puhul toimub loogika läbi arve ridade ja tagatisandmiku kannete (sarnaselt Kliendipõhisele/hankijapõhisele ettemaksule).

Kasutatav nii ostuarvete kui ostutellimustega ning müügiarvete ja müügitellimustega.

Näiteks ostu puhul: Kulureale lisatakse lisaks miinusmärgiga rida kus kasutatakse tagatiste kontot.

Tagatise kontod peavad olema seadistatud selliselt, et need jääksid INF aruandest välja.

### Kinnipidamised

Kinnipidamiste puhul toimub tagatise arvutus ja loogika reskontros, reskontro summa tükeldatakse konteerimisel.

Kasutatav ainult ostuarvete ja müügiarvetega.

Eelduseks on see, et nii klientide kui hankijate puhul on lubatud kasutada mitut hankija/kliendi konteeringurühma.

# Seadistused

## Lepingute seadistus (Tagatiste haldus vahekaart)

Lepingute seadistuses on võimalik määrata mis tüüpi lahendust ja kus kasutatakse ning lisaks täiendavad seadistused.

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManSetupCol.png" target="_blank"><img src="ContManSetupCol.png" alt="Tagatiste seaded" width="800"/></a>

### Müügi tagatiste lahenduse liik

| Väärtus | Selgitus |
|----------|----------|
| tühi | tagatisi ei kasutata. |
| Tagatis | kasutatakse tagatisandmiku kannete lahendust. |
| Kinnipidamine | kasutatakse reskontro lahendust. |

### Ostu tagatiste lahenduse liik

| Väärtus | Selgitus |
|----------|----------|
| tühi | tagatisi ei kasutata. |
| Tagatis | kasutatakse tagatisandmiku kannete lahendust. |
| Kinnipidamine | kasutatakse reskontro lahendust. |

### Tähtaja seadistused

| Väli | Selgitus |
|-------|----------|
| Lühiajaliste tagatiste tähtaja kuupäevavalem | võimaldab märkida lühiajalise tagatise eeldatava tähtaja arvutamise valemit, kasutatakse juhul kui kannetel pole kasutusel Lepingut. |
| Pikaajaliste tagatise tähtaja kuupäevavalem | võimaldab märkida pikaajalise tagatise eeldatava tähtaja arvutamise valemit, kasutatakse juhul kui kannetel pole kasutusel Lepingut. |

### Kinnipidamiste puhul

| Väli | Selgitus |
|-------|----------|
| Lühiajaliste tagatiste Hankija konteeringurühm, Pikaajaliste tagatiste Hankija konteeringurühm | võimaldab määrata hankija konteeringurühmad, mida kastutatakse tagatiste konteerimiseks. |
| Lühiajaliste tagatiste Kliendi konteeringurühm, Pikaajaliste tagatiste Kliendi konteeringurühm | võimaldab määrata kliendi konteeringurühmad, mida kastutatakse tagatiste konteerimiseks. |
| Pikaajlise tagatise zurnaali nimi, Pikaajalise tagatise žurnaali tööleht | võimaldab määrata millisele peažurnaali töölehele luuakse Pikaajalise tagatise kanded kui kasutatakse kliendi/hankijaanmdiku kandel funktsiooni Arvuta pikaajaline tagatis. |

## Hankija/Kliendi konteeringurühm

### Loo uued konteeringurühmad (Kinnipidamiste lahenduse puhul)

Loo uued konteeringurühmad Lühiajaliste ja Pikaajaliste tagatiste jaoks - tagatise konto märgi Võlgnevuse konto veergu.

### Seadista olemasolevad konteeringurühmad (Tagatiste lahenduse puhul)

Lisa olemasolevatele konteeringurühmadele veergudesse Lühiajaliste tagatise konto ja Pikaajalise tagatise konto vastavad PR kontod.

## Lepingu kaart (Tagatised vahekaart)

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManCardCol.png" target="_blank"><img src="ContManCardCol.png" alt="Tagatised lepingul" width="800"/></a>

| Väli | Selgitus |
|-------|----------|
| Arvuta tagatis KM-ga summast | võimaldab määrata kas tagatise summad arvutatakse KM-ta või KM-ga summast. |
| Lühiajalise tagatise % | võimaldab määrata lühiajalise tagatise protsendi, mida kasutatakse tagatise arvutamisel. |
| Lühiajalise tagatise tähtaeg | võimaldab määrata konkreetse kuupäeva millal lühiajalised tagatised eeldatavalt vabastatakse. |
| Lühiajalise tagatise tähtaja arvutamine | võimaldab määrata kuupäevavalemi mille alusel arvutatakse lühiajalise tagatise tähtaeg, aluseks võetakse dokumendi konteerimiskuupäev. |
| Pikaajalise tagatise % | võimaldab määrata pikaajalise tagatise protsendi, mida kasutatakse tagatise arvutamisel. |
| Pikaajalise tagatise tähtaeg | võimaldab määrata konkreetse kuupäeva millal pikaajalised tagatised eeldatavalt vabastatakse. |
| Pikaajalise tagatise tähtaja arvutamine | võimaldab määrata kuupäevavalemi mille alusel arvutatakse pikaajalise tagatise tähtaeg, aluseks võetakse dokumendi konteerimiskuupäev. |

# Kasutamine (Kinnipidamised)

## Ost

### Ostuarve

#### Ostuarve väljad

| Väli | Selgitus |
|-------|----------|
| Lühiajalise tagatise summa | võimaldab määrata lühiajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Lühiajaline. Lisaks märgitakse Peatatud veergu täheühend STR. |
| Lühiajalise tagatise tähtaeg | võimaldab määrata lühiajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks. |
| Pikaajalise tagatise summa | võimaldab määrata pikaajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Pikaajaline. Lisaks märgitakse Peatatud veergu täheühend LTR. |
| Pikaajalise tagatise tähtaeg | võimaldab määrata pikaajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks. |

#### Ostuarvel nupud

<a href="https://apps.itera.ee/apps/contract-management/docs/et-EE/ContManColActions.png" target="_blank"><img src="ContManColActions.png" alt="Tagatise ostuarvel" width="400"/></a>

##### Arvuta lühiajaline tagatis

Arvutab lühiajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle ostuarve päisesse väljale Lühiajalise tagatise summa ning täidab ära ka Lühiajalise tagatise tähtaja.

NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

##### Arvuta pikaajaline tagatis

Arvutab pikaajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle ostuarve päisesse väljale Pikaajalise tagatise summa ning täidab ära ka Pikaajalise tagatise tähtaja.

NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

### Hankijaandmiku kanded

#### Hankijaandmiku kannete veerud

##### Tagatise liik

- Lühiajaline - märgitakse automaatselt Lühiajalise tagatise kandele.
- Pikaajaline - märgitakse automaatselt Pikaajalise tagatise kandele.

#### Hankijaandmiku kannete nupud

##### Arvuta pikaajaline tagatis

Töötab ainult juhul kui valitud kanne või kanded on Tagatise liigiga - Lühiajaline. Kuvatakse aken kus on võimalik märkida Dokumendi numbrit, konteerimiskuupäeva, Pikaajalise tagatise summat ja Pikaajalise tagatise tähtaega. Kasutatakse juhul kui arve konteerimisel ei lisatud Pikaajalise tagatise infot.

Klikates nupule Loo kanded - avatakse vastavalt seadistustele peažurnaali tööleht kuhu on lisatud Lühiajalise tagatise sulgemiskanne ja pikaajalise tagatise kanne. Konteerimisel seotakse Lühiajalise tagatise reskontrokanne vastava Lühiajalise tagatise reskontrokandega ning lisatakse uus Pikaajalise tagatise reskontrokanne.

## Müük

### Müügiarve

#### Müügiarve väljad

| Väli | Selgitus |
|-------|----------|
| Lühiajalise tagatise summa | võimaldab määrata lühiajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Lühiajaline. Lisaks märgitakse Peatatud veergu täheühend STR. |
| Lühiajalise tagatise tähtaeg | võimaldab määrata lühiajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks. |
| Pikaajalise tagatise summa | võimaldab määrata pikaajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Pikaajaline. Lisaks märgitakse Peatatud veergu täheühend LTR. |
| Pikaajalise tagatise tähtaeg | võimaldab määrata pikaajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks. |

#### Müügiarve nupud

##### Arvuta lühiajaline tagatis

Arvutab lühiajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle müügiarve päisesse väljale Lühiajalise tagatise summa ning täidab ära ka Lühiajalise tagatise tähtaja.

NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

##### Arvuta pikaajaline tagatis

Arvutab pikaajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle müügiarve päisesse väljale Pikaajalise tagatise summa ning täidab ära ka Pikaajalise tagatise tähtaja.

NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

### Kliendiandmiku kanded

#### Hankijaandmiku kannete veerud

##### Tagatise liik

- Lühiajaline - märgitakse automaatselt Lühiajalise tagatise kandele.
- Pikaajaline - märgitakse automaatselt Pikaajalise tagatise kandele.

#### Kliendiandmiku kannete nupud

##### Arvuta pikaajaline tagatis

Töötab ainult juhul kui valitud kanne või kanded on Tagatise liigiga - Lühiajaline. Kuvatakse aken kus on võimalik märkida Dokumendi numbrit, konteerimiskuupäeva, Pikaajalise tagatise summat ja Pikaajalise tagatise tähtaega. Kasutatakse juhul kui arve konteerimisel ei lisatud Pikaajalise tagatise infot.

Klikates nupule Loo kanded - avatakse vastavalt seadistustele peažurnaali tööleht kuhu on lisatud Lühiajalise tagatise sulgemiskanne ja Pikaajalise tagatise kanne. Konteerimisel seotakse lühiajalise tagatise reskontrokanne vastava Lühiajalise tagatise reskontrokandega ning lisatakse uus Pikaajalise tagatise reskontrokanne.

# Kasutamine (Tagatised)

## Ost

### Tagatise kinnipidamine

Ostuarvel/ostutelimusel on järgmised nupud:

#### Arvuta lühiajaline tagatis

Arvutab lühiajalise tagatise vastavalt ostuarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue ostureana.

NB! Nupp on nähtav ainult juhul, kui ostuarve päisesse on valitud Lepingu nr.

#### Arvuta pikaajaline tagatis

Arvutab pikaajalise tagatise vastavalt ostuarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue ostureana.

NB! Nupp on nähtav ainult juhul, kui ostuarve päisesse on valitud Lepingu nr.

Ostuarve konteerimisel luuakse avatud hankija tagatisandmiku kanded. Kande eeldatav tähtaeg arvutatakse tagatise tähtaja arvutamise valemi alusel.

### Tagatise väljamaksmine

Tagatiste väljamaksmist saab käivitada ostuarvel nupuga Too hankijapõhine tagatis.

#### Eeldused

- ostuarvele peab olema määratud vastav Lepingu nr.

Avanenud aknas kuvatakse kõik avatud tagatisandmiku kanded, mis vastavad järgmistele tingimustele:

- sama hankija,
- sama valuuta,
- sama tagatise liik,
- Avatud = Jah.

Kasutaja valib sobiva tagatisandmiku kande.

Tulemusena lisatakse ostuarvele uus osturida tagatisandmiku kande jääksummaga.

Ostuarve konteerimisel:

- tekib uus hankija tagatisandmiku kanne,
- algse kande jääksumma väheneb.

Kui tagatis makstakse lõplikult välja, muutub kinnipidamise kande välja Avatud väärtus väärtuseks Ei.

## Müük

### Tagatise kinnipidamine

Müügiarvel/Müügitellimusel on järgmised nupud:

#### Arvuta lühiajaline tagatis

Arvutab lühiajalise tagatise vastavalt müügiarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue müügireana.

NB! Nupp on nähtav ainult juhul, kui müügiarve päisesse on valitud Lepingu nr.

#### Arvuta pikaajaline tagatis

Arvutab pikaajalise tagatise vastavalt müügiarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue müügireana.

NB! Nupp on nähtav ainult juhul, kui müügiarve päisesse on valitud Lepingu nr.

Müügiarve konteerimisel luuakse avatud kliendi tagatisandmiku kanded. Kande eeldatav tähtaeg arvutatakse tagatise tähtaja arvutamise valemi alusel.

### Tagatise vabastamine

Tagatise vabastamist saab käivitada müügiarvel nupuga Too kliendipõhine tagatis.

#### Eeldused

- müügiarvele peab olema määratud vastav Lepingu nr.

Avanenud aknas kuvatakse kõik avatud tagatisandmiku kanded, mis vastavad järgmistele tingimustele:

- sama klient,
- sama valuuta,
- sama tagatise liik,
- Avatud = Jah.

Kasutaja valib sobiva tagatisandmiku kande.

Tulemusena lisatakse müügiarvele uus müügirida tagatisandmiku kande jääksummaga.

Müügiarve konteerimisel:

- tekib uus kliendi tagatisandmiku kanne,
- algse kande jääksumma väheneb.

Kui tagatis vabastatakse lõplikult, muutub kinnipidamise kande välja Avatud väärtus väärtuseks Ei.

## Lepingu jääkide uuendamine

Süsteem uuendab automaatselt järgmisi lepingu välju:

- Lühiajaliste tagatiste summa
- Pikaajaliste tagatiste summa

Need väärtused näitavad väljamaksmata tagatise summat.

---

Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:  
https://www.itera.ee
