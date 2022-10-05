---
description: Varje DPU från vilken kontrollpanelen ska visa data måste ha en Query API-licens.
title: Verifierar aktivering av fråge-API
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Verifierar aktivering av fråge-API{#verifying-query-api-enablement}

{{eol}}

Varje DPU från vilken kontrollpanelen ska visa data måste ha en Query API-licens.

Nedan finns instruktioner om hur du validerar att Query API är installerat och aktiverat.

1. Hitta din data workbench-servers certifikat.
1. Öppna det här certifikatet i en textredigerare.
1. Kontrollera att raden `Product = Query API` finns i certifikatet.
1. I **[!UICONTROL Trace]** mapp, öppna [!DNL InsightServer64.log] i en textredigerare.
1. I de senaste startloggposterna kontrollerar du att raden `Enabling Query API (licensed)` visas.

* Om Query API inte är aktiverat visas posten `Not enabling Query API (not licensed)`.
* Om du inte ser några loggposter, eller misstänker att data workbench-servern har startats om sedan Query API lades till, startar du om data workbench-servern igen och kontrollerar loggen.

   Om du inte kan verifiera att Query API är aktiverat kontaktar du Adobe ClientCare.
