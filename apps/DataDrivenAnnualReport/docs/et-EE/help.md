# Andmepõhine majandusaasta aruanne
Andmepõhise majandusaasta aruande funktsionaalsus võimaldab BC-s järgmist:

- Klassifikaatorite import
- Pearaamatu kontode sidumine majandusliku sisu klassifikaatoriga ja vaikemääratluste haldus
- Majandusaata aruande jaoks vajaliku andmestiku automaatne koostamine
- Majandusaasta aruande automaatne esitamine (Mikro ettevõtted)

## Sisukord
  - [Seadistamine](#seadistamine)
    - [Klassifikaatroid](#klassifikaatorid)
  - [Kasutamine](#kasutamine)

## Seadistamine
Funktsionaalsuse kasutamiseks tuleb esmalt avada **Majandusaasta aruande (XBRL) seadistus** ning seadistada järgmised väljad:

| Väli | Selgitus |
| --- | --- | 
| **_Mikro_** | Võimaldab märkida seda, kas soovitakse esitada mikroettevõtte aruannet ehk lihtsustatud aruandevormi.|
| **_Majandusaasta aruannete numbrid_** | Võimaldab määrata majandussaasta aruannete numbriseeria.|
|**_Majandusliku sisu klassifikaator_**| Määrab ära Majandusliku sisu klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.|
|**_Tegevusala klassifikaator_**| Määrab ära Tegevusala klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.|
|**_Seotud osapoole klassifikaator_**| Määrab ära Seotud osapoole klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.| 
|**_Andmete esitlusviisi klassifikaator_**| Määrab ära Andmete esitlusviisi klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.|
|**_Varagrupi klassifikaator_**| Määrab ära Varagrupi klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.|
|**_Muutuse liigi klassifikaator_**| Määrab ära Muutuse liigi klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.|
|**_Riigi koodi klassifikaator_**| Määrab ära Riigi koodi klassifikaatori tähise, valik Majandusaasta aruande (XBRL) klassifikaatorite loendist.|
|**_Kliendi võti_**| Võimaldab määrata kliendi võtme, väljastatakse registreerumisel RIK portaalis. 
|**_Kliendi ID_**| Võimaldab määrata kliendi kasutaja ID, väljastatakse registreerumisel RIK portaalis.
|**_Teenuse URL_**| Võimaldab määrata teenuse URL aadressi, vaikimisi täidetud. 

**NB!** Enne klassifikaatori väljade täitmist tuleks avada klassifikaatroite loend, seda saab teha kui klikata nupule **Klassifikaatroid**.

Täiendavalt tuleb seadistada ja üle vaadata järgnevad asukohad, millele ligipääsemiseks on lisatud nupud: **Majandusliku sisu seadistus** ja **PR-Majandusliku sisu vastendus**.

### Klassifikaatorid
Klassifikaatroite lehel tuleb esmalt kasutada nuppu **Uuenda klassifikaatorid** mille tulemusena uuendatakse automaatselt erienvad klassifikaatroid ning nende väärtused.
Kui klassifikaatorid on uuendatud siis tuleb ära määrata klassifikaatori seosed dimensioonidega.

**Mikro aruande** puhul tuleks luua **Tegevusala (EMTAK)** dimensioon ja **Seotud osapoole** dimensioon ning siduda vastavate klassifikaatroitega.

**Standard aruande** puhul tuleks lisaks eelnevale ära seadistada ka ülejäänud klassifikaatorid ja dimensioonid.

**_NB! Majandusliku sisu klassifikaatroile_**_ei ole tarvis dimensiooni seost lisada._

### Majandusliku sisu seadistus
Majandusliku sisu seadistus võimaldab majandusliku sisu klassifikaatroitele lisada vaikeväärtused.

### PR-Majandusliku sisu vastendus
PR-majandusliku sisu vastendus võimaldab siduda majandusliku sisu klassifikaatorid pearaamatu kontodega ning lisada kombinatsioonidele vaikeväärtused.

## Kasutamine

