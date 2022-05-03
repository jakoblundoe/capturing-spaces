# kode - PureData

Jeg vil bruge Pure Data til at designe lydprocesseringen - som til sidst i processen skal implementeres på et Bela Board der udgør hjertet af lyttemaskinen.

## Lyddesign - overordnede mål
Med drømme bevæger vi os flydende mellem tid og rum og det er denne fornemmelse/sansning jeg gerne vil fremme med min lyttemaskine - i størst grad med den datidige repræsentation af lydmiljøerne.

Udfra dette perskeptiv (at tid og sted er blevet manipuleret med) vil jeg gøre brug af effekter som ændrer på rummets karakter. Reverb, delay og chorus/detuning samt simpel stretch(ikke paulxstretch) vil ligge et godt fundament for et tydeligt <em>fjernt (drømmende) rum </em>.

## Kodens struktur

For at organisere min kode bedst muligt vil jeg gøre brug af PD's abstraction-feature. En eller flere abstractions udgør en specifik funktion i main-koden. Alle funktioner og abstractions er listet i en <em>prioriteret rækkefølge</em> alt efter hvad jeg finder vigtigst at få færdigt først.<p>
Dette gør jeg for at vide mig sikker på at jeg har et fungerende produkt til deadline, også selvom nogle tænkte funktioner ikke når at blive implementeret.

## Funktioner
Overordnet set kan mine funktioner deles op i to kategorier som er:<p>
__Analyserende redskaber__<p>
Eksempelvis envelope following, realtime buffering og amplitude og frekvens-analyse.<p>
__Lydprocesserende redskaber__<p>
I.e. lydeffekter som eksempelvis reverb, delay, pitchshifting, compression/limiting og div. generative koncepter.
<br />
<br />

### Loudness_control
Skal bruges til at styre volume på det optagede og gengivede lydmiljø. Noget lyd kan være højt og noget andet kan være lavt i amplituden, og jeg vil så vidt muligt sørge for at alt lyd er ligeligt i deres tydelighed. Det kræver en form for limiter/compressor som kan skrue ned og op afhængigt af den optagede amplitude

__ABSTRACTIONS__

<em>__Compressor__</em>
<br />
<br />

### realtime_samplebuffer
Skal bruges til at optage og gemmme lyd i en samplebuffer med en længde på 150sekunder. Når bufferen er aktiv skal den afspille lyd fra de sidste 150sekunder - med en step-inddeling i perioder af 30sekunder.<p>Disse 'afspilningsperioder' bliver valgt af timeslideren.<p>

__ABSTRACTIONS__

<em>__micInputSystem__</em><p>
<em>__changeBufferSequencer__</em><p>
<em>__liveBufferingToolStereo__</em><p>
<br />
<br />

### timeSlideParam_fader
Valg af afspilningsperiode i bufferen er styret af denne timeSlideParam_fader. Udover at sætte afspilningsperioden afgiver den også en lyd(fungerer som auditiv feedback til brugeren).<p>
Da de individuelle buffer's ikke repræsenterer en specifik tidsperiode er det nødvendigt at skabe en 'imaginær buffer' som repræsenterer tiden frem for selve buffer~-objektet. Dette vil jeg gøre ved at lave en abstraction som cirkulært sekvenserer rækkefølgen af alle buffer's, kaldet 'circularSequencer'.<p>

__ABSTRACTIONS__<p>

<em>__timeScrollParam__</em><p>
<em>__auditiveFeedbackDelay__</em><p>
<em>__scrollAmplitudeParam__</em><p>
<em>__circularSequencer__</em><p>
<br />
<br />

### on/off_toggle
Hvis ikke on/off timer kan nås, er en toggle-switch til at tænde og slukke for lyden en mulighed. <p>
Igen gerne med et sample til at give auditiv feedback - 'wooosh'.
<br />
<br />

### createRandomValues
Dette er det grundlæggende fundament for den generative maskine.<p>

#### SoundSnippetPicker
Indenfor den valgte tidsperiode i bufferen skal denne 'soundpicker' vælge et tilfældigt sted at afspille fra.<p>

#### pitchShiftParam
Pitchshifting kan forekomme med en tilfældig afspilningshastighed.<p>

#### delayShiftParam
Delay kan forekomme med tilfældige værdier - feedback,, delaytime og amplitude.<p>
<br />
<br />

### Reverb_effektering
Generel effekt. Sidst i kæden. Skal medvirke til ens fornemmelse af et drømmende univers.
<br />
<br />

### Knitren
Generel effekt. Kan være et sample eller en granularsynth. Skal medvirke til ens fornemmelse af et drømmende univers.
<br />
<br />

### drone_vibe
Ekstra lydlig effekt til at skabe en stemning. Skal fungere som en slags 'underlægningslyd' til det drømmende univers.<P>
<em>__ambiPlusScrollFeed__</em><p>
<em>extra notes: the auditiveFeedbackDelay abstraction is included here. The 'ambiPlusScrollFeed' is created as a subpatcher instead of an abstraction due to the loading architecture which has been set for the project</em><p>
<br />
<br />

### on/off_timer
Maskinen skal tænde for lyden af sig selv ved interaktion med momentary switch eller fader-knappen. <p>
Gerne med et sample til at give auditiv feedback - 'wooosh'.
<br />
<br />

### nutidDatidTransition
Overgang mellem den nutidige og datidige lyd.
Gerne med en fastforward/rewind effekt i dobbelt hastighed.<p>
Overgang fra:<p>
datidige til nutidige --> fastforward<p>
nutidige til datidige --> rewind<p>

__ABSTRACTIONS__<p>
<em>__bufferFastforward__</em><p>
<em>__bufferRewind__</em><p>

<em>Ekstra noter:<p>
Hvordan skal overgang mellem det presente og det fortidige lydmiljø repræsenteres - repræsentation skal ske i skiftet af rum - rummet repræsentere tiden vi er i(de to stadier) og overgang skal på bedst mulig vis repræsentere disse rum.<p>
En stærk / tydelig kommunikation af det datidige lydmiljø kan ved brug af reverb og delay processering. —->(det repræsenterer datid - som er noget man mindes - det drømmende - det fjerne(fjern fortid)) super sanselige vigtige keywords.</em>

