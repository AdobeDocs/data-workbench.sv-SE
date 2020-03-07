---
description: Varje DPU från vilken kontrollpanelen ska visa data måste ha en Query API-licens.
solution: Analytics
title: Verifierar aktivering av fråge-API
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verifierar aktivering av fråge-API{#verifying-query-api-enablement}

Varje DPU från vilken kontrollpanelen ska visa data måste ha en Query API-licens.

Nedan finns instruktioner om hur du validerar att Query API är installerat och aktiverat.

1. Hitta din data workbench-servers certifikat.
1. Öppna det här certifikatet i en textredigerare.
1. Kontrollera att raden `Product = Query API` finns i certifikatet.
1. I **[!UICONTROL Trace]** mappen öppnar du [!DNL InsightServer64.log] i en textredigerare.
1. Kontrollera att raden `Enabling Query API (licensed)` visas i de senaste startloggposterna.

* Om Query API inte är aktiverat visas posten `Not enabling Query API (not licensed)`.
* Om du inte ser några loggposter, eller misstänker att data workbench-servern har startats om sedan Query API lades till, startar du om data workbench-servern igen och kontrollerar loggen.

   Om du inte kan verifiera att Query API är aktiverat kontaktar du Adobe ClientCare.
