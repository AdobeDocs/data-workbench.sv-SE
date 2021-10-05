---
description: Du kan exportera en arbetsyta som en PNG-bildfil eller exportera data från vissa fönster till en Excel-fil (.xls eller .xlsx).
title: Exportera en arbetsyta
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Exportera en arbetsyta{#export-a-workspace}

Du kan exportera en arbetsyta som en PNG-bildfil eller exportera data från vissa fönster till en Excel-fil (.xls eller .xlsx).

## Exportera en arbetsyta som en PNG-fil {#section-f9fbe0f0a1c341e2b063cce106cac35e}

Du kan spara en ögonblicksbild av en arbetsyta i Portable Network Graphic-format (`.png` filer). Följande färgalternativ är tillgängliga när du sparar arbetsytor som `.png`-filer:

* **Svart** bakgrund kopierar arbetsytan som den visas.
* **Vit** bakgrund kopierar arbetsytans element i färg och visar dem på en vit bakgrund.
* **Vit bakgrund (svartvitt)** kopierar arbetsytans element i gråskala och visar dem på en vit bakgrund.

**Exportera en arbetsyta som en PNG-fil**

Klicka på **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>* på titelfältmenyn på en arbetsyta.

Dialogrutan [!UICONTROL Save Image As] visas.

Navigera till den katalog där du vill spara filen, ändra filens namn om det behövs och klicka på **[!UICONTROL Save]**.

## Exportera arbetsytedata till Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

När du exporterar en arbetsyta till Excel exporteras data från vissa visualiseringar, dimensions- och värdesförklaringar samt textanteckningar till en ny Excel-arbetsbok med en visualisering per kalkylblad.

Om du vill exportera arbetsytor och enskilda fönster till Microsoft Excel måste följande krav vara uppfyllda:

* Microsoft Excel måste vara installerat på samma dator som Datan Workbench.
* Användarkontot som Datan Workbench körs under måste ha behörighet att komma åt Microsoft Excel.

>[!NOTE]
>
>* När du exporterar data som Excel-filer öppnar du en ny instans av Excel. Mer information om den här processen finns i [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
>* Data Workbench stöder över 256 kolumner och 65 536 rader, men versioner av Microsoft Excel före 8.0 gör det inte.
>


Om dessa krav uppfylls startar Datan Workbench automatiskt Microsoft Excel och exporterar data till en ny Excel-arbetsbok. Data exporteras inte från följande visualiseringar: diagram, webbläsare för sökvägar, processkartor, punktdiagram och glober.

## Använda anpassade titlar {#section-a332e157554546cb8e88922a8d7a4fa2}

Om du inte har angett en anpassad rubrik för fönstret på menyn [!UICONTROL Export] används [!UICONTROL Export title] som listas (till exempel Citatförteckning) som kalkylbladsnamn.

1. Högerklicka på fönstrets övre kant och klicka i fältet **[!UICONTROL Custom title]**.
1. Skriv den rubrik som du vill använda för fönstret.

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>Om du anger ett bindestreck (-) i fältet [!UICONTROL Custom title] exporteras inte visualiseringen med arbetsytan.

När du exporterar arbetsytan till Excel namnges kalkylbladet som innehåller data för det här fönstret med den titel som du angav i stället för titeln i fältet [!UICONTROL Export title].

## Exportera en arbetsyta eller ett sidofält till Excel {#section-360438b66d5f4734826ab463b4a01a75}

**Exportera arbetsytedata till en ny  [!DNL .xls] fil eller  [!DNL .xlsx] fil**

1. Klicka på **[!UICONTROL Export]** > **[!UICONTROL Export]** i arbetsytans namnlist.
1. Ange om du vill exportera arbetsytan, sidofältet eller båda.

## Exportera till en Excel-mallfil {#section-814772929ca64cf6b92b89d3fdd02302}

Du kan exportera data på arbetsytan till en Excel-mallfil (`.xls` eller `.xlsx`). Om du använder en mallfil kan du minska tiden du lägger på att formatera data varje gång arbetsytan exporteras.

>[!NOTE]
>
>Mallfilen måste vara en `.xls`- eller `.xlsx`-fil, inte en `.xlt`-fil.

När data exporteras fylls de befintliga tabbbladen i mallen (som representerar en visualisering) i med de senaste data från arbetsytan, medan alla nya fönster som inte finns i mallen som tabbade blad ignoreras. Alla andra tabeller med flikar i mallfilen ändras inte.

Om du har ett makro definierat i Excel-mallfilen som du vill köra automatiskt när rapporten genereras, ger du makrot &quot;VSExport&quot;.

Säg att du vill använda exporterade kampanjdata från en tabellvisualisering i ett cirkeldiagram på ett annat flikark i en Excel-fil och att du vill uppdatera informationen varje vecka. Du kan använda en mall så att du inte behöver återskapa referenserna från tabellens flikkalkylblad till cirkeldiagrammets flikkalkylblad varje gång du vill uppdatera data. Tabelldata uppdateras vid exporten, vilket automatiskt uppdaterar cirkeldiagrammet.

**Exportera arbetsytedata till en mall  [!DNL .xls] eller  [!DNL .xlsx] fil**

1. Högerklicka på arbetsytans namnlist och klicka på **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. Ange om du vill exportera en arbetsyta, ett sidofält eller båda.

   Dialogrutan [!UICONTROL Select a template worksheet] öppnas.

1. Gör något av följande:

   * Om du använder en `.xls`-mallfil:

      1. Bläddra till och välj mallfilen `.xls`.
      1. Klicka på **[!UICONTROL Open]**.
   * Om du använder en `.xlsx`-mallfil:

      1. Bläddra till mallfilens plats. Filnamnet `.xlsx` visas inte.
      1. I fältet [!UICONTROL File name] skriver du `.xlsx` och klickar på **[!UICONTROL Open]**. Alla `.xlsx`-filnamn visas i fillistan.

      1. Välj mallfilen `.xlsx`.
      1. Klicka på **[!UICONTROL Open]**.
