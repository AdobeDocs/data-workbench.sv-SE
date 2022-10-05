---
description: Adobe Data Workbench tillhandahåller verktyg och processer för att göra era data klara för att följa de allmänna dataskyddsreglerna (GDPR).
title: Data Workbench Support for GDPR
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Data Workbench Support for GDPR

{{eol}}

Adobe Data Workbench tillhandahåller verktyg och processer för att förbereda data för att uppfylla [!DNL General Data Protection Regulations] (GDPR).

I likhet med alla Adobe Analytics-lösningar ger Data Workbench stöd för GDPR genom att tillhandahålla rensning, borttagning och märkning av analytiska variabler vid bearbetning av Adobe Analytics dataflöde. Som stöd för GDPR-implementeringar kan du med Adobe skapa processer för GDPR i enlighet med ditt företags behörigheter som fastställs i ditt avtal med Adobe. Se [Adobe Analytics och GDPR för ytterligare information](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html).

GDPR-förordningen identifierar rollerna och skyldigheterna för de olika parter som ansvarar för GDPR-aktiveringen (se [GDPR och er verksamhet](https://www.adobe.com/se/privacy/general-data-protection-regulation.html)).

* Din organisation fungerar som **datastyrenhet** för att fastställa sammanhang och lagring av personuppgifter baserat på era behov och begränsningar. Adobe bearbetar och lagrar sedan dessa data åt dig.
* Adobe fungerar som **dataprocessor** att tillhandahålla programvara och tjänster för att implementera GDPR-krav baserat på ditt avtal med Adobe.
* Efter integreringen av Data Workbench med GDPR-tjänsten och enligt GDPR-standarderna, besökare på en webbplats ( **registrerade**) kan utöva sin&quot;rätt att bli bortglömd&quot; av Adobe, personuppgiftsbiträdet. För att uppnå rättigheten att bli bortglömd kan du som personuppgiftsansvariga överföra utmanande besökar-ID:n till Adobe från ett användargränssnitt eller ett API. Se [Adobe Analytics GDPR-arbetsflöde](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) för mer information, inklusive [skicka och ta bort förfrågningar](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) -avsnitt.

>[!NOTE]
>
>För andra datakällor ansvarar din organisation för att rensa komplexa besökar-ID:n från andra loggkällor, som CRM, POS, IVR och andra rådatakällor. Tjänstepaket med skräddarsydd omfattning kommer att finnas tillgängliga för att ge stöd till organisationer via _med en fullständig ersättningsuppsättning av filer för varje datakälla_ att det krävs kontinuerlig service för att stödja eller underhålla.

## Uppgraderar DWB för GDPR-implementering

Rådgivning ger dig råd om lämpliga tjänster för att se till att befintliga implementeringar är kompatibla. Kontakta din Customer Success Manager (CSM) om du vill ha mer information.

Om det behövs:

* [Uppgradera till den senaste versionen](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) Data Workbench. För högsta säkerhet har nya certifikat och säkerhetsfunktioner lagts till i DWB 6.7-utgåvorna som krävs för GDPR-integrering.
* Om du använder äldre händelseloggar för TSV Analytics ska du uppgradera till [Avro data feed](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Om du använder en äldre UCP (Unified Customer Process) med Transform för att uppdatera befintliga loggar uppgraderar du till den aktuella processen. Den uppdaterade processen genererar direkt en överordnad sökfil för att mappa besökar-ID:n mellan olika källor.
* Standardisera dataflödet för att passa GDPR-tjänsten.
* Skapa ett tjänstepaket med anpassad omfattning för att hantera andra loggkällor som CRM, POS, IVR och andra rådatakällor.
* Bekräfta en standardperiod för datalagring på 25 månader eller mer i Analytics-kontraktet.
