---
description: Dessa steg gäller endast när du skapar undermenyer och menyalternativ för menyn Arbetsytans fönster.
solution: Analytics
title: Skapa en arbetsytans meny och ett menyalternativ
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Skapa en arbetsytans meny och ett menyalternativ{#create-a-workspace-menu-and-menu-item}

Dessa steg gäller endast när du skapar undermenyer och menyalternativ för menyn Arbetsytans fönster.

Du kan anpassa mått- och dimensionsmenyerna genom att skapa nya mappar och nya härledda mått och dimensioner. Mer information finns i [Skapa och redigera härledda mått](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) och [Skapa och redigera härledda dimensioner](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Så här skapar du en ny fönstermeny för arbetsytan**

1. Klicka på [!DNL Profile Manager]katalogen för att visa dess innehåll **[!UICONTROL Menu]** i .
1. Klicka på [!DNL User] > i **[!UICONTROL Create]** kolumnen för Menu-katalogen **[!UICONTROL Folder]**. En mapp med namnet Ny mapp visas i [!DNL File] kolumnen för [!DNL Menu].

   >[!NOTE]
   >
   >Du kan också skapa en ny mapp för en underkatalog i Menu-katalogen.

1. Byt namn på den nya mappen genom att högerklicka i mappens [!DNL User] kolumn och skriva det nya namnet i Dir-parametern.
1. Lägg till önskade filer i den nya mappen.
1. (Valfritt) I kolumnen [!DNL User] för den nya mappen klickar du på **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   En [!DNL order.txt] fil visas i [!DNL File] kolumnen för den nya mappen och en bock för den nya filen visas i [!DNL User] kolumnen.

1. (Valfritt) Redigera [!DNL order.txt] filen efter behov. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för mappen i [!DNL User] kolumnen och klickar på **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Lägga till ett nytt menyalternativ i en befintlig meny**

1. Gör något av följande:

   * Skapa ett nytt objekt (visualisering, anteckning o.s.v.) för att lägga till i en meny:

      1. Öppna en arbetsyta i Data Workbench och skapa önskat objekt.
      1. Spara objektet i följande katalog:

         *Installationskatalog* för Data Workbench \User\*namn på arbetsprofil*\Arbete

      1. Klicka på [!DNL Profile Manager]katalogen för att visa dess innehåll **[!UICONTROL Work]** i .
      1. Högerklicka på bockmarkeringen för den önskade filen i [!DNL User] kolumnen och klicka på **[!UICONTROL Copy]**.
      1. Klicka på i [!DNL User] kolumnen för den önskade mappen **[!UICONTROL Paste]**.

         En kopia av filen visas i kolumnen [!DNL File] för den nya mappen och en bock för den nya filen visas i [!DNL User] kolumnen.
   * Kopiera och klistra in ett befintligt objekt från en meny (mapp) till en annan:

      1. Klicka på [!DNL Profile Manager]katalogen för att visa dess innehåll **[!UICONTROL Menu]** i .
      1. Högerklicka på bockmarkeringen för den önskade filen i kolumnen med *arbetsprofilens namn* och klicka på **[!UICONTROL Make Local]**.
      1. Högerklicka på bockmarkeringen för filen i [!DNL User] kolumnen och klicka på **[!UICONTROL Copy]**.
      1. Klicka på i [!DNL User] kolumnen för den önskade mappen **[!UICONTROL Paste]**. En kopia av filen visas i kolumnen [!DNL File] för den nya mappen och en bock för den nya filen visas i [!DNL User] kolumnen.


1. (Valfritt) Redigera [!DNL order.txt] filen efter behov. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla som använder arbetsprofilen högerklickar du på den vita bockmarkeringen för varje fil i [!DNL User] kolumnen och klickar på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Valfritt) Om du vill undvika att ett menyalternativ visas på flera menyer, bör du ta bort motsvarande fil från dess ursprungliga mapp genom att högerklicka på bockmarkeringen för filen i kolumnen med *arbetsprofilens namn* och klicka på **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Upprepa det här steget för filens bockmarkering i [!DNL User] kolumnen.

