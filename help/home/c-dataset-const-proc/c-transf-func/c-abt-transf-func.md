---
description: Omformningsfunktionen (Transform) körs på en dator med en workbench-server för att möjliggöra export av loggkälldata för användning i andra program.
title: Om omformningsfunktioner
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
exl-id: db5d6329-407d-43f3-92fc-1b40f7289916
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Om omformningsfunktioner{#about-transformation-functionality}

{{eol}}

Omformningsfunktionen (Transform) körs på en dator med en workbench-server för att möjliggöra export av loggkälldata för användning i andra program.

[!DNL Transform] kan läsa [!DNL .vsl] filer, loggfiler, XML-filer och ODBC-data och exportera data som [!DNL .vsl] filer, textfiler eller avgränsade textfiler som kan användas av inläsningsrutiner, revisionsbyråer eller andra mål för DataWarehouse. Dataextraheringen och dataomvandlingen kan utföras kontinuerligt eller schemalagt.

>[!NOTE]
>
>Vanligtvis [!DNL Transform] är konfigurerad på en FSU för en data workbench-server. Implementeringen kan dock kräva konfiguration på en Data Workbench-server DPU. Kontakta Adobe om du vill ha mer information.

Information om minnesanvändning finns i [!DNL Transform] i gränssnittet Detaljerad status. Mer information finns i kapitlet Administrativa gränssnitt i *Användarhandbok för Data Workbench*.

Med segmentexportfunktionen kan du exportera data från ett Adobe-program på ett annat sätt. [!DNL Transform] Med kan du exportera obearbetade data till ett externt mål, men med segmentexportfunktionen kan du exportera bearbetade data från datauppsättningen och kräver att exporterade data definieras som en dimension i datauppsättningen. Mer information om segmentexport finns i *Användarhandbok för Data Workbench*.
