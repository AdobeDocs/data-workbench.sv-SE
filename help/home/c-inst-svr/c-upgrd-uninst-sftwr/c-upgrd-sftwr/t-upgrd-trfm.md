---
description: Steg för att uppgradera mappen Transform.
title: Uppgraderar omformning
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# Uppgraderar omformning{#upgrading-transform}

Steg för att uppgradera mappen Transform.

1. Öppna [!DNL .zip]-filen för [!DNL Insight Server]-versionspaketet och öppna mappen [!DNL Profiles] i den [!DNL .zip]-filen.
1. Kopiera mappen [!DNL Transform] till mappen [!DNL Profiles] i installationskatalogen för [!DNL Insight Server]. Om du gör det skrivs den befintliga [!DNL Transform]-mappen över.
1. För varje profil som ärver [!DNL Transform]-profilen måste du kontrollera att [!DNL profile.cfg]-filen har en Transform-post i katalogvektorn.
Ombearbetningen av data börjar efter synkronisering av profilen.
