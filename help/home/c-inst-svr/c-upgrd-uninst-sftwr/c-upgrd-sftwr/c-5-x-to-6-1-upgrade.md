---
description: Följ de här stegen för att uppdatera till data workbench v6.1 från din Insight v5.5x-installation.
solution: Analytics
title: Uppgradering av Data Workbench 5.5 till 6.1
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Uppgradering av Data Workbench 5.5 till 6.1{#data-workbench-to-upgrade}

Följ de här stegen för att uppdatera till data workbench v6.1 från din Insight v5.5x-installation.

**Steg 1**: [Serveruppgradering](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**Steg 2**: Uppgradering av [rapportserver](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**Steg 3**: [Klientuppgradering](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>Server-, rapportserver- och klientkomponenterna uppgraderas för att köras på 64-bitars Windows-operativsystem.

## Serveruppgradering {#section-08bd6fe3da8740fcb19688e8cac6f223}

Så här uppdaterar du **[!UICONTROL Server v6.1]** komponenterna:

1. Öppna arbetsytan med hjälp av **[!UICONTROL Software and Docs]** **[!UICONTROL Start Here]** profilen och ladda ned alla serverpaket som behövs till en lokal mapp.

   * Ladda ned **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip-mappar och extrahera alla filer.

      Paketet innehåller **[!UICONTROL Server]** och **[!UICONTROL Lookup]** mappar med **[!UICONTROL Profile]** - och **[!UICONTROL Base]** **[!UICONTROL Transform]** sökfilerna som ska läggas till och ersättas för att uppdatera servern.

   * Hämta nya **[!UICONTROL Profiles]** mappar.
   * Hämta uppdaterade **[!UICONTROL Lookup]** mappar.
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
1. Ange [!DNL Directories] i [!DNL Profile.cfg] filen för att se till att vektorn uppdateras så att antalet objekt för varje profil återspeglas.

   Om du till exempel vill aktivera profilen måste du uppdatera den här inställningen. **[!UICONTROL Predictive Analytics]**

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. Konfigurera och spara [!DNL PAServer.cfg] filen för att uppgradera funktionen Predictive Analytics.

   Om du vill skicka Predictive Analytics-jobb till servrarna måste du konfigurera [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] filen för att hantera klusteröverföringar på serversidan.

   Den anpassade profilen bör ärva inställningarna från konfigurationsprofilen Predictive Analytics, så att du kan konfigurera och spara den [!DNL PAServer.cfg] baserat på implementeringen av webbplatsen.

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
>Innan du uppgraderar till **[!UICONTROL Client v6.1]** måste administratören först uppgradera till **[!UICONTROL Server v6.1.]**

1. Starta [!DNL Insight.exe] men anslut INTE till några profiler.
1. Redigera [!DNL Insight.cfg] filen så att programmet inte uppdateras automatiskt.

   ```
   Update Software = bool: false
   ```

1. Anslut till **[!UICONTROL Software and Docs]** profil (programdokument).
1. Ladda ned [!DNL Software\Insight Client\v6.10].
1. (valfritt) Ändra [!DNL insight.cfg] för att hantera dubbelbytetecken.

   Data workbench har för närvarande stöd för både engelska och förenklad kinesiska. Välj teckensnitt som ska ha stöd för båda dessa språk:

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Avsluta från klienten.
1. Kopiera filerna i det hämtade **v6.1** -klientpaketet till [!DNL Install] mappen.

   >[!NOTE]
   >
   >Filen i installationsmappen är en säkerhetskopia som används för lokalisering och måste finnas i installationskatalogen. [!DNL Insight.zbin] Den här filen eller andra [!DNL .zbin] filer kommer att användas beroende på vilka kommandoradsinställningar som skickas vid start.
   >
   >Om du till exempel vill starta Förenklad kinesiska skapar du ett kortkommando som godkänns i kommandoradsinställningen.
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >Om du vill starta på engelska (standard) behövs ingen kommandoradsändring.

1. Starta [!DNL Insight.exe] för engelska eller genvägen som du skapade för ett annat språk.
1. Anslut till din profil och tillåt klienten att synkronisera med servern.
1. (valfritt) Om du vill använda IME-programmet gör du följande ändringar i [!DNL Insight.cfg] filen:

   ```
   Localized IME = bool: true
   ```

   I Input Method Editor (IME) kan du ange internationella tecken.

1. (valfritt) Redigera [!DNL Insight.cfg] filen så uppdateras programmet automatiskt:

   ```
   Update Software = bool: true
   ```

   Se instruktionerna för implementering av IME.
1. Starta om igen efter profilsynkroniseringen för att använda den senaste [!DNL .zbin] filen.

Klientinstallationen är klar.
