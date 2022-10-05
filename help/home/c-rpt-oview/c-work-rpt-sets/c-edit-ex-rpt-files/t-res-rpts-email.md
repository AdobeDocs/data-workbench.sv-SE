---
description: Steg för att skicka om rapporter via e-post.
title: Skicka rapporter via e-post
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---

# Skicka rapporter via e-post{#resending-reports-by-email}

{{eol}}

Steg för att skicka om rapporter via e-post.

Om **[!UICONTROL Allow Report Regeneration]** -parametern i [!DNL Report.cfg] filen är inställd på [!DNL True], när du gör ändringar i en [!DNL Report.cfg] och sparar filen på servern, genererar Report Server automatiskt om rapporterna i uppsättningen. Rapporterna skickas inte om via e-post.

1. På [!DNL Reports] markerar du undermappen (flik eller nedrullningsbar underkatalog) för den rapportuppsättning som du vill skicka om.
1. Klicka på **[!UICONTROL Report.cfg]**. Parametrarna för [!DNL Report.cfg] för den här rapportuppsättningen.
1. Ändra **[!UICONTROL Start Date]** parametern till den framtida tidpunkt då du vill att rapporterna ska skickas igen.
1. Spara filen genom att högerklicka **[!UICONTROL Report.cfg (modified)]** längst upp i parametrarna och klicka på **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Rapporterna i den här uppsättningen genereras om och skickas igen med e-post till de angivna mottagarna.
