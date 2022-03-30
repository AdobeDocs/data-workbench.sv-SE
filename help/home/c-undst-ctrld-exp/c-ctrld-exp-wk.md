---
description: I ett experiment kan du definiera valfritt antal testgrupper förutom kontrollgruppen.
solution: Analytics
title: Hur fungerar kontrollerade experiment?
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# Hur fungerar kontrollerade experiment?{#how-do-controlled-experiments-work}

I ett experiment kan du definiera valfritt antal testgrupper förutom kontrollgruppen.

När ett experiment körs blir alla besökare på webbplatsen en del av experimentet, antingen som en del av en testgrupp eller kontrollgruppen, så snart de kommer åt någon sida som ingår i experimentet. Besökare tilldelas slumpmässigt till dina experimentgrupper i proportioner som definieras under experimentkonfigurationen.

Kontrollerade experiment implementeras med [!DNL Sensor] programvara som är installerad på var och en av innehållsservrarna i ditt webbkluster. När innehållsservrarna tar emot förfrågningar [!DNL Sensor] väljs besökare för testgrupperna slumpmässigt och deras sidförfrågningar dirigeras om till det experimentella innehållet. När [!DNL Sensor] väljer en besökare för att visa testinnehållet. Adressfältet fortsätter att visa den ursprungligen begärda URI:n, men besökaren dirigeras till test-URI:n. Eftersom den här processen utförs internt i serverprogrammet är användarna inte medvetna om när de testas, vilket är viktigt för opartisk experimenterande.

[!DNL Sensor] skickar test-URI:erna, inte den ursprungliga URI:n som visas för användaren, till loggfilerna som ska användas i analysen.

Resultaten av försöken kan enkelt analyseras med [!DNL Insight] för att avgöra om den experimentella hypotes som du testade är korrekt.

>[!NOTE]
>
>Adobe rekommenderar starkt att kontrollerade experiment samordnas och utförs med synpunkter från de personer i organisationen som ansvarar för att konfigurera och underhålla analysdatauppsättningarna.
