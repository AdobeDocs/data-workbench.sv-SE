---
description: Exportera data Workbench-data till Adobe Target med TargetBulkUpload.exe från detaljtabellen.
title: Exportera till Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportera till Adobe Target{#export-to-adobe-target}

Exportera data Workbench-data till Adobe Target med TargetBulkUpload.exe från detaljtabellen.

Med Data Workbench kan ni exportera filer för integrering med Adobe Target som en del av ett integrerat Adobe Experience Cloud.

Filen **[!DNL TargetBulkUpload]** finns i mappen *Server\Scripts* i serverinstallationsfilerna. Den körbara filen har återförsökslogik samt ytterligare logik för att optimera prestanda.

Du kan ändra filen och flytta den till mappen `TargetBulkUpload.cfg` Server/Admin/Export ** innan du kör överföringsskriptet. Du kan t.ex. ange ett maximalt tidsgränsintervall till 720 minuter (standard) för att timeout för överföringen efter den angivna perioden.

**Så här fungerar det**

När data har skickats till Target övervakas status för överföringen kontinuerligt. Om överföringen lyckas loggas ett meddelande om att överföringen lyckades. Övervakningen fortsätter om överföringen misslyckas eller väntar. Du kan konfigurera tidsgränsen i `TargetBulkUpload.cfg` filen. Om överföringen fastnar på Target loggas ett meddelande och statusen kan fortfarande övervakas.

Det finns två loggfiler som genereras i spårningen för den utlösta exporten under [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

Filen har en detaljerad status för alla poster i flera satser, edge-servern som de ska gå till och status (lyckad, misslyckades, ingen profil hittades, status okänd och fastsatt). `targetbulkuploadexportname.log` Om någon sats fastnar, behandlas inte satsen vidare. Det finns en fastsatt batch-URL för att spåra statusen. Se följande exempeldata från `targetbulkuploadexportname.log.completed` filen:

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

