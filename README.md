# Big data and Cloud

## Intro

2024-09-23

Kursens innehåll ska ge grunder till certifiering AWS eller Microsoft (DP900)
**Studentkostnad ca 500:-**

### What's Big Data?

- kombination av strukturerad, semistrukturerad och ostrukturerad data
- samlad data i stora volymer oavsett form
- högt flöde av data
- volume, velocity, variation
- används för att upptäcka, mönster, trender & insikter
- ger bättre beslutsunderlag

### What's the cloud?

- outsourcing / överlåtelse av drift
- företag slipper köpa & underhålla egen hårdvara och mjukvara samt kan bara hyra och betala enbart för det de använder (scale out/in, scale up/down - dragspelseffekten)
- leverans av IT-resureser som servrar, lagring, databaser, nätverk, programvara & analyser över internet
- fördelar: fysiska servar blir snabbt utdaterade, svåra att flytta på, dyra att underhålla (kräver kunnig personal), inte lika flexibelt (scale in/out & up/down), med molnet betalar man bara för det man utnyttjar

### ISO/TEC 17788-2014 (punkt 6.2)

- alla med tillgång till internet ska kunna ha åtkomst
- mätbara tjänster
- delade resurser / multi-tenancy
- on-demand självservice 
- elasticitet
- resurs-pooling

### Leveransmodellerna

- det publika molnet
- det privata molnet (per definition inte ett moln)
- det hybrida molnet
- community cloud - molnbaserad tjänsteleverans avsedd för en specifik grupp av företag eller organisation

#### Annat gott

- MTBF mean time between failures
- capital expense (investeringskostnad) / operation expense (löpande konstnader)

#### Data vs Information

- data behöver bearbetning, har ingen betydelse i sig, blir till information efter bearbetning
  
## Intro to workshop

### Simple computer architechture

- single purpose
- hardware, OS, application
- remote managment

### Virtualization
  
- Using many virtual servers on one physical server lessens operating costs
- The infrastructure of virtual servers are easier to administer

Fördelar:

- fullständig isolering
- OS flexibilitet
- bekvämt för komplexa system

Nackdelar:

- Resurskrävande
- Långa uppstarttider
  
### Container technology

- builds on one OS (only runs compatible OS on separate containers)
- faster boot time for containers
- also isolated, but not as isolated as VM

### Beräkning av kostnader

- On prem innebär kostnad även för det som man inte förbrukar, kan komma att förändras beroende på licenser etc
- Cloud betalar man för det man förbrukar, går att hyra licens istället för att köpa

Att förhålla sig till vid beräkning av kostnaderna:

- Volym
- Tid
- Licensiering
- Hårdvarukonfiguration
- Region
- Antal anrop
- Bandbredd

## BigData lager & NoSQL (MongoDB)

2024-09-30

### Datainsamlingslagret

- Samlar in data från olika källor, såsom databaser, sensorer, API, sociala medier och filsystem
- Strukturerad, semistrukturerad och ostrukterad data
  
#### Vanligt förekommande verktyg:

- Apache Kafka (realtidsdataflöden)
- Apache FLume (samla in loggdata)
- AWS Kinesis eller Azure Event Hubs (stora mängder av strömmande data)

>[!IMPORTANT]
>
> - Data samlas in från olika källor i realtid eller batch, stöd för det är avgörande.
> - Skalbarhet är också en avgörande faktor för att hantera stora datamängder.
> - Inte minst - kostnadseffektivitet.

### Datalagringslagret

- efter insamling måste data lagras på ett sätt som möjliggör enkel åtkomst och vidare bearbetning
- kan bestå av olika typer av lager beroende på typer av data

#### Vanliga alternativ

- Data Lake (ostrukturerad och semistrukturerad data), ex. AWS S3, Azure Data Lake
- Data Warehouse  (strukturerad data, ofta RDBS), ex. Amazon Redshift, Azure Synapse Analytics
- NoSQL (ostrukturerad och strukturerad data), ex. MongoDB, Cassandra

### Datalagringsoptimeringslagret

- ansvarar för att transformera och bearbeta den insamlade datan.
- bearbetningen kan vara i form av att rensa, strukturera, omvandla data för att göra den användbar för analyser och beslutsfattande.
  
#### Verktyg och tekniker

- Apache Hadoop för batchbearbetning av stora datamändger
- Apache Spark för både batch och strömmande data
- AWS Glue eller Azure Data Factory för ETL-processer
  
>[!IMPORTANT]
>
> - Viktigt med stöd för parallellbearbetning
> - Mångsidighet i att hantera både batch och realtidsströmmar
> - Anpassningsbarhet för olika analysbehov

### Analys- & datasciencelagret

- Efter att data har processerats analyseras den
- möjliggör körning av avancerade analyser, datavisualisering och använda maskininlärning för att upptäcka mönster eller förutsäga framtida trender

#### Verktyg och Plattformer

- SQL-verktyg för datafrågor (Apache Hive, AWS Athena)
- BI-verktyg som Tableau, PowerBi eller Amazon QuickSight för visualisering
- DataScience plattformer

> [!IMPORTANT]
>
> - Integration av både deskriptiv och prediktiv analys.
> - Skalbara

### Data Access Layer

- åtkomstkontroll, säkerhet och hantering av dataintegritet
- endast auktoriserade användare och system kan komma åt rätt data samt att datan hålls säker både vid lagring och överföring

#### Verktyg & teknologier

- Role based access control (RBAC) för åtkomstkontroll
- kryptering av data både i vila och under överföring
- data governance verktyg som AWS Lake formation eller Azure Purview för att övervaka och säkerställa datakvalitet och regelefterlevnad
  
> [!IMPORTANT]
>
> - Hantering av användaråtkomst och datakänslighet
> - Regelefterlevnad som GDPR eller CCPA
> - Data lineage och auditering för spårbarhet av data
>

### Användarinteraktionslagret

- används för att göra data och insikter tillgängliga för alutanvändare via olika gränssnitt
- kan bestå av dashboards, rapporter eller APIer som göra data tillgänglig för användare eller andra services
  
#### Verktyg och teknologier

- API för tillhandhålla åtkomst till andra applikationer
- BI-dashboards och rapportverktyg som PowerBI, Tableu eller Looker

> [!IMPORTANT]
>
> - Användarvänlighet
> - realtidsuppdateringar för att ge aktuell information
> - anpassningsbara visualiseringar och rapporter

### MongoDB & SQL

Vi väljer typ av databas baserat på

- datans natur: strukturerad, ostrukturerad samt hur komplex den är
- applikationens krav, dvs specifika krav inklusive frågetyper, läs/skriv frekvens samt skalbarhet
- konsistensbehov, dvs nivpn av konsistens som krävs av din applikation

#### typer av NoSQL databaser

- Dokumentdatabaser (idealisk för semistrukturerad data som XML och JSON)
- Kolumnbaserade databaser (effektiv läsning och skrivning av stora datamängder)
- Key-value databaser (perfekt för scenarier med höga skrivhastigheter)
- Graf-databaser (data lagras som noder och det skapas relation mellan dessa)
- Time-series databaser

#### DocumentDB

Exempel: MongoDB, Azure CosmosDB, Amazon DocumentDB

Datamodell:

- Data lagras i dokumentformat som JSON & BSON i MongoDB medan CosmosDB förutom MongoDB API har stöd för ytterligare API:er.
- Dokument är strukturerade i nyckel-värde-par och kan innehålla olika fält och strukturer, vilket gör det enkelt att representera komplex och varierad data.

Användningsområden:

- Perfekt för applikationer som hanterar semistrukturerad data eller ostrukturerad data t.ex. innehpllshanteringssystem, kataloger, profiler & loggfiler
- bra för agila utvecklingsmiljöer där schemat kan förändras över tid

Fördelar:

- Flexibel datamodell som kan anpassas efter applikationens behov
- Enklare att representera objektorienterad data
- lämplig för applikationer med varierande strukturer data

#### Key-Value Stores

Exempel: Redis, DynamoDB, Riak, Memcached

Datamodell:

- Data lagras som nyckel-värde-par, där varje nyckel är unik

Användningsområden:

- cachning, sessionshantering, lagring av användarpreferenser

Fördelar:

- extrem snabba läs- och skrivoperationer
- enkel struktur som är lätt att inplementera

Nackdelar

- begränsade möjligheter till komplexa frågor och analyser av data
- passar inte för applikationer som kräver relationer mellan olika nycklar

### Kolumnbaserade databaser

Exempel: Apache Cassandra, HBase, ScyllaDB

Datamodell:

- lagras i rader och kolumner, likt RDB. Iställt för att organisera data i tabeller, lagras kolumner med liknande egenskaper tillsammans i familjer. Snabb åtkomst till specifika kolumner och hanterar stora datamöngder effektivt.

Användningsområden:

- dataanalys och stora datamängder, t.ex. logghantering och realtidsanalys
- lämplig för distribuerade system som kräver hög tillgänglighet och partitionstolerans
  
Fördelar:

- bra för skrivintensiva applikationer och kan hantera stora volymer
- stöd för partitionering och replikering för hög tillgänglihet

Nackdelar:

- svårt att designa optimala datamodeller
- begränsad flexibilitet

### Grafdatabaser

Exempel: Neo4j, Amazon Neptune, OrientDb, ArangoDB

Datamodell:

- varje nod är entitet (en person eller ett föremål) och varje relation beskriver en länk mellan noder (vänskap, ägande)
- 
Användningsområden:

- bra för applikationer som hanterar komplexa relationer mellan objekt t.ex. sociala nätverk, rekommendationsmotorer eller nätversanalys
- för att hantera hierarkiska strukturer, t.ex. organisationshierarkier eller nätversdiagram

Fördelar:

- mönsterigenkänning
- stöd för flera relationer

Nackdelar:

- mindre effektiv för hantering av ostrukturerad eller dokumentliknande data
- kräver särskilda optimeringar och underhåll

### Time-Series-Databases

Exempel: InfluxDB, TimescaleDB, OpenTSDB, Prometheus

Datamodell:

- data organiseras baserat på tidsstömplar och är optimerad för att samla in, lagra och analysera tidsstämplad data
- varje datapunkt lagras med en tidsstämpel som primär nyckel och tillhörande värden (t.ex. temperatur, CPU-anvöndning, sensorvärden) och metadata (t.ex. enhet eller plats)

Användningsområden:

- övervakning av applikationer (klimatförändrigar)

Fördelar:

- optimerad för att hantera stora datamängder

Nackdelar:

- inte lämpad för applikationer som inte baseras på tidsstämplad data

### Hadoop

- open source
- lagring & bearbetning av stora datamängder
- skalar från enska servrar till flera tusen
- skabarhet & flexibilitet

  - utformad för att enkelt skalas upp från en server till tusentals maskiner, var och en erbjuder lokal beräkning och lagring
  - möjliggör bearbetning och lagring av enorma datamängder snabbt och effektivt

- felfördröjning
  
  - automatisk felhantering
  - data är  replikerat över flera noder i klustret
  - säkerställer att systemet kan fortsätta fungera utan avbrott även om en eller flera noder misslyckas

#### Hadoop Distributed File System

- lagrar data på flera system samtidigt
- designat för robusthet och feltolerans genom replikering

#### MapReduce

- programmeringsmodell för databearbetning i parallella system
- delar upp jobbet i små fragment vilka kan bearbetas parallellt

#### YARN

- resurshanteringsteknik för att tillåta fler bearbetningsmotorer att köras på samma Hadoop-system
- ansvarar för allokera systemresurser till de olika applikationerna som körs i ett Hadoop-kluster

#### Hadoop Ecosystem

- mängder av verktyg och koponenter
- några exempel:
  
  - Apache Hive (datalagring)
  - Apache HBase (NoSQL databas)
  - Apache Pig (högnivå dataflödeshanteringsverktyg)
  - Apache Spark (snabb databearbetning)

#### Praktiska tillämpningar av Hadoop

- Sociala medier
- E-handel
- Finansiella tjänster
- Hälsovård & life sciences
- Telecom
- Medier & underhållning
- Energi & naturresurser
- Googles GCP - Dataproc
- Microsoft Azure - HDInsight
- AWS - Elastic MapReduce (EMR)

### Google File System (GFS)

- likheter med Hadoop
- kombinerar GFS och Google MapReduce
- skapar möjlighet att indexera webben i bouta skala
- precis som Hadoop, Open Source

### SPARK

- programspråk med hög tillförlitlighet, säkerhet och möjligheter till underhåll

#### Apache Spark

- open source
- analysmotor för storskalig databehandling där data har en hög grad av komplexitet och där stora datamöngder analyseras i distribuerade system
- stöd för flertalet språk
- anväds ofta i big data analyser och ML

Födelar:

- hastighet
- mångsidighet
- enkelhet
- skalbarhet
- felhantering

Nackdelar:

- minneskrav
- komplexitet vid finjustering
- konstnader för infrastuktur
- begränsat stöd för realtidsbearbetning

### Databricks
