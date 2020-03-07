---
description: Instruktioner för att konfigurera administrativa varningar för Insight Server, Repeater eller Transform.
solution: Insight
title: Konfigurationsinställningar för administrativa aviseringar
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurationsinställningar för administrativa aviseringar{#administrative-alerts-configuration-settings}

Instruktioner för att konfigurera administrativa varningar för Insight Server, Repeater eller Transform.

Slutför parametrarna i följande fil:

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Kategori </td> 
   <td colname="col2"> Namnet på kategorin. En kategori av standard krävs. Se Felkategorier i den här tabellen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felkategorier </td> 
   <td colname="col2"> Gör att du kan kategorisera fel i samband med felkategoriseringsfilen. Varje felkategori kan ha en egen uppsättning mottagare och en egen begränsning. Du kan till exempel skapa en kritisk kategori med en begränsningsfördröjning på 0, så att varje allvarligt fel skickas med e-post direkt till mottagarna som anges i mottagarlistan. Fel som inte matchar en delsträng i filen för felkategorisering tilldelas till kategorin Standard. Om du vill lägga till en ny kategori högerklickar du på ett nummer och klickar på <span class="uicontrol"> Lägg till ny </span> &gt; <span class="uicontrol"> Felkategori </span>. Du kan också kopiera eller ta bort dem med hjälp av högerklicksåtgärden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fel i kategoriseringsfil </td> 
   <td colname="col2"> <p>Namnet på filen som du vill använda för att kategorisera varje varning. Du skapar den här filen med Anteckningar. Filen ska ha tre kolumner på varje rad, avgränsade med tabbar. Den första kolumnen är en sträng som matchar i fel. Ett ^-tecken matchar början och ett $ matchar slutet av strängen. alla andra tecken ordagrant matchas. Den andra kolumnen är en kategori för matchande fel, som finns i Felkategorier. Det tredje är ett alternativt meddelande som läggs till i det faktiska felmeddelandet i e-postmeddelanden som skickas. Om ingen fil anges kategoriseras alla fel som standard. </p> <p>Ett exempel på den här filen finns i <span class="filepath"> Error Categories.txt- </span> filen i katalogen Lookups. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Från </td> 
   <td colname="col2"> <p>Adress som visas i parametern "from" i e-postmeddelandet. </p> <p>Exempel: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minsta diskutrymme (MB) </td> 
   <td colname="col2"> Servern genererar ett e-postmeddelande när tillgängligt diskutrymme i någon katalog som används av servern hamnar under det här värdet. Standardvärdet är 1 000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tidsgräns för sensorvarning (min) </td> 
   <td colname="col2"> <p>Servern genererar en e-postavisering när den inte har fått några data från en konfigurerad och tidigare ansluten <span class="wintitle"> sensor </span> inom det här tidsfönstret. Standardvärdet är 15. </p> <p> <p>Obs!  Timeout för <span class="wintitle"> sensorvarning </span> fungerar bara om en befintlig anslutning till en <span class="wintitle"> sensor </span> släpps. Om servertjänsten stoppas och startas om och <span class="wintitle"> sensorerna </span> inte ansluter, genererar servern inga e-postvarningar. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveradress </td> 
   <td colname="col2"> <p>Adress till SMTP-servern för utgående e-post. </p> <p>Exempel: <span class="filepath"> mail.mycompany.com </span></p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serverlösenord </td> 
   <td colname="col2"> <p>Lösenordet för inloggning på SMTP-servern. Den här parametern är valfri om inte inloggning krävs för att skicka e-post. </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Serveranvändare </td> 
   <td colname="col2"> <p>Användar-ID/namn för inloggning på SMTP-servern. Den här parametern är valfri om inte inloggning krävs för att skicka e-post. </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Begränsningsfördröjning (sekunder) </td> 
   <td colname="col2"> Det minsta antalet sekunder som måste förflyta mellan två fel i den kategorin för att ett e-postmeddelande ska kunna skickas. Värdet 0 innebär att e-postmeddelandet skickas omedelbart. </td> 
  </tr> 
 </tbody> 
</table>

