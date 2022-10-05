---
description: Generera rapporter genom att bearbeta arbetsytor och ange dem som rapporter.
title: Genererar rapporter
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Genererar rapporter{#generating-reports}

{{eol}}

Generera rapporter genom att bearbeta arbetsytor och ange dem som rapporter.

[!DNL Report] genererar dina rapporter med det intervall som anges i [!DNL Every] -parametern i [!DNL Report.cfg] fil (som [!DNL "day],&quot; som dagligen behandlar rapporten), och som bygger på den andra [!DNL Report.cfg] filinställningar.

När du genererar rapporter visas Procent färdigt på [!DNL Reports] under miniatyrbilden för den aktuella rapporten. If [!DNL Report] stöter på ett problem under rapportgenereringen, visas det senaste felmeddelandet på [!DNL Reports] i rapportuppsättningens mapp. If [!DNL Report] påträffar ett fel för en viss rapport och fortsätter att bearbeta de andra rapporterna i uppsättningen.

Du kan generera rapporter i en rapportuppsättning i något eller alla följande format med hjälp av [!DNL Report Types] -parametern i [!DNL Report.cfg] fil:

* Microsoft Excel-fil ( [!DNL .xls] eller [!DNL .xlsx])
* Portable network graphic file ( [!DNL .png])
* Miniatyrbild ( [!DNL .jpg])

tillsammans med de typer av utdata som anges, [!DNL Report] skapar en [!DNL .xml] filen har samma namn som rapporten. Detta *`<report name>`* XML-filen innehåller beskrivningen av rapporten som visas i Data Workbench på [!DNL Reports] under rapportens miniatyrbild. Detta gör beskrivningen tillgänglig för distribution av rapporter via en rapportportal. Mer information om [!DNL Report Portal], se [Arbeta med rapportportal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Om du definierar om ett internt mått fungerar systemet oväntat på grund av fel värde. Dina rapporter genereras bara om ett mätvärde är 100 %. Vi rekommenderar att du inte ändrar måttdefinitioner.
