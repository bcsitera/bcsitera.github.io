# Aadressiotsing (Address Autocomplete)
Lahendus võimaldab Business Centralis teha järgmist: 
- Aadresside otsingut aadressi kirjutamisel 
- Aadressiväljade täitmist valitud aadressiga (_hetkel ainult eesti aadressid toetatud_)


## Seadistus
Lahenduse kasutamiseks tuleb avada **Aadressiotsingu seadistus** ning märkida funktsionaalsus lubatuks.
  
  
|Väli|Selgitus|
|---|---| 
| Eemalda linnaosa linna infost | Määrab, kas eemalda linnaosa linna infost (näiteks "Kesklinna linnaosa"). |
| Otsingu teenus | Vali aadressiotsinguks kasutatav teenusepakkuja (Maa-amet või Google).<br><br>- **Maa-Ameti** gazetteer teenus on tasuta ning võimaldab otsida aadresse Eestis.<br>- **Google** maps võimaldab üleilmset aadressiotsingut ning vastava Place Autocomplete API hinnastuse leiab <a href="https://mapsplatform.google.com/pricing/" target="_blank">siit</a>.<br><br>Märkus! Otsingu teenust saab vahetada ainult siis, kui funktsionaalsus ei ole lubatud olekus. |
| Kuvatav otsingutulemuste arv | Määrab kuvatavate aadressiotsingu tulemuste arvu. Vaike ning soovituslik väärtus on 5. <br><br>Märkus! Väärtus on muudetav ainult Maa-ameti teenuse kasutamise puhul. |
| API võti | Määrab Google Places API võtme.<br>Võtme saab Googlest, peale vastava teenuse kasutajaks registreerimist.<br>Palun kontrollige, et <a href="https://console.cloud.google.com/apis/library/places-backend.googleapis.com?q=place" target="_blank">Places API</a> oleks aktiveeritud (Enabled) Teie Google Cloud projektis.<br>Google nõue on, et Billing peab olema <a href="https://console.cloud.google.com/project/_/billing/enable" target="_blank">Google Cloud Project</a> all aktiveeritud. |
| Keel | Määrab Google aadressiotsingu keele.<br>Eestikeelsete päringuvastuste saamiseks kasuta "et" või nt. inglisekeelsete puhul kasuta "en".<br>Kogu loetelu saadaolevatest keeltest leiab <a href="https://developers.google.com/maps/faq#languagesupport" target="_blank"> siit</a>.<br><br>NB! Valik rakendub ainult otsingutulemustele - st aadressiväljad täidetakse tõlkimata infoga.|
  
  
#### Aadressiotsingut saab kasutada järgmistel lehtedel:
- Kliendi kaart
  - Saaja aadressid
- Müügipakkumine
- Müügitellimus
- Müügiarve
- Hankija kaart
  - Tellimuse aadressid
- Asukoha kaart
- Kontakti kaart
  - Kontakti lisa aadressi kaart
- Töötaja kaart
  - Töötaja lisa aadressi kaart 
- Hooldustellimus
- Hoolduspakkumine
- Ressursi kaart
  
  
---

Täpsema info saamiseks, palun võtke ühendust DIGMATIX-ga:  
<a href="https://www.digmatix.com/ee/kontaktid" target="_blank">https://www.digmatix.com/ee/kontaktid</a>
