---
description: I mappen Workspaces i installationskatalogen för Data Workbench anger filen folder.lock om arbetsytorna i den aktuella mappen är låsta, medan filen workspace name.lock anger om en viss arbetsyta är låst.
solution: Analytics
title: Folder.lock och workspace.lock-filer
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Folder.lock och workspace.lock-filer{#folder-lock-and-workspace-lock-files}

I mappen Workspaces i installationskatalogen för Data Workbench anger filen folder.lock om arbetsytorna i den aktuella mappen är låsta, medan filen workspace name.lock anger om en viss arbetsyta är låst.

När du låser hela mappar kan du låsa dem på mappnivå för arbetsytor eller på undermappsnivå (tabb). Du kan också låsa eller låsa upp alla dina mappar (på mappnivå för arbetsytor) och sedan ange undantagen för vissa undermappar (med [!DNL folder.lock] filer) eller vissa arbetsytor (med *arbetsytans namn*.låsfiler).

Följande exempel på de tre elementen [!DNL Profile Manager] markeras:

* En [!DNL folder.lock] fil för arbetsytemappen
* En [!DNL Monthly Numbers.lock] fil för [!DNL Monthly Numbers.vw] arbetsytefilen

* En [!DNL folder.lock] fil för undermappen Workspaces\Custom

![](assets/wsp_Locking_lockFiles.png)

I det här exemplet är [!DNL Workspaces folder.lock] filen låst, vilket låser alla arbetsytor i den här instansen av Data Workbench. Undermappsfilen Workspaces\Custom är [!DNL folder.lock] inställd på olåst, vilket låser upp alla arbetsytor på [!DNL Custom] fliken. Slutligen är filen låst, vilket innebär att arbetsytan Månatliga nummer låses [!DNL Monthly Numbers.lock] .

## Skapar .lock-filer {#section-c4f78b4b43c347368a376904effb41d2}

Du kan skapa en [!DNL new folder.lock] fil med hjälp av [!DNL Create menu] alternativet i [!DNL Profile Manager] eller [!DNL Workspaces Manager]. Du kan också skapa en [!DNL folder.lock] eller *arbetsytans namn*.lock-fil genom att kopiera och klistra in en befintlig [!DNL .lock] fil i lämplig mapp, ändra filens namn (endast för *arbetsytans namn*.låsfiler) och ändra inställningen i filen om det behövs.

**Så här skapar du en ny mapp.låsfil**

1. I Data Workbench öppnar du [!DNL Workspaces Manager] genom att högerklicka i en arbetsyta och klicka på **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Klicka på den mapp som du vill skapa en [!DNL folder.lock] fil för.
1. Högerklicka i cellen i kolumnen för den mappen och klicka på [!DNL User] > **[!UICONTROL Create]** **[!UICONTROL folder.lock]**. En [!DNL new folder.lock] fil visas. [!DNL New folder.lock] som standard är filerna [olåsta] .
1. (Valfritt) Om du behöver ändra inställningen i filen:

   1. Högerklicka på bockmarkeringen för filen.
   1. Klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Filen [!DNL folder.lock] öppnas.

   1. Ändra inställningen till [låst].
   1. Spara och stäng filen.

1. Om du vill göra den här inställningen för alla användare som arbetar med samma arbetsprofil högerklickar du på bockmarkeringen för filen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Arbetsytorna i den här mappen är nu låsta eller olåsta enligt inställningen i den nya filen.

**Så här skapar du en .lock-fil från en befintlig fil**

1. Högerklicka på bockmarkeringen för en befintlig [!DNL Profile Manager] fil i [!DNL Workspaces Manager]eller [!DNL .lock] klicka på **[!UICONTROL Copy]**.
1. Högerklicka i cellen i kolumnen för den mapp som du vill klistra in [!DNL User] filen i och klicka på [!DNL .lock] **[!UICONTROL Paste]**.
1. Om den här filen används för att låsa en enskild arbetsyta högerklickar du på bockmarkeringen för [!DNL .lock] filen i [!DNL User] kolumnen och ändrar namnet i [!DNL File] fältet så att det matchar namnet på den arbetsyta som du vill låsa.

   Om du till exempel vill låsa [!DNL Monthly Numbers.vw] arbetsytan ger du filen namnet&quot; [!DNL Monthly Numbers.lock].&quot;Om den här filen används för att låsa en enskild arbetsyta högerklickar du på bockmarkeringen för [!DNL .lock] filen i [!DNL User] kolumnen och ändrar namnet i [!DNL File] fältet så att det matchar namnet på den arbetsyta som du vill låsa. Om du till exempel vill låsa [!DNL Monthly Numbers.vw] arbetsytan ger du filen namnet&quot; [!DNL Monthly Numbers.lock].&quot;

1. Så här ändrar du inställningen i filen:

   1. Högerklicka på bockmarkeringen för filen.
   1. Klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Filen [!DNL .lock] öppnas.

   1. Ändra inställningen till [låst] eller [olåst].
   1. Spara och stäng filen.

1. Om du vill göra den här inställningen för alla användare som arbetar med samma arbetsprofil högerklickar du på bockmarkeringen för filen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

De markerade arbetsytorna är nu låsta eller olåsta enligt inställningen i den nya filen.
