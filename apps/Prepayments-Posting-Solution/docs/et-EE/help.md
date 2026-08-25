
# Kasutusjuhend

## Lahendus võimaldab:
-Konteeringurühma automaatset muudatust tellimuspõhisel ettemaksuarvel  
-Konteeringurühma muudatust müügiarvel/tellimusel  
-Konteeringurühma muudatust ostuarvel/tellimusel  

## Seadistus
### Tellimuspõhine ettemaksuarve
Müügi- või Ostutellimuselt väljastatava tellimuspõhise ettemaksuarve puhul **avada Kliendi/Hankija konteeringurühma leht ning täita** lahenduse poolt lisatud väli **Ettemaksuarve Kliendi/Hankija konteeringurühm**.  

Kasutaja määratleb seal alternatiivse Kliendi/Hankija konteeringurühma, mida lahendus kasutab, 
konteerimaks tellimuspõhise ettemaksuarve võlasaldo vastava ettemaksuarve konteeringurühma alusel.  

NB! Kui ei kasutata tellimuspõhiseid ettemaksuarveid, siis ei pea seda määratlust tegema.  

### Tööjärjekorra kanded
Lahenduse installeerimise käigus luuakse automaatselt tööjärjekorra kanded, tegemaks korrigeerimiskandeid standardsetele maksete, laekumiste, sidumiste, lahtisidumiste kannetele.  
Vaikimisi on tööjärjekorra kannete käivitamiste vaheks määratud 15 minutit. Kasutaja saab vajadusel seda muuta.

Vastav tööjärjekorra kanne korrigeerib BC standardloogika (*Kliendi/Hankija konteeringurühm võetakse maksmisel/laekumisel/sidumisel/lahtisidumisel alati Kliendi/Hankija kaardilt*) poolt loodud pearaamatu kanded, tehes täiendava kande, liigutamaks võlgnevusega seotud kande summa väljale, mis määratud arvel oleva Kliendi/Hankija konteeringurühma alusel.  

**Tööjärjekorra kande koodibloki nr. on 24013200** ning parameetrid:  
-"**CUSTOMER**" (korrigeerimaks Kliendi võla makse/laekumise/sidumise/lahtisidumise kannet).  
-"**VENDOR**" (korrigeerimaks Hankija võla makse/laekumise/sidumise/lahtisidumise kannet).  

<br>
Tähelepanu! Tööjärjekorra kande esimesel käivitamisel kontrollib süsteem töökuupäevast lähtuvalt viimase 3 kuu üksikasjalikke Kliendi-/Hankijaandmiku kandeid, leidmaks korrigeerimist vajavaid kandeid. Viimase kontrollitud kande nr. kirjutatakse vastavalt Müügi- ja müügivõlgade seadistus/Ostu- ja ostuvõlgade seadistus tabelisse.


## Kasutamine
### Tellimuspõhine ettemaksuarve
Müügi- ja Ostutellimuselt **tellimuspõhist ettemaksuarvet konteerides võtab lahendus automaatselt** Ettemaksuarve Kliendi/Hankija konteeringurühma.

### Käsitsi konteeringurühma muutmine müügi- ja ostuarvel/tellimusel
Müügi- ja Ostuarve/tellimuse päises **saab Kasutaja ise** muuta Kliendi/Hankija konteeringurühma.  Samuti saab konteeringurühma muuta müügi- ning ostu kreeditarve päises.  
<br>
Tähelepanu! Müügi- ja Ostutellimuse päises on esmalt vaja  Kliendi/Hankija konteeringurühma 
väli isikupärastamisega nähtavaks tuua.

---

Täpsema info saamiseks, palun võtke ühendust DIGMATIX-ga:   <a href="https://www.digmatix.com/ee/kontaktid" target="_blank">https://www.digmatix.com/ee/kontaktid</a>
