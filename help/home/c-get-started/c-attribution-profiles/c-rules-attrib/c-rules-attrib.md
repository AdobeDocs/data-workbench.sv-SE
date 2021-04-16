---
description: Med den nya regelbaserade attribueringsprofilen i Data Workbench kan du snabbt analysera attribueringshändelser och tilldela ansvar som leder till en lyckad konvertering som du har definierat. Attributprofilen innehåller den information som behövs för att din dataarkitekt ska kunna ställa in och utöka sina funktioner, och innehåller färdiga arbetsytor som din analytiker kan använda för att komma igång direkt.
title: Attributionsprofil
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Attributionsprofil{#attribution-profile}

Med den nya regelbaserade attribueringsprofilen i Data Workbench kan du snabbt analysera attribueringshändelser och tilldela ansvar som leder till en lyckad konvertering som du har definierat. Attributprofilen innehåller den information som behövs för att din dataarkitekt ska kunna ställa in och utöka sina funktioner, och innehåller färdiga arbetsytor som din analytiker kan använda för att komma igång direkt.

Med attribueringsprofilen kan ni få ett nytt perspektiv på relationen mellan era marknadsföringssatsningar och en framgångsrik generering av kundleads eller försäljningskonvertering. Attribution profile (Attribution profile) hjälper er att kvalificera interaktioner som ska få kredit för realiserade intäkter eller deltagande längre fram i kundresan. Det hjälper er att identifiera effekten av era marknadsföringssatsningar och kostnader genom att ni snabbt kan analysera attribueringshändelser och sedan tilldela ansvar för första eller sista kontakten eller andra händelser som leder till en framgångsrik försäljning.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>Attributprofilen är konfigurerad för omedelbar användning av användare som har implementerat den Adobe SC-profil som använder dataflödet för analys (SC/Insight). Som standard används händelserna Marketing och Conversion som standardtyper av interaktioner som utvärderas i de regelbaserade modellerna.

Mer information finns i [Distribuera attributprofilen](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) och [Attributmodeller](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d).

## Arkitektur- och analytikerarbetsytor {#section-27c6aff70ba147cca6e11451e127afb4}

I attribueringsprofilen har du definierat arbetsytorna Architect och Analyst på olika flikar i workbench.

![](assets/attribution_profile_tabs.png)

**Arkitekturarbetsytor**

På fliken **Attribution** klickar du på fliken **[!UICONTROL Architect Workspace]** för att öppna arbetsytor som är särskilt utformade för att konfigurera konfigurationsfiler för grundläggande attribueringsmodellering.

![](assets/attribution_profile_arch.png)

Fliken Arkitektur innehåller arbetsytor som du kan använda för att stega igenom varje konfigurationsfil i mappen för profildatamängder. Med **[!UICONTROL Attribution Configuration - Step 1]** kan du till exempel identifiera attributvärdena i avsnittet Transformation i filen [!DNL profile.cfg].

![](assets/attribution_profile_arch_step1.png)

**Arbetsytor** för analytikerKlicka på  **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** fliken för att öppna arbetsytor med fördefinierade analyser som har måtten och måtten som ingår i attributprofilen.

De här arbetsytorna är ordnade i fyra kategorier:

1. **Grundläggande** rapporter visar en modell i en arbetsyta.
1. **Jämförelserapporter** utökade analyserna genom att presentera flera modeller i en enda vy.
1. **Undersökningsrapporter** utökar rapportmallarna så att attribueringsmodellerna visas i olika format. I det här avsnittet introduceras och exponeras också de positionsbaserade viktningsförhållandena.
1. **Pathing** Reportsger insyn i kundens marknadsföringsresa med flera olika målningsvisualiseringar för att fullt ut utforska och uttrycka processflöden och interaktionsvägar

![](assets/attribution_profile_analyst.png)

Fliken Analytiker innehåller arbetsytor som är förkonfigurerade med rapporter. Med **[!UICONTROL First Attribution]** kan du till exempel välja i tabellen **[!UICONTROL Campaign]** för att se attributet **[!UICONTROL Revenue]** baserat på **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)
