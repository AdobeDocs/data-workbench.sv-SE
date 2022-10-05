---
description: Instruktioner om hur du installerar och konfigurerar Sensor för Internet Information Services (IIS) 5.x eller 6.x som körs med Microsoft Windows Server 2000 eller senare.
title: Microsoft IIS på Windows Server 2000 eller senare
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
exl-id: e4b5ac44-b0ac-43be-9b9c-180a64354081
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 0%

---

# Microsoft IIS på Windows Server 2000 eller senare{#microsoft-iis-on-windows-server-or-later}

{{eol}}

Instruktioner om hur du installerar och konfigurerar Sensor för Internet Information Services (IIS) 5.x eller 6.x som körs med Microsoft Windows Server 2000 eller senare.

När du använder IIS 6.x måste loggning vara aktiverat för att sensorn ska fungera korrekt. Om du har inaktiverat loggning för att minska I/O-disken kan du aktivera loggning utan att skriva data till loggarna. Aktivera loggning och rensa sedan alla fält på fliken Avancerat i Egenskaper för W3C Extended Log File Format. Kontakta Adobe Consulting Services om du behöver hjälp.

Programfilerna för Sensor paketeras i en installationsfil som du får från hämtningsplatsen för Adobe. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

Om du vill installera och konfigurera sensorn måste du utföra följande steg på hög nivå:

## 1. Installera programfilerna {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

När Sensor körs på Windows IIS måste programfilerna och diskköfilen finnas i samma katalog.

Innan du installerar programfilerna måste du därför bestämma var du vill underhålla diskkön, eftersom det också är där du måste installera programfilerna.

Använd följande procedur för att extrahera och installera programfilerna för Sensor.

1. På din Windows-dator skapar du en katalog där Sensor-programfilerna ska installeras. Tänk på att diskkön också finns i den här katalogen, så se till att enheten du väljer har tillräckligt med utrymme för en kö med den storlek du behöver.

   Till exempel: C:\VisualSensor

1. Extrahera innehållet i installationsfilen till den katalog du just skapade. Under det här steget installerar Sensor följande filer:

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1">
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
   <td colname="col1"> qlog.dll </td>
   <td colname="col2"> Samlarmodulen (ett ISAPI-filter). </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>En Excel-kalkylbladsfil som arkitekter kan använda för att konfigurera ett kontrollerat experiment. </p> <p>Sensorn använder inte den här filen. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> trust_ca_cert.pem </td>
   <td colname="col2"> Certifikatet som används för att validera det digitala certifikat som Insight Server visar under anslutningsprocessen. </td>
  </tr>
  <tr>
   <td colname="col1"> TXLog.exe </td>
   <td colname="col2"> Sändarprogrammet. </td>
  </tr>
  <tr>
   <td colname="col1"> txlogd.conf </td>
   <td colname="col2"> Sensorkonfigurationsfilen. </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Installationspaketet innehåller en kalkylbladsfil som heter TestExperiment.xls. Detta kalkylblad är ett verktyg som arkitekter använder för att konfigurera ett kontrollerat experiment. Sensorn använder inte den här filen, så du behöver inte installera filen på den dator där sensorn körs (du kan välja att göra det). Du kanske istället vill kopiera filen till en plats där arkitekterna kan komma åt den eller extrahera filen från installationspaketet efter behov. Mer information om kontrollerade försök finns i handboken om insiktskontrollerade experiment.

## 2. Redigera konfigurationsfilen {#section-206daf855e664f16af9a96a5cd3e62b1}

Filen txlogd.conf innehåller konfigurationsparametrarna för Sensor.

Du måste redigera filen för att bland annat ange storleken på diskkön, adressen till Insight Server och det ID som ska kopplas till data som produceras av den här sensorn. Konfigurationsfilen innehåller obligatoriska parametrar och valfria parametrar.

* **Obligatoriska parametrar** är inställningar som du måste ange när du installerar sensor. Utan dessa inställningar kan sensorn inte köras.
* **Valfria parametrar** är inställningar som är standard för fördefinierade värden (som du kan ändra) eller aktivera valfria funktioner.

**Så här redigerar du Sensor-konfigurationsfilen**

1. Öppna `<SensorDirectory>/txlogd.conf` i en textredigerare och ange obligatoriska parametrar samt eventuella valfria parametrar.

   Mer information om parametrarna txlogd.conf finns i Filparametrar för sensorn Txlogd.conf.

   Exempel på slutförda konfigurationsfiler finns i Konfigurationsfiler för sensorprov.

1. Spara och stäng filen.

## 3. Starta sändaren och skapa diskkön {#section-a0af390ee1954109bcff5d9f09798683}

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

## Lägg till insamlaren på webbservern {#section-682dc480e5574791ac18da104daf7906}

För IIS är insamlaren ett ISAPI-filter som du lägger till på webbservern i IIS.

1. Öppna IIS-hanteraren med Start > Administrationsverktyg > IIS-hanteraren (Internet Information Services).
1. Expandera noderna Lokal dator och Webbplatser.
1. Högerklicka på den webbplats där du vill lägga till insamlaren och välj Egenskaper.
1. Välj fliken ISAPI-filter och klicka på Lägg till.
1. Ange ett visningsnamn för filtret i fältet Filternamn. Det föreslagna filternamnet är &quot;Sensor&quot;.
1. Klicka på Bläddra, markera filen qlog.dll (finns i den katalog där du installerade Sensor) och klicka på OK.
1. Klicka på OK för att lägga till filtret.

   När du har lagt till filtret kan insamlaren användas direkt och kan samla in data. En grön pil uppåt ska visas i statuskolumnen på fliken ISAPI-filter i IIS-hanteraren. Du kanske inte ser den gröna pilen förrän trafiken faktiskt flödar genom filtret. I det här fallet måste du skicka en begäran till webbservern för att bekräfta att insamlaren fungerar som den ska.

Om den gröna pilen inte visas efter trafikflödet till insamlaren utför du följande steg:

1. Klicka på Start > Administrationsverktyg > Loggboken för att kontrollera om det finns fel i Loggboken.

   >[!NOTE]
   >
   >Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

1. Markera programloggen i den vänstra rutan i fönstret för Loggboken.
1. I den högra rutan söker du efter händelser med Adobe i kolumnen Källa.
1. Om du hittar ett fel dubbelklickar du på felet för att visa fönstret Händelseegenskaper.

## Hämta ytterligare data {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

Webbsidor är ofta strukturerade med programmeringsspråket ASP (Active Server Pages).

ASP är en Microsoft-teknik som körs i IIS. När en webbläsare begär en ASP-fil skickar IIS begäran till ASP-motorn. ASP-motorn läser ASP-filen, rad för rad, och kör skripten i filen. Slutligen returneras ASP-filen till webbläsaren som HTML. ASP tillhandahåller RESPOND- eller REQUEST-objekt som, utöver andra användningar, tillåter svar eller begäran från användarfrågor eller data som skickas från HTML-formulär.

I vissa fall kanske du inte vill lägga till de värden som anges i formulären till den URL som visas i adressfältet i en användares webbläsare eller som kan visas i själva HTML-koden. Med ett enkelt ASP-skript på serversidan kan du lägga till formulärfältsnamn och deras respektive värden i loggfilen utan att göra dem tillgängliga i användarens webbläsare eller bädda in dem i HTML-filen. Om du vill hämta in de faktiska formulärvärdena som anges i vissa formulär på webbplatsen måste du lägga till några kodrader för att lägga till formulärvärdena i loggbegäran.

Inkludera följande kod på en formulärs bearbetningssida för att lägga till de angivna formulärvärdena i data som efterfrågas (utöver att skriva de skickade formulärvärdena till en extern databas eller annan plats):

```
var sName= Request.Form("Name");
var sCity= Request.Form("City");
var sState= Request.Form("State");
var sZip= Request.Form("Zip");

Response.AppendToLog("&v_1=" +  sName);
Response.AppendToLog("&v_2=" +  sCity);
Response.AppendToLog("&v_3=" +  sState);
Response.AppendToLog("&v_4=" +  sZip);
```

Den här processen lägger till de formulärvärden som definierats till data som efterfrågas på sidan Formulärbearbetning. I loggdata är de tillagda värdena tillgängliga som frågesträngar på sidan Formulärbearbetning, vilket visas nedan. v_1, v_2, v_3 och v_4 skulle nu vara frågesträngar som innehåller data som anges i rätt formulärfält. Syntaxen som beskrivs i föregående exempel kan dupliceras för alla ytterligare formulärfält och värden som du vill hämta:

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Om du vill att alla formulärfält och värden ska hämtas och vara tillgängliga för analys kan du använda följande syntax:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

Det här exemplet tar alla formulärfält som finns i HTML tillsammans med deras respektive värden och lägger till dem som frågesträngar i loggposten för sidan Formulärbearbetning. Observera att detta inkluderar alla dolda fält i formuläret.

Loggdata ska utökas enligt följande tabell:

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_1 | Värde som är associerat med frågesträngen NAME | v_1=Sven Svensson |
| v_2 | Värde som är associerat med CITY-frågesträngen | v_2=Los Angeles |
| v_3 | Värde som är associerat med STATE-frågesträngen | v_3=Kalifornien |
| v_4 | Värde som är associerat med ZIP-frågesträngen | v_4=90210 |
