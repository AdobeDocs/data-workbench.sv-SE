---
description: Steg för att skicka om rapporter via e-post.
solution: Analytics
title: Skicka rapporter via e-post
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skicka rapporter via e-post{#resending-reports-by-email}

Steg för att skicka om rapporter via e-post.

Om **[!UICONTROL Allow Report Regeneration]** parametern i [!DNL Report.cfg] filen är inställd på [!DNL True]återskapas rapporterna i den uppsättningen automatiskt när du gör ändringar i en [!DNL Report.cfg] fil och sparar filen på servern. Rapporterna skickas inte om via e-post.

1. På [!DNL Reports] fliken väljer du undermappen (flik eller nedrullningsbar underkatalog) för den rapportuppsättning som du vill skicka om.
1. Klicka på **[!UICONTROL Report.cfg]**. Parametrarna för [!DNL Report.cfg] rapportuppsättningen visas.
1. Ändra parametern till den **[!UICONTROL Start Date]** tidpunkt då du vill att rapporter ska skickas igen.
1. Spara filen genom att högerklicka **[!UICONTROL Report.cfg (modified)]** överst i parametrarna och klicka på **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
Rapporterna i den här uppsättningen genereras om och skickas igen med e-post till de angivna mottagarna.
