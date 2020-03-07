---
description: Profilhanteraren visar alla kataloger som är associerade med din arbetsprofil.
solution: Analytics
title: Skapa en profilhanterare
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Skapa en profilhanterare{#create-a-profile-manager}

Profilhanteraren visar alla kataloger som är associerade med din arbetsprofil.

Du kanske vill komma åt en underkatalog i katalogen [!DNL Profile Manager] utan att behöva navigera i hela katalogstrukturen. Du kan till exempel använda alternativen [!DNL Metrics] och [!DNL Workspaces] meny som finns på [!DNL Manage] menyn i arbetsytans fönstermeny för att öppna mapparna Metrisk och Arbetsyta för Profilhanteraren.

Mer information om [!DNL Profile Manager]finns [i Profilhanteraren](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Som standard har du åtkomst till följande hanterare:

* **[!DNL Metrics Manager]:**Visar innehållet i profilhanterarens mapp Metrics. Du kan öppna, redigera, ta bort eller kopiera mätvärden som definierats i varje profil.
* **[!DNL Reports Manager]:**Visar innehållet i Profilhanterarens rapportmapp. Du kan öppna, redigera, ta bort eller kopiera rapportarbetsytor eller[!DNL report.cfg]filer.

* **[!DNL Workspaces Manager]:**Visar innehållet i profilhanterarens arbetsytemapp. Alla filer som används för att konfigurera[!DNL Worktop]flikarna finns här. Se[Anpassa arbetsflikar](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Med Data Workbench kan du skapa ytterligare profilhanterare som visar en underkatalog från [!DNL Profile Manager]. Varje hanterare som du skapar måste ha en [!DNL .vw] fil som anger den [!DNL Profile Manager] katalog vars innehåll visas och fönstrets egenskaper. Du kan använda filen som en mall för alla hanterare som tillhandahålls. [!DNL .vw]

**Skapa en profilhanterare**

1. Klicka på [!DNL Profile Manager]katalogen för att visa dess innehåll **[!UICONTROL Menu]** i .
1. Klicka på **[!UICONTROL Admin]** katalogen i Menu-katalogen och sedan på **[!UICONTROL Profile]** katalogen. Filerna [!DNL .vw] för de befintliga hanterarna finns här.
1. Högerklicka på bockmarkeringen för en av *filerna (till exempel* ) i kolumnen [!DNL .vw] profilnamn [!DNL Workspaces.vw]och klicka sedan på **[!UICONTROL Make Local]**.

   En bock för filen visas i [!DNL User] kolumnen.

1. Högerklicka på bockmarkeringen för [!DNL .vw] filen i [!DNL User] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. I [!DNL Profile Path] fältet anger du den [!DNL Profile Manager] katalog som du vill skapa en ny hanterare för. Var noga med att ta med snedstrecket (/) efter katalognamnet.

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

1. I Anteckningar klickar du på **[!UICONTROL File]** > **[!UICONTROL Save As]** för att spara den redigerade filen i installationsmappen för *Data Workbench*\User\*arbetsprofilens namn*\Menu\Admin\Profile Management.

   Tänk på att ändra namnet på [!DNL .vw] filen så att det motsvarar den katalog i [!DNL Profile Manager] vilken den hör till.

1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på bockmarkeringen för [!DNL .vw] filen i [!DNL User] kolumnen och klickar på **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

