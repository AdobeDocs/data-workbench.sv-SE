---
description: Vanligtvis besvarar Data Workbench-servern inkommande användarfrågor när de tas emot och fortsätter att tillhandahålla resultat och uppdateringar i realtid tills användaren inte längre begär dem.
solution: Analytics
title: Frågekö
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Frågekö{#query-queue}

Vanligtvis besvarar Data Workbench-servern inkommande användarfrågor när de tas emot och fortsätter att tillhandahålla resultat och uppdateringar i realtid tills användaren inte längre begär dem.

Ibland, särskilt på system med många Data Workbench-användare, kräver antalet aktiva frågor mer systemresurser än vad som är tillgängligt från servern. [!DNL Query Queue] gör att servern kan placera vissa frågor tillfälligt i vänteläge tills de resurser som krävs för att ge svar blir tillgängliga. Här finns också funktioner för att prioritera frågor baserat på olika parametrar, så att frågor med högre prioritet besvaras först om resurskonflikter uppstår. [!DNL Query Queue]

Frågor från en enskild klient- eller rapportserver placeras i en hög och schemaläggs som en enhet. Du kan konfigurera resursövervakare för att begränsa mängden systemresurser som används av frågor. När de övervakade resurserna tillåter schemaläggning av en annan frågegrupp schemaläggs den högprioriterade gruppen. Användare vars frågor inte har schemalagts ännu, på grund av resursbegränsningar, får inget fel, men meddelas om att deras frågor står i kö och att användaren kan fortsätta att arbeta med det lokala exemplet.

Standardkonfigurationen innehåller en enkel konfiguration för [!DNL Query Queue], men låter den vara inaktiverad. Administratörer kan aktivera eller inaktivera [!DNL Query Queue], konfigurera resursövervakare för att avgöra hur mycket av olika resurser som används för frågor och konfigurera komplexa prioriteringsprinciper för olika användare.

**Så här konfigurerar du filen Server.cfg för[!DNL Query Queuing]**

1. Öppna [!DNL Server.cfg] genom att klicka **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Högerklicka **[!UICONTROL Server.cfg]** och gör den lokal för redigering.
1. Expandera [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Konfigurera följande parametrar:

   * **Användargrupper:** Här kan du konfigurera principer, användare och köprioritet. Se [Användargrupper](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) för frågekö för definitioner.

   * **Aktiv:** (Vector) Aktiverar eller inaktiverar [!DNL Query Queue]. Giltiga värden är true eller false. Standardinställningen är false.

   * **Standardanvändargrupp:** (String) Ange ett namn på den användargrupp som användarna ska läggas till i, om de inte finns med i någon användargrupp.
   * **Resursövervakare:** (Vektor) Högerklicka för att lägga till en resursövervakare. Du kan ange om [!DNL Query Queue] bildskärmen ska övervaka minnet eller antalet frågor. Högerklicka **[!UICONTROL Resource Monitor]** för att välja Minnesbudgetövervakare eller Antal frågor. Mer information finns i Resursövervakare [för](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) frågekö.

   * **Oberörbar prioritet:** (Int) Anger att buntar med en prioritet som är större än eller lika med det här värdet aldrig ska föregås av schemaläggning av högprioriterade buntar. Används tillsammans med den [!DNL Memory Budget Monitor] som beskrivs i tabellen [Parametrar för](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)användargrupp.

