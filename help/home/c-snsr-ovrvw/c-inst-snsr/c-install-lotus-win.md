---
description: Instruktioner om hur du installerar och konfigurerar Sensor för Lotus Sametime för Windows 3.1 eller senare som körs med Microsoft Windows Server 2000 eller senare.
title: Lotus Sametime på Windows Server 2000 eller senare
uuid: 5e24da54-7ef6-42cf-b693-cc4fd267af93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Lotus Sametime på Windows Server 2000 eller senare{#lotus-sametime-on-windows-server-or-later}

Instruktioner om hur du installerar och konfigurerar Sensor för Lotus Sametime för Windows 3.1 eller senare som körs med Microsoft Windows Server 2000 eller senare.

Programfilerna för Sensor paketeras i en installationsfil som du får från Adobes nedladdningswebbplats. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

Om du vill installera och konfigurera sensorn måste du utföra följande steg på hög nivå:

## Installera programfilerna {#section-2f3e85083b4f4aa989a85997330e86ae}

När Sensor körs på Sametime måste programfilerna och diskköfilen finnas i samma katalog.

Innan du installerar programfilerna måste du därför bestämma var du vill underhålla diskkön, eftersom det också är där du måste installera programfilerna.

Använd följande procedur för att extrahera och installera programfilerna för Sensor.

1. Stoppa Lotus Domino Server och loggningstjänsten för Sametime Chat.
1. I katalogen Lotus Domino på Windows-datorn tar du bort eller säkerhetskopierar filen StChatLog.dll.
1. Extrahera innehållet i installationsfilen till Lotus Domino-katalogen. Under det här steget installerar Sensor följande filer:

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
   <td colname="col2"> Meddelanden från Loggboken </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stchatlog.dll </td> 
   <td colname="col2"> Samlarmodulen </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>En Excel-kalkylbladsfil som arkitekter kan använda för att konfigurera ett kontrollerat experiment </p> <p>Sensorn använder inte den här filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certifikatet som används för att validera det digitala certifikat som Insight Server visar under anslutningsprocessen </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Sändarprogrammet </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.conf </p> </td> 
   <td colname="col2"> Sensorkonfigurationsfilen </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Installationspaketet innehåller en kalkylbladsfil som heter TestExperiment.xls. Detta kalkylblad är ett verktyg som arkitekter använder för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen, så du behöver inte installera filen på den dator där sensorn körs (du kan välja att göra det). Du kanske istället vill kopiera filen till en plats där arkitekterna kan komma åt den eller extrahera filen från installationspaketet efter behov. Mer information om kontrollerade försök finns i handboken om insiktskontrollerade experiment.

## Aktivera loggning på Sametime-servern {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Steg som gör att du kan logga in på Sametime-servern.

1. Använd klienten Lotus Domino Administrator för att ansluta till Lotus Domino-servern som kör Sametime.
1. Klicka på fliken Filer i Lotus Domino Administrator och dubbelklicka sedan på Sametime Configuration - stconfig.nsf för att öppna filen Sametime Configuration.
1. Öppna formuläret Community Services i konfigurationsfilen för Sametime och dubbelklicka någonstans i formuläret för att gå till redigeringsläget.
1. Ställ in chattloggningsflaggan till&quot;strict&quot; och hämtningstjänsttypen till&quot;0x1000&quot;.
1. Spara och stäng formuläret Community Services och stäng sedan konfigurationsfilen för Sametime.
1. Starta om Sametime-servern.

## Redigera sensorkonfigurationsfilen {#section-de0eb4a646394b61abb6cd5a2b706de0}

Filen txlogd.conf innehåller konfigurationsparametrarna för Sensor.

Du måste redigera den här filen för att bland annat ange storlek och plats för diskköfilen, adressen till Insight Server och det ID som ska kopplas till händelsedata som skapas av den här sensorn.

Konfigurationsfilen innehåller obligatoriska parametrar och valfria parametrar.

* **Obligatoriska parametrar** är inställningar som du måste ange när du installerar sensorn. Utan dessa inställningar kan sensorn inte köras.
* **Valfria parametrar** är inställningar som är standard för fördefinierade värden (som du kan ändra) eller aktivera valfria funktioner.

**Så här redigerar du Sensor-konfigurationsfilen**

* Öppna `<Sensor directory>/txlogd.conf` filen i en textredigerare och ange de obligatoriska parametrarna samt eventuella valfria parametrar.
* Spara och stäng filen.

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

   >[!NOTE]
   >
   >Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. Välj programloggen i den vänstra rutan i fönstret för Loggboken.
   1. I den högra rutan söker du efter händelser med&quot;Adobe&quot; i kolumnen Källa.
   1. Om du hittar ett fel från&quot;Adobe&quot; dubbelklickar du på felet för att visa fönstret Händelseegenskaper. Det här fönstret innehåller detaljerad information om felet.

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

1. Starta om Lotus Domino Server och loggningstjänsten för Sametime-chatt.

