---
description: Dessa steg gäller endast när du skapar undermenyer och menyalternativ för menyn Arbetsytans fönster.
title: Skapa en arbetsytans meny och ett menyalternativ
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 1%

---

# Skapa en arbetsytans meny och ett menyalternativ{#create-a-workspace-menu-and-menu-item}

{{eol}}

Dessa steg gäller endast när du skapar undermenyer och menyalternativ för menyn Arbetsytans fönster.

Du kan anpassa mått- och dimensionsmenyerna genom att skapa nya mappar och nya härledda mått och dimensioner. Mer information finns i [Skapa och redigera härledda mått](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) och [Skapa och redigera härledda Dimensioner](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Så här skapar du en ny fönstermeny för arbetsytan**

1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Menu]** för att visa dess innehåll.
1. I [!DNL User] -kolumn för Menu-katalogen klickar du på **[!UICONTROL Create]** > **[!UICONTROL Folder]**. En mapp med namnet Ny mapp visas i [!DNL File] kolumn för [!DNL Menu].

   >[!NOTE]
   >
   >Du kan också skapa en ny mapp för en underkatalog i Menu-katalogen.

1. Byt namn på den nya mappen genom att högerklicka i dialogrutan [!DNL User] -kolumnen för mappen och skriver det nya namnet i Dir-parametern.
1. Lägg till önskade filer i den nya mappen.
1. (Valfritt) I dialogrutan [!DNL User] kolumn för den nya mappen klickar du på **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   An [!DNL order.txt] filen visas i [!DNL File] kolumnen för den nya mappen och en bock för den nya filen visas i [!DNL User] kolumn.

1. (Valfritt) Redigera [!DNL order.txt] vid behov. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för mappen i [!DNL User] kolumn och klicka **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Lägga till ett nytt menyalternativ i en befintlig meny**

1. Gör något av följande:

   * Skapa ett nytt objekt (visualisering, anteckning o.s.v.) för att lägga till i en meny:

      1. Öppna en arbetsyta i Datan Workbench och skapa önskat objekt.
      1. Spara objektet i följande katalog:

         *Installationskatalog för Data Workbench*\Användare\*namn på arbetsprofil*\Arbete

      1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Work]** för att visa dess innehåll.
      1. I [!DNL User] högerklicka på bockmarkeringen för den önskade filen och klicka på **[!UICONTROL Copy]**.
      1. I [!DNL User] för den önskade mappen klickar du på **[!UICONTROL Paste]**.

         En kopia av filen visas i [!DNL File] kolumnen för den nya mappen och en bock för den nya filen visas i [!DNL User] kolumn.
   * Kopiera och klistra in ett befintligt objekt från en meny (mapp) till en annan:

      1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Menu]** för att visa dess innehåll.
      1. I *arbetsprofilsnamn* högerklicka på bockmarkeringen för den önskade filen och klicka på **[!UICONTROL Make Local]**.
      1. Högerklicka på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Copy]**.
      1. I [!DNL User] för den önskade mappen klickar du på **[!UICONTROL Paste]**. En kopia av filen visas i [!DNL File] kolumnen för den nya mappen och en bock för den nya filen visas i [!DNL User] kolumn.


1. (Valfritt) Redigera [!DNL order.txt] vid behov. Se [Anpassa menyer med Order.txt-filer](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för varje fil i dialogrutan [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Valfritt) Om du inte vill att ett menyalternativ ska visas på flera menyer, bör du ta bort motsvarande fil från den ursprungliga mappen genom att högerklicka på bockmarkeringen för filen i dialogrutan *arbetsprofilsnamn* kolumn och klicka **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Upprepa det här steget för filens bockmarkering i dialogrutan [!DNL User] kolumn.
