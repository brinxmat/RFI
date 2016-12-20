#RFI

#5.1 Overordnede prinsipper

##5.1.1 Gode muligheter for integrasjon med eksisterende og fremtidige systemer, herunder bruk av åpne standarder. Gjeldende og varslende integrasjoner, fagstandarder og protokoller må støttes fullt ut.

RFI-en responsen beskriver ikke et "biblioteksystem", men et økosystem for bibliotekstjenester.

Det som beskrives som ønskelig tilsvarer et modulært system bygd i forhold til dagens distribuerte, ikke-monolitiske arkitektur. En slik arkitektur tar seg av kommunikasjon mellom ulike moduler og gjør det mulig å utvikle og tilpasse eksisterende moduler smidig for hver kunde, uten at en opplever konflikter ved oppgraderinger. Det gjør det mulig å rulle ut ny funksjonalitet etter behov og sikrer at systemet til en hver tid er fremtidsdyktig.

Pr. skrivende stund er det kun ett levende system som er tilgjengelig som er et slikt økosystem, og det er systemet som er tatt i bruk hos Deichmanske bibliotek. Her er det moduler for det aller meste av biblioteksfunksjonalitet, samt en fremtidsrettet dataplattform som gjør det mulig å levere annet en de kjente MARC-deriverte datastrukturer som hemmer dagens systemer ellers. Økosystemet kan skaleres i det uendelig da det kan opptre både som felles og som distribuert system.

Dataplattformen er så smidig at den leverer data til MARC21 + RDA kilder, og disse kan da eksponeres til tjenester som Z39.50 og OAI-PMH, samt gjennom enkel direkte eksponering som linked data, enten dette er som 5-star linked data eller BIBFRAME, eller noe annet. Her finnes det svært få begrensninger, og lokale tilpasninger er alltid mulig gjennom standardteknikker som navnerom og navngitte grafer.

Systemet er API-basert. For å snakke med APIene kan bibliotekene enkelt lage eller få laget moduler som dekker deres ønsker i et hvilket som helst programmeringsspråk  — disse modulariseres og driftes så i økosystemet. Systemet kan driftes av bibliotekene, av Computas eller en annen leverandør. 

Kommunikasjon med eksterne API-er foregår via tjenestelag som abstraherer disse, slik at moduler internt i økosystemet bruker uniform/enhetlig kommunikasjon for samme funksjonalitet — det vil si at vi bruker, for eksempel, samme API-kall for interaksjon med eksterne finanssystemer selv om disse selv har ulike API-er. Dette gjør det mye lettere å utvikle moduler som berører finans og eventuelt bytte eksterne systemer.

Plattformen er utelukkende basert på åpne standarder og støtter nåværende standarder innenfor domenet; mangler det noe som ønskes er det fullt mulig å legge dette til. Der kommunikasjonen per API ikke er "standardisert" av en ekstern myndighet er dokumentasjon og all kildekode åpen og tilgjengelig. Bibliotekene kan (få hjelp til å) opprette sine egne utviklings- og testmiljø for økosystemet.

##5.1.2 Plattformuavhengighet. Publikum må fritt kunne velge hvilken type enhet de skal bruke biblioteksystemet fra, inklusive mobil, nettbrett og PC. Bibliotekene bør være mest mulig frie til å velge enheter som skal brukes av personalet.

Alle frontend som utvikles er automatisk testet for funksjonalitet, samt testet på de vanligste nettlesere på mobil, nettbrett og PC. Videre er alle grensesnitt mot eksterne brukere testet mot lovpålagte krav om universell utforming og støtter flerspråklighet; videre er testingen informert ved faktisk brukere av skjermlesere og andre assistive teknologier. Frontendene utvikles med brukerne og det er svært ønskelig at disse videreutvikles sammen med fokusgrupper fra kunden. Skal kunden eller en annen leverandør lage eller tilpasse moduler, er utviklingsteknikken som ivaretar alle disse punktene klart dokumentert og synlig gjennom modulærisering i modulene.

##5.1.3 Sentraldrift for å frigi lokale ressurser og sikre felles løsninger, utvikling og katalog. 

Løsningen driftes sentralt eller distribuert — ønskes en sentral løsning, er dette selvføgelig mulig. Ønskes en løsning driftet på "norsk jord" for å sikre brukernes personvern så er dette også mulig.

##5.1.4 Mulighet for tilpasninger, både sentrale og lokale. Det er viktig for bibliotekene å kunne innovere raskt med nye tjenester og muligheter og få disse integrert og tilpasset i et fremtidig system.

Det kan konfigueres, tilpasses og utvikles ulike frontend for de ulike bibliotekene og tjenestene som bruker dataplattformen og andre moduler i økosystemet. Fleksibiliteten medfører ikke store kostnader, og moderne utviklingsteknikker gjør det mulig å ha noe avvikende kodebaser som likevel deler mye av samme kode, og disse holdes synkronisert til enhver tid.

##5.1.5 Eierskap til data. Bibliotekene må ha fullt eierskap til egenutviklede metadata i systemet og enkelt kunne eksportere disse eller hente de ut via maskinlesbare API-er

Dataene eies av de som legger inn dataene — Computas kan gi råd om valg av lisens når plattformen brukes som fellesinstans og ved eventuell levering av data fra API-er mot eksterne tjenester. Gjeldende lover for data hentet fra eksterne kilder må tas i betraktning her, og igjen vi kan gi råd angående hva og hvordan bibliotekene forholder seg til slike.

##5.1.6 Tjenestene skal være digitale – helhetlige, brukervennlige og universelt utformet. Grensesnittet mot publikum må være brukertestet og sluttbrukerfunksjonalitet må baseres på publikums ønsker og behov. Publikum skal være mest mulig selvhjulpne i de ulike prosessene, samtidig som det må legges til rette for økt brukermedvirkning/interaksjon.

Tjenestene utvikles etter behov og utformes etter bibliotekenes ønsker.

##5.1.7 Skalerbar arkitektur. Systemet må kunne skaleres opp til sentralisert drift for langt flere bibliotek og større samlinger.

Økosystemet er utviklet med skalerbarhet som en grunnleggende prinsipp.

##5.1.8 Modulær arkitektur. Må være mulig å endre eller bytte ut moduler av systemet etter behov.

Økosystemet er utviklet med dette som en grunnleggende prinsipp.

##5.1.9 Sluttbrukergrensesnittet for publikum må ha støtte for flerspråklig systemdialog samt mulighet for å bygge ut med flere språk ved behov.

Økosystemet er utviklet med dette som en grunnleggende prinsipp.

#5.2 Innspill fra leverandør

#5.2.1 Integrasjoner/teknologi/arkitektur

##5.2.1.1 Hvilken utvikling ser vi for oss de neste 5 - 10 årene? Vil en stor økning i digitale filer framskynde overgangen fra MARC til RDF?

Økosystemet vi leverer til Deichman er allerede linked-data-basert og er klar til å levere dagens og kommende standarder.

Utviklingen hos de fleste leverandører blir preget av stadig økende sentralisering og forenkling av tilbud; stadig mer funksjonalitet tilbys som ferdige pakker og det gis store løfter med hensyn til integrasjon med eksterne systemer. Systemene vi ser i dag blir nok det samme de kommende årene — også de som nyutvikles følger samme mønster; MARC-orienterte dataplattformer som fungerer likt med systemene vi har nå kjent i tjue år.

Overgangen fra MARC blir neppe relevant for de fleste leverandører — MARC er en sentral del av bibliotekenes delingskultur og flere arbeidsflyttilfeller er avhengig av data på dette formatet. Da holder det å kunne levere oversettelser til BIBFRAME og andre formater, for å kunne si at en driver med linked data og BIBFRAME. Nytten av slike tiltak er noe som er ennå ukjent, men kan sammenlignes med dagens eksport av MARC data til andre formater.

Kravene til linked data innebærer også at identifikatorene er URI-er. Vi kommer til å se at systemleverandører åpner for at bibliotekene legger lenker inn i spesielle felt i MARC-data, og at disse lenkene tolkes som URI-er når de brukes i frontend. Dette er et tiltak bibliotekene har brukt over lengre tid for å bringe inn litt av det gode, men det er ikke fullt ut linked data siden URI-en fortsatt kun er en tekststreng som må tolkes og systemene som gjør slike tiltak ikke kjenner/støtter linked data, bare tekststrenger.

##5.2.1.2 Bør man fortsatt basere seg på MARC-formatet i bunn, eller bør man katalogisere etter RDA/RDF med mulighet for MARC-konvertering?

Inntil bibliotekene finner en fullverdig erstatning, bør MARC eksistere for oppgaven den er tiltenkt — som utvekslingsformat. Datamodellen i systemet bør imidlertid bidra til at man kan levere dataene som trengs for å skape moderne tjenester, ikke bare det én bestemt standard sier. At bibliotekene har brukt MARC som fysisk modell for sine data og til dels som arbeidsflyten for katalogisering har sinket systemutviklingen siden 1980-tallet.

Sådan bruker økosystemet en katalogiseringsklient som danner en arbeidsflyt som katalogisatorer nok i grove trekk kan gjenkjenne. Hvordan dataene er strukturert i plattformen er noe de ikke behøver å håndtere direkte — i motsetning til de fleste andre systemene. Denne abstraksjonen gjør det mulig å konsentrere seg om relasjoner mellom entiteter, ikke tegnsetting.

Som beskrevet over, leverer økosystemet også MARC21, og dette brukes da til ILL og statistikk, samt noen få biblioteksoppgaver som krever MARC-poster. Det betyr også at en kan lett migrere av platformen til et annet system som bruker MARC — om dette er NORMARC eller noe annet. Hvis ønskelig kan MARC21 også støtte RDA i større grad, men dette er igjen et valg bibliotekene må ta.

##5.2.1.3 Hvilke muligheter vil åpne seg med RFID-teknologi? NFC? UHF?

Mulighetene med RFID/NFC/UHF er mange, og økosystemet har ingen problemer med å integrere med dem. De kommende årene kommer vi nok til å se spennende og tidsbesparende mobilapplikasjoner som kan brukes til interne og sluttbrukertjenester. Samtidig er det erfaringsmessig viktig at bibliotekene har en god samarbeidspartner i leverandøren av utstyr som brukes sammen med disse teknologiene da standardisering av protokollene er begrenset og siden de utbredte standardene faktist er de facto standarder med mange lokale særegenheter og ikke ekte standarder.

##5.2.1.4 Hvilke muligheter ser man for seg med Linked Open Data og FRBR?

Økosystemets dataplattform bruker linked data som sitt hovedformat; dette er sentralt for å kunne levere metadata i nettverksdistribuerte kontekster og er en selvfølge i nyutvikling av metadatasystemer.

FRBR er en abstrakt skisse for deler av den funksjonaliteten brukere trenger for å gjøre det de ønsker med et bibliotekssystem. Den er i stor grad monografsentrisk og anvendbarheten av hele FRBR gjenstår å bevise. Work-Expression-Manifestation-Item strukturen har blitt implementert flere ganger i flere kontekster, men det er ikke blitt noen stor suksess av slike implementasjoner. BIBFRAME med sin forenklede model Work-Instance er ganske lik det som ble utviklet som basisdatamodell for dataene i Deichmanske bibliotek sin implementasjon av økosystemet, men det kan vise seg at noe annet er ønskelig i andre implementasjoner — dataplattformen støtter linked data og det er ingen begrensning av hvordan dataene ellers er strukturert. Det bør nevnes at Deichman-modellen også er ganske lik det som er utviklet hos OCLC, hvilket er påfallende med tanke på at de er utviklet helt uavhengig av hverandre.

Her er det viktig å merke seg at så lenge vi baserer inndata på MARC, blir analysene som legges til grunn for sammenslåing av poster like tilfeldig som deduplisering basert på de samme dataene. Dataene i økosystemet analyseres slik, men det må legges ned arbeid i å sikre at kvalitetene i dataene er bra nok både før og etter konverteringen. Deichmanske bibliotek har kommet et stykke på veien her og deres analyser og forbedringer kan godt benyttes i videre arbeid.

##5.2.1.5 Hvordan vil Nasjonalbibliotekets tanker rundt nasjonal infrastruktur prege våre kataloger?

Nasjonalbibliotekets (NB) tanker rundt nasjonal infrastruktur påvirker arbeidet med økosystemet i stor grad og vi har derfor tett dialog med både Nasjonalbiblioteket og BIBSYS (som er leverandør av tjenestene til NB). Det virker ganske klart at NBs satsning på ulike registre øker sannsynligheten for at vi får bedre data og jobber mer koordinert med autoriteter, men disse skal være les/skriv, ikke bare les, og dette krever nytekning. Her har økosystemet et fortrinn da det allerede bruker slike grensesnitt internt. Videre, peker teknologisatsningen til NB klart i retning av MARC21 og linked data fremfor de lokale formatene.

Deichmanske bibliotek sin datamodell er implementert med tanke på at den skal være kompatibel med kommende linked data løsninger fra NB og dialogen har vært åpen med dem angående ønsker og krav til slike løsninger. Siden økosystemet er det eneste av sitt slag og er det eneste operativ linked-data-baserte biblioteksystem, er det stor sannsylighet for at erfaringene fra dette systemet blir førende ellers i domenet, også internasjonalt der økosystemet også vekker interesse både i USA og Europa.

##5.2.1.6 Hvilke muligheter ser vi for oss med integrasjon av økonomisystemer? Hvor langt kan dette automatiseres? Alt fra innkjøp av medier til gebyr og erstatningshåndtering, webbasert betaling og mobil-betaling

I utgangspunktet er alt mulig og dette har en utviklingskostnad — det kan være lurt å samles på én plattform for betaling som håndterer dette via en felles API. Dette kan vi rådgi om.

##5.2.1.7.  Unicode tegnstøtte. Katalog må håndtere alle tegn og alfabeter

Dette er håndtert gjennom hele økosystemet.

#5.2.2 Lånerhåndtering

##5.2.2.1 Hvordan bør man håndtere en nasjonal database over lånere? Er det mulig med integrasjon med andre nasjonale persondatabaser for å sikre best mulig kvalitet på dataene?

Gitt at dagens nasjonal lånerdatabase driftes på vegne av Nasjonalbiblioteket av en av biblioteksystemleverandørene og den har en begrenset API (som ikke-medlemmer av systemleverandørgruppen ikke kan regne med å få tilgang til), er Deichmanske og Libriotechs løsning det som anbefales inntil politiske føringer rundt dette er klare. 

Det er mulig å integrere med andre persondatabaser, både lokale og (inter)nasjonale; hvis ønskelig kan økosystemet integreres med eksterne brukerdatabaser, men det bør også innvilges tid til å utforske hvilken informasjon som bør være tilgjengelig i systemet og om en eksisterende database dekker/kan dekke disse behovene.

##5.2.2.2 Hvordan sikre dublettkontroll og oppdatert kontaktinformasjon til lånere?

Bruken av Koha som basissystem for én av modulene gjør at dubletter kan lokaliseres og fjernes. Det kan i tillegg brukes ulike teknikker for å analysere lånerdatabasens innhold. Deichmans løsning for å holde dataene oppdatert er å la brukeren selv redigere innholdet i kontaktinformasjon. Samtidig brukes fødselsnummeret ved kontakt via tredjepartsaktører (som da bruker fellesregisteret); dette kan gjerne beholdes.

Det bør nevnes at lånerdatabasens innhold som oftest ikke brukes ved integrasjon med andre systemer — i samtale med tjenesteytende tredjeparter har det kommet frem at de bruker fødselsnummer/DUF-nummer til oppslag i folkeregisteret. Slike identifikatorer er også nødvendig ved oppslag i nasjonalt lånerregisteret og vi har måttet sikre at disse opplysningene er lagret i henhold til loven om personvern (disse er ikke hemmelige opplysninger) i tillegg til å sikre at lånere — som ofte betrakter fødselsnummer som hemmelig — opplever at biblioteksansatte at de ikke har tilgang til slike identifikatorer.

##5.2.2.3 Hvilke andre nasjonale personregistre er det mulig å koble seg opp mot? Altinn? Folkeregisteret? ID-Porten?

Per i dag har ingen moduler muligheten til slike oppkoplinger da Deichmanske ikke har sett at slike koplinger har en verdi utover verifisering av persondata. Siden fødselsnummer som identifikator, er det forventet at slike koplinger teknisk sett er fullt mulig. Ved ev. behov må det juridisk sett sikres tilgang.

##5.2.2.4 Må ha mulighet til å opprette (koble til) endre og slette (koble fra) lånere.

Koha har alle muligheter når det gjelder brukerhåndtering.

##5.2.2.5 Låner må kunne opprette konto / registrere lånekort på egenhånd.

Funksjonaliteten er tilgjengelig i sluttbrukermodulen; verifisering av brukerens identitet er bestemt av organisasjonen og hos Deichman er dette bestemt skal skje ved personlig oppmøte med ID. Dette utelukker ikke muligheten for en annen tilnærming/praksis hvis dere beslutter dette, eller ved integrasjon med e.g. identifikasjonstjeneste.

##5.2.2.6 Låner må kunne bestille nytt lånekort/ny pinkode (ny lånertilgang) på egenhånd.

Denne funksjonaliteten ligger i sluttbrukermodulen.

##5.2.2.7 Låner må kunne gjenfinnes i søk. Alle felt må være søkbare - selv ved kryptering.

Låner kan finnes ved søk. Noen felt kan ha begrenset søkemuligheter da det er mulig å utvide brukerdatabasen utover standardkonfigurasjonen. Er dette noe som er en begrensning kan dette lett tilpasses.

##5.2.2.8 Det må være full integrasjon med nasjonalt lånerregister - helst uten å laste ned lokale kopier.

Gitt dagens tekniske plattform for nasjonalt lånerregister fraråder vi for tett integrasjon. API-et til nasjonalt lånerregisteret er utviklet av Bibliotek-systemer AS. Det har vært krevende da ikke-medlemmer av bibliotekleverandørgruppen verken har fått mulighet til å være med på utformingen av API-et og fått tilgang det.

##5.2.2.9 Solid tilgangskontroll, helst to-stegs, ved enkelte transaksjoner

Tilgangen innebygd i dagens økosystem er sikker og bruker TLS for all kommunikasjon. Dette kan imidlertid utvides om nødvendig.

##5.2.2.10 Fleksibel rettighetshåndtering. Ulike roller skal kunne ulikt tilgangsnivå (aldersgrenser, meråpent osv.)

Brukere og roller bestemmes av Koha, og rettigheter og regler kan lett konfigureres i systemet. Det oppfordres til en gjennomgang av erfaringer hos Deichmanske bibliotek.

##5.2.2.11 Automatisk utsendelse av informasjon, reglement, påmelding nyhetsbrev osv. ved opprettelse av konto. Digital signatur.

Dette er dekket av dagens system med unntak av digital signatur. Det bør beskrives hvordan tenkes digital signatur skal gjennomføres.

#5.2.3 Katalog

##5.2.3.1. En moderne katalog må kunne håndtere fysiske og digitale objekter. Katalogen må kunne koble seg til gode, eksterne metadatatjenester.

Katalogen er basert på linked data og utviklet av utviklere med ti års erfaring med RDF og linked data i samarbeid med kunnskapsorganiseringsavdelingen ved Deichmanske bibliotek. Den er i høyest grad fleksibel og i stand til å møte alle utfordringer som et moderne bibliotek måtte ha. 

Katalogiseringsmodulen gir per i dag mulighet til å kople seg mot hvilken som helst av Z39.50 kilder, og har svært god støtte for datavasking av Biblioteksentralens BIBBI siden de aller fleste postene kommer fra denne kilden.

Støtte for kilder som bruker HTTP-baserte protokoller (SRU, OAI-PMH, andre) må utvides etter behov. Støtte for MARC21 kilder er på plass, mens XML-kilder (Bokbasen, CrossRef) må bygges ut og konfigureres. Dette er i fleres interesse.

##5.2.3.2 Hvordan løser man praktisk en god, felles database for metadata for flere bibliotek?

Linked-data-kataloger kan ikke sammenlignes med MARC-kataloger; å ha én stor, felles database er den enkleste og smidigste løsningen — teknologien tåler milliader av entiteter uten nevneverdige utfordringer i ytelsen.

For å sikre at søket kan avgrenses til bestemte kommuner, og filialer under disse, må linked-data-relasjonene til beholdningsposter i Koha utvides med én triple som sier hvilket bibliotek eier posten.

##5.2.3.3 Hvordan kan dette integreres med Nasjonalbibliotekets planer for nasjonal distribusjon av metadata?

I samråd med NB og BIBSYS som deres systemleverandør ble systemet planlagt for nettopp slik integrasjon. Integrasjonen skjer via linked data og les/skriv API.

##5.2.3.4 Hvilke muligheter har man for å bygge nye tjenester rund RDF (Bibframe)?

Plattformen bygger på RDF. Ønskes det RDF med bestemte profiler (BIBFRAME, EDM, og så videre) er dette en lett sak (en CONSTRUCT-spørring samt en plan for eksponering av dataene via API-et).

##5.2.3.5 Kan man få på plass et nasjonalt verksregister som kan fungere som en FRBR?

FRBR er antagelig en større utfordring enn å kunne tilby et kapabelt og brukbart verksregister; det sistnevnte er nok innen rekkevidde allerede da Deichmanske bibliotek har et omfattende verksregister som kjernen i deres system. Deichmans konfigurasjon er verksbasert og dette kan videreføres.

##5.2.3.6 Hvor fort fases MARC-formatet ut?

MARC som utvekslingsformat forventes å ha en lang levetid, men som kjerne i systemene er det ikke tidsriktig. MARC eksisterer i Koha som brukes for beholdningshåndtering og det populeres MARC21-poster til dette formålet, men disse brukes kun til ILL og NB-statistikk som krever bruken av MARC. Så fort ILL krever BIBFRAME eller noe annet, er systemet klart for dette.

##5.2.3.8 Hvilke eksportmuligheter er hensiktsmessige etter overgangen til RDF. Vil SRU, Z39.50 og OAI-PMH bestå?

Integrasjon med eldre systemer er nok nødvendig en stund fremover, men gjennom mer gjennomtenkt politikk i behandlingen av data og mer fremtidsrettet leveransemåter — gjerne via egnede rådataleveranseplattformer — forventes biblioteksspesifikke protokoller å forsvinne.

Ved bruk av linked data er det mye lettere å omforme data etter behov da dataene er langt mer atomiske enn det som er tilfelle med MARC og systemer med svak støtte for datatyper. Her kan vi for eksempel levere både BIBFRAME og vanlig linked data gjennom bruk av applikasjonsprofiler der en ber om en bestemt formatering av RDF-en via HTTP.

##5.2.3.9 Ved felles metadata/bibliografisk base trenger en mulighet til å koble egne eksemplarer til post. Videre må det være standard eksemplar-funksjonalitet som kopiering, sletting, masseoppretting, gruppering og utlånsregler samt alternativer for visning på web.

Dette er på plass allerede — bibliografisk data lagres som linked data mens beholdningen lagres i en relasjonsdatabase; dette gjør at logistikken rundt beholdninger ikke påvirkes av åpen-verden-modellen i RDF som ikke egner seg til bruk der vi har sanhetskondisjoner. Denne skillen gjør at løsningen støtter felleskatalog med lokalbeholdning på en smidig måte og gjør at ansatte opplever systemet ganske likt dagens situasjon.

#5.2.4 Søk og gjennfinning

##5.2.4.1 Hva bør et moderne biblioteksøk gi oss?

Moderne søketeknologi handler om flere ting som må være på plass i datagrunnlaget:

- atomisk data
- entiteter
- relasjoner
- tilgang til alle nivå i dataene (også beholdninger)
- støtte for flerspråklighet

Slik kan en lage søk som fungerer slik brukerne er vant til fra andre kjente tjenester. Datagrunnlag som baserer seg på entiteter, fremfor strengene som MARC kan levere, har mulighet til samling av begrep slik at søketreff blir mer presise siden dublettene blir borte og nesten like funn kan clusteres. I stedet for rent søk kan man også levere noe av det som kunnskapsorganiseringsbegrepet lover. Her kan en lage tjenester som gir mulighet til avgrensning av søket på fornuftige måter samt "veier videre". Det er nok i disse veier videre at vi ser de mest interessante utfordringer for tida — hva trenger en bruker for å gjøre det de trenger nå de vil finne informasjon om hendelser eller steder? Hvis de har funnet noe som interesser dem, hva bør vi ellers presentere av stoff fra katalogen jf. "See also"?

##5.2.4.2 Hvordan kan vi bygge et moderne søk som gir oss stavekontroll, oppslag på lignende ord (mente du?) og fortløpende søkeforslag?

Slike løsninger opprettes gjennom analyse av dataene i kunnskapsbasen — bibliografisk data — og bruk av entitetene en har opprettet der. Fortløpende søkeforslag avhenger av konfigurering og ytelsen av søkeindeksen som er i bruk; Deichmanske bibliotek jobber med problemstillingen for tida. Vi kan bidra med spisskompetanse innen søk og praktiske kundeeksempler fra andre kunder.

##5.2.4.3 Hvordan kan vi bygge et treff som gir oss alle relevante kilder, både kvalitetssikrede treff fra eksterne kilder, egne metadata, nasjonale autoriteter, bilder, omtaler, anmeldelser og brukernes egne vurderinger.

Her er det flere mulige tilnærminger, men siden vi bruker linked data og indeksen kan populeres fra flere kilder er det trolig best at en bare bruker disse mulighetene. Teknologiene baserer seg på lenke-begrepet og kan lett bygges ut for å støtte de nevnte kildene. 

##5.2.4.4 Hvordan kan vi få opp lenkede data som gir lånerne tips om lignende forfattere eller verk.

Økosystemet baseres på linked data. I motsetning til å prøve å tvinge lenker inn i MARC, støtter hele økosystemet linked data og lenke-begrepet, noe som gjør at den kan ta imot og bruke linked data på en fornuftig måte.

##5.2.4.5 Hvordan kan vi få på plass klassisk Amazon-funksjonalitet som «andre som leste/lånte/kjøpte denne...»

Her er vi litt avhengig av lovgivningen om personvern og lagring av metadata knyttet til brukerens atferd. Det viser seg at det ikke er så lett å anonymisere dataene som enkelte vil ha det til i de små brukerkretsene bibliotek har. Jo større brukerkrets en har jo mindre sannsynlig er det at disse problemene dukker opp; dermed er samarbeid mellom norske bibliotek et must for å få til slik funksjonalitet.

Ellers er dette relativt enkelt å få til.

##5.2.4.6 Hvordan kan vi få på plass en treffliste som gir oss de mest relevante treffene på første side?

Dette fås til gjennom bruk av entitetsbasertkatalogisering og vekting i relevansbasert søk. Entitetene gjør at vi clustrer ting som er det samme og hindrer at bare "nyeste" kommer på toppen. Dette er lett å få på plass, men krever et vedlikeholdsarbeid og kan ikke baseres på MARC-data da disse blir basert på enkle dedupliseringsalgoritmer.

##5.2.4.7 Hvordan kan vi få på plass en treffliste som viser oss det som er ledig/tilgjengelig på en god måte?

Gjennom en systemarkitektur som gjør data tilgjengelig på lik linje om det kommer fra bibliografisk eller beholdningsdata. Dette er på plass i Deichmans installasjon og utvikles videre for å vise status enda mer nøyaktig.

##5.2.4.8 Hvordan kan vi få en webkatalog som inviterer til sosial interaksjon, deling og kommentering?

Dette får vi til gjennom bruk av standard web-arkitektur og web-orienterte API-er og frontender som kan integreres i andres platformer, samt mottak av data fra eksterne tjenester.

#5.2.5 Transaksjoner

##5.2.5.1 Bør man ha en samlet oversikt over fysiske og digitale utlån?

Det er kanskje fordeler for brukeren i å samle oversikt — hvorvidt dette er mulig avhenger av plattformen som velges for levering av digitale utlån. For biblioteket er statistikk interessant, men digitale og fysiske utlån skjer i ulike prosesser og blanding av disse har muligens begrensede fordeler.

##5.2.5.2 Hvordan løser man best historikk over tidligere lån, samt gode anbefalinger basert på historikk og låners vurderinger?

Lånerens historikk (som kan lagres så lenge brukeren tillater det) kan presenteres i sluttbrukermodulen og relateres til anonymisert bruksdata og vurderinger. 

##5.2.5.3 Hvordan setter man enklest opp egne utlånsregler basert på materialgrupper/eksemplar, bibliotek/filial og lånergruppe/låner?

Ikke sikkert at jeg forstår problemet — Koha har en ganske rett frem måte å handtere dette på j.f. Deichmans installasjon.

##5.2.5.4 Hvordan sikrer man automatisk kvittering på forhåndsvalgt kommunikasjonsplattform ved utlån og innlevering (reservering, fornyelse, påminnelse, gebyrbetaling osv.)?

Dette er en preferanse i Koha og stilles av brukeren selv i sluttbrukermodulen.

##5.2.5.5 Hvordan få på plass en mulighet for å videreføre lån til bekjente?

Dette er særfunksjonalitet som også bygges ved Deichman for å videreføre praksis rundt håndtering av klassesett som lånes ut til én lærer for å så viderelånes til studenter. Ønskes dette utvidet til å gjelde andre tilfeller med ulike regler i forhold til reservasjonskø og så videre er det mulig.

##5.2.5.6 Alle transaksjoner må kunne utføres av lånerne. Enten ved selvbetjeningsutstyr i biblioteket, eller vha eget mobilt utstyr

API-ene som økosystemet bruker muliggjør dette. Er det behov for funksjonalitet som ikke finnes, utvikles dette.

#5.2.6 Statistikk

##5.2.6.1 Hvordan sikrer vi at lovpålagt statistikk til Nasjonalbiblioteket/Kostra blir full-automatisert

Automatiserte rapporter fra Koha. Rapportene ble utviklet av Deichman og er en del av standardkonfigurasjon. Automatiseringen er en enkel sak.

##5.2.6.2 Hvordan kan få et statistikkverktøy som er fleksibelt nok til å brukes som et styringsverktøy?

Gjennom bruk av eksterne verktøy som passer deres behov, samt bruk statistiske rapporter generert fra økosystemet.

##5.2.6.3 Hvordan kan vi sette opp fast rapportering (sanntid?) til media og publikum på nøkkeltall?

Relatert til 5.2.6.1 rapportene kan utvides og dedikerte rapport kan lages ved behov av bibliotekarer.

##5.2.6.4 Hvordan kan vi koble egen statistikk sammen med kommunale rapporterings- og styringssystemer (f.eks. Corporater), økonomisystemer (f.eks. Agresso) og 3. parts statistikkverktøy (f.eks. Google Analytics)?

Rapport generes og sendes enten videre eller tas inn og sammenstilles i et egnet verktøy. Google analytics er allerede implementert i sluttbrukermodulen. 

##5.2.6.5 Hvordan kan vi eksportere deler av statistikken vår som åpne datasett slik at andre kan lage tjenester basert på disse?

Lag egnede rapporter og lever resultatene via en egnet plattform.

#5.2.7 Samarbeid om felles biblioteksystem?

##5.2.7.1 Hvilke fordeler og mulige gevinster finnes ved å velge et felles biblioteksystem?

Mer tid til gevinstbringende arbeid fremfor vedlikehold, enklere overgang til nytt kjernesystem, bedre tjenester til alle brukere, bedre datakvalitet.

##5.2.7.2 Hvilke utfordringer og ulemper finnes ved å velge et felles biblioteksystem?

Å lage en egen instans av et økosystem kan gjør det enkelte biblioteket friere i sin handling og bestille det de trenger i systemet, mens fellesinsatsen betyr at bibliotekene må i større grad være enige om innsatsområder. Det er allikevel mulighet til å bestille på egenhånd.

#5.2.8 Frie innspill

Det vi beskriver er implementering av åpen og fri programvare og kostnadene her tilknyttes ikke kjøp av lisens, men utvikling, tilpassing og drift. Det settes opp ulike budsjett for dette, avhengig av kundens behov og ønsker.

Vi kan bistå styringsgrupper/implementeringsteam og innføringsteam med prosjekt- og teknologiledelsesrådgivning etter behov.

Gjennom en slik prosess kan bibliotekene få en løsning som har et felles grunnlag som er svært fremtidsrettet og utviklet etter moderne prinsipper, og som gjør det mulig å differensiere tilbudet til brukerne. Dette er særlig interessant med tanke på at det er snakk om flere ulike bibliotek med spesialsamlinger og digitaliserte dokumenter.
