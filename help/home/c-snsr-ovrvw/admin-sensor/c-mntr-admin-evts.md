---
description: För att upptäcka sensorfel så snart som möjligt och åtgärda dem innan de orsakar större problem eller avbrott bör du regelbundet övervaka dina händelseloggar.
solution: Insight
title: Övervaka administrativa händelser
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Övervaka administrativa händelser{#monitoring-administrative-events}

För att upptäcka sensorfel så snart som möjligt och åtgärda dem innan de orsakar större problem eller avbrott bör du regelbundet övervaka dina händelseloggar.

**Rekommenderad frekvens:** Minst en timme

Du kan övervaka de här händelserna med Windows Event Viewer- eller Unix Syslog-filen och med de filer som [!DNL *.sensor-log] finns som standard i [!DNL Logs] mappen i [!DNL Sensor] installationskatalogen. Dessa filer anger att det finns fel under datainsamlingen, särskilt om en användare inte [!DNL Sensor] kan ansluta till målet [!DNL data workbench server] och startar köa data.

## Övervaka händelser i Windows {#section-7c0443a356af4381bf22259654f5cd17}

Sensorn loggar fel i programloggen för Windows Event Viewer med källan&quot;Adobe&quot;.

Meddelanden loggas som &quot;Information&quot;, &quot;Varning&quot; eller &quot;Fel&quot; beroende på hur allvarliga de är.

**Så här öppnar du Windows Event Viewer**:

* Klicka på **Start > Kontrollpanelen > Administrationsverktyg > Loggboken**.

## Övervakningshändelser på Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Sensorn loggar fel till [!DNL syslog] daemon.

Synkdaemon skriver felmeddelanden för att logga filer baserat på reglerna som du angav i filen syslog.conf. Fel loggas med flaggorna &quot;LOG_DAEMON&quot; och antingen &quot;LOG_NOTICE&quot; eller &quot;LOG_ERR&quot; beroende på allvarlighetsgrad.

**Så här öppnar du Unix-syslog**

Unix-syslog finns vanligtvis i [!DNL /var/adm/messages] eller [!DNL /var/log/messages].

Bläddra till rätt plats och öppna syslog.

## Om meddelandeformat {#section-a0899add30fd4b2da58a23b9e3324693}

Alla sensormeddelanden innehåller strängen &quot;Sensor&quot; och är numrerade för att återspegla vikten av det meddelande som visas.

| Meddelandenummer | Meddelandebetydelse | Meddelandesträng |
|---|---|---|
| 1xxx | Information | Sensorinformation # |
| 2xxx | Varning | Sensorvarning # |
| 3xxx | Konfigurationsfel | Sensorfel # |
| 4xxx | Operationsfel | Sensorfel # |
| 5xxx | Internt fel | Sensorfel # |

>[!NOTE]
>
>Varningar (2xxx) används inte för närvarande. Dessa nummer är reserverade för framtida bruk.

Ditt nätverkshanteringsverktyg kan ställas in så att du kan övervaka dina meddelanden var 5:10:e minut för att se om det finns fel med Sensor-källan och informera lämplig personal om problem som kan kräva åtgärder. Du kan välja att övervaka systemet endast för vissa typer av händelsemeddelanden, till exempel strängen &quot;Sensorfel&quot;. Du kan också använda olika regler för händelser som är prefekterade med strängarna &quot;Sensorinformation&quot;, &quot;Sensorvarning&quot; och &quot;Sensorfel&quot;.

## Identifiera viktiga meddelanden {#section-5a20f5dc18ca4012931d194db855e54e}

I händelseloggarna bör du vara särskilt uppmärksam på och omedelbart ta itu med eventuella meddelanden om köstorlek.

Meddelanden som&quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; behöver till exempel åtgärdas.

## Svara på meddelanden om sensorhändelser {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tabeller som beskriver sensorhändelser och föreslagna åtgärder för de webbserverplattformar som stöds.

**Alla plattformar**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Händelsemeddelande </th> 
   <th colname="col2" class="entry"> Föreslagen åtgärd </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Sensorinformation 1010: Sensorn har initierats. </td> 
   <td colname="col2"> Ingen åtgärd krävs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorinformation 1011: Sensorn avslutades. Totalt antal klick i kö ## </td> 
   <td colname="col2"> Ingen åtgärd krävs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorinformation 1012: Adobe-skivkön är #% full </td> 
   <td colname="col2"> Det här meddelandet loggas varje gång diskköutnyttjandet överskrider ett tröskelvärde på 10 %. Om procentandelen fortsätter att växa bör åtgärder vidtas innan kön är full och data förloras. Det troligaste problemet är att sensorn har slutat kommunicera med Insight Server. Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorinformation 1013: Sensorkonfigurationen har ändrats </td> 
   <td colname="col2"> Ingen åtgärd krävs. Sensorn upptäckte en ändring i en av sina konfigurationsfiler och kommer att läsas in igen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorinformation 1014: Problem med att skicka slumptalsgenerator </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorinformation 1016: Konfigurationsfilens namn har lästs in </td> 
   <td colname="col2"> Ingen åtgärd krävs. Sensorn har läst in konfigurationsfilen i listan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorinformation 1017: Experimentfilens namn har lästs in </td> 
   <td colname="col2"> Ingen åtgärd krävs. Sensorn har läst in den angivna experimentfilen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 3016: Det gick inte att läsa in konfigurationsfilen /mypath/myfile </td> 
   <td colname="col2"> Bekräfta att sensorkonfigurationsfilen som anges i webbserverkonfigurationen finns och har de behörigheter som krävs för att läsas av webbserverprocessen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017: Det gick inte att läsa in den kontrollerade experimentella konfigurationsfilen /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Kontrollera att den kontrollerade experimentfilen som anges i txlogd.conf finns och att txlogd-processen har de behörigheter som krävs för att läsa filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 3018: Det går inte att analysera innehållsfilterlistor. Kontrollera txlog-konfigurationsfilen </td> 
   <td colname="col2"> Kontrollera syntaxen för posterna ContentFilterInclude och ContentFilterExclude i txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 3023: Det gick inte att skapa låset (g_lockThrottle) </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 3024: Det gick inte att skapa lås (g_lockConfigCheck) </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 4014: Det gick inte att öppna diskkön. </td> 
   <td colname="col2"> Kontrollera att QueueFile-filnamnet finns i txlogd.conf och kontakta Adobe ClientCare om du tror att det är rätt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 4020: Inte en köfil </td> 
   <td colname="col2"> Kontrollera att QueueFile-filnamnet finns i txlogd.conf och kontakta Adobe ClientCare om du tror att det är rätt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 4021: Kön är full </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 4022: Det går inte att mappa minnesblock med längden &lt;x&gt; vid förskjutningen &lt;y&gt; </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5012: Det gick inte att skapa mutex. </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5013: Det gick inte att hämta mutex. </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5030: Fel på gaffeln. </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5031: setsid misslyckades. </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5032: Fel på gaffeln. </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5033: chdir misslyckades. </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5034: Signal mottagen </td> 
   <td colname="col2"> Programmet avslutades troligtvis av en extern signal. Kontakta Adobe ClientCare om det inte går att fastställa källan till signalen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5035: Avsluta anropat från utsidan av huvudboken </td> 
   <td colname="col2"> Kontakta Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorfel 5036: txlogd körs redan </td> 
   <td colname="col2"> En annan instans av txlog daemon körs redan. Stoppa den andra instansen först om du vill köra en ny. </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP-server**

| Händelsemeddelande | Föreslagen åtgärd |
|---|---|
| Sensorfel 3015: Direktivet VisualSciencesConfig saknas i httpd.conf. | Detta är ett konfigurationsfel. Direktivet VisualSciencesConfig måste finnas i httpd.conf med en parameter som är platsen för txlogd.conf. |
| Sensorfel 3019: vys-cookie anropades inte före vys-log. Kontakta supporten. | Kontakta Adobe ClientCare. |
| Sensorfel 3025: Underbegäran pekar tillbaka till sig själv | Kontakta Adobe ClientCare. |

**AOL-server**

| Händelsemeddelande | Föreslagen åtgärd |
|---|---|
| Sensorfel 3015: Avsnittet ns/server/[server]/modul/[modul] saknas i konfigurationsfilen för AOLServer. | Detta är ett konfigurationsfel. Korrigera enligt felmeddelandet. |
| Sensorfel 3019: vys-cookie anropades inte före vys-log. Kontakta supporten. Kontakta Adobe ClientCare. | Kontakta supporten. Kontakta Adobe ClientCare. |
| Sensorfel 3020: VisualSciencesConfig saknas som första post i [avsnittsavsnittet] i konfigurationsfilen för AOLServer. | Detta är ett konfigurationsfel. Korrigera enligt felmeddelandet. |
| Sensorfel 3021: VisualSciencesConfig saknar ett värde i [avsnittsavsnittet] i konfigurationsfilen för AOLServer. | Detta är ett konfigurationsfel. Korrigera enligt felmeddelandet. |

**Webbservrar för iPlanet och Java System**

| Händelsemeddelande | Föreslagen åtgärd |
|---|---|
| Sensorfel 3011: Initieringsdirektiv krävs. Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Detta är ett konfigurationsfel. Initieringsdirektivet för iPlanet saknas. |
| Sensorfel 3015: config-file har inte angetts i direktivet iPlanet Init | Detta är ett konfigurationsfel. Sökvägen till konfigurationsfilen angavs inte i direktivet iPlanet Init. |
| Sensorfel 3019: vys-cookie anropades inte före vys-log. Kontrollera konfigurationsfilen | vys-cookie måste anges som första NameTrans-direktiv för varje virtuell programserver. |

