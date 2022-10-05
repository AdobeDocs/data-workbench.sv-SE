---
description: Som standard visar nyligen skapade flikar undermapparna i den associerade katalogen som hierarkiska, nedrullningsbara underkataloger i stället för som undermappar.
title: Visa undermappar som underflikar
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Visa undermappar som underflikar{#display-subfolders-as-subtabs}

{{eol}}

Som standard visar nyligen skapade flikar undermapparna i den associerade katalogen som hierarkiska, nedrullningsbara underkataloger i stället för som undermappar.

Du kan visa undermappar som underflikar (vilket visas i följande exempel) genom att montera en [!DNL empty folder.useTabs] i *arbetsprofilsnamn*\Workspaces\*tab name folder* i Datans Workbench installationskatalog.

I följande exempel visas [!DNL Custom] med nedrullningsbara underkataloger.

![](assets/client-sub.png)

Om du monterar en [!DNL empty folder.useTabs] i mappen Workspaces\Custom visas alla undermappar i mappen Custom i [!DNL Worktop] som undertabbar, vilket visas i följande exempel:

![](assets/client-sub2.png)

**Så här visar du undermappar som undermappar i[!DNL Worktop]**

>[!NOTE]
>
>Varje katalognivå måste ha en [!DNL Tab Name.useTabs] för att innehållet i undermappen ska visas som underflikar i stället för som hierarkiska, nedrullningsbara underkataloger.

1. I [!DNL Profile Manager], klicka **[!UICONTROL Workspaces]** för att visa innehållet.
1. I *arbetsprofilsnamn* högerklicka på bockmarkeringen för en av [!DNL folder.useTabs] filer och klicka på **[!UICONTROL Copy]**.
1. Högerklicka i dialogrutan [!DNL User] kolumn för arbetsytorna\*fliknamn* och klicka på **[!UICONTROL Paste]**. Undermapparna på den fliken visas nu som underflikar.
1. (Valfritt) Om du vill göra den här ändringen tillgänglig för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för [!DNL new folder.useTabs] i [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
