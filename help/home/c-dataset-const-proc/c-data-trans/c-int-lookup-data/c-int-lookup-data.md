---
description: Data workbench innehåller en uppsättning omvandlingar som gör att data workbench-servern kan införliva sökdata i datauppsättningen.
title: Integrera uppslagsdata
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Integrera uppslagsdata{#integrating-lookup-data}

Data workbench innehåller en uppsättning omvandlingar som gör att data workbench-servern kan införliva sökdata i datauppsättningen.

Uppslagsdata är externa data från företagsdatabaser eller uppslagsfiler som du kan kombinera med händelsedata för att skapa datauppsättningen. Vanligtvis använder du sökdata för att förstärka händelsedata från dina loggkällor. Du kan komma på att använda sökdata för att fylla i händelsedataposter med ytterligare kolumner med information.

När du använder sökdata läser du in data i en minnesbaserad uppslagstabell. En kolumn i tabellen måste innehålla en vanlig nyckel som också finns i händelsedataposterna. Data i själva uppslagstabellen kan läsas in från en platt fil eller från en ODBC-datakälla. Uppslagsdata kan införlivas i datauppsättningen under loggbehandlings- eller transformeringsfasen i datauppsättningsprocessen.

Om du vill inkludera sökdata måste du först generera en uppslagsfil eller ha den information som behövs för att få åtkomst till en SQL-databas och sedan definiera en eller flera av följande omformningar i datauppsättningens konfigurationsfiler för loggbearbetning och transformering.

**Integrera uppslagsdata i datauppsättningen**

1. Generera sökfilen. Se [Fylla i uppslagstabellen](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. Definiera en av följande typer av omformningar i parametern Transformations i rätt datauppsättningskonfigurationsfil:

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>Observera att [!DNL ODBCLookup]-omformningen endast fungerar när den definieras i [!DNL Transformation.cfg]-filen eller i en [!DNL Transformation Dataset Include]-fil.
