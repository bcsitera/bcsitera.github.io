# Andmepõhine majandusaasta aruanne
Andmepõhise majandusaasta aruande funktsionaalsus võimaldab BC-s järgmist:

- Klassifikaatorite import
- Pearaamatu kontode sidumine majandusliku sisu klassifikaatoriga ja vaikemääratluste haldus
- Majandusaata aruande jaoks vajaliku andmestiku automaatne koostamine
- Majandusaasta aruande automaatne esitamine (Mikro ettevõtted)

## Sisukord
  - [Seadistamine](#seadistamine)
    - [Klassifikaatroid](#klassifikaatorid)
    - [Majandusliku sisu seadistus](#majandusliku-sisu-seadistus)
    - [PR-Majandusliku sisu vastendus](#pr-majandusliku-sisu-vastendus)
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

**_NB! Majandusliku sisu klassifikaatroile_** _ei ole tarvis dimensiooni seost lisada._

### Majandusliku sisu seadistus
Majandusliku sisu seadistus võimaldab majandusliku sisu klassifikaatroitele lisada vaikeväärtused.\
Iga majandusliku sisu klassifikaatoriga on võimalik siduda teisi klassifikaatoreid ja määrata nende kohustuslikkust.
Teiste klassifikaatroite sidumisel on iga klassifikatroi juures võimalik määrata kohustuslikkust:
* **Ei** - ei ole kohustuslik.
* **Jah** - on kohustuslik. Kohustuslikkus lisatakse PR kontoga vastendamisel PR kontole dimensiooni kohustuslikkusena: **_Tähis kohustuslik_**.
* **Vaikimisi** - araunde koostamisel võetakse väärtus vastava klassifikaatori **_Vaikimisi ..._** veerust. PR kontoga sidumisel PR kontole vaikedimensiooni kohustuslikkust ei lisata.


### PR-Majandusliku sisu vastendus
PR-majandusliku sisu vastendus võimaldab siduda majandusliku sisu klassifikaatorid pearaamatu kontodega ning lisada kombinatsioonidele vaikeväärtused.\
PR kontode lisamiseks võib kasutada nuppu **Lisa PR kontod**, avanevas aknas on võimalik valida millised kontode lisatakse (tuleks lisada kõik kontod v.a. bilansivälised kontod.)

Kui kontod on lisatud tuleb iga konto ära vastendada **Majandusliku sisu klassifikaatoriga**. Majandusliku sisu klassifikaatroi valimisel tuuakse kaasa vastavad vaikeväärtused.\
Kui vastendus on tehtud, siis saab vajadusel vaikeväärtuseid muuta ehk tekitada **PR konto - Majandusliku sisu klassifikaatori** kombinatsioonide põhised seadistused.

**_Näiteks_**_: Kui on kasutusel 2 erinevat PR kontot nõuete jälgimiseks (Grupivalised ja Grupisisesed), mõlemad kontod seotakse sama klassifikaatroiga **103010 Nõuded - Ostjate vastu (Lühiajaline)**._
_Grupisisese nõuete konto kombinatsiooni reale saama lisada **Seotud osapoole** kohustuslikkuse._

## Kasutamine

