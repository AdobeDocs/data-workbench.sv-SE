---
description: I Workspaces-mappen i Datans Workbench installationskatalog anger filen folder.lock om arbetsytorna i den aktuella mappen är låsta, medan filen workspace name.lock anger om en viss arbetsyta är låst.
title: Folder.lock och workspace.lock-filer
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 0%

---

# Folder.lock och workspace.lock-filer{#folder-lock-and-workspace-lock-files}

{{eol}}

I Workspaces-mappen i Datans Workbench installationskatalog anger filen folder.lock om arbetsytorna i den aktuella mappen är låsta, medan filen workspace name.lock anger om en viss arbetsyta är låst.

När du låser hela mappar kan du låsa dem på mappnivå för arbetsytor eller på undermappsnivå (tabb). Du kan också låsa eller låsa upp alla dina mappar (på mappnivå för arbetsytor) och sedan ange undantag för vissa undermappar (med [!DNL folder.lock] filer) eller särskilda arbetsytor (med *arbetsytans namn*.lock-filer).

Följande exempel på [!DNL Profile Manager] markerar tre element:

* A [!DNL folder.lock] fil för arbetsytemappen
* A [!DNL Monthly Numbers.lock] filen för [!DNL Monthly Numbers.vw] arbetsytefil

* A [!DNL folder.lock] fil för arbetsytorna\Anpassad undermapp

![](assets/wsp_Locking_lockFiles.png)

I det här exemplet [!DNL Workspaces folder.lock] filen är låst, vilket innebär att alla arbetsytor i den här Datan Workbench låses. Undermappen Workspaces\Custom [!DNL folder.lock] filen är inställd på olåst, vilket låser upp alla arbetsytor på [!DNL Custom] -fliken. Slutligen [!DNL Monthly Numbers.lock] filen är låst, vilket låser arbetsytan Månadsnummer.

## Skapar .lock-filer {#section-c4f78b4b43c347368a376904effb41d2}

Du kan skapa en [!DNL new folder.lock] filen med [!DNL Create menu] i [!DNL Profile Manager] eller [!DNL Workspaces Manager]. Du kan också skapa en [!DNL folder.lock] eller *arbetsytans namn*.lock-fil genom att kopiera och klistra in en befintlig [!DNL .lock] till lämplig mapp, ändra filens namn (för *arbetsytans namn*.lock-filer) och ändra inställningen i filen om det behövs.

**Så här skapar du en ny mapp.låsfil**

1. Öppna Datan Workbench [!DNL Workspaces Manager] genom att högerklicka på en arbetsyta och klicka **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Klicka på den mapp som du vill skapa en [!DNL folder.lock] -fil.
1. I [!DNL User] för den mappen högerklickar du i cellen och klickar **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] filen visas. [!DNL New folder.lock] filer anges till [olåst] som standard.
1. (Valfritt) Om du behöver ändra inställningen i filen:

   1. Högerklicka på bockmarkeringen för filen.
   1. Klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL folder.lock] filen öppnas.

   1. Ändra inställningen till [låst].
   1. Spara och stäng filen.

1. Om du vill göra det här till en inställning för alla användare som arbetar med samma arbetsprofil högerklickar du på bockmarkeringen för filen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Arbetsytorna i den här mappen är nu låsta eller olåsta enligt inställningen i den nya filen.

**Så här skapar du en .lock-fil från en befintlig fil**

1. I [!DNL Profile Manager] eller [!DNL Workspaces Manager]högerklicka på bockmarkeringen för en befintlig [!DNL .lock] och klicka på **[!UICONTROL Copy]**.
1. I [!DNL User] -kolumnen för den mapp som du vill klistra in mappen i [!DNL .lock] , högerklicka i cellen och klicka **[!UICONTROL Paste]**.
1. Om den här filen används för att låsa en enskild arbetsyta högerklickar du på bockmarkeringen för [!DNL .lock] i [!DNL User] och ändra namnet i [!DNL File] fält som matchar namnet på arbetsytan som du vill låsa.

   Om du till exempel vill låsa [!DNL Monthly Numbers.vw] på arbetsytan skulle du namnge filen &quot; [!DNL Monthly Numbers.lock].&quot;Om den här filen används för att låsa en enskild arbetsyta högerklickar du på bockmarkeringen för [!DNL .lock] i [!DNL User] och ändra namnet i [!DNL File] fält som matchar namnet på arbetsytan som du vill låsa. Om du till exempel vill låsa [!DNL Monthly Numbers.vw] på arbetsytan skulle du namnge filen &quot; [!DNL Monthly Numbers.lock].&quot;

1. Så här ändrar du inställningen i filen:

   1. Högerklicka på bockmarkeringen för filen.
   1. Klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL .lock] filen öppnas.

   1. Ändra inställningen till [låst] eller [olåst].
   1. Spara och stäng filen.

1. Om du vill göra det här till en inställning för alla användare som arbetar med samma arbetsprofil högerklickar du på bockmarkeringen för filen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

De markerade arbetsytorna är nu låsta eller olåsta enligt inställningen i den nya filen.
