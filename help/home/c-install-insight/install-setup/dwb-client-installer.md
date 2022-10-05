---
description: Datan Workbench innehåller en konfigurationsguide för installation av arbetsstationsprogrammet (klientprogrammet).
title: Guiden Installera arbetsstation
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
exl-id: bfd9f2ad-282a-4be8-9f66-53e045648ef1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 0%

---

# Guiden Installera arbetsstation{#workstation-setup-wizard}

{{eol}}

Datan Workbench innehåller en konfigurationsguide för installation av arbetsstationsprogrammet (klientprogrammet).

## Installera arbetsstationen med installationsguiden {#section-58da9bb6196c46eab3b54146913fdcb8}

Starta installationsguidens körbara fil och gå igenom varje steg för att installera arbetsstationens klientprogram. När du har installerat arbetsstationen kan du ansluta till servrar och profiler.

1. Dubbelklicka på arbetsstationens installationsfil.
1. Klicka **Ja** så att programmet kan installeras i Windows.
1. Välj en **Språk** för installationsguiden.

   Guiden öppnas:

   ![](assets/6_4_workstation_wizard.png)

1. Klicka **Nästa** på **Välkommen till installationsguiden för Data Workbench** -dialogrutan.

1. Välj om du vill installera en **Ny installation** eller till **Uppgradera eller reparera** en befintlig installation.

   **Ny installation** skriver över tidigare installerade filer.

   **Uppgradera** uppdaterar din arbetsstation till den senaste versionen eller låter dig reparera en befintlig installation. Datan Workbench kommer att jämföra installerade **Insight.exe** och kör installationsguiden för arbetsstationen om det finns en nyare version av klienten.

1. Välj installationsplats:

   **Normal** installeras i en standardmapp och på en standardplats.

   * Programfiler sparas som standard till:

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Datafiler (profiler, certifikat, spårningsloggar och användarfiler) sparas som standard till:

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >En allmän ***Insight.cfg*** filen utan serverinformation installeras från början. Vi rekommenderar att du använder den nyinstallerade ***Insight.cfg*** och anpassa den i stället för att flytta en fil från en tidigare installation. Eftersom sökvägen för installation av arbetsstationen har ändrats läggs teckensnitt till och tas bort *Användarmapp* och du bör ta bort *TraceFileComponent *.

1. (valfritt) Välj **Egen** för att välja språkpaket och plats för programmet och datafilerna.
1. Välj plats för **kortkommandon på Start-menyn**.

   ![](assets/6_4_workstation_wizard_folder.png)

   Klicka **Skapa ingen startmenymapp** om du inte vill installera ett kortkommando på Start-menyn i Windows.

1. Klicka **Nästa.** En sammanfattning av de valda sökvägarna och språken för filplatser visas. Klicka **Installera.**

1. Leta reda på **Datans Workbench certifikat**.

   Om installationsguiden inte kan hitta certifikatet för Datan Workbench under installationen öppnas en dialogruta där du kan bläddra till platsen för certifikatet (en **.pem** fil som finns som standard i klienten **Certifikat** eller klicka på **Hoppa över** för att hitta certifikatet efter installationen.

   Klicka **Installera** efter att certifikatet har hittats.

1. När installationsguiden är klar och Datan Workbench är installerad klickar du på **Slutför** för att slutföra installationen.

   >[!NOTE]
   >
   >Standardloggplatsen för installationsguiden för arbetsstationen på  `C:\Users\<userName>\AppData\Local\Temp`.

   Välj **Starta programmet** för att öppna workbench efter installationen.

1. **Konfigurera anslutningar** till servrar i **[!DNL Insight.cfg]** -fil.

   Efter installationen öppnas arbetsytan Förbättrad arbetsstationskonfiguration med ytterligare information om [ange serveranslutningsinformation](/help/home/c-get-started/c-insght-config-param.md) i *Insight.cfg* och ett alternativ för att välja en profil i listrutan. Du kan även visa anslutningsstatus för dina servrar.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Installationsmappar {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Datans Workbench mappstruktur har två installationsplatser:

* **Programfiler** The **Insight.exe** och tillhörande klientfiler (**Insight.ini**) finns nu som standard på

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* The **Appdata** mapp.

   **Insight.cfg**, profiler, certifikat, spårningsloggar och användarfiler finns nu som standard på

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Du kan ange sökvägen för **Appdata** i `Insight.ini` fil:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Avinstallerar arbetsstationen {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Datan Workbench innehåller nu en körbar fil som avinstallerar arbetsstationen (som är standard på **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Starta och följ stegen för att ta bort arbetsstationsfilerna för Data Workbench från hårddisken.

>[!NOTE]
>
>Du kan starta **unins000.exe** körbar från mappen, med **Avinstallera Data Workbench** genväg från Start-menyn eller från **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
