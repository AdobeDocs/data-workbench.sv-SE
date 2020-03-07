---
description: När du har skapat och sparat arbetsytorna i rapportuppsättningsmappen måste du skapa en ny Report.cfg-fil.
solution: Analytics
title: Konfigurera rapportuppsättningen
topic: Data workbench
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera rapportuppsättningen{#configure-the-report-set}

När du har skapat och sparat arbetsytorna i rapportuppsättningsmappen måste du skapa en ny Report.cfg-fil.

Du måste ange i [!DNL Report.cfg] filen för rapportuppsättningen när och hur rapporterna ska genereras och distribueras.

**Så här skapar du en ny Report.cfg**

1. I data workbench öppnar du [!DNL Profile Manager] genom att högerklicka i en arbetsyta och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Klicka **[!UICONTROL Reports]** för att öppna [!DNL Reports] mappen.
1. Klicka på mappen för din rapportuppsättning.
1. Högerklicka i kolumnen för rapportuppsättningsmappen och välj [!DNL User] > **[!UICONTROL Create]** **[!UICONTROL Report]**. En ny [!DNL Report.cfg] fil visas i [!DNL File]kolumnen.
1. Högerklicka på bockmarkeringen för den nya [!DNL User] filen i [!DNL Report.cfg] kolumnen för [!DNL Report.cfg] filen och klicka sedan på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Steginformation](assets/cfg_reportcfg.png)

1. Redigera konfigurationsparametrarna efter behov. Mer information om de här parametrarna finns i [Report.cfg-parametrar](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >Exemplet [!DNL Report.cfg] som visas i det här exemplet innehåller som standard bara de parametrar som finns i [!DNL Report.cfg] filen. Om du behöver lägga till ytterligare parametrar i en [!DNL Report.cfg] fil måste du göra det med en textredigerare. Anvisningar om hur du gör det finns i [Redigera befintliga Report.cfg-filer](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Spara filen genom att högerklicka **[!UICONTROL Report.cfg (modified)]** överst i filen och klicka på **[!UICONTROL Spara som rapporter\]***&lt;**[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Stäng filen.
1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen i [!DNL User] kolumnen för den nya [!DNL Report.cfg] filen och väljer **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
