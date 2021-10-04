---
description: Följ de här stegen för att uppdatera till data workbench v6.1 från din Insight v5.5x-installation.
title: Uppgradering av Data Workbench 5.5 till 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Uppgradering av Data Workbench 5.5 till 6.1{#data-workbench-to-upgrade}

Följ de här stegen för att uppdatera till data workbench v6.1 från din Insight v5.5x-installation.

**Steg 1**:  [Serveruppgradering](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Steg 2**:  [Uppgradering av rapportserver](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Steg 3**:  [Klientuppgradering](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Server-, rapportserver- och klientkomponenterna uppgraderas för att köras på 64-bitars Windows-operativsystem.

## Serveruppgradering {#section-08bd6fe3da8740fcb19688e8cac6f223}

Så här uppdaterar du **[!UICONTROL Server v6.1]**-komponenterna:

1. Använd profilen **[!UICONTROL Software and Docs]** för att öppna arbetsytan **[!UICONTROL Start Here]** och hämta alla serverpaket som behövs till en lokal mapp.

   * Hämta zip-mappar för **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** och extrahera alla filer.

      Paketet **[!UICONTROL Server]** innehåller mapparna **[!UICONTROL Lookup]** och **[!UICONTROL Profile]** med sökfilerna **[!UICONTROL Base]** och **[!UICONTROL Transform]** som ska läggas till och ersättas för att uppdatera servern.

   * Hämta nya **[!UICONTROL Profiles]**-mappar.
   * Hämta uppdaterade **[!UICONTROL Lookup]**-mappar.
   * Hämta **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]**-paketet.
   * Hämta ytterligare **[!UICONTROL Sensor]**-, **[!UICONTROL Documentation]**- och **[!UICONTROL Dashboard]**-filer efter behov.

1. Stoppa tjänsten **[!UICONTROL Adobe Insight Server]**.

   ![](assets/install_server_download1.png)

1. Från det hämtade **[!UICONTROL Server]**-paketet:

   1. Ersätt mappen [!DNL Server\Bin] för att uppdatera [!DNL InsightServer64.exe] och stödfilerna.

   1. Ersätt mappen [!DNL Server\Profiles]. Du kan skriva över alla filer.
   1. Uppdatera mappen [!DNL Server\Lookups]. Du vill lägga till de nyligen hämtade filerna i de anpassade filer som redan finns i mappen.
   1. Ersätt mappen [!DNL Server\Software] för att uppdatera [!DNL Insight.exe] och [!DNL ReportServer.exe]

   1. Uppdatera mappen [!DNL Server\Scripts] för att uppdatera [!DNL TnTSend.exe].

1. Om du använder **[!UICONTROL DeviceAtlas]** måste du [uppdatera paketet](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) i mappen [!DNL Server\Lookups].
1. Ange [!DNL Directories] i [!DNL Profile.cfg]-filen för att se till att vektorn uppdateras så att antalet objekt för varje profil återspeglas.

   Om du till exempel vill aktivera profilen **[!UICONTROL Predictive Analytics]** måste du uppdatera den här inställningen.

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. Konfigurera och spara filen [!DNL PAServer.cfg] för att uppgradera funktionen Predictive Analytics.

   Om du vill skicka Predictive Analytics-jobb till servrarna måste du konfigurera [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg]-filen för att hantera klusteröverföringar på serversidan.

   Den anpassade profilen bör ärva inställningarna från konfigurationsprofilen Predictive Analytics, så att du kan konfigurera och spara [!DNL PAServer.cfg] baserat på implementeringen av din webbplats.

1. Definiera **[!UICONTROL Log Source ID]**.

   **[!UICONTROL Recording of Rows per Log Source]** lades till i **[!UICONTROL v6.04]** och definierades i den anpassade profilens [!DNL Log Processing.cfg]-fil genom att lägga till ett unikt namn med namnet **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Om du inte har definierat ID för loggkälla visas följande fel:

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. Eftersom [!DNL EventMessages.dll] har uppdaterats måste du avregistrera och sedan registrera **[!UICONTROL Adobe Insight Server]** i klustret.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Starta tjänsten **[!UICONTROL Adobe Insight Server]** i klustret.

Serverinstallationen är klar.

## Uppgradering av rapportserver {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Innan du uppgraderar till **[!UICONTROL Report Server v6.1]** måste du först uppgradera till **[!UICONTROL Server v6.1]**.

1. Hämta **[!UICONTROL v6.1]** från **[!UICONTROL Report Server]**-paketet till en lokal mapp med profilen **[!UICONTROL Software and Docs]**.
1. Kopiera **[!UICONTROL Report Server 6.1]** från det hämtade paketet och ersätt profilpaketen.

   >[!NOTE]
   >
   >Filen [!DNL Insight.zbin] i mappen [!DNL install] är en säkerhetskopia som används för lokalisering och måste finnas i katalogen [!DNL install]. Den här filen eller andra [!DNL .zbin]-filer används beroende på vilka kommandoradsinställningar som skickas när du startar.

1. (valfritt) Ändra rapportserverns konfigurationsfil så att den stöder dubbelbyte-tecken.

   Data workbench har för närvarande stöd för engelska (-en-us) och kinesiska (-zh-cn). Du måste ange ett teckensnitt som stöder enkla tecken och dubbelbyte-tecken:

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Windows-operativsystemet måste också ha teckensnitten installerade.

1. Konfigurera [!DNL Report Server v6.1].

   1. Stoppa tjänsten **[!UICONTROL Adobe Insight Report Server]**.
   1. Starta en kommandotolk som administratör.
   1. Navigera till mappen Report Server [!DNL install].
   1. Ta bort tjänsten Report Server med följande kommando:

      ```
      ReportServer.exe /unregserver
      ```

1. Starta tjänsten baserat på språkinställningarna:

   ```
   ReportServer.exe -RegServer -Locale -en-us (English)
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. Kontrollera att Report Server körs med rätt inställningar genom att öppna **[!UICONTROL Windows Service Manager]** och högerklicka på **[!UICONTROL Adobe Insight Report Server - Properties]**. Sökvägen till den körbara filen visar de uppdaterade kommandoradsinställningarna.

Rapportserverinstallationen är nu klar.

## Klientuppgradering {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Innan du uppgraderar till **[!UICONTROL Client v6.1]** måste administratören först uppgradera till **[!UICONTROL Server v6.1.]**

1. Starta [!DNL Insight.exe] men anslut INTE till några profiler.
1. Redigera [!DNL Insight.cfg]-filen om du inte vill uppdatera programvaran automatiskt.

   ```
   Update Software = bool: false
   ```

1. Anslut till profilen **[!UICONTROL Software and Docs]** (programdokument).
1. Hämta [!DNL Software\Insight Client\v6.10].
1. (valfritt) Ändra [!DNL insight.cfg] om du vill ha stöd för dubbelbytetecken.

   Data workbench har för närvarande stöd för både engelska och förenklad kinesiska. Välj teckensnitt som ska ha stöd för båda dessa språk:

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. Avsluta från klienten.
1. Kopiera filerna i det hämtade **v6.1**-klientpaketet till mappen [!DNL Install].

   >[!NOTE]
   >
   >Filen [!DNL Insight.zbin] i installationsmappen är en säkerhetskopia som används för lokalisering och måste finnas i installationskatalogen. Den här filen eller andra [!DNL .zbin]-filer används beroende på vilka kommandoradsinställningar som skickas när du startar.
   >
   >Om du till exempel vill starta Förenklad kinesiska skapar du ett kortkommando som godkänns i kommandoradsinställningen.
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >Om du vill starta på engelska (standard) behövs ingen kommandoradsändring.

1. Starta [!DNL Insight.exe] för engelska eller genvägen som du skapade för ett annat språk.
1. Anslut till din profil och tillåt klienten att synkronisera med servern.
1. (valfritt) Om du vill använda IME-programmet gör du följande ändringar i [!DNL Insight.cfg]-filen:

   ```
   Localized IME = bool: true
   ```

   I Input Method Editor (IME) kan du ange internationella tecken.

1. (valfritt) Redigera [!DNL Insight.cfg]-filen så uppdateras programmet automatiskt:

   ```
   Update Software = bool: true
   ```

   Se instruktionerna för implementering av IME.
1. Starta om igen efter profilsynkroniseringen för att använda den senaste [!DNL .zbin]-filen.

Klientinstallationen är klar.
