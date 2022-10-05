---
description: Detaljerade anvisningar för installation och konfigurering av Sensor för Apache Jakarta Tomcat 4.1 eller senare som körs med Windows Server 2000 eller senare.
title: Tomcat Server på Windows Server 2000 eller senare
uuid: 58feec67-ffbb-4f25-8f22-3d109d464e9a
exl-id: 6f4f1592-2b7d-434a-b292-9333e170f851
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1199'
ht-degree: 0%

---

# Tomcat Server på Windows Server 2000 eller senare{#tomcat-server-on-windows-server-or-later}

{{eol}}

Detaljerade anvisningar för installation och konfigurering av Sensor för Apache Jakarta Tomcat 4.1 eller senare som körs med Windows Server 2000 eller senare.

Programfilerna för Sensor paketeras i en installationsfil som du får från hämtningsplatsen för Adobe. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

J2EE-implementeringar som stöds omfattar:

* JBoss Server 4.0.5 eller senare som körs på Microsoft Windows Server 2000 eller senare.

Om du vill installera och konfigurera sensorn måste du utföra följande steg:

## Installera programfilerna {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedur för att extrahera och installera programfilerna för Sensor.

1. Skapa en katalog på din Tomcat-server där du kan installera Sensor-programfilerna. Tänk på att diskkön finns i den här katalogen, så se till att enheten du väljer har tillräckligt med utrymme för en kö med den storlek du behöver.

   ```
   C:\VisualSensor
   ```

1. Extrahera innehållet i installationsfilen till den katalog du just skapade. Under det här steget installerar Sensor följande filer:

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
   <td colname="col1"> visual_sciences.dll </td> 
   <td colname="col2"> Insamlingsmodulen. </td> 
   <td colname="col3"> I alla kataloger. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> Insamlarens bibliotek för inläsningsmodulen </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> Sändarprogrammet. </td> 
   <td colname="col3"> I alla kataloger </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensorkonfigurationsfilen. </td> 
   <td colname="col3"> I alla kataloger </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certifikatet som används för att validera det digitala certifikat som Insight Server visar under anslutningsprocessen </td> 
   <td colname="col3"> I alla kataloger </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Installationspaketet innehåller en kalkylbladsfil med namnet [!DNL TestExperiment.xls]. Detta kalkylblad är ett verktyg som arkitekter använder för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen, så du behöver inte installera filen på den dator där sensorn körs (du kan välja att göra det). Du kanske istället vill kopiera filen till en plats där arkitekterna kan komma åt den eller extrahera filen från installationspaketet efter behov. Mer information om kontrollerade försök finns i handboken om insiktskontrollerade experiment.

## Redigera sensorkonfigurationsfilen {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

The [!DNL txlogd.conf] filen innehåller konfigurationsparametrarna för sensorn.

Du måste redigera den här filen för att bland annat ange storlek och plats för diskköfilen, adressen till Insight Server och det ID som ska kopplas till händelsedata som skapas av den här sensorn.

Konfigurationsfilen innehåller obligatoriska parametrar och valfria parametrar.

* **Obligatoriska parametrar** är inställningar som du måste ange när du installerar sensor. Utan dessa inställningar kan sensorn inte köras.
* **Valfria parametrar** är inställningar som är standard för fördefinierade värden (som du kan ändra) eller aktivera valfria funktioner.

**Så här redigerar du Sensor-konfigurationsfilen**

* Öppna [!DNL /etc/txlogd.conf] i en textredigerare och ange obligatoriska parametrar samt eventuella valfria parametrar.
* Spara och stäng filen.

**Så här redigerar du Sensor-konfigurationsfilen**

1. Öppna [!DNL /etc/txlogd.conf] i en textredigerare och ange obligatoriska parametrar samt eventuella valfria parametrar.
1. Spara och stäng filen.

## Starta sändaren och skapa diskkön {#section-55630de65f264274aefd771da2002852}

När du har konfigurerat filen txlogd.conf kan du starta överföringsprogrammet, registrera det som en Windows-tjänst och skapa diskkön.

1. Välj Tillbehör > Kommandotolk på Start-menyn i Windows.
1. I kommandotolkfönstret navigerar du till katalogen där du installerade Sensor och kör följande kommando:

   ```
   txlog /regserver
   ```

   Det här kommandot startar sändaren, skapar diskkön och registrerar Sensor som en Windows-tjänst.

1. Bekräfta att sändaren fungerar som den ska genom att klicka på Start > Kontrollpanelen > Administrationsverktyg > Tjänster.

   >[!NOTE]
   >
   >Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. Leta reda på posten för sensorn i tjänstlistan och bekräfta att statusen är Startad och startmetoden är Automatisk.
   1. Stäng kontrollpanelen Tjänster.

1. Om du vill kontrollera om sändaren råkade ut för fel under starten klickar du på Start > Kontrollpanelen > Administrationsverktyg > Loggboken för att öppna Loggboken.

   1. Välj programloggen i den vänstra rutan i fönstret för Loggboken.
   1. I den högra rutan söker du efter händelser med Adobe i kolumnen Källa.
   1. Om du hittar ett fel från &quot;Adobe&quot; dubbelklickar du på felet för att visa fönstret Händelseegenskaper. Det här fönstret innehåller detaljerad information om felet.

1. Stäng Loggboken när du är klar med granskningen av programloggen.
1. Kontrollera att sändaren har skapat diskkön (Diskq2000.log) i den katalog där du installerade Sensor-programfilerna och att det är den storlek som du angav i parametern QueueSize i filen txlogd.conf.

   Om kön inte har skapats korrekt:

   1. Granska filen txtlogd.conf och kontrollera att parametern QueueSize är korrekt inställd.
   1. Kontrollera att enheten som du installerade Sensor på har tillräckligt med ledigt utrymme för en fil med den storlek som anges i parametern QueueSize.
   1. Stoppa sändaren med hjälp av kontrollpanelen Tjänster i Windows.
   1. Ta bort köfilen.
   1. Registrera om Sensor som en Windows-tjänst: Välj Tillbehör > Kommandotolk på Start-menyn i Windows. I kommandotolkfönstret navigerar du till katalogen där du installerade Sensor och kör följande kommando:

      ```
      txlog /regserver
      ```

Sändaren är utformad för att köras kontinuerligt. Om du startar om datorn startas sändaren om automatiskt. Om du behöver starta och stoppa sändaren manuellt kan du göra det med hjälp av kontrollpanelen Tjänster i Windows.

## Lägg till insamlaren på webbservern {#section-c5b83ae4ebce430aa764f951e849b333}

För JBoss-servrar fungerar insamlaren som ett filter i serverbehållaren.

Om du vill lägga till insamlaren på webbservern måste du redigera [!DNL web.xml] så som beskrivs nedan och starta om webbprogrammet.

1. Använd en textredigerare för att öppna [!DNL web.xml] för webbservern vars händelser Sensor fångar.
1. Lägg till följande `<filter>` och `<filter-mapping>` -element till beskrivningsfilen. Om du inte har installerat txlogd.conf i katalogen /etc måste du ange rätt sökväg till filen i `<param-value>` element:

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

1. Starta om webbserverprocessen (du behöver inte starta om hela serverdatorn, utan bara starta om webbserverprocessen). Insamlaren läses in med webbservern och börjar samla in händelsedata och skriva dem till diskkön.

## Ändra sökvägen till Java-biblioteket {#section-0dae181ef8884f10a57f6cfda8500969}

Instruktioner för att lägga till visual_Sciences.dll i Tomcat java-bibliotekssökvägen.

1. Navigera till installationskatalogen för Tomcat på Windows-servern. (Tomcat > bin)
1. Kör Tomcat9w.exe (Common daemon service manager) under mappen bin.

   Lägg till en ny rad under Java-alternativen på fliken Java:

   ```
   -Djava.library.path=C:\Sensor directory
   ```

   Där [!DNL C:\Sensor] är den katalog som innehåller [!DNL visual_sciences.dll] -fil.

## Hämta ytterligare data {#section-9483b663cbd0432daaca50c1089c7fca}

Du kan samla in ytterligare mätdata från J2EE-baserade webbprogram med hjälp av funktionen appendToLog().

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
