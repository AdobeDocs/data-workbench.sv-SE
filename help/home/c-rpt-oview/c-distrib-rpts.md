---
description: När rapporterna har skapats distribuerar Report rapporterna i uppsättningen baserat på inställningarna i filen Report.cfg.
title: Distribuera rapporter
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Distribuera rapporter{#distributing-reports}

{{eol}}

När rapporterna har skapats distribuerar Report rapporterna i uppsättningen baserat på inställningarna i filen Report.cfg.

[!DNL Report] Med kan du distribuera rapporterna i en uppsättning på följande sätt:

* **E-post:** Om du vill distribuera rapporter som Excel-filer [!DNL .png] filer, eller miniatyrbilder via e-post (i eller som bilagor), anger du parametrarna för e-postrapporten i rapportuppsättningens [!DNL Report.cfg] -fil. Alla rapporter i den uppsättningen skickas via e-post till angivna mottagare i ett meddelande.

* **Delad katalog:** Om du vill distribuera rapporter som Excel-filer [!DNL .png] filer, eller miniatyrbilder till en delad katalog, anger du katalogen i parametern Utdatarot i rapportuppsättningens [!DNL Report.cfg] -fil.

* **Rapporteringsportal:** Med en rapportportal kan du visa rapporter via webbläsaren. Adobe [!DNL Report Portal] visar rapporter som skapats som Excel eller [!DNL .png] filer, men inte de som genereras som miniatyrbilder ( [!DNL .jpg]). Om du vill distribuera rapporter till en portal anger du dokumentroten för den webbserver som används för portalen i parametern Utdatarot i rapportuppsättningens [!DNL Report.cfg] -fil. Mer information om hur du installerar och använder [!DNL Report Portal], se [Arbeta med rapportportal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Att läsa utdata som för närvarande stöds av [!DNL Report]måste du ha ett program som kan visa rapporterna i det önskade formatet. Om du till exempel vill visa [!DNL .xlsx] måste du ha Microsoft Excel 2007 eller senare.

Du kan också använda en kombination av dessa genererings- och distributionsalternativ. Om du till exempel anger [!DNL Report Types] parameter för att generera en rapportuppsättning som Excel och [!DNL .png] och sedan ange [!DNL Mail Report]och [!DNL Output Root] parametrar distribueras alla rapporter i den uppsättningen till den angivna utdatakatalogen (kanske ska visas i en portal) och skickas med e-post till mottagarna.

Anvisningar om hur du konfigurerar rapportuppsättningar finns i [Arbeta med rapportuppsättningar](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Mer information om [!DNL Report.cfg] parametrar, se [Parametrar för Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
