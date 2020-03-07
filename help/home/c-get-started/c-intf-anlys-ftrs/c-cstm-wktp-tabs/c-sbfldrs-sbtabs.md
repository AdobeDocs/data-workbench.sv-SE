---
description: Som standard visar nyligen skapade flikar undermapparna i den associerade katalogen som hierarkiska, nedrullningsbara underkataloger i stället för som undermappar.
solution: Analytics
title: Visa undermappar som underflikar
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visa undermappar som underflikar{#display-subfolders-as-subtabs}

Som standard visar nyligen skapade flikar undermapparna i den associerade katalogen som hierarkiska, nedrullningsbara underkataloger i stället för som undermappar.

Du kan visa undermappar som underflikar (vilket visas i följande exempel) genom att placera en [!DNL empty folder.useTabs] fil i *arbetsprofilens namn*\Workspaces\*tfliknamnsmapp* i installationskatalogen för Data Workbench.

I följande exempel visas fliken [!DNL Custom] med underkataloger i listrutor.

![](assets/client-sub.png)

Om du placerar en [!DNL empty folder.useTabs] fil i mappen Workspaces\Custom visas alla undermappar i mappen Custom i [!DNL Worktop] form av underflikar, vilket visas i följande exempel:

![](assets/client-sub2.png)

**Så här visar du undermappar som undermappar i[!DNL Worktop]**

>[!NOTE]
>
>Varje katalognivå måste ha en [!DNL Tab Name.useTabs] fil för att innehållet i undermappen ska visas som underflikar i stället för som hierarkiska underkataloger.

1. Klicka på [!DNL Profile Manager]för **[!UICONTROL Workspaces]** att visa innehållet.
1. Högerklicka på bockmarkeringen för en av *filerna i kolumnen med* arbetsprofilens namn [!DNL folder.useTabs] och klicka på **[!UICONTROL Copy]**.
1. Högerklicka i [!DNL User] kolumnen för mappen Arbetsytor\*och klicka på **[!UICONTROL Paste]**. Undermapparna på den fliken visas nu som underflikar.
1. (Valfritt) Om du vill göra den här ändringen tillgänglig för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för [!DNL new folder.useTabs] filen i [!DNL User] kolumnen och klickar på **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

