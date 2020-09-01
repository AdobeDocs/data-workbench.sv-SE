---
description: Anvisningar för installation av data workbench Monitoring Profile.
solution: Analytics
title: Installera övervakningsprofilen
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: 300b4fb872e9a48cb90297c29a2f93e0db60e7c2
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---


# Installera övervakningsprofilen{#installing-the-monitoring-profile}

Anvisningar för installation av data workbench Monitoring Profile.

## Installationssteg {#section-d4355dbea8a447f48ab168db6ccff612}

1. Konfigurera en ny Sensor-instans som om den ska användas för insamling av taggade webbsidesdata. Kontrollera att filen zig.gif finns i dokumentroten för sensorwebbservern. Sensorn kan köras på samma värd som bildskärmsprofilerna. (Detta är inget problem om du använder en textfil för detta ändamål.)

   >[!NOTE]
   >
   >Den här Sensor-instansen måste dedikeras till att endast ta emot trafik från övervakningsagenterna. Sensorn kan även konfigureras för att köras på en annan port om du återanvänder en webbserver för den här samlingen.

1. I [!DNL txlogd.conf] filen finns standardraden:

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   För programmet för övervakningsprofil för data workbench (eller någon&quot;taggad&quot; sidimplementering) måste bildtypen tas bort för att kunna samlas in via en GIF-fil. Den uppdaterade raden är:

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. Kopiera filen [!DNL insight_monitor.zip/insight_monitor_agent] till en tillfällig plats.
1. Uppdatera [!DNL insight_monitor_agent.cfg] filen för din miljö. Följ kommentarerna i konfigurationsfilen:

   **Konfigurationsfilen för övervakning:**

   ![](assets/monitor_agent_cfg_sensor.png)

   Definiera var du samlar in all information och ange URL-adress. Detta måste vara en dedikerad sensor och bör inte ta emot någon trafik förutom det här programmet.

   ![](assets/monitor_agent_cfg_dump.png)

   Det finns sökvägar som förutsätter att det finns ett e: disk. Du kanske vill ändra den här sökvägen för din miljö.

   ![](assets/monitor_agent_cfg_quickcheck.png)

   När du kör en omformningsprofil kan data workbench inte svara. Med det här värdet kan du skicka en varning om processen inte svarar tre gånger i rad. Detta är ett sätt att minska falska positiva varningar.

   ![](assets/monitor_agent_cfg_groups.png)

   Här ställer du in miljö- och gruppdimensioner. Detta kan skilja sig från värd till värd.

   Här ser du ![](assets/monitor_agent_cfg_debug.png)exakt vad skärmagenten gör genom att visa felloggarna i den här sökvägen.

   ![](assets/monitor_agent_cfg_tempdb.png)

   Detta är för att använda den tillfälliga databasen internt. Den kan larmas när den når sin kapacitet. Detta skiljer sig från fysisk diskanvändning.

1. Kopiera mappen *insight_monitor_agent* till varje DPU- och FSU-värd som kör data workbench-servern. Standardplatsen som anges i konfigurationsfilen är [!DNL e:\insight_monitor_agent] men du kan ändra den här platsen.

1. Lägg till en schemalagd aktivitet i Windows för att anropa agenten var 10:e minut (den här perioden antas i beräkningarna av bearbetningsfrekvens). Programmet är [!DNL e:insight_monitor/insight_monitor_agent.exe]. Argumentet är config-file e:\insight_monitor\insight_monitor.cfg. Börja i e:\insight_monitor. Användaren som kör uppgiften måste ha behörighet att läsa/skriva [!DNL e:\insight_monitor] och läsa Win32 OLE-objektet [!DNL root\CIMV2] (krävs för att kontrollera startläget för tjänsten data workbench och för att kontrollera hur mycket utrymme som finns på de lokala diskarna)

1. Bekräfta att VSL börjar växa när övervakningsposterna ackumuleras. Detta kommer att ta en stund eftersom trafikvolymen blir extremt låg i en liten installation (var 10:e minut skickar agenten bara en träff för värdspecifika data plus en träff per bearbetningsprofil).
1. Zippa upp insight_monitor.zip\profiles\Insight Historic to a temporary location.
1. Uppdatera värdnamnet i [!DNL profile.cfg], [!DNL dataset\cluster.cfg]och [!DNL dataset\segment export.cfg].

1. Uppdatera filerna till katalogen med data workbench-profiler.
1. Uppdatera loggservern och sökvägen [!DNL dataset\log processing.cfg] till den plats där sensorn VSL samlas.
1. [Du kan också] göra samma sak med profilerna [!DNL Insight Profile Status] och [!DNL Insight Server Status]. Dessutom bör statusprofilerna bearbetas om natten med ett efterföljande tvådagarsfönster. Lägg till en schemalagd aktivitet för Windows: Programmet är [!DNL e:\insight_monitor\insight_reprocess.exe]. Argumentet är [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Lämna [!DNL start in] tomt. Lägg till en annan schemalagd aktivitet för *&quot;insight-serverstatus&quot;*. *insight_reprocess.exe* kräver läs- och skrivåtkomst till *log processing.cfg* för att uppdatera starttiden.

1. Dessutom bör statusprofilerna bearbetas om natten med ett efterföljande tvådagarsfönster. Lägg till en schemalagd aktivitet för Windows: Programmet är *e:\insight_monitor\insight_reprocess.exe*. Argumentet är - [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. Lämna *början* tom. Lägg till en annan schemalagd aktivitet för [!DNL "insight server status"]. [!DNL insight_reprocess.exe] kräver läs-/skrivåtkomst för [!DNL log processing.cfg] att uppdatera starttiden. Bekräfta att varje profil läser VSL när de samlas in. Detta kommer att ta en stund - förmodligen timmar - på grund av den extremt låga volymen.

## Installationsinformation {#section-17722441ab0046fcbcb46b957d56230a}

* **Konfigurera övervakningsprofilen i en licensierad testmiljö**. Testmiljöpaketet ingår i din implementering av data workbench, vilket gör att du kan installera och konfigurera programmet. Om du installerar på en FSU- eller DPU-produktionsserver måste du konfigurera servern så att den körs på en separat port.
* **Distribuera en ny sensor specifikt för övervakningsprofilen**. Du måste installera en ny instans av sensorn på servern som kör övervakningsprofilen. Detta är utöver produktionsinstansen för Sensor. (Det kostar inget extra att installera Sensor på en produktionsserver eller icke-produktionsserver specifikt för övervakningsprofilen.)
* **Inaktivera övervakningsagenten under underhåll** av data workbench. För att undvika att få negativa mått på drifttid och prestanda kan du ställa in startläget för tjänsten till manuell för tjänsten InsightServer (Omniture Insight Server). Ett praktiskt PowerShell-kommando är *set-service -name insightserver -startuptype manual*. Ställ in det på automatisk efter underhållet: *set-service -name insightserver -startuptype automatic*. Ett annat alternativ är att tillfälligt inaktivera övervakaragentens schemalagda aktivitet.
* **Statusprofilerna behöver ett efterföljande fönster** för att kunna släppa gamla värdar och profiler samt gamla värdprofilsmappningar. Men om mängden händelsedata är så liten att data workbench inte buffrar den kan du behöva utöka fönsterstorleken en hel del för att det ska kunna bearbetas.
* **Agenten samlar in den övergripande och äldsta tidpunkten från data workbench-detaljstatus**, som rapporteras i lokal värdtid om händelseloggens tidsstämplar är i UTC (som i VSL filer). Om tidsstämplarna för händelsedata finns i en annan tidszon än UTC kommer tidpunkten att förskjutas i den resulterande statusprofilen för insight-profilen. Om **alla** tidsstämplar för händelsedata finns i samma tidszon kan du lägga till förskjutningen i *Insight-profilen Status\metrics\as of delay minutes.metric*.

* **Två nya dimensioner introducerades för att hjälpa kunderna att gruppera sina servrar om de befinner sig i olika lägen**, till exempel produktion, staging, testservrar och servrar i andra delstater. Om du till exempel söker efter&quot;aktiv tid&quot;, tittar du bara på servrar i produktionsläge. Därför är gruppdimensionen bara ett annat sätt att godtyckligt gruppera servrar efter behov. I filen Övervakningskonfiguration kan du till exempel ange vilken värd som din avdelning betjänar, till exempel Operations, Development eller Marketing.

