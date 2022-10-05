---
description: Information för att generera rapporter som Excel-filer.
title: Generera rapporter som Microsoft Excel-filer
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Generera rapporter som Microsoft Excel-filer{#generating-reports-as-microsoft-excel-files}

{{eol}}

Information för att generera rapporter som Excel-filer.

Följande krav måste vara uppfyllda:

* Microsoft Excel måste vara installerat på samma dator som [!DNL Report Server].
* Användarkontot som [!DNL Report Server] processen körs måste ha behörighet att komma åt Microsoft Excel.

   >[!NOTE]
   >
   >
   >
   >
   >    * När du genererar rapporter som Excel-filer öppnar du en ny instans av Excel. Mer information om processen finns i [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Även om data workbench har stöd för mer än 256 kolumner och 65 536 rader data, har inte Microsoft Excel det.


Om dessa krav är uppfyllda, [!DNL Report Server] startar automatiskt Microsoft Excel och tar fram data från vissa visualiseringar, dimensioner, värdesförklaringar och textanteckningar i en ny Excel-arbetsbok med en visualisering per kalkylblad.

>[!NOTE]
>
>Data exporteras inte från diagram, sökvägsläsare, processkartor, spridningspunkterna och glober.

Om du inte har angett en [!DNL Custom Title] för visualiseringen används fönstertypen (till exempel Filmtabell) som kalkylbladsnamn.

Mer information om hur du anger [!DNL Custom Titles] för visualiseringar, se [Data Workbench Client Guide](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html).

## Använda en mallfil {#section-40ab11916f464b1a88214ab969da6751}

Du kan också generera en rapport som en Excel-fil med en Excel-mall ( [!DNL .xls] eller [!DNL .xlsx]). Genom att använda en mallfil kan du minska tiden du lägger på att formatera dina data varje gång rapporten genereras.

Den här mallfilen måste vara en [!DNL .xls] eller [!DNL .xlsx] fil, inte en [!DNL .xlt] -fil.

Du kan välja att definiera en mall för varje enskild rapport, en allmän mall för alla rapporter eller en kombination av båda. Dessa två objekt utesluter inte varandra, så du kan definiera en allmän mall och sedan definiera specifika mallar.

Om du vill generera en rapport med en allmän mall som du använder för alla rapporter, måste du ange namnet på den Excel-filen i Excel-standardmallsparametern i dialogrutan [!DNL Report.cfg] för den rapportuppsättningsfilen och sedan montera mallfilen i samma mapp som [!DNL Report.cfg] för den rapportuppsättningen (*installationskatalog för data workbench*\*ProfileName*\Reports\*ReportSetName*). Mer information om den här parametern finns i [Parametrar för Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

Om du vill generera en rapport med en mall som är specifik för en rapport måste du ge Excel-filen samma namn som rapportarbetsytan ( [!DNL .vw]) placerar du sedan mallfilen i samma mapp som rapportarbetsytan ( [!DNL .vw]).

När rapporten genereras fylls de befintliga tabbbladen i mallen (där vart och ett representerar en visualisering) i med de senaste data från rapporten, medan alla nya fönster som inte finns i mallen som tabbade blad ignoreras. Alla andra tabeller med flikar i mallfilen ändras inte.

Om du har ett makro definierat i Excel-mallfilen som du vill köra automatiskt när rapporten genereras, ger du makrot &quot;VSExport&quot;.
