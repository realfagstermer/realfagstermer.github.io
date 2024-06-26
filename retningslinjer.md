---
layout: default.nb
title: Retningslinjer
---

# Retningslinjer for indeksering

*Sist oppdatert 3. april 2017*

## Innledning

Formålet med emneordsindekseringen er å beskrive dokumentene slik at gjenfinningen blir mest mulig *presis* og *fullstendig*: Det relevante blir funnet, det ikke-relevante blir utelatt. Emneordene brukes først og fremst til søking, men er også nyttige for å vurdere dokumentets relevans uten å ha det i hånda.

Disse retningslinjene følger [Humords indekseringsregler](http://bibsys.no/files/pdf/handbok/humord_indekseringsregler_handbok.pdf) så langt det er mulig. Regler og eksempler er hentet derfra der det er relevant. Eksemplene er kodet med MARC 21. For ordforklaringer, *se [ordliste](ordliste.html)*.

:warning: Vi bruker programmet [Roald](http://folk.uio.no/knuthe/progdist/) for indeksering.
Emneord skal aldri skrives inn manuelt, men limes inn fra Roald. Dette er fordi selv
det mest pertentlige menneske ikke kan garantere 100 % enhetlig skrivemåte. Innliming sikrer også
at termene legges i korrekt felt,
og at emneordskilden (Realfagstermer) registreres korrekt som `$2 noubomn`.

:bulb: Årsaken til at vi benytter metoden *innliming* skyldes at Alma ikke per i dag tilbyr tilfredsstillende *funksjonalitet*.
Etter overgangen til Alma prøver vi ut direkteredigering fra Roald,
men det gjenstår foreløpig å utvikle arbeidsflyten for indeksering i nytt biblioteksystem.

## Indekseringsnivå

Den bibliografiske beskrivelsen vår foregår normalt på dokumentnivå. Det bør derfor ikke dypindekseres på kapittelnivå, unntatt i spesielle tilfeller. Med dette menes at emneord og klassifikasjonskoder skal gi en dekkende beskrivelse av dokumentets generelle emneinnhold, ikke av innholdet i enkeltkapitlene. Vi følger [retningslinjer for emnefelter](http://www.bibsys.no/files/out/pdf/handbok/emnefelter_handbok.pdf) utviklet av Marit Almo i samarbeid med Referansegruppe for BIBSYS EMNE.

*Unntak*: Det kan gjøres unntak i tilfeller hvor det er behov for å fremheve en spesiell artikkel, for eksempel et kapittel i en bok, eller der et etterspurt tema som ellers kan være vanskelig å finne, er behandlet. 

## Spesifisitet

Emneordene skal gi en dekkende beskrivelse av det dokumentet spesielt handler om. Som hovedregel skal det ikke tildeles overordnede emneord. Hvis man bruker overordnede emneord også for bøker om spesielle emner, vil det føre til en opphopning av litteratur på de generelle emneordene.

*Eksempler:*

* En bok om solur får emneordet [Solur](http://data.ub.uio.no/realfagstermer/c008719),
  ikke [Fysikk](http://data.ub.uio.no/realfagstermer/c003067).
* En bok om spekkhoggere får emneord [Spekkhoggere](http://data.ub.uio.no/realfagstermer/c010898),
  ikke [Hvaler](http://data.ub.uio.no/realfagstermer/c005007).
* En bok om bartrær får emneordet [Bartrær](http://data.ub.uio.no/realfagstermer/c001526),
  ikke [Trær](http://data.ub.uio.no/realfagstermer/c000468).
* En bok om Blankvann får emneordet [Blankvann](http://data.ub.uio.no/realfagstermer/c030657),
  ikke [Oslo](http://data.ub.uio.no/realfagstermer/c030208).

*Unntak:*

* Ved spesielle og ukjente stedsnavn kan det være hensiktsmessig å gi en term for et større geografisk område i tillegg til stedsnavnet.

## Faglig og formelt omfang

Realfagstermer er laget med utgangspunkt i samlingene i bibliotekene som utgjorde det Matematisk-naturvitenskapelige fakultetsbibliotek. Realfagsbibliotekets samlinger beskrives med Realfagstermer, som oppdateres etter behov. Forslag til nye emneord, eller endringer i gamle, registreres [på GitHub](https://github.com/realfagstermer/realfagstermer/issues).

Realfagstermer skal ikke inneholde [korporasjonsnavn](ordliste.html#korporasjon) eller navn på historiske personer. Slike navn normeres etter katalogiseringsreglene, og registreres obligatorisk i andre MARC-felt. Fagreferentene må gi beskjed til katalogisator i disse tilfellene.

*Merk*: Per juni 2016 har vi fremdeles en del korporasjonsnavn igjen. Det er en langsiktig oppgave å rydde ut alle.

## Fasetter og strenger

Begreper i Realfagstermer er delt inn i fire *fasetter* (ikke-bibliotekarer: tenk kategorier):
emner, steder, tider og former. Hvert begrep hører til én og bare én fasett.

Begrepene i Realfagstermer kan dessuten kombineres (koordineres) for å gi strenger. Strenger
bygges i indekseringsprosessen, men lagres i autoritetsdataene så de kan brukes for gjenfinning.

:warning: Merk:

* I de bibliografiske postene registreres kun én type strenger, nemlig `Emneterm : Underemneterm`.
  Sted-, tid- og formtermer lagres i egne marcfelt.
* I autoritetspostene lagres i tillegg strenger som inneholder stedtermer, tidtermer og formtermer.
  Disse presenteres blant annet i [Emnesøk](https://app.uio.no/ub/emnesok/realfagstermer/).

Termene registreres altså i de bibliografiske postene som frittstående emneord for
postkoordinert gjenfinning, med unntak av emnetermer som kan registreres som `Hovedemne : Underordnet emne`:

```
650 $a Emneterm $x Underemneterm $2 noubomn
648 $a Tidterm $2 noubomn
651 $a Stedterm $2 noubomn
655 $a Formterm $2 noubomn
```

### Fasett: Emne

Inneholder **innholdsbeskrivende emneord** (eng. *topical subject headings*). «Emneord som tilhører denne typen, kan benyttes som eneste emneord for et dokument. (…) De fleste emneord vil falle inn under denne kategorien.»[^1]

Termene skal beskrive dokumentets innhold, hva dokumentet handler om. Der det er lik skrivemåte for flere termer, er det lagt til en kvalifikator (forklarende parentes). De registreres i marcfelt 687.

*Eksempler:*

* `650 $a Akustiske bølger`
* `650 $a Fugler`
* `650 $a Kopper (grunnstoff)`
* `650 $a Kopper (sykdom)`
* `650 $a Kart`

Du kan velge å legge inn et underemne i `$x` som avgrenser hovedemnet. *Eksempler*:

* `650 $a Amfibier $x Reproduksjon` (ikke: Amfibiereproduksjon)
* `650 $a Fugler $x Taksonomi` (ikke: Fugletaksonomi)

Ofte vil underinndeling/avgrensing av hovedemnet ved hjelp av `$x` gjøres ved hjelp av ord med så generell betydning at det gir liten mening hvis det står alene. Det kalles innholdsbeskrivende emneord av allmenn karakter[^1]. Eks: 
`Regulering`, `Påvirkning`, `Reaksjoner`. *Eksempler*:

* `Metabolisme : Regulering`
* `Angiospermer : Utvikling`

#### Siteringsorden  i  streng

Siteringsorden mellom leddene er:

1. Innholdsbeskrivende emneord
2. Innholdsbeskrivende emneord av allmenn karakter

Dersom begge leddene tilhører samme kategori, følges siteringsorden etter Ranganathan.  Redaksjonen følger opp dette.
Før du lager en streng, vurdér om det er et sammensatt ord eller uttrykk som kan brukes.  Ordet bør være (eller høres ut som det er) godt innarbeidet i norsk språkbruk: 

* `Hundeavl` (ikke: `Hunder : Avl`)
* `Molekylmodellering` (ikke: `Molekyler : Modellering`)

### Fasett: Form/sjanger 

Dette er ikke en emnefasett. Form brukes til å beskrive hvilken form eller sjanger et dokument er (for eksempel et atlas, eller en science fiction-roman).

:warning: Må ikke forveksles med at et dokument handler *om* en form eller sjanger (for eksempel en bok om kart, eller om science fiction).

Form/sjangertermer registreres i marcfelt 655. Hvis du får spørsmål om formtermen skal ha rolle som form eller emne, er det form som er riktig svar i dette tilfellet. Se også Bruksanvisning for Roald II ==LENKE!==.

### Fasett: Tid

Tidsperioder eller historiske epoker. `1700-tallet` og `Etterkrigstiden` er eksempler på det som finnes her.

:warning: Vær oppmerksom på at emneord som betegner geologiske tidsavsnitt, eller historiske hendelser avgrenset i tid, ikke finnes her, men i den vanlige emneordlista. (Eksempler på disse er Jura, Kvartær, Andre verdenskrig.)

Tidtermer registreres i marcfelt 648. Noen vil legge merke til at tidtermen dubleres i marcfelt 687. Dette er en midlertidig ordning som er nødvendig av systemtekniske grunner.

Tidtermer kan opptre i streng som avgrensing av et annet emne. *Eksempel* fra `The quest for the invisible : microscopy in the Enlightenment`:

```
650 $a Mikroskopi
648 $a Opplysningstiden
```

I emnesøk og Roald vil strengen `Mikroskopi : Opplysningstiden` vises.

### Fasett: Sted

Stedsnavn. Her inkluderes navn på planeter, geologiske områder, nasjonalparker, vulkaner og lignende. 
Emneord som betegner geografiske steder registreres i marcfelt 651. 

Vanligvis vil en stedterm være en avgrensing av et annet emne.

* Eksempel: Strengen `Vegetasjonskartlegging : Norge` er registrert på dokumentet `Truete vegetasjonstyper i Norge` som:

    ```
    650 $a Vegetasjonskartlegging
    651 $a Norge
    ```
  
Dersom det geografiske området er behandlet generelt i en bestemt form eller sjanger, eller avgrenset til en bestemt tidsperiode eller historisk epoke, får vi strenger som innledes med stedtermen.

* Strengen `Grønland : 1800-tallet : Historie` er registrert på dokumentet `Grønland på 1800-tallet` som:

    ```
    651 $a Grønland 
    655 $a Historie
    648 $a 1800-tallet
    ```

* Strengen `Norge : Atlas` er registrert på dokumentet `Store Norgesatlas` som:

    ```
    651 $a Norge
    655 $a Atlas
    ```

* Strengene `Norge : Historie` og `Geografi : Norge` er registrert på dokumentet `Norge` som:
 
    ```
    650 $a Geografi
    651 $a Norge 
    655 $a Historie 
    ```


## Spesielle emner

### Biografier/omtalte personer og sekundærlitteratur 

* *Omtalt person* registreres i `600 $a` (Emneinnførsel personnavn) med navneform
  fra personautoritetsregisteret. *Eksempel* fra
  [Schrödinger's kittens and the search for reality](http://katapi.biblionaut.net/documents/show/952397994):

    ```
    600 $a Schrödinger, Erwin
    ```

    der «Schrödinger, Erwin» er den foretrukne navneformen [i personautoritetsregisteret](http://hdl.handle.net/11250.1/36091498).

 * *Omtalt verk* registreres i marcfelt `600 $t`. *Eksempel* fra
   [The Principia : mathematical principles of natural philosophy](http://katapi.biblionaut.net/documents/show/990335577):

        ```
        600 $a Newton, Isaac $t Principia
        ```

        Merk at vi fremdeles bruker `600 Emneinnførsel personnavn`.
        ==Når kan vi bruke `630 Emneinnførsel standardtittel`?==

* For biografier registreres formtermen [Biografier](http://data.ub.uio.no/realfagstermer/c030117). *Eksempler*:

 * [Kristine Bonnevie : et forskerliv](http://katapi.biblionaut.net/documents/show/121695743) :
   Her registreres *omtalt person* (600) fra personautoritetsregisteret, og form/sjanger (655)
   fra Realfagstermer:

        ```
        600 $a Bonnevie, Kristine $d 1872-1948
        655 $a Biografier $2 no-ubo-mn
        ```

 * [Charles Darwin’s The origin of species : new interdisciplinary essays](http://katapi.biblionaut.net/documents/show/120023849): Her registreres *omtalt person (600) fra personautoritetsregisteret. Boken faller ikke inn under
 noen kjent form/sjanger i Realfagstermer, så 655 registreres ikke.

        ```
        600 $a Darwin, Charles $d 1809-1882 $t On the origin of species
        ```

### Ordbøker

Alle ordbøker får formtermen [Ordbøker](http://data.ub.uio.no/realfagstermer/c030101)
i tillegg til emneterm for kildespråk. Term for målspråk registreres som underemneterm.
*Eksempler*:

* [Nynorskordboka](http://katapi.biblionaut.net/documents/show/061377104):
    ```
    650 $a Nynorsk
    655 $a Ordbøker
    ```

    (tilsvarer strengen: `Nynorsk : Ordbøker`)

* Tysk-norsk ordbok

    ```
    650 $a Tysk språk $x Norsk språk
    655 $a Ordbøker
    ```

    (tilsvarer strengen `Tysk språk : Norsk språk : Ordbøker`)

* Arabisk-norsk-engelsk ordbok

    ```
    650 $a Arabisk språk $x Norsk språk
    650 $a Arabisk språk $x Engelsk språk
    655 $a Ordbøker
    ```

    (tilsvarer strengene `Arabisk språk : Norsk språk : Ordbøker` og
    `Arabisk språk : Engelsk språk : Ordbøker`.

* Fagordbøker får i tillegg term for fagområde, og formtermen
  [Terminologi](http://data.ub.uio.no/realfagstermer/c030165) hvis den er relevant. Eksempel fra

 * [Norsk geologisk ordbok](https://okapi.biblionaut.net/documents/54c7ac911e02e5d02d9d5ab5)

    ```
    650 $a Geologi
    655 $a Ordbøker
    ```

    (tilsv. strengen `Geologi : Ordbøker`
    

 * [Norsk-engelsk teknisk ordbok](https://okapi.biblionaut.net/documents/54c7d41f1e02e5d02dab5921)

    ```
    650 $a Teknikk
    650 $a Norsk språk $x Engelsk språk
    655 $a Ordbøker
    655 $a Terminologi
    ```

    (tilsv. strengene `Teknikk : Terminologi`, `Teknikk : Ordbøker` og ` Norsk språk : Engelsk språk : Ordbøker`)


** Ekstra **

*Eksempler:*

* Strengen `Fugler : Antikken` registreres som 

    ```
    650 $a Fugler
    648 $a Antikken
    ```

* Strengen `Fugler : Bestemmelseslitteratur` registreres som  

    ```
    650 $a Fugler
    655 $a Bestemmelseslitteratur
    ```

* Strengen `Fugler : Costa Rica` registreres som

    ```
    650 $a Fugler
    651 $b Costa Rica
    ```

* Strengen `Fugler : Taksonomi` registreres som

    ```
    650 $a Fugler $x Taksonomi
    ```

* Felt registreres bare én gang selv om de benyttes i
  flere strenger. Om alle de fire ovenstående strengene
  skulle registreres på samme dokument, ville
  `650 $a Fugler` fremdeles bare registreres én gang:

    ```
    650 $a Fugler $x Taksonomi
    650 $a Fugler 
    648 $a Antikken
    651 $a Costa Rica
    655 $a Bestemmelseslitteratur
    ```

## Noter

Til noen av termene finnes det interne noter som gir
anvisning for bruk av termen.

## Nynorsk: Kunnskapsoverføring fra nynorskprosjektet

(fra epost fra Verbjørn 29. oktober 2016)

Nokre forsøksvis korte punkt om utfordringar/val undervegs:

– Nettopp fordi det er snakk om til dels ganske fagspesifikke termar, er det ein heil del av dei som ikkje er å finna i andre ordbøker. Det inneber at me har måtta leita i andre kjelder for å finna eller få stadfest kva som er etablerte nynorsktermar for ulike omgrep. I den samanhengen har særleg det nynorske tekstkorpuset (http://no2014.uio.no/korpuset/), Wikipedia og ikkje minst ymse nynorskutgåver av gamle lærebøker på Nasjonalbiblioteket sine nettsider kome til nytte. I nokre få tilfelle har me òg snubla over omgrep som tilsynelatande ikkje har hatt nokon etablert nynorskterm før no, slik at me har måtta omsetja etter beste evne.

– På nynorsk er der, som på bokmål (!), ein del valfridom i rettskrivinga. Men der folk flest™ ikkje kjenner so godt til at mange ord kan skrivast/bøyast på ulike måtar på bokmål, er det full fest på nynorsk, noko som gjer det lite tenleg å utelukka den eine eller andre stave-/bøyingsforma. Me har difor freista ha med (innanfor rimelege grenser) alle normerte former av same termen (med ei av dei som «primærform» og resten som alternative former), slik at folk skal få opp rett søkjetreff sjølv om dei søkjer med t.d. hankjønnsbøying av ein term som òg kan vera hokjønn. Dette er ikkje minst viktig fordi det ikkje lenger finst noko formelt skilje mellom hovud- og klammeformer i rettskrivinga, slik det gjorde før.

So skulle eg sjølvsagt gjerne ha vore meir konkret, både når det gjeld døme på kva former me har måtta leita oss fram til, kva me har måtta koma opp med sjølve, og kva for nokre former som har fått stå øvst (i feit skrift, som primærform) – men eg får av ein eller annan grunn berre feilmelding når eg prøver å logga meg inn i på trans.biblionaut.net, so eg har ikkje høve til å søkja opp gode døme … Det eg veit, er at Maria har nytta nynorskkorpuset som referanse for kva former som er mest i bruk, og at desse so (i alle fall i eit visst omfang) har fått forrang.

Men for å prøva å gje ei enkel oppskrift på korleis de kan få nye termar til å samsvara språkleg med dei som ligg inne frå før: Bruk søkjefunksjonen og leit opp liknande termar. Då kan de sjå kva slags former som har fått vera den øvste/primære forma i andre termar som inneheld det same ordet/elementet.

Til dømes vil de ved å søkja opp alle termar som inneheld «bylgje», sjå om det er bylgje, bølgje eller bølge som har fått vera den øvste/primære forma. På same vis vil de kunna finna ut av kva for eit grammatisk kjønn som er «føretrekt» for tvikjønna ord (søk opp alle ord som sluttar på -planter/-plantar for å sjå om det er han- eller hokjønnsbøyinga som har fått forrang i andre termar som sluttar på -planter/-plantar).

Normalt ville eg ha laga ei sokalla språkliste, altso eit oversyn over kva former som er valde. Det trur eg ikkje eg gjorde i dette tilfellet (i so fall er eg ikkje kar om å finna att lista …), dels for å spara arbeidstid, og dels fordi det nok har vore enklare reint praktisk å berre søkja opp tilsvarande ord etter kvart som eg kom over noko eg var usikker på. Sidan mykje av arbeidet vart gjort i ein relativt avgrensa periode, hadde eg nok òg mykje av det langt framme i korttidsminnet då eg sat og arbeidde med det.

Det me derimot har, er nokre små notat Maria kladda ned undervegs i arbeidet, som kan vera nyttig for dykk når de vert usikre på kva kjønn ulike ord skal ha:

(n1=inkjekjønn, m1=hankjønn)

* n1: -id -on -at -eder -som (-osom)
* m1: -ase -ant
* Variable: -in -an
 
* I biologien: -ida/-idae (t.d. priapulida) vert bøygd som m1
* I fysikken: -on (t.d. foton, tachyon, boson, osb.) vert bøygd som n1
 

## Referanser
**Fotnoter:**

[^1]: Hjortsæter, E. Emneordskatalogisering: innholdsanalyse, emnerepresentasjon og lagring. 2005, Oslo: Høgskolen i Oslo, Avdeling journalistikk, bibliotek- og informasjonsfag, s. 73-74.

