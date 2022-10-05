---
description: Detaljerade anvisningar för installation och konfigurering av Sensor för en Apache Server 1.3.x i RedHat Linux 7.x eller senare, SUSE Linux 9.x eller senare, Sun Solaris SPARC 2.6 eller senare, Sun Solaris x86 9 eller senare, FreeBSD 4 eller senare eller Mac OS X PowerPC.
title: Apache Server 1.3.x i Linux, Sun Solaris, FreeBSD eller Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 0%

---

# Apache Server 1.3.x i Linux, Sun Solaris, FreeBSD eller Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

Detaljerade anvisningar för installation och konfigurering av Sensor för en Apache Server 1.3.x i RedHat Linux 7.x eller senare, SUSE Linux 9.x eller senare, Sun Solaris SPARC 2.6 eller senare, Sun Solaris x86 9 eller senare, FreeBSD 4 eller senare eller Mac OS X PowerPC.

Programfilerna för Sensor paketeras i en installationsfil som du får från hämtningsplatsen för Adobe. Om du inte redan har installationsfilen för sensorn för din webbserver hämtar du den (eller hämtar den från din Adobe-representant) innan du börjar med följande procedurer.

Om du vill installera och konfigurera sensorn måste du utföra följande steg på hög nivå:

## Installera programfilerna {#section-aae323e252394212bf4096d65fdd280c}

Instruktioner för att extrahera och installera programfilerna för Sensor på serverdatorn.

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

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> Insamlarens belastningsmodul </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
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

Som standard har programfilerna i tjärfilen följande behörigheter. Beroende på hur systemet är konfigurerat kan dessa inställningar ändras (omaskeras) när du extraherar filerna. Om du vill återställa behörigheterna till de rekommenderade standardinställningarna använder du chmod-kommandona nedan. Kontrollera att katalogerna som du har installerat filerna i tillåter minst den här åtkomstnivån.

| Fil | Standardbehörigheter | chmod, kommando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Redigera Sensor-konfigurationsfilen {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

The [!DNL txlogd.conf] filen innehåller konfigurationsparametrarna för sensorn.

Du måste redigera filen för att bland annat ange storleken på diskkön, adressen till Insight Server och det ID som ska kopplas till data som produceras av den här sensorn.

Konfigurationsfilen innehåller obligatoriska parametrar och valfria parametrar.

* Obligatoriska parametrar är inställningar som du måste ange när du installerar sensor. Utan dessa inställningar kan sensorn inte köras.
* Valfria parametrar är inställningar som är standard för fördefinierade värden (som du kan ändra) eller aktivera valfria funktioner.

Så här redigerar du Sensor-konfigurationsfilen

1. Öppna filen /etc/txlogd.conf i en textredigerare och ange obligatoriska parametrar samt eventuella valfria parametrar.
1. Spara och stäng filen.

## Starta sändaren och skapa diskkön {#section-a453d912ec3d47aa8e40ccacf527119d}

Instruktioner för hur du skapar diskkön när du har konfigurerat filen txlogd.conf.

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

## Lägg till insamlaren på webbservern {#section-a7fb6425956f4f518ae3a7db091b33d2}

För Apache-servrar är samlaren ett dynamiskt delat objekt som du läser in i webbserverprocessen.

Om du vill lägga till insamlaren på webbservern måste du redigera httpd.conf-filen enligt beskrivningen nedan och starta om webbservern.

Om sensorn hämtar data för flera webbservrar på serverdatorn måste du utföra följande procedur för varje webbserver.

1. Använd en textredigerare för att öppna [!DNL httpd.conf] för webbservern vars händelser Sensor fångar.
1. Lägg till följande rader i slutet av filen:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Linjerna är skiftlägeskänsliga. Skriv dem exakt som de visas ovan.

1. Starta om webbservern. Insamlaren läses in med webbservern och börjar samla in händelsedata och skriva dem till diskkön.

## Testa sensorn {#section-83d9f60b39a6474f9c76bee3e19b2575}

Starta sändaren och verifiera att den kan ansluta till Insight Server och överföra händelsedata till den.

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
   * The [!DNL ServerAddress] och [!DNL ServerPort] parametrar anges korrekt i [!DNL txtlogd.conf].

   * Om du angav [!DNL ServerAddress] med ett servernamn kan du försöka använda den numeriska IP-adressen i stället. Värdet för [!DNL CertName] parametern matchar det vanliga namnet som visas i det digitala certifikatet för målservern Insight exakt.

## Lägg till sändaren i systemstartskriptet {#section-4e1ffa6e043941ab91411d91d596477a}

Information som ser till att sändaren läses in automatiskt när webbserverdatorn startas om.

Lägg till följande kommando (som startar sändaren) i systemets startskript.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Det här kommandot startar sändaren som ett daemon. Åtgärds- och felmeddelanden som skickas till syslog.

>[!NOTE]
>
>Vissa Solaris-användare kan råka ut för felet&quot;Det går inte att hämta mutex&quot;. För att sensorn ska fungera på dessa system måste följande rad antingen läggas till eller redigeras i filen /etc/system:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>Standardinställningen för Solaris är 60. Baserat på tester utförda med Sensor, som använder tre semaforer för varje instans, rekommenderar Adobe att du använder 1024 som inställning. Det här antalet är tillräckligt högt för att sensorn ska fungera tillsammans med andra program på servern som kan kräva semaforer, men som inte påverkar prestandan. Som stöd för denna rekommendation noterar ni att Adrian Cockcroft angav följande i sin bok Sun Performance and Tuning (Prentice Hall, oktober 1994): &quot;Databaser använder ofta många delade minnes- och semaforinställningar. Dessa påverkar inte prestanda. så länge de är tillräckligt stora kommer programmen att köras.&quot;
