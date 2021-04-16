---
description: Vanligtvis besvarar Datan Workbench inkommande användarfrågor när de tas emot och fortsätter att tillhandahålla resultat och uppdateringar i realtid tills användaren inte längre begär dem.
title: Frågekö
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Frågekö{#query-queue}

Vanligtvis besvarar Datan Workbench inkommande användarfrågor när de tas emot och fortsätter att tillhandahålla resultat och uppdateringar i realtid tills användaren inte längre begär dem.

Ibland, särskilt på system med många Data Workbench, kräver antalet aktiva frågor mer systemresurser än vad som är tillgängligt från servern. [!DNL Query Queue] gör att servern kan placera vissa frågor tillfälligt i vänteläge tills de resurser som krävs för att ge svar blir tillgängliga. [!DNL Query Queue] innehåller även funktioner för att prioritera frågor baserat på en mängd parametrar, så att frågor med högre prioritet besvaras först om resurskonflikter uppstår.

Frågor från en enskild klient- eller rapportserver placeras i en hög och schemaläggs som en enhet. Du kan konfigurera resursövervakare för att begränsa mängden systemresurser som används av frågor. När de övervakade resurserna tillåter schemaläggning av en annan frågegrupp schemaläggs den högprioriterade gruppen. Användare vars frågor inte har schemalagts ännu, på grund av resursbegränsningar, får inget fel, men meddelas om att deras frågor står i kö och att användaren kan fortsätta att arbeta med det lokala exemplet.

Standardkonfigurationen innehåller en enkel konfiguration för [!DNL Query Queue], men låter den vara inaktiverad. Administratörer kan aktivera eller inaktivera [!DNL Query Queue], konfigurera resursövervakare för att avgöra hur mycket av olika resurser som används för frågor och konfigurera komplexa prioriteringsprinciper för olika användare.

**Så här konfigurerar du filen Server.cfg för[!DNL Query Queuing]**

1. Öppna [!DNL Server.cfg] genom att klicka på **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Högerklicka på **[!UICONTROL Server.cfg]** och gör den lokal för redigering.
1. Expandera [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Konfigurera följande parametrar:

   * **Användargrupper:** Här kan du konfigurera principer, användare och köprioritet. Se [Användargrupper för frågekö](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) för definitioner.

   * **Aktiv:** (Vector) Aktiverar eller inaktiverar  [!DNL Query Queue]. Giltiga värden är true eller false. Standardinställningen är false.

   * **Standardanvändargrupp:** (Sträng) Ange ett namn på den användargrupp som användarna ska läggas till i, om de inte finns med i någon användargrupp.
   * **Resursövervakare:**  (Vector) Högerklicka för att lägga till en resursövervakare. Du kan ange om [!DNL Query Queue] ska övervaka minnet eller antalet frågor. Högerklicka på **[!UICONTROL Resource Monitor]** för att välja Minnesbudgetövervakare eller Antal frågor. Mer information finns i [Resursövervakare för frågekö](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325).

   * **Oberörbar prioritet:** (Int) Anger att buntar med en prioritet som är större än eller lika med det här värdet aldrig ska föregås av schemaläggning av högprioriterade buntar. Används tillsammans med [!DNL Memory Budget Monitor] som beskrivs i tabellen [Parametrar för användargrupp](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
