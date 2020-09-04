---
description: Instruktioner för installation och konfigurering av Sensor för Sun Java System Application Server Standard Edition 7 som körs i Windows Server 2000 eller senare.
title: Sun Java Server på Windows Server 2000 eller senare
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---


# Sun Java Server på Windows Server 2000 eller senare{#sun-java-server-on-windows-server-or-later}

Instruktioner för installation och konfigurering av Sensor för Sun Java System Application Server Standard Edition 7 som körs i Windows Server 2000 eller senare.

Programfilerna för Sensor paketeras i en installationsfil som du får från hämtningsplatsen för Adobe. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

Sensorn stöder följande servrar som körs under RedHat Linux 7.x eller senare eller Sun Solaris SPARC 2.6 eller senare:

Om du vill installera och konfigurera sensorn måste du utföra följande steg:

## Installera programfilerna {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedur för att extrahera och installera programfilerna för Sensor till servern.

1. I Netscape Enterprise, iPlanet, Sun ONE och Sun Java System Server skapar du en katalog där du kan installera Sensor-programfilerna. Tänk på att diskkön finns i den här katalogen, så se till att enheten du väljer har tillräckligt med utrymme för en kö med den storlek du behöver.

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
   <td colname="col1"> saf_visual_Sciences.dll </td> 
   <td colname="col2"> Insamlingsmodulen. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/visual_sciences</i> </td> 
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

1. Välj Tillbehör > Kommandotolk på Start-menyn i Windows.
1. I kommandotolkfönstret navigerar du till katalogen där du installerade Sensor och kör följande kommando:

   ```
   txlog /regserver
   ```

   Det här kommandot startar sändaren, skapar diskkön och registrerar Sensor som en Windows-tjänst.

1. Bekräfta att sändaren fungerar som den ska genom att klicka på Start > Kontrollpanelen > Administrationsverktyg > Tjänster. Leta reda på posten för sensorn i tjänstlistan och bekräfta att statusen är Startad och startmetoden är Automatisk. Stäng sedan kontrollpanelen Tjänster.
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

## Ändra startskriptet {#section-19a38f27c9f44adf88f8910f5ed483a3}

I filen init.conf (t.ex. C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf) lägger du till följande rader i slutet av filen:

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

I filen obj.conf (t.ex. C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf) lägger du till följande rader direkt under den befintliga `<Object name="default">` raden:

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```

