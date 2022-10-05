---
description: Exportera Data Workbench till Adobe Target med TargetBulkUpload.exe från detaljtabellen.
title: Exportera till Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# Exportera till Adobe Target{#export-to-adobe-target}

{{eol}}

Exportera Data Workbench till Adobe Target med TargetBulkUpload.exe från detaljtabellen.

Med Data Workbench kan du exportera filer för integrering med Adobe Target som en del av en integrerad Adobe Experience Cloud.

The **[!DNL TargetBulkUpload]** filen finns i *Server\Skript* i serverns installationsfiler. Den körbara filen har återförsökslogik samt ytterligare logik för att optimera prestanda.

Du kan ändra `TargetBulkUpload.cfg` och flytta den till *Server/administratör/export* innan överföringsskriptet körs. Du kan t.ex. ange ett maximalt tidsgränsintervall till 720 minuter (standard) för att timeout för överföringen efter den angivna perioden.

**Så här fungerar det**

När data har skickats till Target övervakas status för överföringen kontinuerligt. Om överföringen lyckas loggas ett meddelande om att överföringen lyckades. Övervakningen fortsätter om överföringen misslyckas eller väntar. Du kan konfigurera timeout-intervallet i `TargetBulkUpload.cfg` -fil. Om överföringen fastnar på Target loggas ett meddelande och statusen kan fortfarande övervakas.

Det finns två loggfiler som genereras i spårningen för den utlösta exporten under [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

The `targetbulkuploadexportname.log` filen har detaljerad status för alla poster i flera satser, edge-servern de ska gå till och status (lyckades, misslyckades, profilen hittades inte, status okänd och fastsatt). Om någon sats fastnar, behandlas inte satsen vidare. Det finns en fastsatt batch-URL för att spåra statusen. Se följande exempeldata från `targetbulkuploadexportname.log.completed` fil:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

Stängningsstatusvärdet ökas med den totala fastlagrade batchstorleken oavsett hur många överföringar som har slutförts eller misslyckats. Värdet för den totala radsumman ökas också med samma antal fasta gruppstorlekar.

>[!NOTE]
>
>Tidigare exporterades DWB-data med [!DNL ExportIntegration.exe]. För närvarande används endast MMP-, CRS- och S/FTP-exporter med den här körbara filen. Integreringen med Adobe Target använder nu [!DNL TargetBulkUpload.exe] i Data Workbench.
