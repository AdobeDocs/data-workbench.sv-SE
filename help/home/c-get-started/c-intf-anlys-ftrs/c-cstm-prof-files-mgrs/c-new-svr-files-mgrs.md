---
description: Serverfilshanteraren visar alla kataloger i serverns installationskatalog, inklusive konfigurations- och sökningsfiler.
title: Skapa en hanterare för serverfiler
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Skapa en hanterare för serverfiler{#create-a-server-files-manager}

{{eol}}

Serverfilshanteraren visar alla kataloger i serverns installationskatalog, inklusive konfigurations- och sökningsfiler.

Du kanske vill komma åt en del av [!DNL Server Files Manager] utan att behöva navigera i hela katalogstrukturen eller bara visa några av underkatalogerna för att tillgodose ett visst behov. Du kanske vill skapa en separat [!DNL Server Files Manager] som endast visar underkatalogerna Åtkomstkontroll och Användare, vilket gör att du kan hantera dina användare och deras åtkomst.

Varje chef som du skapar måste ha en [!DNL .vw] -fil. Du kan använda [!DNL Server Files.vw] som en mall.

Mer information om [!DNL Server Files Manager], se [Serverfilhanteraren](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Så här skapar du en serverfilshanterare**

1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Menu]** katalog och sedan **[!UICONTROL Admin]** katalog. The [!DNL Server Files.vw] filen finns här.
1. I *profilnamn* högerklicka på bockmarkeringen för [!DNL Server Files.vw] och klicka på **[!UICONTROL Make Local]**. En bock för filen visas i [!DNL User] kolumn.
1. Högerklicka på bockmarkeringen för [!DNL Server Files.vw] i [!DNL User] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Server Files.vw] filen öppnas.
1. Om du vill ta bort en katalog högerklickar du på den övre kanten på [!DNL Server Files Manager] och klicka **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Om du vill lägga till en katalog högerklickar du på den övre kanten på [!DNL Server Files Manager], klicka **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Skriv katalogens URI i fältet URI och klicka på **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Du kan ange flera kataloger i fältet URI. Om du till exempel skriver [!DNL Profiles\Marketing\], innehåller serverfilhanteraren underkatalogen Marketing, men ingen annan underkatalog i katalogen Profiles.

1. Högerklicka på den övre kanten av [!DNL Server Files Manager] och klicka **[!UICONTROL Save]**.
1. Om du vill skapa en ny hanterare ändrar du filnamnet i [!DNL File Name] fält och klicka sedan på **[!UICONTROL Save]**. Om du vill skriva över den befintliga hanteraren klickar du på **[!UICONTROL Save]**.
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare i arbetsprofilen högerklickar du på bockmarkeringen för [!DNL .vw] i [!DNL User] kolumn.

   Klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
