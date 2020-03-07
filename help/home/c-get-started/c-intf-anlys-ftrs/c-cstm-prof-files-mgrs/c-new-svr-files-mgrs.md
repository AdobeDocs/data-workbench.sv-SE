---
description: Serverfilshanteraren visar alla kataloger i Data Workbench-serverns installationskatalog, inklusive konfigurations- och sökfiler.
solution: Analytics
title: Skapa en hanterare för serverfiler
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skapa en hanterare för serverfiler{#create-a-server-files-manager}

Serverfilshanteraren visar alla kataloger i Data Workbench-serverns installationskatalog, inklusive konfigurations- och sökfiler.

Du kanske vill komma åt en del av [!DNL Server Files Manager] filen utan att behöva navigera i hela katalogstrukturen eller bara visa några av underkatalogerna för ett visst behov. Du kan till exempel skapa en separat [!DNL Server Files Manager] som bara visar underkatalogerna Åtkomstkontroll och Användare, så att du kan hantera dina användare och deras åtkomst.

Varje hanterare som du skapar måste ha en [!DNL .vw] fil. Du kan använda [!DNL Server Files.vw] filen som en mall.

Mer information om [!DNL Server Files Manager]finns i [Serverfilshanteraren](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Så här skapar du en serverfilshanterare**

1. Klicka på [!DNL Profile Manager]katalogen i **[!UICONTROL Menu]** och sedan på **[!UICONTROL Admin]** katalogen. Här finns [!DNL Server Files.vw] filen.
1. Högerklicka på bockmarkeringen för *filen i kolumnen* Profilnamn [!DNL Server Files.vw] och klicka på **[!UICONTROL Make Local]**. En bock för filen visas i [!DNL User] kolumnen.
1. Högerklicka på bockmarkeringen för [!DNL Server Files.vw] filen i [!DNL User] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Filen [!DNL Server Files.vw] öppnas.
1. Om du vill ta bort en katalog högerklickar du på den övre kanten av [!DNL Server Files Manager] och klickar på **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Om du vill lägga till en katalog högerklickar du på den övre kanten av [!DNL Server Files Manager]mappen och klickar på **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Skriv katalogens URI i fältet URI och klicka på **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Du kan ange flera kataloger i fältet URI. Om du till exempel skriver [!DNL Profiles\Marketing\] innehåller serverfilhanteraren underkatalogen Marketing, men ingen annan underkatalog i katalogen Profiles.

1. Högerklicka på den övre kanten av [!DNL Server Files Manager] och klicka på **[!UICONTROL Save]**.
1. Om du vill skapa en ny hanterare ändrar du filnamnet i [!DNL File Name] fältet och klickar sedan på **[!UICONTROL Save]**. Om du vill skriva över den befintliga hanteraren klickar du på **[!UICONTROL Save]**.
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på bockmarkeringen för [!DNL .vw] filen i [!DNL User] kolumnen.

   Klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

