---
description: Steg för att uppgradera mappen Transform.
title: Uppgraderar omformning
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# Uppgraderar omformning{#upgrading-transform}

{{eol}}

Steg för att uppgradera mappen Transform.

1. Öppna [!DNL .zip] filen för [!DNL Insight Server] och öppna [!DNL Profiles] i den mappen [!DNL .zip] -fil.
1. Kopiera [!DNL Transform] mapp till [!DNL Profiles] i din [!DNL Insight Server] installationskatalog. Om du gör det skrivs befintliga [!DNL Transform] mapp.
1. För varje profil som ärver [!DNL Transform] bekräfta att [!DNL profile.cfg] filen har en Transform-post i katalogvektorn.
Ombearbetningen av data börjar efter synkronisering av profilen.
