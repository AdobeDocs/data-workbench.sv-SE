---
description: När du har skapat och sparat arbetsytorna i rapportuppsättningsmappen måste du skapa en ny Report.cfg-fil.
title: Konfigurera rapportuppsättningen
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Konfigurera rapportuppsättningen{#configure-the-report-set}

När du har skapat och sparat arbetsytorna i rapportuppsättningsmappen måste du skapa en ny Report.cfg-fil.

Du måste ange i [!DNL Report.cfg]-filen för rapportuppsättningen när och hur rapporterna ska genereras och distribueras.

**Så här skapar du en ny Report.cfg**

1. I data workbench öppnar du [!DNL Profile Manager] genom att högerklicka i en arbetsyta och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Klicka på **[!UICONTROL Reports]** för att öppna mappen [!DNL Reports].
1. Klicka på mappen för din rapportuppsättning.
1. Högerklicka och välj **[!UICONTROL Create]** > **[!UICONTROL Report]** i kolumnen [!DNL User] för rapportuppsättningsmappen. En ny [!DNL Report.cfg]-fil visas i kolumnen [!DNL File].
1. Högerklicka på bockmarkeringen för [!DNL Report.cfg]-filen i kolumnen [!DNL User] för den nya [!DNL Report.cfg]-filen och klicka sedan på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Steginformation](assets/cfg_reportcfg.png)

1. Redigera konfigurationsparametrarna efter behov. Mer information om de här parametrarna finns i [Report.cfg Parameters](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >Exemplet [!DNL Report.cfg] som visas i det här exemplet innehåller bara de parametrar som finns i [!DNL Report.cfg]-filen som standard. Om du behöver lägga till ytterligare parametrar i en [!DNL Report.cfg]-fil måste du göra det med en textredigerare. Anvisningar om hur du gör detta finns i [Redigera befintliga Report.cfg-filer](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Spara filen genom att högerklicka på **[!UICONTROL Report.cfg (modified)]** överst i filen och klicka på **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Stäng filen.
1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen i kolumnen [!DNL User] för den nya [!DNL Report.cfg]-filen och väljer **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
