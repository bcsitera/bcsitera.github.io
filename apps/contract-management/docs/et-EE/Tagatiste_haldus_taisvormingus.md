# Tagatiste haldus

## Sisukord

- [Üldine](#üldine)
- [Tagatised](#tagatised)
- [Kinnipidamised](#kinnipidamised)
- [Seadistused](#seadistused)
- [Hankija/Kliendi konteeringurühm](#hankijakliendi-konteeringurühm)
- [Lepingu kaart (Tagatised vahekaart)](#lepingu-kaart-tagatised-vahekaart)
- [Kasutamine (Kinnipidamised)](#kasutamine-kinnipidamised)
- [Kasutamine (Tagatised)](#kasutamine-tagatised)
- [Lepingu jääkide uuendamine](#lepingu-jääkide-uuendamine)

---

## Üldine
Tagatiste haldust saab hallata kahte moodi, seadistatav lepingute seadistuses millist lahendust ja kus (Ost, Müük) kasutatakse.

## Tagatised
Tagatiste puhul toimub loogika läbi arve ridade ja tagatisandmiku kannete (sarnaselt Kliendipõhisele/hankijapõhisele ettemaksule).

Kasutatav nii ostuarvete kui ostutellimustega ning müügiarvete ja müügitellimustega.

Näiteks ostu puhul: Kulureale lisatakse lisaks miinusmärgiga rida kus kasutatakse tagatiste kontot.

Tagatise kontod peavad olema seadistatud selliselt, et need jääksid INF aruandest välja.

## Kinnipidamised
Kinnipidamiste puhul toimub tagatise arvutus ja loogika reskontros, reskontro summa tükeldatakse konteerimisel.

Kasutatav ainult ostuarvete ja müügiarvetega

Eelduseks on see, et nii klientide kui hankijate puhul on lubatud kasutada mitut hankija/kliendi konteeringurühma.

## Seadistused
### Lepingute seadistus (Tagatiste haldus vahekaart)
Lepingute seadistuses on võimalik määrata mis tüüpi lahendust ja kus kasutatakse ning lisaks täiendavad seadistused

Müügi tagatiste lahenduse liik:

tühi - tagatisi ei kasutata.

Tagatis - kasutatakse tagatisandmiku kannete lahendust.

Kinnipidamine - kasutatakse reskontro lahendust.

Ostu tagatiste lahenduse liik

tühi - tagatisi ei kasutata.

Tagatis - kasutatakse tagatisandmiku kannete lahendust.

Kinnipidamine - kasutatakse reskontro lahendust.

Lühiajaliste tagatiste tähtaja kuupäevavalem - võimaldab märkida lühiajalise tagatise eeldatava tähtaja arvutamise valemit, kasutatakse juhul kui kannetel pole kasutusel Lepingut. 

Pikaajaliste tagatise tähtaja kuupäevavalem - võimaldab märkida pikaajalise tagatise eeldatava tähtaja arvutamise valemit, kasutatakse juhul kui kannetel pole kasutusel Lepingut. 

Kinnipidamiste puhul:

Lühiajaliste tagatiste Hankija konteeringurühm, Pikaajaliste tagatiste Hankija konteeringurühm - võimaldab määrata hankija konteeringurühmad, mida kastutatakse tagatiste konteerimiseks.

Lühiajaliste tagatiste Kliendi konteeringurühm, Pikaajaliste tagatiste Kliendi konteeringurühm - võimaldab määrata kliendi konteeringurühmad, mida kastutatakse tagatiste konteerimiseks.

Pikaajlise tagatise zurnaali nimi, Pikaajalise tagatise žurnaali tööleht - võimaldab määrata millisele peažurnaali töölehele luuakse Pikaajalise tagatise kanded kui kasutatakse kliendi/hankijaanmdiku kandel funktsiooni Arvuta pikaajaline tagatis.

### Hankija/Kliendi konteeringurühm
Loo uued konteeringurühmad (Kinnipidamiste lahenduse puhul)
Loo uued konteeringurühmad Lühiajaliste ja Pikaajaliste tagatiste jaoks - tagatise konto märgi Võlgnevuse konto veergu. 

Seadista olemasolevad konteeringurühmad (Tagatiste lahenduse puhul)
Lisa olemasolevatele konteeringurühmadele veergudesse Lühiajaliste tagatise konto ja Pikaajalise tagatise konto vastavad PR kontod.  

## Lepingu kaart (Tagatised vahekaart)
Arvuta tagatis KM-ga summast - võimaldab määrata kas tagatise summad arvutatakse KM-ta või KM-ga summast.

Lühiajalise tagatise % - võimaldab määrata lühiajalise tagatise protsendi, mida kasutatakse tagatise arvutamisel.

Lühiajalise tagatise tähtaeg - võimaldab määrata konkreetse kuupäeva millal lühiajalised tagatised eeldatavalt vabastatakse.

Lühiajalise tagatise tähtaja arvutamine - võimaldab määrata kuupäevavalemi mille alusel arvutatakse lühiajalise tagatise tähtaeg, aluseks võetakse dokumendi konteerimiskuupäev.

Pikaajalise tagatise % - võimaldab määrata pikaajalise tagatise protsendi, mida kasutatakse tagatise arvutamisel.

Pikaajalise tagatise tähtaeg - võimaldab määrata konkreetse kuupäeva millal pikaajalised tagatised eeldatavalt vabastatakse.

Pikaajalise tagatise tähtaja arvutamine - võimaldab määrata kuupäevavalemi mille alusel arvutatakse pikaajalise tagatise tähtaeg, aluseks võetakse dokumendi konteerimiskuupäev.

## Kasutamine (Kinnipidamised)
Ost
Ostuarve
Ostuarve väljad:

Lühiajalise tagatise summa - võimaldab määrata lühiajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Lühiajaline. Lisaks märgitakse Peatatud veergu täheühend STR.

Lühiajalise tagatise tähtaeg - võimaldab määrata lühiajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks.  

Pikaajalise tagatise summa - võimaldab määrata pikaajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Pikaajaline. Lisaks märgitakse Peatatud veergu täheühend LTR.

Pikaajalise tagatise tähtaeg - võimaldab määrata pikaajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks.  

Ostuarvel nupud: 

Arvuta lühiajaline tagatis - arvutab lühiajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle ostuarve päisesse väljale Lühiajalise tagatise summa ning täidab ära ka Lühiajalise tagatise tähtaja. NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

Arvuta pikaajaline tagatis - arvutab pikaajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle ostuarve päisesse väljale Pikaajalise tagatise summa ning täidab ära ka Pikaajalise tagatise tähtaja. NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

Hankijaandmiku kanded
Hankijaandmiku kannete veerud:

Tagatise liik:

Lühiajaline - märgitakse automaatselt Lühiajalise tagatise kandele.

Pikaajaline - märgitakse automaatselt Pikaajalise tagatise kandele.

Hankijaandmiku kannete nupud:

Arvuta pikaajaline tagatis - töötab ainult juhul kui valitud kanne või kanded on Tagatise liigiga - Lühiajaline. Kuvatakse aken kus on võimalik märkida Dokumendi numbrit, konteerimiskuupäeva, Pikaajalise tagatise summat ja Pikaajalise tagatise tähtaega. Kasutatakse juhul kui arve konteerimisel ei lisatud Pikaajalise tagatise infot.

Klikates nupule Loo kanded - avatakse vastavalt seadistustele peažurnaali tööleht kuhu on lisatud Lühiajalise tagatise sulgemiskanne ja pikaajalise tagatise kanne. Konteerimisel seotakse Lühiajalise tagatise reskontrokanne vastava Lühiajalise tagatise reskontrokandega ning lisatakse uus Pikaajalise tagatise reskontrokanne.

Müük
Müügiarve
Müügiarve väljad:

Lühiajalise tagatise summa - võimaldab määrata lühiajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Lühiajaline. Lisaks märgitakse Peatatud veergu täheühend STR.

Lühiajalise tagatise tähtaeg - võimaldab määrata lühiajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks.  

Pikaajalise tagatise summa - võimaldab määrata pikaajalise tagatise summa. Konteerimisel luuakse vastava summaga reskontro kanne millele lisatakse Tagatise liik - Pikaajaline. Lisaks märgitakse Peatatud veergu täheühend LTR.

Pikaajalise tagatise tähtaeg - võimaldab määrata pikaajalise tagatise eeldatavat tähtaega. Konteerimisel lisatakse see kuupäeva loodavale reskontrokandele tähtajaks.  

Müügiarve nupud: 

Arvuta lühiajaline tagatis - arvutab lühiajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle müügiarve päisesse väljale Lühiajalise tagatise summa ning täidab ära ka Lühiajalise tagatise tähtaja. NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

Arvuta pikaajaline tagatis - arvutab pikaajalise tagatise (vastavalt lepingu kaardil seadistatule) ja lisab selle müügiarve päisesse väljale Pikaajalise tagatise summa ning täidab ära ka Pikaajalise tagatise tähtaja. NB! Nupp on nähtav ainult juhul kui päisesse on valitud Lepingu nr.

Kliendiandmiku kanded
Hankijaandmiku kannete veerud:

Tagatise liik:

Lühiajaline - märgitakse automaatselt Lühiajalise tagatise kandele.

Pikaajaline - märgitakse automaatselt Pikaajalise tagatise kandele. 

Kliendiandmiku kannete nupud:

Arvuta pikaajaline tagatis - töötab ainult juhul kui valitud kanne või kanded on Tagatise liigiga - Lühiajaline. Kuvatakse aken kus on võimalik märkida Dokumendi numbrit, konteerimiskuupäeva, Pikaajalise tagatise summat ja Pikaajalise tagatise tähtaega. Kasutatakse juhul kui arve konteerimisel ei lisatud Pikaajalise tagatise infot.

Klikates nupule Loo kanded - avatakse vastavalt seadistustele peažurnaali tööleht kuhu on lisatud Lühiajalise tagatise sulgemiskanne ja Pikaajalise tagatise kanne. Konteerimisel seotakse lühiajalise tagatise reskontrokanne vastava Lühiajalise tagatise reskontrokandega ning lisatakse uus Pikaajalise tagatise reskontrokanne.

## Kasutamine (Tagatised)
Ost
Tagatise kinnipidamine
Ostuarvel/ostutelimusel on järgmised nupud:
Arvuta lühiajaline tagatis – arvutab lühiajalise tagatise vastavalt ostuarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue ostureana.
NB! Nupp on nähtav ainult juhul, kui ostuarve päisesse on valitud Lepingu nr.

Arvuta pikaajaline tagatis – arvutab pikaajalise tagatise vastavalt ostuarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue ostureana.
NB! Nupp on nähtav ainult juhul, kui ostuarve päisesse on valitud Lepingu nr.

Ostuarve konteerimisel luuakse avatud hankija tagatisandmiku kanded. Kande eeldatav tähtaeg arvutatakse tagatise tähtaja arvutamise valemi alusel.

Tagatise väljamaksmine
Tagatiste väljamaksmist saab käivitada ostuarvel nupuga Too hankijapõhine tagatis.

Eeldused:

ostuarvele peab olema määratud vastav Lepingu nr.

Avanenud aknas kuvatakse kõik avatud tagatisandmiku kanded, mis vastavad järgmistele tingimustele:

sama hankija,

sama valuuta,

sama tagatise liik,

Avatud = Jah.

Kasutaja valib sobiva tagatisandmiku kande.

Tulemusena lisatakse ostuarvele uus osturida tagatisandmiku kande jääksummaga.

Ostuarve konteerimisel:

tekib uus hankija tagatisandmiku kanne,

algse kande jääksumma väheneb.

Kui tagatis makstakse lõplikult välja, muutub kinnipidamise kande välja Avatud väärtus väärtuseks Ei.

Müük
Tagatise kinnipidamine
Müügiarvel/Müügitellimusel on järgmised nupud:

Arvuta lühiajaline tagatis – arvutab lühiajalise tagatise vastavalt müügiarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue müügireana.
NB! Nupp on nähtav ainult juhul, kui müügiarve päisesse on valitud Lepingu nr.

Arvuta pikaajaline tagatis – arvutab pikaajalise tagatise vastavalt müügiarve ridade summale ja lepingu kaardil seadistatud tingimustele ning lisab tulemuse uue müügireana.
NB! Nupp on nähtav ainult juhul, kui müügiarve päisesse on valitud Lepingu nr.

Müügiarve konteerimisel luuakse avatud kliendi tagatisandmiku kanded. Kande eeldatav tähtaeg arvutatakse tagatise tähtaja arvutamise valemi alusel.

Tagatise vabastamine
Tagatise vabastamist saab käivitada müügiarvel nupuga Too kliendipõhine tagatis.

Eeldused:

müügiarvele peab olema määratud vastav Lepingu nr.

Avanenud aknas kuvatakse kõik avatud tagatisandmiku kanded, mis vastavad järgmistele tingimustele:

sama klient,

sama valuuta,

sama tagatise liik,

Avatud = Jah.

Kasutaja valib sobiva tagatisandmiku kande.

Tulemusena lisatakse müügiarvele uus müügirida tagatisandmiku kande jääksummaga.

Müügiarve konteerimisel:

tekib uus kliendi tagatisandmiku kanne,

algse kande jääksumma väheneb.

Kui tagatis vabastatakse lõplikult, muutub kinnipidamise kande välja Avatud väärtus väärtuseks Ei.

## Lepingu jääkide uuendamine
Süsteem uuendab automaatselt lepingu välju:

Avatud lühiajalised garantiid

Avatud pikaajalised garantiid

Need väärtused näitavad kui palju garantiisummasid on veel aktiivsed.