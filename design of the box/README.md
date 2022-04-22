# Design of the box itself

Design af selve kassen, som indeholder Belaboard'et og PD koden, og som skal fremme tydeligheden og forståelsen af interaktionen - hvordan timeshuffleren virker og skal bruges.

Med andre ord <em>den fysiske del af interaktionen</em>

## Kassens UI

### Den nutidige momentary switch

<em>Formål</Em> <p>
At give opleveren en mulighed for at forstå maskinens output og fremstilling af det omkringliggende nære lydmiljø. At maskinen rent faktisk optager og på forskellig vis reproducerer og processerer dette lydmiljø.

<em>Form og funktion</em> <p>
En momentary switch der tænder og slukker for processering er det presente lydmiljø. <p>
  
Derudover giver denne switch også opleveren en <em>aktiv interaktiv rolle</em> - knappen skal holdes inde for at fortsætte processeringen af det nutidige lydmiljø. Hvis knappen bliver sluppet vender maskinen tilbage til at shuffle i tiden.

### Timeslider - en fader hvor man kan slide rundt i datidens lyd
  <em>Formål</Em> <p>
At give opleveren mulighed for at styre hvor i datidens lydmiljø man er. Man kan via slideren finde et specifikt tidspunkt fra tidligere som man gerne vil genbesøge, det kan både være en anden tid og et andet sted (hvis maskinen var et andet sted på det givne tidspunkt. Altså er formålet med slideren at give opleveren den drømmende og skiftende fornemmelse af tid og sted.
    
<em>Form og funktion</em> <p>
Bufferens samlede længde skal være 300sek. og timeslider-fader'en skal have 10 stepped values som den skifter imellem. Disse 10 steps indeholder en 30sek. buffer fra et specifikt tidspunkt i den 300sek. lange buffer. <p>
Fader'en er en toggle fader - altså forbliver dens nuværende position indtil den aktivt bliver ændret igen.

## Form
Kassens udformning bliver simpel, hvor det vigtigste fokus ligger i at den kan holdes i ens hænder. Via. sine tommelfingre kan man styre hhv. switch'en, og timeslider fader'en så ergonomisk som muligt.
