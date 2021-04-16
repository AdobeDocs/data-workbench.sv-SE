---
description: Steg för att mappa rapportportalen till en virtuell katalog (IIS 7.0 eller senare).
title: Mappa rapportportalen till en virtuell katalog (IIS 7.0 eller senare)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Mappa rapportportalen till en virtuell katalog (IIS 7.0 eller senare){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Steg för att mappa rapportportalen till en virtuell katalog (IIS 7.0 eller senare).

För närvarande har de flesta klienter för hanterade tjänster servrar med operativsystemet Windows Server 2008 och webbservern IIS 7.0 eller senare.

## Förutsättningar {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Kontrollera att ASP- och [!DNL ASP.Net]-komponenter är installerade för IIS 7.0 eller senare.
* Kontrollera att IIS-webbanvändaren har [!DNL Modify]-åtkomst till filen [!DNL E:\Portal\data\users.mdb]. Du kan ändra det genom att högerklicka på filen **[!UICONTROL users.mdb]** och under [!DNL Properties] gå till fliken [!DNL Security]. Om du inte ser IIS-webbanvändaren som listas eller inte kan lägga till IIS-webbanvändaren i listan ger du bara [!DNL Users]-gruppen åtkomsten [!DNL Modify].

* Kontrollera att det användarkonto som används för att köra [!DNL Application Pools] även har [!DNL Modify] åtkomst till mapparna [!DNL E:\Portal\data\users.mdb] och [!DNL C:\Windows\Temp\] .

## Installationssteg {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Starta [!DNL IIS Manager] på datorn där [!DNL Report Portal] är installerat:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Välj **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Högerklicka på **[!UICONTROL Default Web Site]** och välj **[!UICONTROL Add Virtual Directory]**.

1. Ange Portal för ett alias.
1. Ange [!DNL E:\Portal\PortalASP] för den fysiska sökvägen.
1. Klicka på **[!UICONTROL OK]**.

   Den virtuella katalog som du skapade visas under [!DNL Default Web Site].

1. Lägg till följande virtuella kataloger under den virtuella katalog som du just skapade.

   | Skapa det här aliaset.. | För den här fysiska resursen |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Bilder | [!DNL E:\Portal\PortalFiles\Images] |
   | Utdata | Den fysiska platsen för katalogen där [!DNL Report Server] sparar utdata för rapportuppsättningarna. Utdatamappen kan finnas var som helst och kan namnges vad som helst. Den innehåller en undermapp för varje rapportuppsättning. Du kan ta bort [!DNL E:\Portal\PortalFiles\Output], men flytta [!DNL profiles.xml] till den fysiska platsen för utdatafilen. |

1. När du är klar kontrollerar du att IIS visar fyra nya virtuella kataloger. Kontrollera att katalogstrukturen har en överordnad mapp (med samma namn som portalen) och fyra undermappar.
1. Klicka på **[!UICONTROL Application Pools]** och sedan **[!UICONTROL DefaultAppPool]** (förutsatt att det är den som du konfigurerar med portalen).

1. Klicka på **[!UICONTROL Advanced Settings]** och välj True för Aktivera 32-bitarsprogram.
1. För att [!DNL Portal] ska fungera måste du konvertera den till ett program. När du har konfigurerat de virtuella katalogerna högerklickar du på den virtuella katalogen för portalen och väljer **[!UICONTROL Convert to Application]**.

## Ytterligare tips och tricks {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Du kan hämta [!DNL Portal] från Softdocs under **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Du kan bara hämta [!DNL ReportPortal-Release-1-0-0-7.zip].

* Du behöver inte längre [!DNL ReportPortalSetup.xml], så den kan tas bort.
* För standardiseringens skull bör du placera innehållet i zip-filen i [!DNL E:\Portal].
* Du kan ta reda på vilken SMTP-server du använder för klienter med hanterade tjänster här.
* Ange en begäran med NetOps om att ändra domännamnsposten i IIS för rapportservern till något mer användarvänligt - till exempel [!DNL reports.clientname.insight.omniture.com], så att den övergripande portalwebbadressen är [!DNL http://reports.clientname.insight.omniture.com/Portal]. Konfigurera din [!DNL email.asa]-fil när den här ändringen har gjorts.
