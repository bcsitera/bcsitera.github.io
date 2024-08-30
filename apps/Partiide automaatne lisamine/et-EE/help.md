# Partiide automaatne määramine

Partiide automaatse määramise lahendus võimaldab:

* seadistada müümisel, tootmisel või laoseisust maha kandmisel tingimused, mille alusel lisatakse toodetele partiid ühe nupuvajutusega

* seadistada müümisel kliendipõhised säilivusaja nõuded erinevatele toodetele

## Seadistamine

Lahenduse kasutamiseks tuleb esmalt teha seadistused.

### Ladude seadistus

Kõigepealt tuleb ära seadistada laod, milles lubatakse partiisid automaatselt määrata.

Selleks trüki otsingusse **Partii lisamise reeglite seadistus**. Avanenud loendis saab seadistada ladusid ja meetodeid järgnevalt:

* Asukoha kood – siia vali asukoht Asukohtade loendist

* Luba automaatne partii lisamine – aktiveerib partiide automaatse lisamise müügi- ja kompl.tellimuse ridadel ning kaubažurnaalis

* Meetod – defineeritakse ära meetod, mille alusel partiisid lisatakse

	* FIFO – partiid leitakse FIFO meetodi alusel (First-In-First-Out)

   * FEFO – partiid leitakse FEFO meetodi alusel (First-Expired-First-Out)

  * Klient – partiid leitakse kliendipõhise seadistuse alusel

### Seadistused Kaubakaardil

Kui tahetakse tooteid väljastada kliendipõhiste aegumiste järgi, siis tuleb täita kaubakaardil, sakil Müügi arvutused, järgmised väljad:

**Kauba säilivus päevades** - toote lõplik säilivusaeg (kohustuslik)

**Kauba säilivus kliendile** - toote vaikimisi säilivusaeg kliendile (kohustuslik)

**Karantiini arvutamine** - kui toodet ei tohi kohe peale valmimist kliendile saata, siis siin saab määrata talle buffer aja mille jooksul muutub ta müügikõlbulikuks

### Seadistused Kliendikaardil

Kui kliendile tahetakse väljastada tooteid nende ette defineeritud aegumiste alusel, siis tuleb need aegumised defineerida ja kliendikaardile seadistada. Selleks mine kliendikaardile ning leia sakk **Aegumisrühmad**. Siin saate valida kliendipõhise aegumisrühma.

### Kliendipõhised aegumisrühmad

Kliendiaegumisrühmad võivad olla ainult ühe konkreetse kliendi põhised või standardsed mida saab kasutada erinevatel klientidel.

Kõigepealt loo uus kliendiaegumisrühm. Selleks vali menüüst **Uus > lisa Kood > lisa Kirjeldus**.

Nüüd defineeri millised tooted sellesse kliendiaegumisrühma kuuluvad. Selleks vali menüüst **Seotud > Kliendi aegumised**.

Avanenud tabelis loo kaupadele või kaubakategooriatele read. Vali menüüst **Redigeeri loendit > Tüüp > Kood**. Kui kaubakaardil on seadistatud toote säilivus kliendile, siis tuuakse väärtus koheselt ka veegu “Kauba säilivus kliendile”.

Edasi tuleb määrata kas “Realiseerimisaeg (%)” väärtus või “Realiseerimistähtaeg (päevades)”.

Kui kaubakaardil muudetakse väärtust väljal “Kauba säilivus kliendile”, siis saab väärtused ümber arvutada järgmiselt: **Rohkem suvandeid > Toimingud > Arvuta aegumised ümber**.

# Kasutamine

## Müügitellimused

Kui eelnevad seadistused on tehtud siis partiide lisamine Müügitellimuse ridadel käib järgnevalt. Sisestage müügitellimuse ridadele kaubad mis tuleb partiidega lähetada. Partiide lisamiseks tee järgmist: **Read menüüst vali: Rida > Lisa partiid**.

## Kompl.tellimused

Kui tooded, mis liiguvad partiiga, on osaks kooslusest, siis nendele saab partiisid lisa Kompl.tellimuse ridadel järgmiselt: **Read > Rida > Lisa partiid**.

NB! Kompl.tellimustel saab partiide määramisel kasutada ainult Meetodeid FIFO ja FEFO.

## Kaubažurnaalid

Kui tooteid soovitakse läbi kaubažurnaali maha kanda negatiivse täpsustusega, siis on võimalik samuti partiisid lisada ridadele automaatselt. See käib järgmiselt: Menüüst vali **Rida > Lisa partiid**.

NB! Kaubažurnaalides saab partiide määramisel kasutada ainult Meetodeid FIFO ja FEFO.
