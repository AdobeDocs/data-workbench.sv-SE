---
description: Serverfilshanteraren visar alla kataloger i serverns installationskatalog, inklusive konfigurations- och sökningsfiler.
title: Skapa en hanterare för serverfiler
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Skapa en serverfilshanterare{#create-a-server-files-manager}

Serverfilshanteraren visar alla kataloger i serverns installationskatalog, inklusive konfigurations- och sökningsfiler.

Du kanske vill komma åt en del av [!DNL Server Files Manager] utan att behöva navigera i hela katalogstrukturen eller bara visa några av underkatalogerna för att tillgodose ett visst behov. Du kan till exempel skapa en separat [!DNL Server Files Manager] som endast visar underkatalogerna Åtkomstkontroll och Användare, så att du kan hantera dina användare och deras åtkomst.

Varje hanterare som du skapar måste ha en [!DNL .vw]-fil. Du kan använda filen [!DNL Server Files.vw] som en mall.

Mer information om [!DNL Server Files Manager] finns i [Serverfilshanteraren](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Så här skapar du en serverfilshanterare**

1. Klicka på katalogen **[!UICONTROL Menu]** i [!DNL Profile Manager] och sedan på katalogen **[!UICONTROL Admin]**. Filen [!DNL Server Files.vw] finns här.
1. Högerklicka på bockmarkeringen för [!DNL Server Files.vw]-filen i kolumnen *profilnamn* och klicka på **[!UICONTROL Make Local]**. En bock för filen visas i kolumnen [!DNL User].
1. Högerklicka på bockmarkeringen för filen [!DNL Server Files.vw] i kolumnen [!DNL User] och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Filen [!DNL Server Files.vw] öppnas.
1. Om du vill ta bort en katalog högerklickar du på den övre kanten av [!DNL Server Files Manager] och klickar på **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]***.
1. Om du vill lägga till en katalog högerklickar du på den övre kanten av [!DNL Server Files Manager], klickar på **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Skriv katalogens URI i URI-fältet och klicka på **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Du kan ange flera kataloger i fältet URI. Om du till exempel skriver [!DNL Profiles\Marketing\] innehåller serverfilhanteraren underkatalogen Marketing, men ingen annan underkatalog i katalogen Profiles.

1. Högerklicka på den övre kanten av [!DNL Server Files Manager] och klicka på **[!UICONTROL Save]**.
1. Om du vill skapa en ny hanterare ändrar du filnamnet i fältet [!DNL File Name] och klickar sedan på **[!UICONTROL Save]**. Om du vill skriva över den befintliga hanteraren klickar du på **[!UICONTROL Save]**.
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på bockmarkeringen för filen [!DNL .vw] i kolumnen [!DNL User].

   Klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
