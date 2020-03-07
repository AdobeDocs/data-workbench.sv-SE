---
description: Steg för att uppgradera mappen Transform.
solution: Insight
title: Uppgraderar omformning
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Uppgraderar omformning{#upgrading-transform}

Steg för att uppgradera mappen Transform.

1. Öppna [!DNL .zip] filen för [!DNL Insight Server] versionspaketet och öppna [!DNL Profiles] mappen i den [!DNL .zip] filen.
1. Kopiera [!DNL Transform] mappen till [!DNL Profiles] mappen i din [!DNL Insight Server] installationskatalog. Om du gör det skrivs den befintliga [!DNL Transform] mappen över.
1. För varje profil som ärver [!DNL Transform] profilen måste du kontrollera att [!DNL profile.cfg] filen har en Transform-post i katalogvektorn.
Ombearbetningen av data börjar efter synkronisering av profilen.
