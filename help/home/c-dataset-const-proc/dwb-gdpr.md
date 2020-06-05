---
description: Adobe Data Workbench innehåller verktyg och processer för att förbereda dina data så att de överensstämmer med de allmänna dataskyddsreglerna (GDPR).
solution: Analytics
title: Data Workbench-stöd för GDPR
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# Data Workbench-stöd för GDPR

Adobe Data Workbench innehåller verktyg och processer för att förbereda data för att uppfylla kraven i [!DNL General Data Protection Regulations] (GDPR).

Precis som alla Adobe Analytics-lösningar har Data Workbench stöd för GDPR genom att tillhandahålla rensning, borttagning och märkning av analysvariabler vid bearbetning av Adobe Analytics dataflöde. För att stödja GDPR-implementeringar kan Adobe låta er skapa processer för GDPR i enlighet med ert företags behörigheter som fastställs i ert avtal med Adobe. Mer information finns i [Adobe Analytics och GDPR](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

GDPR-förordningen identifierar rollerna och skyldigheterna för de olika parter som ansvarar för GDPR-aktiveringen (se [GDPR och Er verksamhet](https://www.adobe.com/privacy/general-data-protection-regulation.html)).

* Din organisation fungerar som **personuppgiftsansvarig** för att fastställa sammanhang och lagring av personuppgifter baserat på dina behov och begränsningar. Adobe bearbetar och lagrar sedan dessa data åt dig.
* Adobe fungerar som **personuppgiftsbiträde** och tillhandahåller programvara och tjänster för att implementera GDPR-krav baserat på ditt avtal med Adobe.
* Efter integrering av Data Workbench med GDPR-tjänsten och enligt GDPR-standarderna kan besökare på en webbplats (de **registrerade**) utöva sin&quot;rätt att bli bortglömd&quot; av Adobe, dataprocessorn. För att uppnå rättigheten att bli bortglömd kan du som personuppgiftsansvariga överföra utmanande besökar-ID:n till Adobe från ett användargränssnitt eller API. Mer information finns i dokumentationen för [Adobe Analytics GDPR-arbetsflöde](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) , inklusive förfrågningar om [åtkomst och borttagning](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) .

>[!NOTE]
>
>För andra datakällor ansvarar din organisation för att rensa komplexa besökar-ID:n från andra loggkällor, som CRM, POS, IVR och andra rådatakällor. Tjänstepaket med skräddarsydd räckvidd kommer att finnas tillgängliga för att ge stöd till organisationer genom _att tillhandahålla en fullständig uppsättning ersättningsfiler för varje datakälla_ som kontinuerliga tjänstbehållare krävs för att stödja eller underhålla.

## Uppgraderar DWB för GDPR-implementering

Rådgivning ger dig råd om lämpliga tjänster för att se till att befintliga implementeringar är kompatibla. Kontakta din Customer Success Manager (CSM) om du vill ha mer information.

Om det behövs:

* [Uppgradera till den senaste versionen](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) av Data Workbench. För högsta säkerhet har nya certifikat och säkerhetsfunktioner lagts till i DWB 6.7-utgåvorna som krävs för GDPR-integrering.
* Om du använder äldre händelseloggar för TSV Analytics ska du uppgradera till [Avro-dataflödet](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Om du använder en äldre UCP (Unified Customer Process) med Transform för att uppdatera befintliga loggar uppgraderar du till den aktuella processen. Den uppdaterade processen genererar direkt en huvudsökningsfil för att mappa besökar-ID:n mellan olika källor.
* Standardisera dataflödet för att passa GDPR-tjänsten.
* Skapa ett tjänstepaket med anpassad omfattning för att hantera andra loggkällor som CRM, POS, IVR och andra rådatakällor.
* Bekräfta en standardperiod för datalagring på 25 månader eller mer i Analytics-kontraktet.
