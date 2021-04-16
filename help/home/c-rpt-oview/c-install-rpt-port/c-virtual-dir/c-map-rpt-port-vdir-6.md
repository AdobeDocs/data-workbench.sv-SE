---
description: Steg för att mappa rapportportalen till en virtuell katalog (IIS 6.0).
title: Mappa rapportportalen till en virtuell katalog (IIS 6.0)
uuid: e09d23d7-09de-4180-8260-60527f47aa98
exl-id: 39335705-7391-49af-a63d-c0fe4ca3f8f0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Mappa rapportportalen till en virtuell katalog (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

Steg för att mappa rapportportalen till en virtuell katalog (IIS 6.0).

Mappning av [!DNL Report Portal] till en virtuell katalog i IIS 6.0 innebär tre separata åtgärder:

1. [Redigera konfigurationsfilen](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importera konfigurationsfilen till IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Aktivera ASP (Active Server Pages) på IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Du måste slutföra alla tre uppgifterna.

## Redigera konfigurationsfilen {#section-eaf1c58935074cfa840dac33e1286520}

1. Öppna \*PortalName*\ReportPortalSetup.xml i en textredigerare som Anteckningar på den dator där [!DNL Report Portal] är installerat.

1. Använd redigerarens sök-och-ersätt-funktion för att globalt ersätta (Ersätt alla) strängen&quot;VSVirtualPortalName&quot; med namnet på portalen. Om du till exempel vill använda&quot;VisualReportPortal&quot; som namn på [!DNL Report Portal] söker du efter&quot;VSVirtualPortalName&quot; och ersätter det med&quot;VisualReportPortal&quot;.
1. Leta reda på följande element i den här filen:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Ange det här elementets [!DNL Path]-attribut till den fysiska platsen för katalogen där [!DNL Report Server] sparar utdata för rapportuppsättningarna.

   Utdatamappen kan finnas var som helst, ha valfritt namn och innehålla en undermapp för varje rapportuppsättning.

   >[!NOTE]
   >
   >Detta måste vara samma katalog som du anger i parametern Utdatarot i [!DNL Report.cfg]-filen för en rapportuppsättning. Mer information finns i [Konfigurera Report.cfg-filer](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   I följande kodexempel visas hur du skulle ange attributet [!DNL Path] om dina rapporter sparades i [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >Det är viktigt att attributet [!DNL Path] är korrekt inställt.

1. Om du ändrade [!DNL Path]-standardelementet för [!DNL Output] flyttar du [!DNL profiles.xml]-filen från *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. I exemplet ovan flyttar du [!DNL profiles.xml] till [!DNL E:\VSReport\ReportOutput].

1. Kontrollera att [!DNL Path]-attributen för alla andra [!DNL IIsWebVirtualDir]-element mappas till rätt plats genom att söka efter alla förekomster av [!DNL C:\Inetpub\wwwroot] och ersätta dem med rätt sökväg.

1. Spara filen. Om du vill bevara originalfilen kan du spara konfigurationsfilen med ett nytt namn.

## Importera konfigurationsfilen till IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. Starta IIS-hanteraren med **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]** på den dator där [!DNL Report Portal] är installerat.

1. Välj **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Högerklicka på **[!UICONTROL Default Web Site]** och välj **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (från fil).

1. Markera filen **[!UICONTROL ReportPortalSetup.xml]** och klicka på **[!UICONTROL Read File]**.

1. Kontrollera att sex virtuella kataloger finns med i listan för din [!DNL Report Portal] enligt följande exempel.

   ![](assets/rptPort_dia_VirDirs.png)

   Om du inte ser sex virtuella kataloger eller om du får ett felmeddelande klickar du på **[!UICONTROL Cancel]** och kontrollerar om konfigurationsfilen innehåller fel.

1. Markera den första virtuella katalogen i listan (den som är överordnad de andra fem katalogerna) och klicka på **[!UICONTROL OK]**. IIS importerar mappningarna och lägger till de virtuella katalogerna på standardwebbplatsen.

   Se till att den resulterande katalogstrukturen har en överordnad mapp (med samma namn som portalen) och fem underkataloger enligt följande exempel.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Klicka på varje virtuell katalog för att kontrollera att IIS kan hitta den fysiska katalog som den representerar. Om IIS visar ett fel högerklickar du på den virtuella katalognamnet och kontrollerar att fältet [!DNL Local Path] pekar på rätt fysisk katalog.

## Aktivera Active Server Pages (ASP) på IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

ASP måste vara aktiverat på IIS för att du ska kunna använda [!DNL Report Portal]. (ASP är som standard inaktiverat när IIS 6.0 är installerat.) Använd följande procedur för att verifiera att ASP är aktiverat på din IIS.

1. Välj **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]** i IIS-hanterarfönstret.
1. Kontrollera att tillägget [!DNL Active Server Pages] är inställt på [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Om deras status är Förbjuden väljer du **[!UICONTROL Active Server Pages]** och klickar på **[!UICONTROL Allow]**.
1. Stäng IIS-hanteraren.
