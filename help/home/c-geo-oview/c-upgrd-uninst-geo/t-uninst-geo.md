---
description: Steg för att avinstallera data workbenchGeography.
title: Avinstallerar Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Avinstallerar Data Workbench Geography{#uninstalling-data-workbench-geography}

Steg för att avinstallera data workbenchGeography.

>[!NOTE]
>
>Om den profil som du använder data workbench [!DNL Geography] med körs på ett data workbench-serverkluster avinstallerar du profilen [!DNL Geography] från den överordnad data workbench-servern i klustret.

1. Följ de här stegen för att uppdatera [!DNL profile.cfg]-filen för varje profil som du använde data workbench [!DNL Geography] för.

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Fönstret [!DNL profile.cfg] visas.

   1. I fönstret [!DNL profile.cfg] tar du bort profilposten [!DNL Geography] från [!DNL Directories]-vektorn.

   1. Om du har använt en datatjänst tar du bort profilposten [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] från [!DNL Directories]-vektorn.

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL profile.cfg] i kolumnen [!DNL User] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Ta bort mappen Geography från mappen Profiles i installationskatalogen för data workbench-servern.
1. Om du har använt en datatjänst tar du bort mappen IP Geo-Intelligence eller IP Geo-location från mappen Profiles i installationskatalogen för Data Workbench-servern.
1. Ta bort mappen Geography från mappen Lookups i installationskatalogen för Data Workbench-servern.
1. Om du har använt en datatjänst tar du bort mappen IP Geo-Intelligence eller IP Geo-location från mappen Lookups i installationskatalogen för Data Workbench-servern.
1. Om du har skapat nya terrängbilder tar du bort filen [!DNL Terrain Images.cfg] från mappen Komponenter i installationskatalogen för Data Workbench-servern.
