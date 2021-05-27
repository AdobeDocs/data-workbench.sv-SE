---
description: Generera rapporter genom att bearbeta arbetsytor och ange dem som rapporter.
title: Genererar rapporter
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Genererar rapporter{#generating-reports}

Generera rapporter genom att bearbeta arbetsytor och ange dem som rapporter.

[!DNL Report] genererar dina rapporter med det intervall som anges i  [!DNL Every] parametern i  [!DNL Report.cfg] filen (till exempel  [!DNL "day]&quot;, som dagligen bearbetar rapporten) och baserat på de andra  [!DNL Report.cfg] filinställningarna.

När du genererar rapporter visas procentandelen färdig på fliken [!DNL Reports] under miniatyrbilden för den aktuella rapporten. Om [!DNL Report] påträffar ett problem under rapportgenereringen visas det senaste felmeddelandet på fliken [!DNL Reports] i rapportuppsättningens mapp. Om [!DNL Report] påträffar ett fel för en viss rapport fortsätter den att bearbeta de andra rapporterna i uppsättningen.

Du kan generera rapporter i en rapportuppsättning i något eller alla följande format med parametern [!DNL Report Types] i filen [!DNL Report.cfg]:

* Microsoft Excel-fil ( [!DNL .xls] eller [!DNL .xlsx])
* Grafikfil för portabla nätverk ( [!DNL .png])
* Miniatyrbild ( [!DNL .jpg])

Förutom de utdatatyper som anges skapar [!DNL Report] en [!DNL .xml]-fil med samma namn som rapporten. Filen *`<report name>`*.xml innehåller beskrivningen av rapporten som visas i Data Workbench på fliken [!DNL Reports] under rapportens miniatyrbild. Detta gör beskrivningen tillgänglig för distribution av rapporter via en rapportportal. Mer information om [!DNL Report Portal] finns i [Arbeta med rapportportalen](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Om du definierar om ett internt mått fungerar systemet oväntat på grund av fel värde. Dina rapporter genereras bara om ett mätvärde är 100 %. Vi rekommenderar att du inte ändrar måttdefinitioner.
