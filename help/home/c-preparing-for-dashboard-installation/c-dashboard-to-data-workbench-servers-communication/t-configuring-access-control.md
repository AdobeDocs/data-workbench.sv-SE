---
description: Kontrollpanelen kräver vissa skrivskyddade behörigheter för att kunna komma åt och visa data i din data workbench-data. Skrivbehörighet krävs inte.
title: Konfigurera åtkomstkontroll för instrumentpanel
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Konfigurera åtkomstkontroll för instrumentpanel{#configuring-dashboard-access-control}

{{eol}}

Kontrollpanelen kräver vissa skrivskyddade behörigheter för att kunna komma åt och visa data i din data workbench-data. Skrivbehörighet krävs inte.

När du konfigurerar åtkomstkontrollen måste du redigera [!DNL Access Control.cfg] fil på FSU:erna och lägga till en ny grupp för att ge behörighet till kontrollpanelen för data workbench:

1. Redigera [!DNL AccessControl.cfg] -fil (helst med arbetsstationen för data workbench).
1. Skapa en ny grupp med namnet *Åtkomst till Insight Dashboard*.
1. Under gruppens medlemmar lägger du till rätt CN som du fått för detta (exempel: CN:INSIGHT-USER01). Kontakta Adobe kundtjänst för detta CN.
1. Ändra listan under den här gruppens skrivskyddade åtkomst så att den återspeglar följande:

* /Profiler/$
* /Profiler/
* /Adresser
* /Status/
* /Användare/$

1. Ta bort objekt från åtkomstavsnittet för läsbehörighet eftersom inga skrivbehörigheter krävs för instrumentpanelen.
1. Spara ändringarna i [!DNL AccessControl.cfg] till servern för att behörigheterna ska börja gälla.
