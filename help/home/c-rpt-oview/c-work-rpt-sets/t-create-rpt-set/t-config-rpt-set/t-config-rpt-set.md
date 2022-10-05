---
description: När du har skapat och sparat arbetsytorna i rapportuppsättningsmappen måste du skapa en ny Report.cfg-fil.
title: Konfigurera rapportuppsättningen
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Konfigurera rapportuppsättningen{#configure-the-report-set}

{{eol}}

När du har skapat och sparat arbetsytorna i rapportuppsättningsmappen måste du skapa en ny Report.cfg-fil.

Du måste ange i dialogrutan [!DNL Report.cfg] för rapportuppsättningen när och hur rapporterna ska genereras och distribueras.

**Så här skapar du en ny Report.cfg**

1. I data workbench öppnar du [!DNL Profile Manager] genom att högerklicka på en arbetsyta och klicka **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. Klicka **[!UICONTROL Reports]** för att öppna [!DNL Reports] mapp.
1. Klicka på mappen för din rapportuppsättning.
1. I [!DNL User] kolumn för rapportuppsättningsmappen, högerklicka och välj **[!UICONTROL Create]** > **[!UICONTROL Report]**. En ny [!DNL Report.cfg] filen visas i [!DNL File]kolumn.
1. I [!DNL User] kolumn för den nya [!DNL Report.cfg] , högerklicka på bockmarkeringen för [!DNL Report.cfg] filen och klicka sedan på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![Steginformation](assets/cfg_reportcfg.png)

1. Redigera konfigurationsparametrarna efter behov. Mer information om de här parametrarna finns i [Parametrar för Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >Provet [!DNL Report.cfg] som visas i det här exemplet innehåller bara de parametrar som ingår i [!DNL Report.cfg] som standard. Om du behöver lägga till ytterligare parametrar i en [!DNL Report.cfg] måste du göra det med en textredigerare. Anvisningar om hur du gör detta finns i [Redigera befintliga Report.cfg-filer](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. Spara filen genom att högerklicka **[!UICONTROL Report.cfg (modified)]** längst upp i filen och klicka på **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. Stäng filen.
1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen i dialogrutan [!DNL User] kolumn för den nya [!DNL Report.cfg] och markera **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
