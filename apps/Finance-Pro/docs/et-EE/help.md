# Finance Pro
Finance Pro lahendus laiendab standardset finantsfunktsionaalsust rakenduses Microsoft Dynamics 365 Business Central järgmiste funktsionaalsustega:
- [Seotud dimensioonid](#seotud-dimensioonid)
- [Perioodiseerimiskanded sisaldavad rohkem teavet](#perioodiseerimiskanded-sisaldavad-rohkem-teavet)
- [Partnerite kohesed saldod](#partnerite-kohesed-saldod)
- [PR kannete lisateave](#pr-kannete-lisateave)
- [Põhivarade kohene ülevaade](#põhivarade-kohene-ülevaade)
- [Erisoodustus](#erisoodustus-eesti-ettevõtetele)

<br>

# Funktsioonid
## Seotud dimensioonid
See funktsionaalsus võimaldab siduda teiste dimensioonide väärtuseid soovitud globaaldimensiooni väärtusega (_nii et on võimalik luua nn dimensioonipuu_).  
Pärast seadistamist, kui kasutaja valib kannetele globaaldimensiooni väärtuse (_millel on seotud dimensioonid_), lisatakse automaatselt ka kõik vastavad seotud dimensioonid.

Seotud dimensioone on võimalik kasutada järgmistel kirjetel:
- Müügidokumendi päis ja read (sh müügitellimus, müügiarve ja müügi kreeditarve)
- Ostudokumendi päis ja read (sh ostutellimus, ostiarve ja ostu kreeditarve)
- Peažurnaal
- Põhivara PR žurnaal ja põhivara žurnaal
- Maksete žurnaal ja maksete vastavustamine žurnaal
- Kaupade žurnaal

### Seadistamine
Seotud dimensioonide kasutamiseks peate globaaldimensiooni väärtusega siduma soovitud teiste dimensioonide väärtused. Selleks:
1. Navigeerige dimensioonide lehele
2. Avage globaaldimensiooni dimensiooniväärtused
3. Valige toiming „Seotud dimensioonid"
4. Lisage soovitud dimensioonide dimensiooniväärtused, mis antud globaaldimensiooni väärtusega peavad olema seotud

**Seadistamise märkused:**
- Kasutaja ei saa valida sama dimensiooni seotud dimensiooniks.
- Kasutaja ei saa valida dimensiooni seotud dimensiooniks, kui see dimensioon on juba määratud selle praeguse dimensiooni seotud dimensiooniks.
- Kui kasutaja valib dimensiooni, mis on juba määratud alus-dimensiooni seotud dimensiooniks, siis teavitatakse kasutajat ja palutakse tal kinnitada, kas ta soovib jätkata.

## Perioodiseerimiskanded sisaldavad rohkem teavet
See funktsionaalsus lisab vastava alus-rea kirjelduse perioodiseerimisgraafiku ridade kirjeldusele (ja sealt lähevad need pearaamatu kannete kirjelduseks).
- Perioodiseerimiskannete kirjeldused saavad sisaldada rea kirjeldust seotud:
  - Müügirealt
  - Osturealt
  - Žurnaalirealt

  Märkus! Müügi-/ostudokumentides lisatakse rea kirjeldus perioodiseerimisgraafiku ridade kirjeldusele ainult juhul, kui rida on liigiga „PR konto", sest neid ei koondata PR kannete loomisel (_erinevalt näiteks kaup liigiga ridadest_).

### Seadistamine
Müügi-/ostudokumentide rea kirjelduste kasutamiseks perioodiseerimiskannetel navigeerige „Müügi ja müügivõlgade seadistus" lehele ja/või „Ostude ja ostuv. seadistus" lehele ning lubage:
- „Kopeeri rea kirjeldus PR kandele" (_see muudab järgneva välja nähtavaks_)
- „Lisa rea kirjeldus periodiseerimise kannetele"

Märkus! Peažurnaali kasutamisel ei ole seadistamist vaja (_st peažurnaali rea kirjeldus lisatakse alati perioodiseerimisgraafiku ridade kirjeldusele_).

## Partnerite kohesed saldod
See funktsionaalsus võimaldab saada partneri saldo mis tahes kuupäeva seisuga kiiresti, kasutades ainult kuupäevafiltrit kliendi/hankija loendis.
Lisage loendis kuupäevafilter ja uus väli „Saldo kuupäevaks (KV)" näitab saldot lõppkuupäeval, mis sai kuupäevafiltris määratud.

## PR kannete lisateave
Pearaamatu kannetele lisatakse järgmine teave:
- Allika nimi ja Korr. konto nimetus
  - Sõltuvalt liigist võib see olla:
    - Kliendi nimi
    - Hankija nimi
    - Töötaja nimi
    - Põhivara nimi
    - Pangakonto nimi

## Põhivarade kohene ülevaade
- Põhivara loendisse lisatud väljad:
  - Jääkväärtus
  - Soetusmaksumus
  - Soetuse kuupäev
  - Kulum %
  - Kulumiraamat
  - Kulumi alguse kuupäev
  - Kulumi lõpu kuupäev
  - Kulumiaastate arv
  - Järelejäänud kulumi aeg
  - Likvideerimiskuupäev
  - Järgmise hoolduse kuupäev
  - Garantii kuupäev
  - Seerianumber
  - Hankija nimi
  - Hooldushankija nimi

Märkus! Kui loendis on tuhandeid põhivarasid, võib loendi avamine olla aeglane (_kuna paljud neist väljadest on arvutatud ehk flowfieldid_). Sellisel juhul palun peidake väljad, mida te ei vaja.

## Erisoodustus (Eesti ettevõtetele)
See on aktiveeritud ainult siis, kui ettevõtte andmetes on "Riigi/regiooni tähis" väärtuseks "EE".  
Kui funktsionaalsus on aktiveeritud, siis PR kontode kaardil on võimalik märkida kontot kui "Erisoodustuse konto" (jaotises "Erisoodustus").  
Kui "Erisoodustuse konto" on märgitud, siis on võimalik määrata PR kontod, kuhu erisoodustusega seotud maksud arvutatakse, genereerides vastavasisulised lisaread ostudokumentidel.

  
---

Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:
<a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>
