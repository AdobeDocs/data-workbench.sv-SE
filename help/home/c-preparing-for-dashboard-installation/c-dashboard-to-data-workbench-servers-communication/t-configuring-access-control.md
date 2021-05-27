---
description: Kontrollpanelen kräver vissa skrivskyddade behörigheter för att kunna komma åt och visa data i din data workbench-data. Skrivbehörighet krävs inte.
title: Konfigurera åtkomstkontroll
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Konfigurera åtkomstkontroll{#configuring-access-control}

Kontrollpanelen kräver vissa skrivskyddade behörigheter för att kunna komma åt och visa data i din data workbench-data. Skrivbehörighet krävs inte.

När du konfigurerar åtkomstkontrollen måste du redigera din [!DNL Access Control.cfg]-fil på FSU:erna och lägga till en ny grupp för att ge behörighet till kontrollpanelen för data workbench:

1. Redigera [!DNL AccessControl.cfg]-filen (helst med arbetsstationen data workbench).
1. Skapa en ny grupp med namnet *Insight Dashboard Access*.
1. Under gruppens medlemmar lägger du till rätt CN som du fått för detta (exempel: CN:INSIGHT-USER01). Kontakta Adobe kundtjänst för detta CN.
1. Ändra listan under den här gruppens skrivskyddade åtkomst så att den återspeglar följande:

* /Profiler/$
* /Profiler/
* /Adresser
* /Status/
* /Användare/$

1. Ta bort objekt från åtkomstavsnittet för läsbehörighet eftersom inga skrivbehörigheter krävs för instrumentpanelen.
1. Spara ändringarna i [!DNL AccessControl.cfg]-filen på servern för att behörigheter ska börja gälla.
