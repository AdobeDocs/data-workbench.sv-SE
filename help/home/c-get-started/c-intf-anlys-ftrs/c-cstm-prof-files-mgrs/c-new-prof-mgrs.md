---
description: Profilhanteraren visar alla kataloger som är associerade med din arbetsprofil.
title: Skapa en profilhanterare
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---

# Skapa en profilhanterare{#create-a-profile-manager}

{{eol}}

Profilhanteraren visar alla kataloger som är associerade med din arbetsprofil.

Du kanske vill komma åt en underkatalog till [!DNL Profile Manager] utan att behöva navigera i hela katalogstrukturen. Till exempel [!DNL Metrics] och [!DNL Workspaces] menyalternativ som finns på [!DNL Manage] på arbetsytans fönstermeny kan du öppna mapparna Profilhanterarens mått och arbetsytor.

Mer information om [!DNL Profile Manager], se [Profilhanteraren](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Som standard har du åtkomst till följande hanterare:

* **[!DNL Metrics Manager]:** Visar innehållet i profilhanterarens mapp Metrics. Du kan öppna, redigera, ta bort eller kopiera mätvärden som definierats i varje profil.
* **[!DNL Reports Manager]:** Visar innehållet i Profilhanterarens rapportmapp. Du kan öppna, redigera, ta bort eller kopiera rapportarbetsytor eller [!DNL report.cfg] filer.

* **[!DNL Workspaces Manager]:** Visar innehållet i profilhanterarens arbetsytemapp. Alla filer för att konfigurera [!DNL Worktop]Här finns flikarna. Se [Anpassa arbetsflikar](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Med Data Workbench kan du skapa ytterligare profilhanterare som visar en underkatalog från [!DNL Profile Manager]. Varje chef som du skapar måste ha en [!DNL .vw] filen som anger [!DNL Profile Manager] katalog vars innehåll visas och fönstrets egenskaper. Du kan använda [!DNL .vw] fil för någon av de angivna hanterarna som en mall.

**Skapa en profilhanterare**

1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Menu]** för att visa dess innehåll.
1. I Menu-katalogen klickar du på **[!UICONTROL Admin]** och sedan **[!UICONTROL Profile]** katalog. The [!DNL .vw] filer för befintliga chefer finns här.
1. I *profilnamn* högerklickar du på bockmarkeringen för en av [!DNL .vw] filer (till exempel [!DNL Workspaces.vw]) och sedan klicka på **[!UICONTROL Make Local]**.

   En bock för filen visas i [!DNL User] kolumn.

1. Högerklicka på bockmarkeringen för [!DNL .vw] i [!DNL User] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. I [!DNL Profile Path] fält, skriv [!DNL Profile Manager] katalog som du vill skapa en ny hanterare för. Var noga med att ta med snedstrecket (/) efter katalognamnet.

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

1. I Anteckningar klickar du på **[!UICONTROL File]** > **[!UICONTROL Save As]** för att spara den redigerade filen i *Datans Workbench installationsmapp*\Användare\*namn på arbetsprofil*\Menu\Admin\Profile Management.

   Var noga med att ändra namnet på [!DNL .vw] som återspeglar katalogen i [!DNL Profile Manager] som den motsvarar.

1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare i arbetsprofilen högerklickar du på bockmarkeringen för [!DNL .vw] i [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
