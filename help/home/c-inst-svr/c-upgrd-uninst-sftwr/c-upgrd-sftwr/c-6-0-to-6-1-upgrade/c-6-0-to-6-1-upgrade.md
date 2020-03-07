---
description: Följ de här stegen för att uppdatera till data workbench v6.1 från din Data Workbench v6.0x-installation.
solution: Analytics
title: Uppgradering av Data Workbench 6.0 till 6.1
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Uppgradering av Data Workbench 6.0 till 6.1{#data-workbench-to-upgrade}

Följ de här stegen för att uppdatera till data workbench v6.1 från din Data Workbench v6.0x-installation.

**Steg 1**: Uppgradering av [server](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**Steg 2**: Uppgradering av [rapportserver](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Steg 3**: Uppgradering av [klient](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Server-, rapportserver- och klientkomponenterna uppgraderas för att köras på 64-bitars Windows-operativsystem.

## Serveruppgradering {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Så här uppdaterar du **[!UICONTROL Server v6.1]** komponenterna:

1. Öppna arbetsytan med hjälp av **[!UICONTROL Software and Docs]** **[!UICONTROL Start Here]** profilen och ladda ned alla serverpaket som behövs till en lokal mapp.

   * Ladda ned **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip-mappar och extrahera alla filer.

      Serverpaketet innehåller **[!UICONTROL Lookup]** och **[!UICONTROL Profile]** mappar med **[!UICONTROL Base]** - och **[!UICONTROL Transform]** -profiler för att uppdatera servern.

      * Hämta **[!UICONTROL Profiles]** mapparna.
      * Hämta **[!UICONTROL Lookup]** mapparna.
      * Hämta **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** -paketet.
      * Hämta ytterligare **[!UICONTROL Sensor]** filer **[!UICONTROL Documentation]** och **[!UICONTROL Dashboard]** filer efter behov.

1. Stoppa **[!UICONTROL Adobe Insight Server]** tjänsten.

   ![](assets/install_server_download1.png)

1. Från det hämtade **[!UICONTROL Server]** paketet:

   1. Ersätt [!DNL Server\Bin] mappen för att uppdatera [!DNL InsightServer64.exe] och stödfilerna.

   1. Ersätt [!DNL Server\Profiles] mappen. Du kan skriva över alla filer.
   1. Uppdatera [!DNL Server\Lookups] mappen. Du vill lägga till de nyligen hämtade filerna i de anpassade filer som redan finns i mappen.
   1. Ersätt den [!DNL Server\Software] mapp som ska uppdateras [!DNL Insight.exe] och [!DNL ReportServer.exe]
   1. Uppdatera den [!DNL Server\Scripts] mapp som ska uppdateras [!DNL TnTSend.exe].

1. Om du använder **[!UICONTROL DeviceAtlas]** måste du [uppdatera paketet](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) som finns i [!DNL Server\Lookups] mappen.

1. Konfigurera [!DNL Profile.cfg] filen så att vektorn uppdateras med antalet objekt för varje profil.

   Om du till exempel vill aktivera profilen måste du uppdatera den här inställningen. **[!UICONTROL Predictive Analytics]**

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Konfigurera och spara filen PAServer.cfg för funktionen Predictive Analytics.

   Om du vill skicka Predictive Analytics-jobb till servrarna måste du konfigurera [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] filen för att hantera klusteröverföringar på serversidan.

   Den anpassade profilen bör ärva inställningarna från konfigurationsprofilen Predictive Analytics, så att du kan konfigurera och spara [!DNL PAServer.cfg] filen baserat på implementeringen av webbplatsen.

1. Definiera **[!UICONTROL Log Source ID]**.

   Den **[!UICONTROL Recording of Rows per Log Source]** lades till **[!UICONTROL v6.04]** och definierades i den anpassade profilens [!DNL Log Processing.cfg] fil genom att lägga till ett unikt namn **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   Om du inte har definierat ID för loggkälla visas följande fel:

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. Eftersom filen [!DNL EventMessages.dll] har uppdaterats måste du avregistrera och sedan registrera den **[!UICONTROL Adobe Insight Server]** i hela klustret.

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Starta **[!UICONTROL Adobe Insight Server]** tjänsten i klustret.

Serverinstallationen är klar.

## Uppgradering av rapportserver {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>Innan du uppgraderar till **[!UICONTROL Report Server v6.1]** måste du först uppgradera till **[!UICONTROL Server v6.1]**.

1. Använd **[!UICONTROL Software and Docs]** profilen för att hämta **[!UICONTROL v6.1]** från **[!UICONTROL Report Server]** paketet till en lokal mapp.

1. Kopiera **[!UICONTROL Report Server 6.1]** från det hämtade paketet och ersätt profilpaketen.

   >[!NOTE]
   >
   >Filen [!DNL Insight.zbin] i [!DNL install] mappen är en säkerhetskopia som används för lokalisering och måste finnas i [!DNL install] katalogen. Den här filen eller andra [!DNL .zbin] filer kommer att användas beroende på vilka kommandoradsinställningar som skickas vid start.

1. (valfritt) Data workbench har för närvarande stöd för engelska (-en-us) och kinesiska (-zh-cn). Du måste ange ett teckensnitt som stöder enkla tecken och dubbelbyte-tecken:

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Windows-operativsystemet måste också ha teckensnitten installerade.

1. Konfigurera [!DNL Report Server v6.1] för lokalisering.

   1. Stoppa **[!UICONTROL Adobe Insight Report Server]** tjänsten.
   1. Starta en kommandotolk som administratör.
   1. Navigera till [!DNL install] mappen Report Server.
   1. Ta bort tjänsten Report Server med följande kommando:

      ```
      ReportServer.exe /unregserver
      ```

   1. Starta tjänsten baserat på språkinställningarna:

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)  
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. Kontrollera att Report Server körs med rätt inställningar genom att öppna **[!UICONTROL Windows Service Manager]** och högerklicka **[!UICONTROL Adobe Insight Report Server - Properties]**. Sökvägen till den körbara filen visar de uppdaterade kommandoradsinställningarna.

Rapportserverinstallationen är nu klar.

## Klientuppgradering {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Innan du uppgraderar till **[!UICONTROL Client v6.1]** måste administratören först uppgradera till **[!UICONTROL Insight Server v6.1.]**

1. Starta [!DNL Insight.exe] men anslut inte till några profiler.
1. Redigera [!DNL Insight.cfg] filen.

   ```
   Update Software = bool: true
   ```

1. Anslut till din profil.

   Tillåt klienten att synkronisera med servern så uppgraderas klienten med de senaste v6.1-klientprofilerna, körbara filer och konfigurationsfilerna.

   >[!NOTE]
   >
   >Filen [!DNL Insight.zbin] i [!DNL install] mappen är en säkerhetskopia som används för lokalisering och måste finnas. Den här filen eller andra [!DNL .zbin] filer kommer att användas beroende på vilka kommandoradsinställningar som skickas vid start.

   Se [konfigurera lokaliserade språk](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) för att lägga till en [!DNL insight.zbin] fil som krävs för lokaliserade inställningar.

**Ytterligare klientinställningar**

Innan du konfigurerar [!DNL Insight.exe] och stöder filer måste du avsluta klientprogrammet.

Så här installerar du förenklad kinesiska:

1. Skapa ett kortkommando som skickas i kommandoradsinställningen till [!DNL Insight.exe] filen.

   ```
   Insight.exe -zh-cn
   ```

1. Konfigurera [!DNL Insight.cfg] för tecken med en eller två byte.

   Data workbench har för närvarande stöd för både engelska och förenklad kinesiska. Du kan välja teckensnitt som har stöd för båda dessa språk:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   Windows-operativsystemet måste också ha de begärda teckensnitten installerade.

1. Starta genvägen som du skapade för att synkronisera profiler och den uppdaterade versionen. [!DNL zbin] -fil.

Använda IME (Input Method Editor).

Med IME kan du ange internationella tecken.

1. Uppdatera [!DNL Insight.cfg] filen med följande inställningar:

   ```
   Localized IME = bool: true
   ```

1. Starta genvägen som du skapade för att synkronisera profiler och den uppdaterade [!DNL .zbin] filen.

Klientinstallationen är klar.
