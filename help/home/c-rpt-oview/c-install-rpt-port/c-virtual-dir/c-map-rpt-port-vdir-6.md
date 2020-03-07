---
description: Steg för att mappa rapportportalen till en virtuell katalog (IIS 6.0).
solution: Analytics
title: Mappa rapportportalen till en virtuell katalog (IIS 6.0)
topic: Data workbench
uuid: e09d23d7-09de-4180-8260-60527f47aa98
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappa rapportportalen till en virtuell katalog (IIS 6.0){#mapping-report-portal-to-a-virtual-directory-iis}

Steg för att mappa rapportportalen till en virtuell katalog (IIS 6.0).

Mappning av [!DNL Report Portal] till en virtuell katalog i IIS 6.0 innebär tre olika åtgärder:

1. [Redigera konfigurationsfilen](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-eaf1c58935074cfa840dac33e1286520)
1. [Importera konfigurationsfilen till IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-9d61f6bfa93846dcb96973fec5573b19)
1. [Aktivera ASP (Active Server Pages) på IIS](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-6.md#section-a7725ec2afc64ffc854c5bd8c5c31802)

Du måste slutföra alla tre uppgifterna.

## Redigera konfigurationsfilen {#section-eaf1c58935074cfa840dac33e1286520}

1. Öppna \*PortalName*\ReportPortalSetup.xml i en textredigerare som Anteckningar på datorn där [!DNL Report Portal] är installerat.

1. Använd redigerarens sök-och-ersätt-funktion för att globalt ersätta (Ersätt alla) strängen&quot;VSVirtualPortalName&quot; med namnet på portalen. Om du till exempel vill använda&quot;VisualReportPortal&quot; som namn på din [!DNL Report Portal]dator söker du efter&quot;VSVirtualPortalName&quot; och ersätter den med&quot;VisualReportPortal&quot;.
1. Leta reda på följande element i den här filen:

   ```
   <IIsWebVirtualDir Location= "/LM/W3SVC/1/Root/PortalName/Output" AccessFlags="AccessRead | AccessScript” AppFriendlyName="Output" . . . >
   ```

1. Ange det här elementets [!DNL Path] attribut till den fysiska platsen för katalogen där utdata för rapportuppsättningarna [!DNL Report Server] sparas.

   Utdatamappen kan finnas var som helst, ha valfritt namn och innehålla en undermapp för varje rapportuppsättning.

   >[!NOTE]
   >
   >Detta måste vara samma katalog som du anger i parametern Utdatarot i [!DNL Report.cfg] filen för en rapportuppsättning. Mer information finns i [Konfigurera Report.cfg-filer](../../../../home/c-rpt-oview/c-admin-rpt/c-config-rpt-files.md#concept-cf4b95344fcb4c8c877db91e5f1d345d).

   I följande kodexempel visas hur du ställer in attributet om dina rapporter sparades i [!DNL Path] [!DNL E:\VSReport\ReportOutput]:

   ```
   < . . . 
   AppIsolated="2" 
       AppRoot="/LM/W3SVC/1/Root/PortalName/OutputFolder" 
       DirBrowseFlags="DirBrowseShowDate | DirBrowseShowTime |...  
       Path="E:\VSReport\ReportOutput"
   ```

   >[!NOTE]
   >
   >Det är viktigt att attributet [!DNL Path] är rätt inställt.

1. Om du har ändrat standardvärdet [!DNL Path] för [!DNL Output] elementet flyttar du [!DNL profiles.xml] filen från *\PortalName*\PortalFiles\Output folder to the output directory that you specified in Step 4. I exemplet ovan skulle du gå [!DNL profiles.xml] till [!DNL E:\VSReport\ReportOutput].

1. Kontrollera att attributen [!DNL Path] för alla andra [!DNL IIsWebVirtualDir] element mappas till rätt plats genom att söka efter alla förekomster av [!DNL C:\Inetpub\wwwroot] och ersätta dem med rätt sökväg.

1. Spara filen. Om du vill bevara originalfilen kan du spara konfigurationsfilen med ett nytt namn.

## Importera konfigurationsfilen till IIS {#section-9d61f6bfa93846dcb96973fec5573b19}

1. Starta IIS-hanteraren på datorn där [!DNL Report Portal] är installerad med **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Systems (IIS) Manager]**.

1. Välj **[!UICONTROL (local computer)]** > **[!UICONTROL Web Sites]** > **[!UICONTROL Default Web Site]**.

1. Högerklicka **[!UICONTROL Default Web Site]** och välj **[!UICONTROL New]** > **[!UICONTROL Virtual Directory]** (från fil).

1. Select the **[!UICONTROL ReportPortalSetup.xml]** file and click **[!UICONTROL Read File]**.

1. Verifiera att sex virtuella kataloger är listade för dig [!DNL Report Portal] enligt följande exempel.

   ![](assets/rptPort_dia_VirDirs.png)

   Om du inte ser sex virtuella kataloger eller om du får ett felmeddelande klickar du på **[!UICONTROL Cancel]** och kontrollerar om konfigurationsfilen innehåller fel.

1. Markera den första virtuella katalogen i listan (den som är överordnad de övriga fem) och klicka på **[!UICONTROL OK]**. IIS importerar mappningarna och lägger till de virtuella katalogerna på standardwebbplatsen.

   Se till att den resulterande katalogstrukturen har en överordnad mapp (med samma namn som portalen) och fem underkataloger enligt följande exempel.

   ![](assets/rptPort_scrn_VirDirs_Installed.png)

1. Klicka på varje virtuell katalog för att kontrollera att IIS kan hitta den fysiska katalog som den representerar. Om ett fel visas i IIS högerklickar du på namnet på den virtuella katalogen och kontrollerar att [!DNL Local Path] fältet pekar på rätt fysisk katalog.

## Aktivera Active Server Pages (ASP) på IIS {#section-a7725ec2afc64ffc854c5bd8c5c31802}

ASP [!DNL Report Portal]måste vara aktiverat på IIS för att kunna användas. (ASP är som standard inaktiverat när IIS 6.0 är installerat.) Använd följande procedur för att verifiera att ASP är aktiverat på din IIS.

1. Välj **[!UICONTROL (local computer)]** > **[!UICONTROL Web Service Extensions]** i IIS-hanterarfönstret.
1. Kontrollera att [!DNL Active Server Pages] tillägget är inställt på [!DNL Allowed].

   ![](assets/report_aspenable.png)

1. Om deras status är förbjuden markerar du **[!UICONTROL Active Server Pages]** och klickar på **[!UICONTROL Allow]**.
1. Stäng IIS-hanteraren.

