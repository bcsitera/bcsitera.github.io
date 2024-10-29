---
---
##### Versioon 20.0.24303.0
- Üksikute kuludokumentide toomisel CostPocketist mindud kuupäevalise kontrolli asemel üle staatusepõhise kontrolli peale.
  - _Kui kuludokument on edukalt BC-sse toodud, siis saadetakse CostPocketisse staatyse muutmise päring, mis märgib dokumendi staatuseks Edastatud._  

##### Versioon 20.0.24252.0
- Lisatud makseviiside automaatika
  - _Kuluaruannete seadistuses toiming "Makseviisi vastendamine", saab tuua CostPocketist makseviisid (sh krediitkaart) ning vastendada need BC makseviisidega, selleks et pangakaardi aruande puhul süsteem määraks kuludokumendile kohe automaatselt vastava makseviisi._
- Lisatud kuluaruandele numbriseeria valiku võimalus _(eeldusel et numbriseeriates on loodud seotud numbriseeria)_.  

##### Versioon 20.0.24144.0
- Parandatud olukord, kus lähetuse päevarahadega kuluaruandeid ei õnnestunud CostPocketist BC-sse tuua.  

##### Versioon 20.0.24134.0
- Lisatud lahendusele manustatud dokumentide parem eelvaade (sh suur eelvaade).
  - Lisaks saab nüüd valida, millises formaadis manused tulevad (kas PDF või Pilt).
- Lisatud esmane makseviiside tugi kuludokumentidele.  

##### Versioon 20.0.24107.0
- Lisatud võimalus konteeritud kuluaruande ja kuludokumentide nupust tühistamiseks/parandamiseks.  

##### Versioon 20.0.24091.0
- Täiendatud kuluaruande konteerimise loogikat nii, et kui Hankija kaardil on KM äri konteeringurühm täidetud, siis kasutatakse konteerimisel seda
  - Varem võeti konteerimisel alati "KM äri konteeringurühm" tabeli "Üld. ärikonteeringurühmad" väljalt "Vaikimisi KM äri kont.rühm"
- Väiksemad tehnilised täiendused  

##### Versioon 20.0.23103.0
- Tehtud lahendus BC22 versiooniga ühilduvaks
- Lisatud päevarahade konto määramisel loogika, et dimensioonid kuluaruandele luuakse nii töötaja, kui PR konto vaikedimensioonide alusel
- Parandatud veaolukord, mis tekkis kuluaruande manuaalsel loomisel (_süsteem läks ekslikult kohe kuluaruande esitajat otsima_)
- UX täiendused  

##### Versioon 15.6.23045.0
- Lisatud kuluaruandele väljad Riigi tähis (nähtav) ja Riigi nimetus (vaikimisi peidus), et kuvada lähetusaruandel külastatud riiki
- Lisatud kuluaruandele väli Päevarahade kande kirjeldus (vaikimisi peidus), et kasutajal oleks võimalik muuta päevarahade PR kandele tulevat kande kirjeldust
- Parandatud olukord, kus kuludokumendi ridades arvandmete muutmine ei kajastunud koheselt kuludokumendi päises olevates summades
- Parandatud olukord, kus hankija manuaalsel lisamisel kuludokumendile tuli kasutajal eemaldada ning uuesti lisada kululiik, et aktiveeruks kululiigi alusel dokumendi PR konto määratlus  

##### Versioon 15.6.22178.0
- Parandatud olukord, kus manuseid ei õnnestunud kuluaruannetele/kuludokumentidele BC20 versiooniga lisada
- Parandatud olukord, kus kuluaruannete toomisel Costpocketist tuli viga "Tabelit Töövoo sündmus pole olemas."

##### Versioon 15.6.22143.1
- Nüüd saab lisada dimensioone ka kuludokumendi ridadele

##### Versioon 15.3.22091.0
- Parandatud olukord, kus kuluaruannete loendist õnnestus konteerida kinnitamata, kuid aktiivse kinnituse töövooga, kuluaruanne
- Väiksemad bugiparandused ja UX täiendused

##### Versioon 15.3.22031.0
- Fikseeritud kululiikide asemel kohandatav puu struktuuriga kululiigid, mida saab ka CostPocketiga sünkroniseerida
- BC-s saab aruande ettevalmistada ning CostPocketisse saata (et nt seal dokumendid lisada)
- Kuludokumentidele saab otse BC-st pildistades dokumenti lisada
- BC ning CostPocketi liides kasutab nüüdsest staatuse märget nii aruannete tõmbamisel, kui tõmmatud aruande märkimisel saadetuks
- BC-s saab nüüd otse kuluaruandelt algatada uue kuludokumendi loomist
- Täiendatud kulukonto valikut dokumendil nii, et kuvatakse ainult konteerimise liigiga kasumiaruande kontod
- Lähetuse algus- ja lõppkuupäev ning päevarahade summa kuvatakse nüüd ainult aruannetel, mille liigiks Lähetus 
- Parandatud olukord, kus ettevalmistatud kuludokumentide lisamisel BC-s ei tekkinud seost kuludokumendi rea ning aruande vahel
- Väiksemad UX täiendused
