---
description: Identifiera minimikrav och rekommendationer för Data Workbench (tidigare [!DNL Insight])-serverkomponenter innan du planerar och implementerar systemet.
title: Systemkrav för server
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Systemkrav för server{#server-system-requirements}

Identifiera minimikrav och rekommendationer för Data Workbench-serverkomponenter innan du planerar och implementerar systemet.

## DPU-krav{#dpu-requirements}

DPU (server Data Processing Unit) är huvudkomponenten i Datan Workbench för databearbetning. Den lyssnar efter nätverksanslutningar från Data Workbench, läser råkälldata från filserverenheten (FSU) och använder omfattande dator- och lagringsresurser.

### Licensierad kapacitet {#section-71850e13783443798b3df9eb22cc63dc}

Se servicebeskrivningen i *Adobe [!DNL Data Workbench (Insight)]-serviceavtalet* för information om licenskapacitet.

>[!NOTE]
>
>För *MS System Center Endpoint Protection* på Windows 2012-servrar måste dessa körbara filer läggas till i ***Exkluderade processer:*** >
>* [!DNL InsightServer64.exe]
>* [!DNL ReportServer.exe]
>* [!DNL ExportIntegration.exe]

>


### Recommendations och krav för DPU-system {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe ger rekommendationer om en Data Workbench som uppfyller företagets behov. Följande riktlinjer är emellertid användbara när du väljer operativsystem (OS) och maskinvara, eftersom DPU-programvarans optimerade karaktär ställer specifika krav på operativsystemet/maskinvaruplattformen.

Om en enskild datauppsättning begränsas av kapaciteten eller hastigheten för en enskild DPU kan du gruppera dem. Anta till exempel att du har tre licensierade kopior av DPU-programmet som används tillsammans för att snabbare köra en större datauppsättning. Eftersom data fördelas jämnt mellan maskinerna multipliceras den licensierade kapaciteten för datauppsättningen med tre. Bearbetningshastigheten per rad blir dessutom tre gånger snabbare än för ett enda DPU.

För att få bästa möjliga prestanda från DPU-investeringen rekommenderar Adobe följande högpresterande komponenter som beskrivs i följande tabell:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> </th>
   <th colname="col2" class="entry"> Obligatoriskt </th>
   <th colname="col3" class="entry"> Rekommenderas </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Operativsystem </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td>
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>CPU </p> </td>
   <td colname="col2"> <p>Se rekommendationer. </p> </td>
   <td colname="col3"> Den senaste generationens processorer med fyra kärnor+ från Intel eller AMD rekommenderas. 8 kärnor för optimala prestanda, 4 kärnor rekommenderas för en kompromiss mellan hastighet och kostnad. </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>8 GB </p> </td>
   <td colname="col3"> <p>12 GB </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Aktuell datalagring </p> </td>
   <td colname="col2"> <p>1 TB+ total logisk tillfällig lagring. </p> <p>Åtkomst till diskundersystemet med låg fördröjning </p> </td>
   <td colname="col3"> <p>För tillfällig lagring rekommenderar Adobe antingen: </p>
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283">
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 till 8) * (750 GB eller mer) SATA-hårddiskar (3,5-tumsfack.) </li>
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 till 10) * (300 GB eller mer) SATA-hårddiskar (2,5-tumsfack.) </li>
    </ul> <p>Dessa bör konfigureras i en JBOD-matris. Om bruttodiskkapaciteten överstiger 2 TB kan du även använda en matris med RAID1-volymer på 2 diskar. Du kan till exempel konfigurera sex diskar som ett 3*(2*750 GB RAID 1-par.) </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Systemdatalagring </p> </td>
   <td colname="col2"> <p>Dessutom kräver Adobe lagring med hög tillgänglighet och en måttlig storlek (20 GB) för operativsystemet, DPU-programmet och andra systemprogram. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Klustring av maskinvara </p> </td>
   <td colname="col2"> <p>Se rekommendationer. </p> </td>
   <td colname="col3"> <p>Använd en homogen uppsättning servrar. I ett DPU-kluster minskar den långsammaste servern prestanda för hela datauppsättningen. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Nätverksprestanda för kluster </td>
   <td colname="col2"> En Ethernet-anslutning med växlad gigabit eller mer. </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

### Alternativa diskdelsystem {#section-6f984eabe8074759aa9deaf17e3a68b7}

När du överväger alternativa diskdelsystem för tillfällig lagring bör du tänka på följande faktorer och riktlinjer:

* DPU-processorn kräver oftast ett system med högpresterande diskar, så om du konfigurerar ett undersystem med otillräcklig diskprestanda kan det orsaka flaskhalsar i prestandan.
* DPU-programmet utför sin egen prestandainriktade dataskiktning på en uppsättning JBOD-skivor. Använd inte RAID för att öka hastigheten.
* Adobe rekommenderar att DPU:n har mer än 400 MB/s sammanlagd bandbredd för diskarna.
* De genomsnittliga lässtorlekarna är mycket höga (2 MB+). Därför fungerar SAS-hårddiskar på 15 000 eller 10 000 v/min ofta lite bättre (eller sämre) än SATA-diskar till en avsevärd kostnad och kapacitet.
* Undvik att använda en SAN-arkitektur. Erfarenheten visar att kostnaden för att få ett SAN att fungera på den nivå som krävs vanligtvis är extrem.
* Det lokala diskundersystemet används som virtuellt minne - inga data förloras permanent om ett hårddiskfel inträffar. Undvik därför kostsamma, långsammare system med hög tillgänglighet.

### Tänk på hastighet {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe kan inte tillhandahålla någon garanti eller representation avseende den hastighet med vilken data bearbetas av en konfigurerad Data Workbench, eftersom en rad faktorer påverkar databearbetningshastigheten, inklusive men inte begränsat till följande:

* Antal rader med data
* Antal dimensioner (kolumner) av data
* Antal anpassade bearbetningssteg och deras komplexitet
* Användning av klustring
* Hastighet för maskinvara

## Krav på filserverenhet{#file-server-unit-requirements}

Serverns filserverenhet (FSU, File Serving Unit) är den huvudsakliga datalagrings- och hanteringskomponenten för Data Workbench. FSU:n fungerar som en filserver för råkälldata till DPU:n och koordinerar vid behov klustringen av DPU:er. Varje FSU är licensierad att leverera källdata till upp till fem (5) DPU:er.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E">
 <thead>
  <tr>
   <th colname="col1" class="entry"> FSU-komponenter </th>
   <th colname="col2" class="entry"> Rekommendationer </th>
   <th colname="col3" class="entry"> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Operativsystem, CPU, RAM </p> </td>
   <td colname="col2"> <p>Dessa krav är desamma som för DPU. För FSU rekommenderar Adobe dock att man använder minimikraven i stället för att följa rekommendationerna. </p> </td>
   <td colname="col3"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Disksystem </p> <p>FSU kräver högtillgänglig, redundant lagring för stora datavolymer. Adobe kommer att arbeta tillsammans med dig för att fastställa dina exakta krav. </p> </td>
   <td colname="col1"> <p>Adobe rekommenderar: </p>
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539">
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 eller fler) * (750 GB eller mer) SATA-hårddiskar i en RAID 5/6-konfiguration. </li>
     <li id="li_3F84F63F9541476987015C27FDE8251B">Högpresterande SAN-anslutning som stöder 100 MB/s+ kontinuerlig bandbredd. </li>
    </ul> <p>Eftersom FSU lagrar råkälldata skulle eventuella förluster inte kunna återvinnas och Adobe föreslår att dessa data säkerhetskopieras regelbundet. </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Nätverksprestanda </p> </td>
   <td colname="col2"> <p>Adobe kräver Ethernet-anslutningar med växlade gigabit mellan FSU:er och DPU:er som fungerar tillsammans. </p> </td>
   <td colname="col3"> </td>
  </tr>
 </tbody>
</table>

## Sensorkrav{#sensor-requirements}

Data Workbench Sensor samlar in händelsedata från webb-, program- och datainsamlingsservrar som ska överföras till valfri server. [!DNL Sensor’s] -instrumentering ger en konsekvent korrekt mätning av händelser som inträffar i din internetkanal. [!DNL Sensor] har stöd för många kombinationer av webbserverprogramvara och operativsystem.

### Sensorsystem Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

I följande tabell beskrivs systemrekommendationerna för [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Funktioner </th>
   <th colname="col2" class="entry"> Rekommenderas </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Disklagring </p> </td>
   <td colname="col2"> <p>Minst 512 MB. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>RAM </p> </td>
   <td colname="col2"> <p>32 MB RAM måste vara tillgängligt för <span class="wintitle"> sensor </span> på HTTP-servern eller någon annan serverdator som är dess värd. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Nätverksprestanda </p> </td>
   <td colname="col2"> <p>1 Mbit/s eller bättre nätverksanslutning till en upprepande server eller <span class="keyword"> data workbench server </span>. <span class="wintitle"> Sensorn förbrukar  </span> vanligtvis betydligt mindre bandbredd än en (1) Mbit/s. Dina Adobe-konsulter hjälper dig att uppskatta den faktiska bandbredd som skulle behövas rutinmässigt. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Nätverksportar och brandväggar </p> </td>
   <td colname="col2"> <p> <span class="wintitle"> Sensorn  </span> ansluter till  <span class="keyword"> data workbench-servern  </span> med HTTPS (vanligtvis port 443, även om detta är konfigurerbart) eller HTTP (vanligtvis port 80, även om detta är konfigurerbart). </p> <p>Lämplig port på en brandvägg som finns mellan en <span class="wintitle">-sensor </span> och målservern <span class="keyword"> för data workbench </span> eller en upprepande server ska bara öppnas mellan respektive <span class="wintitle">-sensor </span>-värddator och <span class="keyword"> data workbench server </span> eller en upprepande server innan <span class="wintitle">-servern startas installationsprocess för ensor </span>. <span class="wintitle"> Sensorn  </span> gör en enkelriktad HTTPS- eller HTTP-anslutning till en  <span class="keyword"> data workbench-server  </span> eller en upprepande server. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Nätverkshanteringssystem </p> </td>
   <td colname="col2"> <p>Befintliga nätverkshanteringssystem bör övervaka hälsotillståndet för den underliggande datormaskinvaran (till exempel diskutrymme, nätverkstjänst) och nätverksanslutning samt Windows-händelseloggen eller UNIX-syslog. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Servertidssynkronisering </p> </td>
   <td colname="col2"> <p>Kontrollera att datorns systemtid är kontinuerligt synkroniserad på alla datorer som är värdar för en <span class="wintitle">-sensor </span>. Webbserverprogrammen och datorerna som övervakas av <span class="wintitle">-sensorn </span> måste ha synkroniserade systemtider för att händelsedata som samlas in från dem ska vara korrekta. Se dokumentationen för ditt operativsystem för hur du synkroniserar systemtider fortlöpande med NTP eller andra tidssynkroniseringsfunktioner. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Användning av DNS-namn </p> </td>
   <td colname="col2"> <p>Adobe rekommenderar att <span class="wintitle">-sensorer </span> använder ett DNS-namn (i stället för en IP-adress) för att matcha nätverksadressen för en <span class="keyword"> data workbench-server </span> eller en upprepande server. När en <span class="wintitle">-sensor </span> använder ett DNS-namn måste värdwebbserverns DNS-fil eller lokala värdfil konfigureras för att matcha namnet på <span class="keyword">-data workbench-servern </span> eller den upprepade servern. </p> </td>
  </tr>
 </tbody>
</table>

### Support Server-programvara {#section-d6071706539f49d9a861d87b98e6f382}

I följande tabell visas de vanligaste kombinationerna som [!DNL Sensor] har stöd för:

<table id="table_99EA23BBC1A148B49643F4B5E4341C08">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Webbserverprogramvara </th>
   <th colname="col2" class="entry"> Operativsystem </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Apache Server/IBM HTTP Server 2.2 </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 eller senare; RedHat Enterprise Linux 6.x eller senare; Sun Solaris 8.x eller senare; IBM AIX 5.1x eller senare. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Apache Server 2.4 </p> </td>
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x eller senare </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Microsoft IIS </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 eller senare </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Java-programservrar (Tomcat, JBoss, iPlanet, Weblogic) </p> </td>
   <td colname="col2"> <p>Microsoft Windows Server 2003 eller senare; RedHat Enterprise Linux 6.x eller senare; Sun Solaris 8.x eller senare; IBM AIX 5.1x eller senare. </p> </td>
  </tr>
 </tbody>
</table>

För andra kombinationer av server och operativsystem, se Adobe angående tillgängligheten. Alla funktioner i [!DNL Sensor] är inte tillgängliga för alla kombinationer av webb-/programserver och operativsystem. Mer information om [!DNL Sensor]-versioner får du av Adobe Support.

## Krav för rapportservern{#report-server-requirements}

Data workbench-rapportservern är den komponent som tillåter utdata för schemalagd rapportering. De rapporter som skapas kan antingen vara PNG-bilder, XLS-kalkylblad eller e-postmeddelanden i ett filsystem. Dess maskinvarukrav är identiska med [Data Workbench Client](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html).

Följande krav gäller för [!DNL report server]:

* Åtkomst till filsystem för utdata av data (nätverksresurs eller lokal enhet).
* Åtkomst till konfigurerad SMTP-server.
* Microsoft Excel 2003 eller senare är installerat på [!DNL report]-servern. Mer information finns i [Att tänka på vid serverautomatisering av Office](https://support.microsoft.com/kb/257757).

## Nätverkshantering{#network-management}

Adobe rekommenderar att befintliga nätverkshanteringssystem övervakar den maskinvara och det nätverk som Datan Workbench använder.

Dessutom rekommenderar Adobe att du övervakar Windows-händelseloggarna för FSU:er och DPU:er, som skrivs till när ett fel inträffar.

>[!NOTE]
>
>Loggfiler för nätverkslagringssystem måste innehålla minst 10 MB per DPU med kontinuerlig bandbredd.

## Datatillgänglighet{#data-availability}

Det är en normal och nödvändig vana för en server-DPU att bearbeta och bearbeta om data till en ny eller uppdaterad datauppsättning.

Detta kan inträffa på grund av konfigurationsändringar, ändringar i datakällan, maskinvaruändringar, felaktig konfiguration, maskinvarufel, programvarufel, strömavbrott osv. När sådan behandling eller ombearbetning sker krävs att alla data och systemdata är omedelbart tillgängliga för DPU- och FSU-komponenterna. Om detta krav inte uppfylls kan det leda till betydande och onödig driftstopp.

## Problem med DPU- och FSU-nätverk{#dpu-and-fsu-network-issues}

Tänk på detta när du arbetar med DPU- och FSU-nätverk.

* För nätverksdistribution av loggfiler måste alla värdloggfiler för nätverkslagringssystem tillhandahålla minst 10 MB per DPU med kontinuerlig bandbredd.
* DPU, FSU och Data Workbench kommunicerar dubbelriktat via HTTP eller HTTPS på port 80 eller 443 (som standard). portar kan konfigureras alternativt).
* Datan Workbench [!DNL Sensor(s)] måste kunna ansluta (envägs) till servrarna.
* Om DPU:n ska kunna skicka varningsmeddelanden via SMTP måste den kunna kontakta den konfigurerade SMTP-servern.
* Adobe rekommenderar att FSU och DPU får nätverksnamn som FSU01.CLIENT.COM för att undvika omkonfigurering om en IP-adress ändras.
