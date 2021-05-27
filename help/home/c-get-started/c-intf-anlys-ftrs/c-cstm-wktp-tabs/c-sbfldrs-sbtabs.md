---
description: Som standard visar nyligen skapade flikar undermapparna i den associerade katalogen som hierarkiska, nedrullningsbara underkataloger i stället för som undermappar.
title: Visa undermappar som underflikar
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Visa undermappar som underflikar{#display-subfolders-as-subtabs}

Som standard visar nyligen skapade flikar undermapparna i den associerade katalogen som hierarkiska, nedrullningsbara underkataloger i stället för som undermappar.

Du kan visa undermappar som underflikar (vilket visas i följande exempel) genom att placera en [!DNL empty folder.useTabs]-fil i *arbetsprofilens namn*\Workspaces\*tfliknamnsmapp* i Datans Workbench installationskatalog.

I följande exempel visas fliken [!DNL Custom] med underkataloger i listrutor.

![](assets/client-sub.png)

Om du placerar en [!DNL empty folder.useTabs]-fil i mappen Workspaces\Custom visas alla undermappar i mappen Custom i mappen [!DNL Worktop] som underflikar, vilket visas i följande exempel:

![](assets/client-sub2.png)

**Så här visar du undermappar som undermappar i[!DNL Worktop]**

>[!NOTE]
>
>Varje katalognivå måste ha en [!DNL Tab Name.useTabs]-fil för att innehållet i undermappen ska visas som underflikar i stället för hierarkiska underkataloger.

1. Klicka på **[!UICONTROL Workspaces]** i [!DNL Profile Manager] för att visa innehållet.
1. Högerklicka på bockmarkeringen för en av [!DNL folder.useTabs]-filerna i kolumnen *arbetsprofilnamn* och klicka på **[!UICONTROL Copy]**.
1. Högerklicka i kolumnen [!DNL User] för mappen Workspaces\*fliknamn* och klicka på **[!UICONTROL Paste]**. Undermapparna på den fliken visas nu som underflikar.
1. (Valfritt) Om du vill göra den här ändringen tillgänglig för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för filen [!DNL new folder.useTabs] i kolumnen [!DNL User] och klickar på **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
