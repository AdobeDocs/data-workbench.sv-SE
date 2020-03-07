---
description: Detaljerade anvisningar för installation och konfigurering av Sensor för J2EE-implementeringar som körs på RedHat Linux 7.x eller senare, Sun Solaris SPARC 2.6 eller senare eller Sun Solaris x86 9 eller senare.
title: JBoss-, Tomcat- och WebLogic-servrar i RedHat Linux eller Sun Solaris
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# JBoss-, Tomcat- och WebLogic-servrar i RedHat Linux eller Sun Solaris{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

Detaljerade anvisningar för installation och konfigurering av Sensor för J2EE-implementeringar som körs på RedHat Linux 7.x eller senare, Sun Solaris SPARC 2.6 eller senare eller Sun Solaris x86 9 eller senare.

Programfilerna för Sensor paketeras i en installationsfil som du får från Adobes nedladdningswebbplats. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

J2EE-implementeringar som stöds omfattar:

* JBoss Server 3.2.x eller senare
* Apache Jakarta Tomcat Server 4.1 eller senare
* WebLogic Server 6.x eller senare

Om du vill installera och konfigurera sensorn måste du utföra följande steg:

## Installera programfilerna {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedur för att extrahera och installera programfilerna för Sensor.

1. Logga in som rotanvändare eller som användare med rotbehörighet.
1. Dekomprimera och packa upp installationsfilen med följande kommando:

   * I Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * På Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Kopiera de opackade programfilerna till katalogerna i följande tabell:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fil </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Målkatalog </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Insamlingsmodulen. </td> 
   <td colname="col3"> <i> IBMHttpServer/moduler</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Sändarprogrammet. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>—OR—</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensorkonfigurationsfilen. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certifikatet som används för att validera det digitala certifikat som Insight Server visar under anslutningsprocessen </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Installationspaketet innehåller en kalkylbladsfil som heter TestExperiment.xls. Detta kalkylblad är ett verktyg som arkitekter använder för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen, så du behöver inte installera filen på den dator där sensorn körs (du kan välja att göra det). Du kanske istället vill kopiera filen till en plats där arkitekterna kan komma åt den eller extrahera filen från installationspaketet efter behov. Mer information om kontrollerade försök finns i handboken om insiktskontrollerade experiment.

**Behörigheter för programfilerna**

>[!NOTE]
>
>Felaktiga behörigheter för programfilerna orsakar de flesta problem som uppstår när Sensor installeras. Kontrollera att du har angett exakt den behörighet som anges i det här avsnittet.
>
>Som standard har programfilerna i tjärfilen följande behörigheter. Beroende på hur systemet är konfigurerat kan dessa inställningar ändras (omaskeras) när du extraherar filerna. Om du vill återställa behörigheterna till de rekommenderade standardinställningarna använder du chmod-kommandona nedan. Kontrollera att katalogerna som du har installerat filerna i tillåter minst den här åtkomstnivån.

| Fil | Standardbehörigheter | chmod, kommando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Redigera sensorkonfigurationsfilen {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Filen innehåller [!DNL txlogd.conf] konfigurationsparametrarna för sensorn.

Du måste redigera den här filen för att bland annat ange storlek och plats för diskköfilen, adressen till Insight Server och det ID som ska kopplas till händelsedata som skapas av den här sensorn.

Konfigurationsfilen innehåller obligatoriska parametrar och valfria parametrar.

* **Obligatoriska parametrar** är inställningar som du måste ange när du installerar sensorn. Utan dessa inställningar kan sensorn inte köras.
* **Valfria parametrar** är inställningar som är standard för fördefinierade värden (som du kan ändra) eller aktivera valfria funktioner.

**Så här redigerar du Sensor-konfigurationsfilen**

* Öppna [!DNL /etc/txlogd.conf] filen i en textredigerare och ange de obligatoriska parametrarna samt eventuella valfria parametrar.
* Spara och stäng filen.

**Så här redigerar du Sensor-konfigurationsfilen**

1. Öppna [!DNL /etc/txlogd.conf] filen i en textredigerare och ange de obligatoriska parametrarna samt eventuella valfria parametrar.
1. Spara och stäng filen.

## Starta sändaren och skapa diskkön {#section-55630de65f264274aefd771da2002852}

När du har konfigurerat filen txlogd.conf kan du starta överföringsprogrammet, registrera det som en Windows-tjänst och skapa diskkön.

1. Om katalogen som diskkön finns i inte redan finns skapar du den. Kontrollera att katalogen ger både insamlingsmodulen och sändarprogrammet läs- och skrivåtkomst till filen.

   Mer information om de behörigheter som krävs för diskköfilerna finns i Sensor UNIX File Permissions (Sensorfilbehörigheter för UNIX-filer).
1. Kör följande kommando på den dator där Sensor är installerat för att starta sändaren:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * Alternativet &quot;i&quot; i det här kommandot startar sändaren i &quot;interaktivt läge&quot;. I det här läget visas sändarmeddelanden på skärmen och du kan även använda tangentbordskommandon för att interagera med sändaren.
   * Alternativet &quot;c&quot; dirigerar sändaren till diskkön.
   * Alternativet &quot;f&quot; anger platsen för konfigurationsfilen.
   Mer information om de alternativ du kan använda när du startar sändaren finns i Kommandoradsalternativ för sensorsändaren.

1. Kontrollera att sändaren har skapat diskkön på den plats som anges i parametern QueueFile och med den storlek som anges i parametern QueueSize.
1. Om kön inte har skapats på rätt sätt skriver du Ctrl+C för att avsluta sändaren och gör sedan följande:

   1. Granska filen txtlogd.conf och kontrollera att parametrarna QueueFile och QueueSize är korrekt inställda.
   1. Kontrollera att den enhet som diskkön är tilldelad till är i drift och har tillräckligt med ledigt utrymme för en fil med den storlek som anges i parametern QueueSize.
   1. Gör nödvändiga korrigeringar och upprepa proceduren.

## Lägg till insamlaren på webbservern {#section-c5b83ae4ebce430aa764f951e849b333}

För Apache-servrar är samlaren ett dynamiskt delat objekt som du läser in i webbserverprocessen.

Om du vill lägga till insamlaren på webbservern måste du redigera [!DNL httpd.conf] filen enligt beskrivningen nedan och starta om webbservern.

>[!NOTE]
>
>Om sensorn hämtar data för flera webbservrar på serverdatorn måste du utföra följande procedur för varje webbserver.

1. Använd en textredigerare och öppna [!DNL httpd.conf]filen för webbservern vars händelser sensorn fångar.
1. Lägg till följande `<filter>` och `<filter-mapping>` element i beskrivningsfilen. Om du inte har installerat txlogd.conf i katalogen /etc måste du ange rätt sökväg till den här filen i `<param-value>` elementet:

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
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

1. Starta om webbserverprocessen (du behöver inte starta om hela serverdatorn, utan bara starta om webbserverprocessen). Insamlaren läses in med webbservern och börjar samla in händelsedata och skriva dem till diskkön.

## Testa sensorn {#section-0dae181ef8884f10a57f6cfda8500969}

Kontrollera att insamlaren samlar in händelsedata och att sändaren skickar dem till målservern för Insight.

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

## Lägg till sändaren i systemstartskriptet {#section-19a38f27c9f44adf88f8910f5ed483a3}

Information om automatisk inläsning av sändaren till systemets startskript.

För att säkerställa att sändaren läses in automatiskt när webbserverdatorn startas om lägger du till följande kommando (som startar sändaren) i systemets startskript:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Det här kommandot startar sändaren som ett daemon. Operations- och felmeddelanden som sändaren genererar skrivs till [!DNL syslog].

Standardinställningen för Solaris är 60. Baserat på tester utförda med Sensor, som använder tre semaforer för varje instans, rekommenderar Adobe att du använder 1024 som inställning. Det här antalet är tillräckligt högt för att sensorn ska fungera tillsammans med andra program på servern som kan kräva semaforer, men som inte påverkar prestandan. Som stöd för denna rekommendation noterar ni att Adrian Cockcroft angav följande i sin bok Sun Performance and Tuning (Prentice Hall, oktober 1994): &quot;Databaser använder ofta många delade minnes- och semaforinställningar. Dessa påverkar inte prestanda. så länge de är tillräckligt stora kommer programmen att köras.&quot;

## Hämta ytterligare data {#section-9483b663cbd0432daaca50c1089c7fca}

Sensorer för alla plattformar kan samla in alla data som är tillgängliga i rubrikerna för HTTP-begäran och -svar.

Sensorerna för J2EE-plattformen erbjuder en mekanism för insamling av data som inte är tillgängliga på andra plattformar. Insamlaren för J2EE-plattformen (J2EE-insamlaren) finns i programlagret, vilket gör att den kan samla in känsliga data som bara är tillgängliga för programmet och som inte ska visas genom sidtaggning eller i sidhuvudena.

>[!NOTE]
>
>Sidmärkord och sidhuvudsändringar kan dölja data, men är fortfarande tillgängliga för dem som undersöker källkoden för en sida eller tittar på sidhuvudena med hjälp av verktygen för webbläsarplugin.

J2EE-insamlaren kan till exempel användas för att samla in kostnadsdata per klickning (CPC) för länkar som visas på en sida, känslig partnerinformation på en sida och många andra datapunkter. J2EE-miljön gör det enkelt för dig att ändra din WEBAPP för att hämta in anpassade data med vår insamlingsklass.

När en sensor för J2EE-plattformen tar emot en begäran, anropas en samlingsklass som importerar funktionen appendToLog. Funktionen appendToLog lägger till frågesträngsparametrarna som anges i funktionen appendToLog till den första begäran. Detta resulterar i URI:n för den initiala begäran som innehåller ytterligare par med namn/värde för frågesträngar som motsvarar namnen och värdena på de data som hämtas. CPC=20 skulle till exempel läggas till den första begäran när värdet för en viss annonsplacering eller klicklänken är 20 cent. Insight Server bearbetar dessa värden i datauppsättningen för analys. En annan fördel med den här samlingsmetoden är att den tillåter insamling av ytterligare data utan att skapa extra loggposter, vilket kan vara fallet med sidtaggningsmetoder.

Mer information om bearbetning finns i konfigurationsguiden för datauppsättningar.

**Hämta ytterligare data från en sida**

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

