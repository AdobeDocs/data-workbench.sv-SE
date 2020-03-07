---
description: Instruktioner för installation och konfigurering av sensor för Apache Server 1.3, Apache Server 2.0.42 eller senare eller Apache Server 2.2 som körs med Microsoft Windows Server 2000 eller senare.
title: Apache Server 1.3, 2, 2.2 eller 2.4 i Windows Server 2000 eller senare
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3, 2, 2.2 eller 2.4 i Windows Server 2000 eller senare{#apache-server-or-on-windows-server-or-later}

Instruktioner för installation och konfigurering av sensor för Apache Server 1.3, Apache Server 2.0.42 eller senare eller Apache Server 2.2 som körs med Microsoft Windows Server 2000 eller senare.

Programfilerna för Sensor paketeras i en installationsfil som du får från Adobes nedladdningswebbplats. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

* Apache Server 1.3
* Apache Server 2.0.42 eller senare
* Apache Server 2.2 som körs med Microsoft Windows Server 2000 eller senare

## Installera programfilerna {#section-2f3e85083b4f4aa989a85997330e86ae}

Innan du installerar programfilerna måste du bestämma var du vill underhålla diskkön, eftersom det också är där du måste installera programfilerna.Procedur för att extrahera och installera programfilerna för Sensor.

Om du vill installera och konfigurera sensorn måste du utföra följande steg:

1. På din Windows-dator skapar du en katalog där Sensor-programfilerna ska installeras. Tänk på att diskkön också finns i den här katalogen, så se till att enheten du väljer har tillräckligt med utrymme för en kö med den storlek du behöver.

   ```
   C:\VisualSensor
   ```

1. Extrahera innehållet i installationsfilen till den katalog du just skapade. Under det här steget installerar Sensor följande filer:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fil </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Meddelanden i Loggboken. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> Samlarmodulen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>En Excel-kalkylbladsfil som arkitekter kan använda för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certifikatet som används för att validera det digitala certifikat som Insight Server visar under anslutningsprocessen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Sändarprogrammet </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensorkonfigurationsfilen </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Installationspaketet innehåller en kalkylbladsfil som heter TestExperiment.xls. Detta kalkylblad är ett verktyg som arkitekter använder för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen, så du behöver inte installera filen på den dator där sensorn körs (du kan välja att göra det). Du kanske istället vill kopiera filen till en plats där arkitekterna kan komma åt den eller extrahera filen från installationspaketet efter behov. Mer information om kontrollerade försök finns i handboken om insiktskontrollerade experiment.

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
1. Lägg till följande två rader i slutet av filen:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Linjerna är skiftlägeskänsliga. Skriv dem exakt som de visas ovan.

1. Starta om webbserverprocessen (du behöver inte starta om hela serverdatorn, utan bara starta om webbserverprocessen). Insamlaren läses in med webbservern och börjar samla in händelsedata och skriva dem till diskkön.

