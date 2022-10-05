---
description: Information om hur du anger parametrar i filen Transform.cfg baserat på flera scenarier.
title: Exempel på Datan Workbench Transform.cfg-filer
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Exempel på Datan Workbench Transform.cfg-filer{#sample-data-workbench-transform-cfg-files}

{{eol}}

Information om hur du anger parametrar i filen Transform.cfg baserat på flera scenarier.

* [A Simple Insight Transform.cfg File](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [Utdata med kommaseparerade värden](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [Exempelloggfiler](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Dela upp loggfiler efter webbplatsavsnitt](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

I varje exempel visas filen som [!DNL Transform.cfg] i data workbench.

## En enkel Data Workbench Transform.cfg-fil {#section-b7e83cafa3a947c597bd09d316930190}

Följande [!DNL Transform.cfg] fönstret innehåller instruktioner för att läsa [!DNL .vsl] filer från [!DNL Logs] och exportera x-timestring- och x-trackingid-fälten till en textfil som lagras i katalogen Logs\VT. Eftersom ingen filrotationsperiod eller utdatafilens namnformat har angetts innehåller varje fil data för en kalenderdag och har ett namn i standardformatet [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## Utdata med kommaseparerade värden {#section-03916934ad574efc8695abbae54a1816}

Följande [!DNL Transform.cfg] fönstret innehåller instruktioner för att läsa [!DNL .vsl] filer från katalogen Logs och exportera fälten 0 till 13 till ett kommaavgränsat ( [!DNL .csv]) i katalogen Logs\VT\CSV. Eftersom ingen filrotationsperiod har angetts innehåller varje fil data för en kalenderdag. Utdatafilerna är [!DNL .csv] filer som namngetts i formatet [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## Exempelloggfiler {#section-113b3b0c0c7547ea9536bb2f465c0875}

Du kan konfigurera omvandlingsfunktioner för att skapa och underhålla en uppdaterad, kompakt version av dina fullständiga loggfiler. På så sätt kan du testa datauppsättningskonfigurationerna snabbt, med ombearbetningstider på sekunder eller minuter i stället för timmar som behövs för att bearbeta hela datauppsättningen på nytt. Följande exempel innehåller ett exempel på hur du konfigurerar omformningsfunktioner för att göra detta.

Följande [!DNL Transform.cfg] fönstret innehåller instruktioner för att läsa [!DNL .vsl] filer från katalogen Logs och exportera x-timestring- och x-trackingid-fälten till en textfil som lagras i katalogen Logs\VT. Det angivna hash-tröskelvärdet filtrerar vissa spårnings-ID:n från datauppsättningen och skapar därmed en datauppsättning som samplas med faktorn 100. Eftersom ingen filrotationsperiod har angetts innehåller varje fil data för en kalenderdag. Utdatafilernas namn har standardformatet [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Dela upp loggfiler efter webbplatsavsnitt {#section-2cac205cd3934d31abb6c6ed8780196d}

Följande [!DNL Transform.cfg] fönstret innehåller instruktioner för att läsa [!DNL .vsl]filer från katalogen Logs och exportera x-timestring- och x-trackingid-fälten till en textfil som lagras i katalogen Logs\VT. Omformning av reguljära uttryck ( [!DNL RETransform]) används som indata i cs-uri-stam-fältet och skapar ett nytt fält (x-site) som definierar ett avsnitt på platsen. Fältet x-site inkluderas i namnet på utdatafilerna, som vart och ett innehåller data för en kalenderdag.

![](assets/cfg_VisualTransform_SplittingExample.png)
