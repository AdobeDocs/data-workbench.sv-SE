---
description: I ett experiment kan du definiera valfritt antal testgrupper förutom kontrollgruppen.
solution: Insight,Analytics
title: Hur fungerar kontrollerade experiment?
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hur fungerar kontrollerade experiment?{#how-do-controlled-experiments-work}

I ett experiment kan du definiera valfritt antal testgrupper förutom kontrollgruppen.

När ett experiment körs blir alla besökare på webbplatsen en del av experimentet, antingen som en del av en testgrupp eller kontrollgruppen, så snart de kommer åt någon sida som ingår i experimentet. Besökare tilldelas slumpmässigt till dina experimentgrupper i proportioner som definieras under experimentkonfigurationen.

Kontrollerade experiment implementeras med hjälp av den programvara som är installerad på alla innehållsservrar i webbklustret. [!DNL Sensor] När innehållsservrarna tar emot förfrågningar väljs besökare för testgrupperna slumpmässigt och deras sidförfrågningar omdirigeras till det experimentella innehållet. [!DNL Sensor] När [!DNL Sensor] väljer en besökare för att visa testinnehållet fortsätter adressfältet att visa den ursprungligen begärda URI:n, men besökaren dirigeras till test-URI:n. Eftersom den här processen utförs internt i serverprogrammet är användarna inte medvetna om när de testas, vilket är viktigt för opartisk experimenterande.

[!DNL Sensor] skickar test-URI:erna, inte den ursprungliga URI:n som visas för användaren, till loggfilerna som ska användas i analysen.

Resultaten av försöken kan enkelt analyseras med hjälp av [!DNL Insight] vilken man kan avgöra om den experimentella hypotes som du testade är korrekt.

>[!NOTE]
>
>Adobe rekommenderar starkt att kontrollerade experiment samordnas och utförs med hjälp av synpunkter från de personer i organisationen som ansvarar för att konfigurera och underhålla analysdatauppsättningarna.

