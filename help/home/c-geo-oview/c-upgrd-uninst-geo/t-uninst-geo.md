---
description: Steg för att avinstallera data workbenchGeography.
title: Avinstallerar Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Avinstallerar Data Workbench Geography{#uninstalling-data-workbench-geography}

{{eol}}

Steg för att avinstallera data workbenchGeography.

>[!NOTE]
>
>Om profilen som du använder data workbench med [!DNL Geography] körs på en data workbench-serverkluster, avinstallera [!DNL Geography] profil från den överordnad data workbench-servern i klustret.

1. Använd följande steg för att uppdatera [!DNL profile.cfg] fil för varje profil som du använde data workbench för [!DNL Geography].

   1. Öppna [!DNL Profile Manager].
   1. Högerklicka på bockmarkeringen bredvid [!DNL profile.cfg] och klicka **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL profile.cfg] visas.

   1. I [!DNL profile.cfg] fönster, ta bort [!DNL Geography] profilpost från [!DNL Directories] vektor.

   1. Om du har använt en datatjänst tar du bort [!DNL IP Geo-intelligence] eller [!DNL IP Geo-location] profilpost från [!DNL Directories] vektor.

   1. Högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I [!DNL Profile Manager], högerklicka på bockmarkeringen för [!DNL profile.cfg] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Ta bort mappen Geography från mappen Profiles i installationskatalogen för data workbench-servern.
1. Om du har använt en datatjänst tar du bort mappen IP Geo-Intelligence eller IP Geo-location från mappen Profiles i installationskatalogen för Data Workbench-servern.
1. Ta bort mappen Geography från mappen Lookups i installationskatalogen för Data Workbench-servern.
1. Om du har använt en datatjänst tar du bort mappen IP Geo-Intelligence eller IP Geo-location från mappen Lookups i installationskatalogen för Data Workbench-servern.
1. Om du har skapat nya terrängbilder tar du bort [!DNL Terrain Images.cfg] från mappen Komponenter i installationskatalogen för data workbench-servern.
