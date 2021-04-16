---
description: I Workspaces-mappen i Datans Workbench installationskatalog anger filen folder.lock om arbetsytorna i den aktuella mappen är låsta, medan filen workspace name.lock anger om en viss arbetsyta är låst.
title: Folder.lock och workspace.lock-filer
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 0%

---

# Folder.lock och workspace.lock-filer{#folder-lock-and-workspace-lock-files}

I Workspaces-mappen i Datans Workbench installationskatalog anger filen folder.lock om arbetsytorna i den aktuella mappen är låsta, medan filen workspace name.lock anger om en viss arbetsyta är låst.

När du låser hela mappar kan du låsa dem på mappnivå för arbetsytor eller på undermappsnivå (tabb). Du kan också låsa eller låsa upp alla dina mappar (på mappnivå för arbetsytor) och sedan ange undantagen för vissa undermappar (med [!DNL folder.lock]-filer) eller vissa arbetsytor (med *namn på arbetsytan*.lock-filer).

I följande exempel markeras tre element:[!DNL Profile Manager]

* En [!DNL folder.lock]-fil för arbetsytemappen
* En [!DNL Monthly Numbers.lock]-fil för arbetsytefilen [!DNL Monthly Numbers.vw]

* En [!DNL folder.lock]-fil för undermappen Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

I det här exemplet är [!DNL Workspaces folder.lock]-filen inställd på låst, vilket låser alla arbetsytor i den här instansen av Data Workbench. Arbetsytor\Anpassad undermapp [!DNL folder.lock] är inställd på olåst, vilket låser upp alla arbetsytor på fliken [!DNL Custom]. Slutligen är [!DNL Monthly Numbers.lock]-filen låst, vilket låser arbetsytan Månadsnummer.

## Skapar .lock-filer {#section-c4f78b4b43c347368a376904effb41d2}

Du kan skapa en [!DNL new folder.lock]-fil med alternativet [!DNL Create menu] i [!DNL Profile Manager] eller [!DNL Workspaces Manager]. Du kan också skapa en [!DNL folder.lock]- eller *arbetsytans namn*.lock-fil genom att kopiera och klistra in en befintlig [!DNL .lock]-fil i lämplig mapp, ändra filens namn (endast för *arbetsytans namn*.lock-filer) och ändra inställningen i filen om det behövs.

**Så här skapar du en ny mapp.låsfil**

1. I Data Workbench öppnar du [!DNL Workspaces Manager] genom att högerklicka i en arbetsyta och klicka på **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Klicka på den mapp som du vill skapa en [!DNL folder.lock]-fil för.
1. Högerklicka i cellen i kolumnen [!DNL User] för den mappen och klicka på **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. En [!DNL new folder.lock]-fil visas. [!DNL New folder.lock] som standard är  [] upplåsta.
1. (Valfritt) Om du behöver ändra inställningen i filen:

   1. Högerklicka på bockmarkeringen för filen.
   1. Klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Filen [!DNL folder.lock] öppnas.

   1. Ändra inställningen till [låst].
   1. Spara och stäng filen.

1. Om du vill göra den här inställningen för alla användare som arbetar med samma arbetsprofil högerklickar du på bockmarkeringen för filen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

Arbetsytorna i den här mappen är nu låsta eller olåsta enligt inställningen i den nya filen.

**Så här skapar du en .lock-fil från en befintlig fil**

1. Högerklicka på bockmarkeringen för en befintlig [!DNL .lock]-fil i [!DNL Profile Manager] eller [!DNL Workspaces Manager] och klicka på **[!UICONTROL Copy]**.
1. Högerklicka i cellen i kolumnen [!DNL User] för mappen som du vill klistra in filen i och klicka på **[!UICONTROL Paste]**.[!DNL .lock]
1. Om den här filen används för att låsa en enskild arbetsyta högerklickar du på bockmarkeringen för filen [!DNL .lock] i kolumnen [!DNL User] och ändrar namnet i fältet [!DNL File] så att det matchar namnet på den arbetsyta som du vill låsa.

   Om du till exempel vill låsa arbetsytan [!DNL Monthly Numbers.vw] ger du filen namnet [!DNL Monthly Numbers.lock].Om den här filen används för att låsa en enskild arbetsyta högerklickar du på bockmarkeringen för filen [!DNL .lock] i kolumnen [!DNL User] och ändrar namnet i fältet [!DNL File] så att det matchar namnet på den arbetsyta som du vill låsa. Om du till exempel vill låsa arbetsytan [!DNL Monthly Numbers.vw] ger du filen namnet &quot;[!DNL Monthly Numbers.lock]&quot;.

1. Så här ändrar du inställningen i filen:

   1. Högerklicka på bockmarkeringen för filen.
   1. Klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Filen [!DNL .lock] öppnas.

   1. Ändra inställningen till [låst] eller [olåst].
   1. Spara och stäng filen.

1. Om du vill göra den här inställningen för alla användare som arbetar med samma arbetsprofil högerklickar du på bockmarkeringen för filen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

De markerade arbetsytorna är nu låsta eller olåsta enligt inställningen i den nya filen.
