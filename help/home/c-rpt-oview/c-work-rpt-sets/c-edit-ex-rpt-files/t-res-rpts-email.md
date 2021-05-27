---
description: Steg för att skicka om rapporter via e-post.
title: Skicka rapporter via e-post
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---

# Skicka rapporter igen via e-post{#resending-reports-by-email}

Steg för att skicka om rapporter via e-post.

Om parametern **[!UICONTROL Allow Report Regeneration]** i filen [!DNL Report.cfg] är inställd på [!DNL True], när du ändrar en [!DNL Report.cfg]-fil och sparar filen på servern, genererar Report Server automatiskt om rapporterna i den uppsättningen. Rapporterna skickas inte om via e-post.

1. På fliken [!DNL Reports] väljer du undermappen (flik eller nedrullningsbar underkatalog) för den rapportuppsättning som du vill skicka om.
1. Klicka på **[!UICONTROL Report.cfg]**. Parametrarna för [!DNL Report.cfg] för den här rapportuppsättningen visas.
1. Ändra parametern **[!UICONTROL Start Date]** till den framtida tidpunkt då du vill att rapporter ska skickas igen.
1. Spara filen genom att högerklicka på **[!UICONTROL Report.cfg (modified)]** överst i parametrarna och klicka på **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Rapporterna i den här uppsättningen genereras om och skickas igen med e-post till de angivna mottagarna.
