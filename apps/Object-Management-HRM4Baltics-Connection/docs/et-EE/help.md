# HRM4Baltics - Objektide ja Arvelduse Lahenduse Kasutajuhend

## Sissejuhatus

See lahendus võimaldab **HRM4Baltics** ja **Object Management and Billing Solution** integreerimist. Lahendus võimaldab valida töötajaid objektidele ja kasutada objekte mitmel HRM4Baltics tabelil, samuti saada vaikedimensioone objektidest.

---

## Seadistamine - Esmased sammud

Enne lahenduse kasutamist peate teostama järgmised seadistustegevused. Järgige samme järjekorras:

### 1. Objektide seadistus

1. Avage **Objektide seadistus**
2. Määrake järgmised andmed:

#### Finantskontod:
- **Töötajatabeli eelarve summa kontod** - Pearaamaatu kontod, kuhu kantakse eelarvestatud summad
- **Töötajatabeli eelarve tundide kontod** - Pearaamaatu kontod, kuhu kantakse eelarvestatud tunnid

#### Konteerimisandmed:
- **Tööajatabeli summade konteerimise žurnaalimall** - Vali standardne päevitamisžurnaalimall (nt GL JOURNAL)
- **Tööajatabeli summade konteerimise žurnaali tööleht** - Žurnaali töölehet nimi (nt DEFAULT)
- **Tööajatabeli summade konteerimise dok nr. prefix** - Dokumendi numbri eesliide (nt WORKSCH)

### 2. Objekti andmete konfigureerimine

1. Avage iga **Objekti kaart**, kus kasutate lahendust
2. Määrake:
   - **Objekti nimi** - Objekti kirjeldus
   - **Objekti kinnitaja** - Töötaja, kes kinnitab objektiga seotud taotlused
   - **Vaikedimensioon** - Dimensioon, mida kasutatakse objektiga seotud kannetes

3. Veenduge, et objekti kinnitajale on määratud **Kasutaja ID** (Kasutaja seadistus tabelis)

### 3. Tööajatabeli grupi eelarve seadistamine

1. Avage **Tööajatabeli grupi kaart**
2. Jaotises **Eelarve**:
   - **Eelarve kontroll summade jaoks** - Valige, kuidas käituda eelarveületus summade puhul (Hoiatus/Viga)
   - **Eelarve kontroll tundide jaoks** - Valige, kuidas käituda eelarveületus tundide puhul (Hoiatus/Viga)
   - **Lubatud hälve %** - Seadistage maksimaalne lubatav ületus protsentides

**Näide:** Kui seate 10%, siis võib sisestada kuni 10% rohkem kui eelarves näeb ette.

### 4. Meiliaadressid

1. Avage iga töötaja **Personali andmete lisaseadistus**
2. Määrake **Ettevõtte meiliaadress** - Seda kasutatakse meeldetuletuste saatmiseks
3. Salvestage andmed

### 5. Asendajate määramine

1. Avage **Asendajate seadistus**
2. Iga töötaja jaoks, kellel on asendaja:
   - Määrake **Asendaja** - Töötaja, kes asendab puudumisel
   - Määrake **Periood** - Millal asendamine kehtib
   - Veenduge, et asendajale on määratud **Kasutaja ID**

---

## Peamised kasutusstsenaariumid

### 1. Meeskonna tegevuste jälgimine

**Lehe nimi:** Meeskonna tegevused

See on töötajate juhendile kohandatud tegevuste juhtimise avaekraan, mis näitab:

#### Kasutamisvõimalused:
- **Minu tiim** - Meeskonna liikmed, keda te juhite
- **Minu tööajatabelid** - Teie isiklikud tööajatabelid
- **Minu puhkused** - Puhkuste saldo ja päevad
- **Minu taotlused** - Tehtud taotlused (puhkus, otsused jne)
- **Minu volitatud puhkused** - Puhkused, mille teie olete kinnitanud
- **Minu tiimi puhkusegraafik** - Meeskonna liikmetest tulenevad puhkusegraafik
- **Üle eelarve tööajatabelid** - Eelarvet ületavad tööajatabelid
- **Minu kinnitada** - Taotlused, mis ootavad teie kinnitust

Iga väli on interaktiivne - klõpsamist väljal kuvatakse seotud andmeid.

---

### 2. Tööajatabeli eelarve juhtimine

**Lehekülg:** Tööajatabelid (HRM4Baltics)

#### Funktsioonid:

**Eelarve kontrolli seadistamine:**
- Objektidele saab määrata tundide ja summade eelarved
- Süsteem kontrollib, kas sisestatud andmed ei ületa eelarvestatud limite

**Maksimaalne hälve:**
- Iga tööajatabeli grupi jaoks saab määrata lubatud kõrvalkaldet (%)
- Näiteks 10% lubab tundide/summade ülekaalust 10%

#### Navigeerimine:
- **Eelnev kuu** - Vaata eelmise kuu andmeid
- **Järgnev kuu** - Vaata järgmise kuu andmeid

---

### 3. Tööajatabeli summate konteerimine

**Aruande nimi:** Kannete konteerimine finantsaruandluseks

#### Otstarve:
Tööajatabeli andmeid saab automaatselt pearaamatusse konteerida finantsaruandluseks.

#### Kasutamine:
1. Avage aruanne **"Kannete konteerimine finantsaruandluseks"**
2. Seadistage parameetrid:
   - **Alates kuupäevast** - Missalates kuupäevast konteerimine algab
   - **Kuni kuupäevni** - Missalates kuupäevani konteerimine kehtib
   - **Kannete koondamine** - Valige koondamise tüüp:
     - **Kuu kaupa** - Kogutakse kuude kaupa
     - **Päeva kaupa** - Kogutakse päevade kaupa

3. Valige **OK**, et käivitada konteerimine
4. Süsteem loob pearaamatusse uued kanded ja salvestab konteerimise logi

#### Tulemused:
- **Loodi X pearaamatu kannet** - Teade, mitu kannet loodi
- Kanded on näha pearaamatusse ja saab neid vaadata

---

### 4. Kinnitamise meeldetuletuste saatmine

**Aruande nimi:** Saada kinnituse meeldetuletus

#### Otstarve:
Saata meilides meeldetuletused töötajatele, kes ootavad kinnitust.

#### Kasutamine:
1. Avage aruanne **"Saada kinnituse meeldetuletus"**
2. Seadistage parameetrid:
   - **Meeldetuletuse aeg** - Kuupäevavalem, mis määrab, milliseid kinnituseid meelde tuletatakse
   - **Teema** - Meili teemaring
   - **Sõnum** - Meili sisu

3. Saate kasutada muutujaid tekstis:
   - `%1` = Ootel kinnituste arv
   - `%2` = Tagasi lükatud kannete arv
   - `%3` = Meeldetuletuse seisu kuupäev
   - `%4` = Töötaja nimi
   - `%5` = Link kinnitustele

4. Valige **OK**, et saata meilid
5. Süsteem näitab, mitu meili saadeti - näiteks **"Saadeti 10 meili"**

---

### 5. Objektidega seotud andmete haldamine

#### Objekti seadistamine töötajale

**Laiendasuhe lehekülged:**
- Töötaja kaart
- Töötaja palkade andmed
- Palkade žurnaali read
- Kuluarve read

**Toimingud:**
- **Objekti nr.** - Valige objekt, millega töötaja on seotud
- **Objekti nimetus** - Näitab valitud objekti nimetust automaatselt

**Kasu:**
- Automaatne dimensiooni määramine objektist
- Palkade ja kulude juhtimine objektide kaupa
- Kulude jagamine objektide vahel

---

### 6. Kinnitamise protsess objektiga seotud taotlustele

#### Funktsioonid:

**Kinnitajate juhtimine:**
- Objektidele määratakse kinnitajad
- Asendajate haldamine puudumise ajal

**Kinnitamisprotsess:**
- Süsteem saadab taotlused objekti kinnitajale
- Puudumise ajal käsitlevad taotlusi määratud asendajad
- Kinnitaja kinnitab taotlused süsteemis

---

### 7. Konteerimisega seotud logid

#### Tööajatabeli summade konteerimise logi

**Lehe nimi:** Tööajatabeli summade konteerimise logi

See lehekülg näitab kõigi tehtud konteerimiste ajalugu.

**Väljad:**
- **Pearaamatukande nr.** - Seotud pearaamatusse loodud kande number
- **Palgaandmiku kande nr.** - Seotud palga andmiku kande number
- **Konteerimata rea nr.** - Algne tööajatabeli rea number

**Kasutamine:**
- Kontrollida, milliseid kandeid on konteeritud
- Jälgida konteerimiste ajalugu

---

## Objektide integratsioon

### Objekti andmed erinevates kohtades

Objekte saab kasutada järgmistel juhtudel:

1. **Töötaja andmetes**
   - Töötaja saab olla seotud objektiga
   - Vaikedimensioon määratakse objektist

2. **Palkade andmetes**
   - Iga palga rida saab olla objektiga seotud
   - Kulu jaotus objektide vahel

3. **Tööajatabelites**
   - Tööaja sisestamisel määratakse objekt
   - Eelarve kontroll objekti kaupa

4. **Kuluaruannetes**
   - Kulurea saab olla objektiga seotud
   - Kulude juhtimine projektide kaupa

5. **Taotlustes**
   - Taotlused (puhkus, otsus) saab lingitud objektiga

### Dimensiooni uuendamine

Kui objekt muutub, uuendatakse seotud dimensioonid automaatselt:
- Dimensioone uuendatakse kõigis seotud kannetes
  - Protsessi kestus oleneb andmete mahust

---

Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:  
<a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>
