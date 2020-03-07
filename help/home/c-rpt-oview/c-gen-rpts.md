---
description: Generera rapporter genom att bearbeta arbetsytor och ange dem som rapporter.
solution: Analytics
title: Genererar rapporter
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Genererar rapporter{#generating-reports}

Generera rapporter genom att bearbeta arbetsytor och ange dem som rapporter.

[!DNL Report] genererar dina rapporter med det intervall som anges i [!DNL Every] parametern i [!DNL Report.cfg] filen (till exempel [!DNL "day]&quot;, som dagligen bearbetar rapporten) och baserat på de andra [!DNL Report.cfg] filinställningarna.

När du genererar rapporter visas procentvärdet för slutfört på [!DNL Reports] fliken under miniatyrbilden för den aktuella rapporten. Om [!DNL Report] ett problem uppstår under rapportgenereringen visas det senaste felmeddelandet på [!DNL Reports] fliken i rapportuppsättningens mapp. Om [!DNL Report] påträffar ett fel för en viss rapport fortsätter den att bearbeta de andra rapporterna i uppsättningen.

Du kan generera rapporter i en rapportuppsättning i något eller alla följande format med hjälp av [!DNL Report Types] parametern i [!DNL Report.cfg] filen:

* Microsoft Excel-fil ( [!DNL .xls] eller [!DNL .xlsx])
* Grafikfil för portabla nätverk ( [!DNL .png])
* Miniatyrbild ( [!DNL .jpg])

Tillsammans med de utdatatyper som anges [!DNL Report] skapar en [!DNL .xml] fil med namnet samma som rapporten. Filen *`<report name>`*.xml innehåller beskrivningen av rapporten som visas i Data Workbench på [!DNL Reports] fliken nedanför rapportens miniatyrbild. Detta gör beskrivningen tillgänglig för distribution av rapporter via en rapportportal. Mer information om [!DNL Report Portal]finns i [Arbeta med rapportportalen](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Om du definierar om ett internt mått fungerar systemet oväntat på grund av fel värde. Dina rapporter genereras bara om ett mätvärde är 100 %. Vi rekommenderar att du inte ändrar måttdefinitioner.
