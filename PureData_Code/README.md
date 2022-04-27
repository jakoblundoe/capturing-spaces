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
__Analyserende redskaber__
Eksempelvis envelope following, realtime buffering og amplitude og -frekvensanalyse.<p>

__Lydprocesserende redskaber__
Også kaldet Forskellige effekter som reverb, delay, pitchshifting, compression/limiting og div. generative koncepter.

### Loudness_control
Skal bruges til at styre volume på det optagede og gengivede lydmiljø. Noget lyd kan være højt og noget andet kan være lavt i amplituden, og jeg vil så vidt muligt sørge for at alt lyd er ligeligt i deres tydelighed. Det kræver en form for limiter/compressor som kan skrue ned og op afhængigt af den optagede amplitude

### Abstractions_loudness-adjust

__Compressor__


Overgang Hvordan skal overgang mellem det presente og det fortidige lydmiljø repræsenteres - repræsentation skal ske i skiftet af rum - rummet repræsentere tiden vi er i(de to stadier) og overgang skal på bedst mulig vis repræsentere disse rum.

En stærk / tydelig kommunikation af det datidige lydmiljø kan ved brug af reverb og delay processering. —->(det repræsenterer datid - som er noget man mindes - det drømmende - det fjerne(fjern fortid)) super sanselige vigtige keywords.
