---
layout: default.nb
title: Retningslinjer
---

# Retningslinjer for indeksering

*Sist oppdatert 19. desember 2014*

## Innledning

Formålet med emneordsindekseringen er å beskrive dokumentene slik at gjenfinningen blir mest mulig *presis* og *fullstendig*: Det relevante blir funnet, det ikke-relevante blir utelatt. Emneordene brukes først og fremst til søking, men er også nyttige for å vurdere dokumentets relevans uten å ha det i hånda.

Disse retningslinjene følger [Humords indekseringsregler](http://bibsys.no/files/pdf/handbok/humord_indekseringsregler_handbok.pdf) så langt det er mulig. Regler og eksempler er hentet derfra der det er relevant. For ordforklaringer, *se [ordliste](ordliste.html)*.

:warning: Vi bruker programmet [Roald](http://folk.uio.no/knuthe/progdist/) for indeksering.
Emneord skal aldri skrives inn manuelt, men limes inn fra Roald. Dette er fordi selv
det mest pertentlige menneske ikke kan garantere 100 % enhetlig skrivemåte. Innliming sikrer også
at termene legges i korrekt felt,
og at emneordskilden (Realfagstermer) registreres korrekt som `$2 noubomn`.

:bulb: Årsaken til at vi benytter metoden *innliming* skyldes at Bibsys ikke per i dag tilbyr et tilfredsstillende *programmeringsgrensesnitt*.
Ved overgangen til Alma antar vi at mulighetene for direkteredigering fra Roald vil være tilstede,
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


**Fotnoter:**

[^1]: Hjortsæter, E. Emneordskatalogisering: innholdsanalyse, emnerepresentasjon og lagring. 2005, Oslo: Høgskolen i Oslo, Avdeling journalistikk, bibliotek- og informasjonsfag, s. 73-74.

