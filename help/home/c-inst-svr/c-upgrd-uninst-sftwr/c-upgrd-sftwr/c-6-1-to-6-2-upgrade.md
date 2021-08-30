---
description: Uppgraderar serverkomponenter för Data Workbench 6.2 och 6.2.2.
title: DWB Server upgrade 6.1 to 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# DWB Server-uppgradering: 6.1 till 6.2{#dwb-server-upgrade-to}

Uppgraderar serverkomponenter för Data Workbench 6.2 och 6.2.2.

## Uppgradera problem med 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Attributprofilen är konfigurerad för användare som har implementerat Adobe SC-profilen för att använda dataflödet från Analytics (SC/Insight). Som standard används händelserna Marketing och Conversion som standardinteraktioner som utvärderas i de regelbaserade modellerna. Mer information finns i [Distribuera attributprofilen](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en).
* För användare av Adobe SC-profilen som uppgraderar till Data Workbench 6.2, om du inte använder standardkonfigurationerna, kontrollerar du att [!DNL x-bot_id]-värdet i [!DNL SC Fields.cfg]-filen avkodas korrekt och att [!DNL x-bot_id]-fältet visas korrekt i [!DNL Decoding Instructions.cfg]- och [!DNL Exclude Hit.cfg]-filerna. Detta blir bara ett problem om du har ändrat konfigurationsfilen från standardkonfigurationen.
* Om du har tagit bort oanvända fält i [!DNL Dataset > Log Processing > SC Fields.cfg]-filen för Adobe SC-profilen måste du uppdatera för att få plats med uppdaterade fältvärden som används för attributprofilen (se [Distribuera attributprofilen](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Uppgradera problem med 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* Uppslagsfilerna **[!UICONTROL Browsers]** och **[!UICONTROL Operating Systems]** uppdateras inte i den äldre **[!UICONTROL Traffic]**-profilen (till exempel [!DNL Lookups\Traffic\Browsers.txt)]. I stället kommer konfigurationen av profilen **[!UICONTROL Traffic]** att använda paketet DeviceAtlas ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) för att tillhandahålla den här konfigurationsinformationen.
* Data Workbench 6.2.1 kommer att vara den sista versionen som tillhandahåller en nedladdning av 32-bitars klientprogrammet. Alla framtida hämtningar av klientprogram kommer att vara 64-bitars och kräver Windows 7 eller senare. Minnesbegränsningarna i 32-bitarsprogrammet åtgärdas med introduktionen av 64-bitarsprogrammet som börjar med 6.1-versionen.

>[!NOTE]
>
>32-bitarsversionen av Data Workbench-klientprogrammet kan ha problem med minnesbegränsningar när prediktiva modeller körs med klustrings- och poängfunktionerna.
