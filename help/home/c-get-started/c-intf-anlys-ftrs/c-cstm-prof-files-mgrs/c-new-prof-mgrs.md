---
description: Profilhanteraren visar alla kataloger som är associerade med din arbetsprofil.
title: Skapa en profilhanterare
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Skapa en profilhanterare{#create-a-profile-manager}

Profilhanteraren visar alla kataloger som är associerade med din arbetsprofil.

Du kanske vill komma åt en underkatalog till [!DNL Profile Manager] utan att behöva navigera i hela katalogstrukturen. Menyalternativen [!DNL Metrics] och [!DNL Workspaces] som finns på menyn [!DNL Manage] på arbetsytans fönstermeny gör att du kan öppna mapparna Profilhanterarens mått och arbetsytor.

Mer information om [!DNL Profile Manager] finns i [Profilhanteraren](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Som standard har du åtkomst till följande hanterare:

* **[!DNL Metrics Manager]:** Visar innehållet i profilhanterarens metrisk mapp. Du kan öppna, redigera, ta bort eller kopiera mätvärden som definierats i varje profil.
* **[!DNL Reports Manager]:** Visar innehållet i Profilhanterarens rapportmapp. Du kan öppna, redigera, ta bort eller kopiera rapportarbetsytor eller [!DNL report.cfg]-filer.

* **[!DNL Workspaces Manager]:** Visar innehållet i profilhanterarens arbetsytemapp. Alla filer som används för att konfigurera flikarna för [!DNL Worktop] finns här. Se [Anpassa arbetsflikar](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Med Data Workbench kan du skapa ytterligare profilhanterare som visar en underkatalog från [!DNL Profile Manager]. Varje hanterare som du skapar måste ha en [!DNL .vw]-fil som anger katalogen [!DNL Profile Manager] vars innehåll visas och fönstrets egenskaper. Du kan använda filen [!DNL .vw] för någon av de angivna hanterarna som en mall.

**Skapa en profilhanterare**

1. Klicka på katalogen **[!UICONTROL Menu]** i [!DNL Profile Manager] för att visa innehållet.
1. Klicka på katalogen **[!UICONTROL Admin]** i Menu-katalogen och sedan på katalogen **[!UICONTROL Profile]**. [!DNL .vw]-filerna för de befintliga hanterarna finns här.
1. Högerklicka på bockmarkeringen för en av [!DNL .vw]-filerna (till exempel [!DNL Workspaces.vw]) i kolumnen *profilnamn* och klicka sedan på **[!UICONTROL Make Local]**.

   En bock för filen visas i kolumnen [!DNL User].

1. Högerklicka på bockmarkeringen för filen [!DNL .vw] i kolumnen [!DNL User] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. I fältet [!DNL Profile Path] anger du katalogen [!DNL Profile Manager] som du vill skapa en ny hanterare för. Var noga med att ta med snedstrecket (/) efter katalognamnet.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. I Anteckningar klickar du på **[!UICONTROL File]** > **[!UICONTROL Save As]** för att spara den redigerade filen i *Datans Workbench installationsmapp*\User\*arbetsprofilens namn*\Menu\Admin\Profile Management.

   Var noga med att ändra namnet på [!DNL .vw]-filen så att det återspeglar katalogen i [!DNL Profile Manager] som den motsvarar.

1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på bockmarkeringen för filen [!DNL .vw] i kolumnen [!DNL User] och klickar på **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
