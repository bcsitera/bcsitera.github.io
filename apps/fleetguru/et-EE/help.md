# FleetGuru - Kasutusjuhend
FleetGuru sõidukipargi haldus lahendus Microsoft Dynamics 365 Business Central tarbeks.
  
Kui teil on äri, kus peate haldama sõidukeid FleetGuru tarkvaras, siis antud lahendus võimaldab saata FleetGuru portaali sõiduki kuludega seonduvaid pearaamatukandeid.

## Sisukord

- [Seadistused](#seadistused)
- [Pearaamatukannete saatmine](#pearaamatukannete-saatmine)

## Seadistused

### Ühendus

Lehel _FleetGuru seadistus_ peate täitma väljad "API URL" ja "API võti", et luua ühendus oma FleetGuru sõidukipargi haldusrakendusega.    

### Dimensioonid

Lehel _FleetGuru seadistus_ peate määrama, milline _Dimensioon_ vastab teil just sõiduki dimensioonile. Vajadusel saab sõidukipargi haldusrakendusele saata ka osakonna ja isiku dimensioonid. 

Kui täidate esimest korda välja „Sõiduki dimensioon, avaneb hüpikaken, kus küsitakse, kas soovite märkida kõik valitud _Dimensiooni Dimensiooniväärtused_ FleetGuru haldusrakendusse saatmisele. 

„Sõiduki dimensiooni” väljal valitud _Dimesnioonile_ lisatakse _Dimensiooniväärtuste_ lehele kaks uut välja. „Saada FleetGuru-sse” – määrab, kas seda _Dimensiooniväärtust_ sisaldavad PR kanded saadetakse FleetGuru-sse või mitte. „Sõiduki reg. nr.” – tuleb täita juhul, kui _Dimensiooniväärtuse tähis_ ei ole sõiduki registreerimisnumber.

### Kulud

Väljal „Kulude PR konto filter” saate määrata, millised _PR kontod_ sisaldavad sõidukikuludega seotud pearaamatukandeid. „Viimane saadetud PR kande nr.” on nö järjehoidja, mis talletab viimast FleetGuru-sse saadetud PR kande. Kui see väli on tühi, pole vaja muretseda – PR kandeid ei saadeta kaks korda. Juba saadetud kirjete kontrollimine võtab lihtsalt rohkem aega ja võib mõjutada jõudlust. 

Kui valik „Saada arve PDF” on märgitud, saadetakse FleetGuru-sse ka PDF manused, mis on _Arve kulukannetel_ salvestatud _Sissetulevate dokumendi failide_ alla.

## Pearaamatukannete saatmine

Võite saata sõiduki kulude PR kanded FleetGuru-sse käsitsi lehel _FleetGuru seadistus_ või luua _Tööjärjekorra kanded_, mis automatiseerivad PR kannete saatmise.

You can send the Vehicle Expense G/L Entries to FleetGuru manually on the _FleetGuru Setup_ page or create _Job Queue Entries_ that automate the sending of the G/L Entries.

## Kontaktinfo
Täpsema info saamiseks, palun võtke ühendust BCS Itera AS-ga:  
<a href="https://www.itera.ee/" target="_blank">www.itera.ee</a>