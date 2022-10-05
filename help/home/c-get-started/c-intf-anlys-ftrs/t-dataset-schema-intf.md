---
description: Steg för att ändra standardvisualiseringen.
title: Konfigurera gränssnittet för datauppsättningsschema
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# Konfigurera gränssnittet för datauppsättningsschema{#configure-the-dataset-schema-interface}

{{eol}}

Steg för att ändra standardvisualiseringen.

Du kan styra vilken typ av visualisering som visas när du klickar på ett dimensionsnamn i en [!DNL Dataset Schema Interface] genom att lägga till filer i mappen Profiler\*profilnamn*\Context\Dimension Legend i Data Workbench Server-installationsmappen. The [!DNL Default.1d] -filen i den här mappen styr standardvisualiseringstypen för alla dimensioner. Genom att lägga till en *dimensionsnamn*.1d-fil (t.ex. [!DNL Hour.1d]) till den här mappen kan du styra standardvisualiseringen för den aktuella dimensionen.

Mer information om [!DNL Dataset Schema Interfaces], se [Gränssnittet för dataset Schema](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Ändra standardvisualisering**

1. I valfri arbetsyta skapar du en visualisering som innehåller de data som du vill ska visas i den nya standardvisualiseringen.

   Om du till exempel vill att dimensionen ska visas i ett stapeldiagram skapar du en diagramvisualisering som visar det önskade måttet och måttet.

1. Högerklicka på bildtextfönstrets övre kant och klicka på **[!UICONTROL Save]**.
1. I [!DNL Save] fönster, klicka ![](assets/btn_folder_up.png), dubbelklicka **[!UICONTROL Context]** dubbelklicka **[!UICONTROL Dimension Legend]**.
1. I [!DNL File Name] anger du dimensionsnamnet.

   Namnet på [!DNL .1d] filen måste matcha namnet på dimensionen exakt. Exempel, [!DNL Hour.1d].

1. Ändra filtillägget till &quot;1d&quot; och klicka på **[!UICONTROL Save]**.

   Filen sparas i mappen User\*workprofile name*\Context\Dimension Legend.

   Nästa gång du klickar på den dimensionen i en [!DNL Dataset Schema Interface]visas den visualisering du angav.

1. (Valfritt) Gör den här ändringen tillgänglig för alla användare av arbetsprofilen:

   1. I [!DNL Profile Manager], klicka **[!UICONTROL Context]** och sedan klicka **[!UICONTROL Dimension Legend]**.

   1. Högerklicka på bockmarkeringen bredvid filnamnet för den nya bildtexten i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
