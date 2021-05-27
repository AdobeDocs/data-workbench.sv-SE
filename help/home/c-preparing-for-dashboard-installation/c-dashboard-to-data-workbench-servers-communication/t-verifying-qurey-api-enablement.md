---
description: Varje DPU från vilken kontrollpanelen ska visa data måste ha en Query API-licens.
title: Verifierar aktivering av fråge-API
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Verifierar aktivering av fråga-API{#verifying-query-api-enablement}

Varje DPU från vilken kontrollpanelen ska visa data måste ha en Query API-licens.

Nedan finns instruktioner om hur du validerar att Query API är installerat och aktiverat.

1. Hitta din data workbench-servers certifikat.
1. Öppna det här certifikatet i en textredigerare.
1. Kontrollera att raden `Product = Query API` finns i certifikatet.
1. Öppna mappen [!DNL InsightServer64.log] i en textredigerare i mappen **[!UICONTROL Trace]**.
1. Kontrollera att raden `Enabling Query API (licensed)` visas i de senaste startloggposterna.

* Om fråge-API:t inte är aktiverat visas posten `Not enabling Query API (not licensed)`.
* Om du inte ser några loggposter, eller misstänker att data workbench-servern har startats om sedan Query API lades till, startar du om data workbench-servern igen och kontrollerar loggen.

   Om du inte kan verifiera att Query API är aktiverat kontaktar du Adobe ClientCare.
