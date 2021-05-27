---
description: Detaljerade anvisningar för installation och konfigurering av Sensor för WebSphere 5.x som körs i AIX 5.1 eller senare.
title: WebSphere i AIX
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 0%

---

# WebSphere på AIX{#websphere-on-aix}

Detaljerade anvisningar för installation och konfigurering av Sensor för WebSphere 5.x som körs i AIX 5.1 eller senare.

Programfilerna för [!DNL Sensor] paketeras i en installationsfil som du får från hämtningsplatsen för Adobe. Om du inte redan har installationsfilen [!DNL Sensor] för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

>[!NOTE]
>
>[!DNL Sensor] för WebSphere-servrar har inte stöd för kontrollerade försök. Mer information om kontrollerade försök finns i *handboken om Data Workbench-kontrollerade experiment.*

## Installera programfilerna {#section-86f69127278c41bc90b97b68bb40bc6e}

Procedur för att extrahera och installera programfilerna för Sensorto på serverdatorn.

1. Logga in som rotanvändare eller som användare med rotbehörighet.
1. Dekomprimera och packa upp installationsfilen med följande kommando:

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. Kopiera de opackade programfilerna till katalogerna i följande tabell:

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fil </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Målkatalog </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_Sciences.so </td> 
   <td colname="col2"> Insamlarens belastningsmodul </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Insamlarens bibliotek för inläsningsmodulen </td> 
   <td colname="col3"> WebSphere /lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> Sändarprogrammet </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>—OR— </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensorkonfigurationsfilen </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certifikatet som används för att validera det digitala certifikat som Insight Server visar under anslutningsprocessen </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Installationspaketet innehåller en kalkylbladsfil som heter TestExperiment.xls. Detta kalkylblad är ett verktyg som arkitekter använder för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen, så du behöver inte installera filen på den dator där sensorn körs (men du kan välja att göra det). Du kanske istället vill kopiera filen till en plats där arkitekterna kan komma åt den eller extrahera filen från installationspaketet efter behov. Mer information om kontrollerade försök finns i handboken om insiktskontrollerade experiment.

**Behörigheter för programfilerna**

Felaktiga behörigheter för programfilerna orsakar de flesta problem som uppstår när Sensor installeras.

Kontrollera att du har angett exakt den behörighet som anges i det här avsnittet.

Som standard har programfilerna i tjärfilen följande behörigheter. Beroende på hur systemet är konfigurerat kan dessa inställningar ändras (omaskeras) när du extraherar filerna.

Om du vill återställa behörigheterna till de rekommenderade standardinställningarna använder du chmod-kommandona nedan.

>[!NOTE]
>
>Kontrollera att katalogerna som du har installerat filerna i tillåter minst den här åtkomstnivån.

| Fil | Standardbehörigheter | chmod, kommando |
|---|---|---|
| libvisual_Sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw- rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

Om du vill använda andra behörigheter än de som rekommenderas läser du informationen i Sensor UNIX File Permissions för att vara säker på att du förstår hur dessa filer används.

## Redigera sensorkonfigurationsfilen {#section-283c8a92fa8841c1b6034e5f834ef4e7}

Filen txlogd.conf innehåller konfigurationsparametrarna för Sensor.

Du måste redigera filen för att bland annat ange storleken på diskkön, adressen till Insight Server och det ID som ska kopplas till data som produceras av den här sensorn.

Konfigurationsfilen innehåller obligatoriska parametrar och valfria parametrar.

* Obligatoriska parametrar är inställningar som du måste ange när du installerar sensor. Utan dessa inställningar kan sensorn inte köras.
* Valfria parametrar är inställningar som är standard för fördefinierade värden (som du kan ändra) eller aktivera valfria funktioner.

**Redigera konfigurationsfilen**

1. Öppna filen /etc/txlogd.conf i en textredigerare och ange obligatoriska parametrar samt eventuella valfria parametrar.
1. Spara och stäng filen.

## Starta sändaren och skapa diskkön {#section-63285a2328604f20a2cb31b3d5cb80e6}

Procedur för att skapa diskkön när du har konfigurerat filen txlogd.conf.

1. Om katalogen som diskkön finns i inte redan finns skapar du den. Kontrollera att katalogen ger både insamlingsmodulen och sändarprogrammet läs- och skrivåtkomst till filen.

1. Kör följande kommando på den dator där Sensor är installerat för att starta sändaren:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Alternativet &quot;i&quot; i det här kommandot startar sändaren i interaktivt läge. I det här läget visas sändarmeddelanden på skärmen och du kan även använda tangentbordskommandon för att interagera med sändaren.
   * Alternativet &quot;c&quot; dirigerar sändaren till diskkön.
   * Alternativet &quot;f&quot; anger platsen för konfigurationsfilen.

1. Kontrollera att sändaren har skapat diskkön på den plats som anges i parametern QueueFile och med den storlek som anges i parametern QueueSize.
1. Om kön inte har skapats korrekt skriver du Ctrl+C för att avsluta sändaren och gör sedan följande:

   1. Granska filen txtlogd.conf och kontrollera att parametrarna QueueFile och QueueSize är korrekt inställda.
   1. Kontrollera att den enhet som diskkön är tilldelad till är i drift och har tillräckligt med ledigt utrymme för en fil med den storlek som anges i parametern QueueSize.
   1. Gör nödvändiga korrigeringar och upprepa proceduren.

## Lägg till insamlaren i webbprogrammet {#section-d17297b1193f4e3cb150fb41f754ef12}

För WebSphere-servrar fungerar insamlaren som ett filter i serverbehållaren.

Om du vill lägga till insamlaren i webbprogrammet lägger du till filtret i webbprogrammets web.xml-distributionsbeskrivning och startar om webbprogrammet.

1. Öppna filen web.xml med en textredigerare för webbservern vars händelser Sensor fångar.
1. Lägg till följande `<filter>`- och `<filter-mapping>`-element i beskrivningsfilen. Om du inte har installerat txlogd.conf i katalogen /etc måste du ange rätt sökväg till filen i `<param-value>`-elementet.

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping>
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping>
   ```

   >[!NOTE]
   >
   >Linjerna är skiftlägeskänsliga. Skriv dem exakt som de visas ovan.

1. Starta om webbprogrammet. Insamlaren läses in med programmet och börjar samla in händelsedata och skriva dem till diskkön.

## Deklarera platsen för filerna för samlaren och det delade objektet {#section-e641f08999d34a648aaee2111b69ca25}

Procedur för att redigera WebSphere-startskriptet för att deklarera platsen för filerna J2EECollector.jar och libvisual_Sciences.so.

1. Öppna filen setupCmdLine.sh i katalogen Websphere /bin.
1. Efter raden som definierar variabeln $WAS_CLASSPATH lägger du till följande rad:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Efter det skiftlägesknapp som definierar variabeln $WAS_LIBPATH lägger du till följande rad:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Spara [!DNL setupCmdLine.sh]-filen.

## Testa sensorn {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

Procedur för att starta sändaren och verifiera att den kan ansluta till Insight Server och överföra händelsedata till den.

>[!NOTE]
>
>Kontrollera att målservern för Insight Server är installerad och igång innan du påbörjar nästa test för att verifiera att sändaren kan skicka händelsedata till Insight Server.

1. Om sändaren inte redan körs startar du om den med följande kommando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Öppna en webbläsare (på vilken dator som helst) och begär en sida från den webbserver där Sensor körs (se till att välja en sida som Sensor övervakar).
1. När du har utfärdat begäran kan du kontrollera avsändarens konsol för meddelanden som anger att den skickar händelsedata till målservern för Insight.
1. Om sensorn inte kan överföra data kontrollerar du att:

   * Målservern för Insight körs.
   * Parametrarna ServerAddress och ServerPort har angetts korrekt i txtlog.conf. Om du har angett ServerAddress med ett servernamn kan du försöka använda den numeriska IP-adressen i stället.
   * Värdet för parametern CertName matchar det vanliga namnet som visas på det digitala certifikatet för målservern Insight exakt.

## Lägg till sändaren i systemstartskriptet {#section-23bb905100d04f018af93873dd4d5f68}

Information som ser till att sändaren läses in automatiskt när webbserverdatorn startas om.

Lägg till följande kommando (som startar sändaren) i systemets startskript.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Det här kommandot startar sändaren som ett daemon. Åtgärds- och felmeddelanden som skickas till syslog.

## Hämta ytterligare data {#section-d5ccf8ee50914a87938e0c17480757e6}

Sensorer för alla plattformar kan samla in alla data som är tillgängliga i rubrikerna för HTTP-begäran och -svar.

Sensorerna för J2EE-plattformen erbjuder en mekanism för insamling av data som inte är tillgängliga på andra plattformar. Insamlaren för J2EE-plattformen (J2EE-insamlaren) finns i programlagret, vilket gör att den kan samla in känsliga data som bara är tillgängliga för programmet och som inte ska visas genom sidtaggning eller i sidhuvudena.

>[!NOTE]
>
>Sidmärkord och sidhuvudsändringar kan dölja data, men är fortfarande tillgängliga för dem som undersöker källkoden för en sida eller tittar på sidhuvudena med hjälp av verktygen för webbläsarplugin.

J2EE-insamlaren kan till exempel användas för att samla in kostnadsdata per klickning (CPC) för länkar som visas på en sida, känslig partnerinformation på en sida och många andra datapunkter. J2EE-miljön gör det enkelt för dig att ändra din WEBAPP för att hämta in anpassade data med vår insamlingsklass.

När en sensor för J2EE-plattformen tar emot en begäran, anropas en samlingsklass som importerar funktionen appendToLog. Funktionen appendToLog lägger till frågesträngsparametrarna som anges i funktionen appendToLog till den första begäran. Detta resulterar i URI:n för den initiala begäran som innehåller ytterligare par med namn/värde för frågesträngar som motsvarar namnen och värdena på de data som hämtas. CPC=20 skulle till exempel läggas till den första begäran när värdet för en viss annonsplacering eller klicklänken är 20 cent. Insight Server bearbetar dessa värden i datauppsättningen för analys. En annan fördel med den här samlingsmetoden är att den tillåter insamling av ytterligare data utan att skapa extra loggposter, vilket kan vara fallet med sidtaggningsmetoder.

Mer information om bearbetning finns i *Konfigurationshandboken för datauppsättningar*.

1. Lägg till följande kod högst upp på .jsp-sidan där du vill hämta data:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Använd metoden appendToLog() för samlingsobjektet för att lägga till önskade namn/värde-par till den begärda .jsp-sidans frågesträng. I följande exempel läggs&quot;A=1&quot; och&quot;B=2&quot; till i frågesträngen för den begärda .jsp-sidan för /index.jsp:

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   Resultat från begäran-URI är /index.jsp?A=1&amp;B=2.

1. Upprepa den här proceduren för varje .jsp-sida från vilken du vill hämta ytterligare data.
