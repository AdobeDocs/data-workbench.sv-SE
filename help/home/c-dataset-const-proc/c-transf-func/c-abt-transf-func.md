---
description: Omformningsfunktionen (Transform) körs på en dator med en workbench-server för att möjliggöra export av loggkälldata för användning i andra program.
solution: Analytics
title: Om omformningsfunktioner
topic: Data workbench
uuid: f797f283-025b-4fb5-a110-84a9483dccaa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Om omformningsfunktioner{#about-transformation-functionality}

Omformningsfunktionen (Transform) körs på en dator med en workbench-server för att möjliggöra export av loggkälldata för användning i andra program.

[!DNL Transform] kan läsa [!DNL .vsl] filer, loggfiler, XML-filer och ODBC-data och exportera data som [!DNL .vsl] filer, textfiler eller avgränsade textfiler som kan användas av DataWarehouse-inläsningsrutiner, revisionsbyråer eller andra mål. Dataextraheringen och dataomvandlingen kan utföras kontinuerligt eller schemalagt.

>[!NOTE]
>
>Vanligtvis [!DNL Transform] är konfigurerad på en FSU för en data workbench-server. Implementeringen kan dock kräva konfiguration på en Data Workbench-server DPU. Kontakta Adobe om du vill ha mer information.

Information om minnesanvändning finns [!DNL Transform] i gränssnittet Detaljerad status. Mer information finns i kapitlet Administrativa gränssnitt i *användarhandboken* för Data Workbench.

Segmentexportfunktionen erbjuder ett annat sätt att exportera data från ett Adobe-program. [!DNL Transform] Med kan du exportera obearbetade data till ett externt mål, men med segmentexportfunktionen kan du exportera bearbetade data från datauppsättningen och kräver att exporterade data definieras som en dimension i datauppsättningen. Mer information om segmentexport finns i användarhandboken för *Data Workbench*.
