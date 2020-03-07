---
description: 'Sensorn består av tre huvudkomponenter: Datainsamling, Diskkö och Dataöverföring.'
title: Vad är grundläggande komponenter?
uuid: 32e6e8d9-90ee-4db1-8883-dbdf245df26f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vad är grundläggande komponenter?{#what-are-basic-components}

Sensorn består av tre huvudkomponenter: Datainsamlare, diskkö och dataöverföringstjänst.

![](assets/Visual-Sensor.png)

## Datainsamling {#section-f970eaff30364a3c8106d5ec9c1b5caa}

Datainsamlaren (insamlaren) är en NSAPI-, ISAPI-, J2EE-filterserver eller Apache-modul som körs i webbserverprocessen.

Den samlar in råa händelsedata om varje HTTP-begäran som webbservern bearbetar och placerar informationen i diskkön. Om du kör flera instanser av en webbserver på samma dator läser varje instans in sin egen instans av insamlarmodulen. Alla instanser av insamlaren skriver emellertid sina händelsedata till samma diskkö.

## Diskkö {#section-41aac77ab30e48478d1b31eac288df05}

Diskkön (kö) är en feltolerant FIFO-fil (först in, först ut) som mappas till minne och som buffrar råhändelsedata som Sensor samlar in, vilket ger tillfällig lagring för insamlade händelsedata på webbservern där den är installerad.

För att förhindra att kön utökas utan begränsningar (och därmed förbrukar allt tillgängligt diskutrymme) behålls kön i en fil med fast storlek, vilket innebär att den bara innehåller så mycket händelsedata som den har fått kapacitet att lagra. Köfilens storlek konfigureras i parametern QueueSize i Sensor-konfigurationsfilen txlogd.conf när sensorn installeras. Mer information om parametrarna txlogd.conf finns i Filparametrar för sensorfilen Txlogd.conf.

När den fysiska längden på filen väl har fastställts växer eller krymper den inte. Insamlaren placerar helt enkelt nya händelsedata i kön och sändaren hämtar händelser från den. Om insamlaren kommer till slutet av filen slutar den att skriva till köfilen.

I allmänhet hämtar sändaren händelser från kön så snabbt som insamlaren placerar dem. Om anslutningen mellan sändaren och Insight Server är långsam eller otillgänglig kan kön fylla med oöverförda händelser. I det här fallet slutar insamlaren samla in data tills avsändaren ritar ned kön. Information om begäranden om att webbservern bearbetar under den här tiden går förlorade permanent.

**Bestämma köstorlek**

Innan du installerar Sensor måste du bestämma hur stor kön måste vara. För att förhindra permanent dataförlust är det viktigt att skapa en kö som är tillräckligt stor för att rymma det antal händelser som kan ackumuleras under det mest troliga driftsavbrottet i anslutningen till Insight Server (det vill säga tillräckligt med lagringsutrymme för flera dagar med maximal aktivitet). Kön måste konfigureras så att den innehåller tillräckligt med händelsedata så att systemadministratörerna har tid att återställa nätverkets tillgänglighet till mål-Insight-servern, eller reparera eller ersätta Insight-servern utan att förlora några data. Om sensorn har misslyckats och det inte finns någon giltig och tillgänglig köfil som kan innehålla händelsedata, går efterföljande data förlorade.

>[!NOTE]
>
>Det är viktigt att administratörerna för varje dator där Sensor körs förstår den lokala köfilens unika karaktär så att de inte behandlar den som en vanlig loggfil som kan tas bort, arkiveras eller komprimeras.

Adobe rekommenderar att kön är konfigurerad att innehålla minst tio (10) toppdagar med händelsedata som produceras av servern där sensorn är installerad. Det vill säga, ta mängden händelsedata från en toppdag under det senaste året och multiplicera den med tio.

Den här rekommendationen förutsätter följande:

* Ert företags IT-team övervakar varje sensor på det sätt som beskrivs i Administrera sensor i den här guiden och gör det minst en gång om dagen. Om så inte är fallet bör denna period förlängas på lämpligt sätt.
* Ditt företags IT-team kan återställa nätverkets tillgänglighet eller ersätta eller reparera installerade Insight-servrar inom 72 timmar. Om så inte är fallet bör denna period förlängas på lämpligt sätt.
* Sensorns konfiguration ändras inte.
* Inga externa händelser (till exempel en stor marknadsföringskampanj) kommer att få antalet händelsedata som genereras av webbservrarna att öka avsevärt.

Ditt val av köstorlek beror till stor del på den önskade nivån av systemövervakning mot bakgrund av ditt företags praxis och principer för svarstider och administration av helgdagar/helgdagar. Eftersom större köstorlekar är bättre rekommenderar Adobe att ditt företag gör kön så stor som möjligt.

>[!NOTE]
>
>Större köfilstorlekar påverkar inte prestanda.

Kontakta Adobes konsulttjänster om du vill veta mer om hur du ändrar storlek på kön.

## Dataöverföring {#section-2dc03d37d73b4cc6bdd5af6b346350d4}

Sändaren är en oberoende process (till exempel en daemon på en UNIX-baserad dator eller en tjänst på en Windows-dator) som körs på samma dator som webbservern.

Sändaren läser händelsedata från diskkön, komprimerar dem och skickar dem via HTTP/S till den angivna Insight-servern, där de bearbetas och lagras i **.vsl** -filer.
