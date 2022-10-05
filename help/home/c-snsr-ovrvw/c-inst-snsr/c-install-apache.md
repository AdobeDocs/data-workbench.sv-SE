---
description: Instruktioner om hur du installerar och konfigurerar Apache Server 2.0.40, 2.0.42 eller senare, Apache Server 2.2 eller Apache Server 2.4 i Linux, Sun Solaris eller FreeBSD.
title: Apache Server 2.0.40, 2.0.42 eller senare och Apache Server 2.2 eller 2.4 i Linux, Solaris eller FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
exl-id: d5b943be-e9ca-4601-88c7-bb2bfdc0d080
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 0%

---

# Apache Server 2.0.40, 2.0.42 eller senare och Apache Server 2.2 eller 2.4 i Linux, Solaris eller FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

{{eol}}

Instruktioner om hur du installerar och konfigurerar Apache Server 2.0.40, 2.0.42 eller senare, Apache Server 2.2 eller Apache Server 2.4 i Linux, Sun Solaris eller FreeBSD.

Programfilerna för Sensor paketeras i en installationsfil som du får från hämtningsplatsen för Adobe. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

Om du vill installera och konfigurera sensorn måste du utföra följande steg på hög nivå:

Följande Apache-servrar stöds:

* Apache Server 2.0.40 som körs under RedHat Linux 7.x eller senare, eller Sun Solaris SPARC 2.6 eller senare.
* Apache Server 2.0.40, 2.0.42 eller senare, Apache Server 2.2 eller Apache Server 2.4 i Linux, Sun Solaris eller FreeBSD
* Apache Server 2.0.42 eller senare som körs under RedHat Linux 7.x eller senare, Sun Solaris SPARC 2.6 eller senare, SUSE Linux 9.x eller senare, eller FreeBSD 5.3.
* Apache Server 2.0.42 eller senare som körs i 64-bitarsversioner av RedHat Linux ES 4 och ES 5.
* Apache Server 2.2 som körs under RedHat Linux 7.x eller senare eller Sun Solaris SPARC 2.6 eller senare.
* Apache Server 2.4 som körs under RedHat Linux 7.x eller senare, eller Sun Solaris x86_64 eller FreeBSD

>[!NOTE]
>
>Även om instruktionerna för att installera sensorer på webbservrar som kör Apache Server version 2.0.40, 2.0.42 eller senare (32-bitars och 64-bitars) eller 2.2 är desamma (förutom där det anges i följande procedurer), skiljer sig installationsfilerna för varje version åt. Innan du installerar sensorn kontrollerar du att du har fått rätt installationsfiler för Apache Server och de operativsystemversioner som du kör.

## Installera programfilerna {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedur för att extrahera och installera programfilerna för Sensor.

1. Logga in som rotanvändare eller som användare med rotbehörighet.
1. Dekomprimera och packa upp installationsfilen med följande kommando:

   * I Linux:

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * På Solaris:

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

## Aktivera loggning på Sametime-servern {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Steg som gör att du kan logga in på Sametime-servern.

1. Använd klienten Lotus Domino Administrator för att ansluta till Lotus Domino-servern som kör Sametime.
1. Klicka på fliken Filer i Lotus Domino Administrator och dubbelklicka sedan på Sametime Configuration - stconfig.nsf för att öppna filen Sametime Configuration.
1. Öppna formuläret Community Services i konfigurationsfilen för Sametime och dubbelklicka någonstans i formuläret för att gå till redigeringsläget.
1. Ställ in chattloggningsflaggan till&quot;strict&quot; och hämtningstjänsttypen till&quot;0x1000&quot;.
1. Spara och stäng formuläret Community Services och stäng sedan konfigurationsfilen för Sametime.
1. Starta om Sametime-servern.

## Redigera sensorkonfigurationsfilen {#section-de0eb4a646394b61abb6cd5a2b706de0}

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

För IBM HTTP-servrar är insamlaren ett dynamiskt delat objekt som du läser in i webbserverprocessen.

Om du vill lägga till insamlaren på webbservern måste du redigera httpd.conf-filen enligt beskrivningen nedan och starta om webbservern.

Om sensorn hämtar data för flera webbservrar på serverdatorn måste du utföra följande procedur för varje webbserver.

1. Använd en textredigerare och öppna filen httpd.conf för webbservern vars händelser Sensor fångar.
1. Lägg till följande två rader i slutet av filen:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
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

För att se till att sändaren läses in automatiskt när webbserverdatorn startas om lägger du till följande kommando (som startar sändaren) i systemets startskript:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Det här kommandot startar sändaren som ett daemon. Åtgärds- och felmeddelanden som skickas till syslog.
