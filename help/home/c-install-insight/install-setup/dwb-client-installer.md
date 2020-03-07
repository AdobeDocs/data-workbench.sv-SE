---
description: Data Workbench innehåller en konfigurationsguide för installation av arbetsstationsprogrammet (klientprogrammet).
title: Guiden Installera arbetsstation
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Guiden Installera arbetsstation{#workstation-setup-wizard}

Data Workbench innehåller en konfigurationsguide för installation av arbetsstationsprogrammet (klientprogrammet).

## Installera arbetsstationen med installationsguiden {#section-58da9bb6196c46eab3b54146913fdcb8}

Starta installationsguidens körbara fil och gå igenom varje steg för att installera arbetsstationens klientprogram. När du har installerat arbetsstationen kan du ansluta till servrar och profiler.

1. Dubbelklicka på arbetsstationens installationsfil.
1. Klicka på **Ja** om du vill tillåta att programmet installeras i Windows.
1. Välj ett **språk** för installationsguiden.

   Guiden öppnas:

   ![](assets/6_4_workstation_wizard.png)

1. Klicka på **Nästa** i dialogrutan **Välkommen till installationsguiden** för Data Workbench.

1. Välj om du vill installera en **ny installation** eller **uppgradera eller reparera** en befintlig installation.

   **Ny installation** skriver över tidigare installerade filer.

   **Uppgradera** uppdaterar din arbetsstation till den senaste versionen eller låter dig reparera en befintlig installation. Data Workbench jämför installerade **Insight.exe** -filer och kör installationsguiden för arbetsstationen om det finns en nyare version av klienten.

1. Välj installationsplats:

   **Vanligtvis** installeras en standardmapp och en standardplats.

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
      >En generisk ***Insight.cfg*** -fil utan serverinformation installeras från början. Vi rekommenderar att du använder den nyligen installerade ***filen Insight.cfg*** och anpassar den i stället för att flytta en fil från en tidigare installation. Eftersom sökvägen för installation av arbetsstationen har ändrats bör du lägga till teckensnitt, ta bort *användarmappen* och ta bort *TraceFileComponent *.

1. (valfritt) Välj** Anpassad** för att välja språkpaket och plats för programmet och datafilerna.
1. Välj plats för **kortkommandon på Start-menyn**.

   ![](assets/6_4_workstation_wizard_folder.png)

   Klicka på **Skapa inte en Start-menymapp** för att inte installera ett kortkommando på Start-menyn i Windows.

1. Klicka på **Nästa.** En sammanfattning av de valda sökvägarna och språken för filplatser visas. Klicka på **Installera.**

1. Leta reda på **Data Workbench-certifikatet**.

   Om installationsguiden inte kan hitta Data Workbench-certifikatet under installationen öppnas en dialogruta där du kan bläddra till platsen för certifikatet (en **.pem** -fil som finns som standard i mappen **Certificates** ) eller klicka på **Hoppa** för att hitta certifikatet efter installationen.

   Klicka på **Installera** när du har hittat certifikatet.

1. När installationsguiden har slutförts och Data Workbench har installerats klickar du på **Slutför** för att slutföra installationen.

   >[!NOTE]
   >
   >Standardloggplatsen för guiden Konfigurera arbetsstation på **[!DNL C:\Users\`<userName>&quot;\AppData\Local\Temp.]**

   Markera kryssrutan **Starta program** för att öppna workbench efter installationen.

1. **Konfigurera anslutningar** till servrar i **[!DNL Insight.cfg]** filen.

   Efter installationen av arbetsstationen öppnas arbetsytan Förbättrad arbetsstationskonfiguration med ytterligare information om hur du [anger serveranslutningsinformation](/help/home/c-get-started/c-insght-config-param.md) i filen *Insight.cfg* och ett alternativ för att välja en profil i listrutan. Du kan även visa anslutningsstatus för dina servrar.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Installationsmappar {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Mappstrukturen Data Workbench har två installationsplatser:

* **Programfiler** **Insight.exe** och tillhörande klientfiler (**Insight.ini**) finns nu som standard på

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Mappen **Appdata** .

   **Insight.cfg**, profiler, certifikat, spårningsloggar och användarfiler finns nu som standard på

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Du kan ange sökvägen för mappen **Appdata** i `Insight.ini` filen:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Avinstallerar arbetsstationen {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbench innehåller nu en körbar fil som avinstallerar arbetsstationen (som är standard på **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Starta och följ stegen för att ta bort arbetsstationsfilerna för Data Workbench från hårddisken.

>[!NOTE]
>
>Du kan starta den körbara filen **unins00.exe** från mappen med genvägen **Avinstallera Data Workbench** från Start-menyn eller från **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
