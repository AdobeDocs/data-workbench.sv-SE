---
description: Steg för att distribuera instrumentpanelen i IIS.
title: Distribuera kontrollpanelen
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Distribuera kontrollpanelen{#deploying-the-dashboard}

Steg för att distribuera instrumentpanelen i IIS.

1. Skapa en installationsmapp för att installera kontrollpanelen, till exempel [!DNL c:\inetpub\wwwroot\dashboard].
1. Skapa instrumentpanelens programpool i IIS.
1. Öppna IIS Manager-konsolen.
1. Gå till **[!UICONTROL Application Pools]**.
1. Välj **[!UICONTROL Add Application Pool…]**på menyn **[!UICONTROL Actions]** till höger.
1. Använd kontrollpanelen för namnet i **[!UICONTROL Add Application Pool]**-formuläret och välj .NET Framework v.4.0.xxxxxx som .NET Framework-version.
1. Låt andra fält vara standardfält och klicka på **[!UICONTROL OK]** för att skapa programpoolen.
1. Distribuera kontrollpanelsprogrammet.
1. Öppna IIS Manager-konsolen.
1. Expandera **[!UICONTROL Default Web Site]**-mappen som du skapade i c:\inetpub\wwwroot\dashboard by default.
1. Högerklicka på mappen och välj **[!UICONTROL Convert to Application]**.
1. Välj **[!UICONTROL Application Pool]**som skapades i steg 2 (till exempel &quot;Kontrollpanel&quot;).
1. Under **[!UICONTROL Sites]** högerklickar du på den webbplats som du vill distribuera till (till exempel &quot;Standardwebbplats&quot;).
1. Välj **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Bläddra till och välj den Dashboard-distributionsfil som tillhandahålls av Adobe.
1. Klicka **[!UICONTROL Next]** två gånger för att gå till skärmen Ange programinformation.
1. På den här skärmen kan du välja att anpassa din instrumentpanelsdistribution.
1. För **[!UICONTROL Application Path]** anger du det mappnamn som tidigare valts.
1. Under **[!UICONTROL Disable Automatic Database Upgrade]** anger du `False` eftersom det här är en ny installation.
1. Anpassa anslutningssträngen om det behövs. Exempel:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Klicka på **[!UICONTROL Next]** så börjar IIS installera programmet.
1. När installationen är klar bör du inte se några fel i installationsloggen.
