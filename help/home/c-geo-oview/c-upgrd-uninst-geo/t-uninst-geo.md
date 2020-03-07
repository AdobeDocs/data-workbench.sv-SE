---
description: Steg för att avinstallera data workbenchGeography.
solution: Analytics
title: Avinstallerar Data Workbench Geography
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Avinstallerar Data Workbench Geography{#uninstalling-data-workbench-geography}

Steg för att avinstallera data workbenchGeography.

>[!NOTE]
>
>Om den profil som du använder data workbench med [!DNL Geography] körs på ett data workbench-serverkluster avinstallerar du [!DNL Geography] profilen från huvuddata workbench-servern i klustret.

1. Följ de här stegen för att uppdatera [!DNL profile.cfg] filen för varje profil som du använde data workbench med [!DNL Geography].

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Fönstret [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg] fönstret tar du bort [!DNL Geography] profilposten från [!DNL Directories] vektorn.

   1. Om du har använt en datatjänst tar du bort posten [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] profilen från [!DNL Directories] vektorn.

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Ta bort mappen Geography från mappen Profiles i installationskatalogen för data workbench-servern.
1. Om du har använt en datatjänst tar du bort mappen IP Geo-Intelligence eller IP Geo-location från mappen Profiles i installationskatalogen för Data Workbench-servern.
1. Ta bort mappen Geography från mappen Lookups i installationskatalogen för Data Workbench-servern.
1. Om du har använt en datatjänst tar du bort mappen IP Geo-Intelligence eller IP Geo-location från mappen Lookups i installationskatalogen för Data Workbench-servern.
1. Om du har skapat nya fjärrbilder tar du bort filen från mappen Komponenter i installationskatalogen för Data Workbench-servern. [!DNL Terrain Images.cfg]
