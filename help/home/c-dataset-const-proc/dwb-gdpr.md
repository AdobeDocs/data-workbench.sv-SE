---
description: Adobe Data Workbench tillhandahåller verktyg och processer för att göra era data klara för att följa de allmänna dataskyddsreglerna (GDPR).
title: Data Workbench Support for GDPR
exl-id: fdc43567-0c57-4851-9073-e295258a8074
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Data Workbench Support for GDPR

Adobe Data Workbench tillhandahåller verktyg och processer för att göra data klara för att uppfylla kraven i [!DNL General Data Protection Regulations] (GDPR).

I likhet med alla Adobe Analytics-lösningar ger Data Workbench stöd för GDPR genom att tillhandahålla rensning, borttagning och märkning av analytiska variabler vid bearbetning av Adobe Analytics dataflöde. Som stöd för GDPR-implementeringar kan du med Adobe skapa processer för GDPR i enlighet med ditt företags behörigheter som fastställs i ditt avtal med Adobe. Mer information finns i [Adobe Analytics och GDPR](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

GDPR-förordningen identifierar rollerna och skyldigheterna för de olika parter som ansvarar för GDPR-aktiveringen (se [GDPR och Ditt företag](https://www.adobe.com/se/privacy/general-data-protection-regulation.html)).

* Din organisation fungerar som **personuppgiftsansvarig** för att fastställa kontext och lagring av personuppgifter baserat på dina behov och begränsningar. Adobe bearbetar och lagrar sedan dessa data åt dig.
* Adobe fungerar som **databehandlare** och tillhandahåller programvaran och tjänsterna för att implementera GDPR-krav baserat på ditt avtal med Adobe.
* Efter integrering av Data Workbench med GDPR-tjänsten och enligt GDPR-standarder kan besökare på en webbplats (de **registrerade**) utöva sin&quot;rätt att bli bortglömd&quot; av Adobe, dataprocessorn. För att uppnå rättigheten att bli bortglömd kan du som personuppgiftsansvariga överföra utmanande besökar-ID:n till Adobe från ett användargränssnitt eller ett API. Mer information finns i [dokumentationen för Adobe Analytics GDPR-arbetsflödet](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html), inklusive [begäran om åtkomst och borttagning](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html).

>[!NOTE]
>
>För andra datakällor ansvarar din organisation för att rensa komplexa besökar-ID:n från andra loggkällor, som CRM, POS, IVR och andra rådatakällor. Tjänstepaket med skräddarsydd omfattning kommer att vara tillgängliga för att ge stöd för organisationer genom att _tillhandahålla en fullständig ersättningsuppsättning med filer för varje datakälla_ som det krävs för att upprätthålla eller stödja pågående tjänstbehållare.

## Uppgraderar DWB för GDPR-implementering

Rådgivning ger dig råd om vilka tjänster som är lämpliga för att se till att befintliga implementeringar följs. Kontakta din Customer Success Manager (CSM) om du vill ha mer information.

Om det behövs:

* [Uppgradera till den senaste ](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) versionen av Datan Workbench. För högsta säkerhet har nya certifikat och säkerhetsfunktioner lagts till i DWB 6.7-utgåvorna som krävs för GDPR-integrering.
* Uppgradera till [Avro data feed](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2) om du använder äldre händelseloggar för TSV Analytics.
* Om du använder en äldre UCP (Unified Customer Process) med Transform för att uppdatera befintliga loggar uppgraderar du till den aktuella processen. Den uppdaterade processen genererar direkt en överordnad sökfil för att mappa besökar-ID:n mellan olika källor.
* Standardisera dataflödet för att passa GDPR-tjänsten.
* Skapa ett tjänstepaket med anpassad omfattning för att hantera andra loggkällor som CRM, POS, IVR och andra rådatakällor.
* Bekräfta en standardperiod för datalagring på 25 månader eller mer i Analytics-kontraktet.
