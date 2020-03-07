---
description: Nya funktioner i Data Workbench 6.0.4, bland annat felkorrigeringar och kända fel.
solution: Analytics
title: Versionsinformation för Data Workbench 6.0
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Versionsinformation för Data Workbench 6.0

Nya funktioner i Data Workbench 6.0.4, bland annat felkorrigeringar och kända fel.

## Nya funktioner {#section-1225066ea8f44cf68e42e019d0bca816}

Data workbench (Insight 6.0) innehåller dessa nya funktioner och visualiseringar för extra rapporteringsfunktioner och verktyg för prediktiv analys.

| Data Workbench-funktioner | Beskrivning |
|---|---|
| [Trattvisualisering](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | Med Trattvisualisering kan ni definiera kundens sekventiella processflöde och synliggöra besökarnas bortfall vid varje steg i processen. |
| [Besökskluster](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | Med klustring kan ni utnyttja kundens egenskaper för att dynamiskt kategorisera besökarna och generera klusteruppsättningar baserat på valda dataindata för kundanalys och målgruppsanpassning. |
| [Korrelationsanalys](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | Med korrelationsanalys kan ni snabbt identifiera relevanta dataförhållanden för att utöka och förbättra analysen. |
| [Uppdaterad DeviceAtlas-distribution](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | DeviceAtlas JSON-filen kommer nu att distribueras i en .bundle-fil (en namnändrad .tar.gz) tillsammans med DeviceAtlas.dll och DeviceAtlas64.dll. |

## Krav för klientuppgradering {#section-f316103b48374b6eac77e8feb5c47ecf}

Utför följande uppgraderingsuppgifter för klientfunktionerna i Data Workbench (Insight 6.0):

**Uppdaterar .zbin-filen för klienten**

Data Workbench har nu stöd för en IME-redigerare (Input Method Editor) som en sekundär textinmatningsprocess där du kan ange internationella tecken från tangentbordet med en flytande textruta. Data workbench har stöd för engelska som standard, men gör det även möjligt att läsa in andra filer för stöd av internationella språk, till exempel ett virtuellt kinesiskt tangentbord (Pinyin IME).

En ny ordlistefil (en Zbin-fil) krävs av klientprogrammet innan version 6.0 uppdateras. Du kan hämta den Zbin-fil som behövs från Software- och Docs-profilen (Softdocs).

Förutsättningar:

* Innan du uppgraderar till Insight 6.0 och Report Server 6.0 måste Insight-administratören först uppgradera till Insight Server 6.0.
* Insight-administratören måste välja en zbin-fil baserat på språk (en-us.zbin, zh-cn.zbin), kopiera språkfilen, sedan byta namn på den till insight.zbin och placera den namnändrade filen i rotkatalogen för rapportservern där den körbara filen finns. Starta sedan om Insight Report Server.

Mer information om uppgradering på serversidan finns i [Serveruppgraderingskraven](../../../home/c-release-notes-insight/release-notes.md) .

**Så här uppgraderar du zbin-filen för klienten (från version 5.x till 6.0)**

1. Om du vill vara säker på att klienten inte uppdateras från Insight Server under uppgraderingen anger du argumentet Insight.cfg som false.

   ```
   Update Software = bool: false
   ```

1. Starta om Insight-klienten.
1. Navigera till profilen Software and Docs (SoftDocs-profilen) och hämta den **[!UICONTROL Insight.zbin]** fil som krävs: [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Kopiera filen Insight.zbin till samma mapp som filen Insight.exe.
1. Om du vill vara säker på att Insight-klienten nu uppdateras från Insight Server ändrar du filargumentet Insight.cfg till true:

   ```
   Update Software = bool: true
   ```

1. Starta om klienten.

   Klienten synkroniseras med servern och ett meddelande om att klienten laddas ned visas. När nedladdningen är klar får du ett meddelande där du tillfrågas om du vill starta om Insight-klienten.
1. Klicka på **OK** för att starta om klienten.

   Klienten startar och uppgraderar till version 6.0.

1. Starta om klienten igen för att synkroniseringen av Insight.zbin-klienten ska börja gälla.

   Om du får följande meddelande betyder det att zbin inte placerades i rätt mapplats tillsammans med filen Insight.exe.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   För att åtgärda problemet tar du bort Insight.exe och byter namn på den senaste versionen av Insight.exe.old till Insight.exe och börjar sedan om med steg 1 ovan.

## Krav för serveruppgradering {#section-d6edba8b36234957ba8d06b555667a5a}

Utför följande uppgraderingsuppgifter för serverfunktionerna i Insight 6.0:

**Uppdatera alla Insight Server 6.0-paket**. Insight 6.0 innehåller serverpaket som behöver uppdateras, inklusive den nya Predictive Analytics-profilen.

>[!IMPORTANT]
>
>Vi rekommenderar att användare uppgraderar sina serverkluster med nya installationer av Insight Server 6.0 vid uppdatering.

Vi rekommenderar också att man uppgraderar serverklustren med en ny installation av Insight Server 6.0.

## Uppgradera serverkluster

**Förbered språkfilen (.zbin-fil).** Insight-administratören väljer `<language>.zbin` filen för det språk som krävs (till exempel: sv-se.zbin , zh-cn.zbin) i `/localization/<language>.zbin` mappen. Administratören kopierar sedan språkfilen och byter namn på den till &quot;insight.zbin&quot;.

När språkfilen (.zbin) har förberetts måste både Insight Client och Report Server uppdateras. Insight Client uppdateras under [klientuppgraderingsprocessen](../../../home/c-release-notes-insight/release-notes.md), men i de flesta fall uppdaterar Insight-administratören Report Server.

**Uppdatera rapportservern med en språkfil (.zbin-fil)**.

För alla språk kräver Report Server 6.0 filen &quot;insight.zbin&quot; som kopieras till rotmappen för Report Server.

Uppdatera språkfilerna för Report Server:

1. Lägg till den namnändrade filen insight.zbin i rotkatalogen ReportServer.
1. Konfigurationsfilen för rapportservern (rapportserver.cfg) kräver teckensnittsinställningar för dubbelbytespråk. Kinesiska kräver till exempel tillägg av teckensnitt med SimSun:

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. En parameter för Report Server 6.0 måste skickas i kommandoraden för lokalisering, till exempel:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Om ingen språkinställning anges används som standard det språk som valts i filen insight.zbin.

   Följ stegen för att starta ReportServer som en tjänst med språkparametrarna:

   1. Starta en kommandotolk som administratör.
   1. Navigera till installationsmappen för ReportServer.
   1. Ange följande kommando för att starta tjänsten:

      * För engelska: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * För kinesiska: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Så här kontrollerar du om ReportServer körs med rätt parametrar:

   1. Öppna Windows Service Manager.
   1. Högerklicka [!DNL Adobe Insight Report Server - Properties].
   Sökvägen till den körbara filen innehåller parametrarna:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Ändra profilkonfigurationsfilen för prediktiv analys**. Insight-administratören måste ändra filen profile.cfg så att den innehåller profilen Predictive Analytics som ska vara tillgänglig i Insight.

Exempel på posten profile.cfg:

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**Uppdatera filen** PAServer.cfg. Om du vill skicka Predictive Analytics-klusterjobb till Insight-servrar måste du konfigurera PAServer.cfg-filen för hantering av klusteröverföringar på serversidan.

Den anpassade profilen bör ärva PAServer.cfg från profilen Predictive Analytics (Server\Profiles\Predictive Analytics\Dataset). Konfigurera och spara PAServer.cfg per implementeringsplats.

>[!NOTE]
>
>När PAServer.cfg har konfigurerats och sparats i en anpassad profil måste Insight Server startas om på hela webbplatsen.

**Server för uppgraderingsrapport.** Du måste uppdatera teckensnitten och startparametrarna för Report Server.

Förutsättningar:

* Innan du uppgraderar Report Server 6.0 måste Insight-administratören först uppgradera till Insight Server 6.0.
* För alla språk kräver Report Server 6.0 att Insight.zbin läggs till i rotmappen för Report Server. Kontrollera att filen `base/localization/<language>.zbin` kopieras och byter namn till &quot;insight.zbin&quot;. Kopiera den till roten i rapportserverkatalogen.

Uppdatera parametrarna Fonts och Start:

1. Report Server kräver teckensnittsinställning för dubbelbyte för att kunna skriva ut på olika språk.

   till exempel:

   Report Server.cfg - Lägg till teckensnitt

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. Parametern för Report Server 6.0 måste skickas i kommandoraden för lokalisering.

   Så här startar du Report Server som en tjänst med språkparametrar:

   1. Stoppa rapportservertjänsten.
   1. Starta en kommandotolk som administratör.
   1. Navigera till installationsmappen för Report Server.
   1. Ange följande kommando för att starta tjänsten:

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Så här kontrollerar du om rapportservern körs med rätt parametrar:

1. Öppna Windows Service Manager
1. Högerklicka [!DNL Adobe Insight Report Server - Properties].
1. Sökvägen till den körbara filen innehåller parametrarna:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Uppgradera SiteCatalyst-dataflödet för Insight 6.0**. Filnamnsformatet för SiteCatalyst-dataflödet för Insight 6.0 har ändrats.

Aktuellt filnamnsformat:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Nytt filnamnsformat:

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Den här ändringen påverkar inte användare som för närvarande distribueras med *wbench/ecom* -versionen av SiteCatalyst-dataflödet.

Ändringen av filnamnsformatet möjliggör fullständig användning av Insight-deklarationerna för start- och sluttid under loggbearbetningen. Detta gör att processen kan utvärdera om innehållet i filen ska läsas, i stället för att filtrera alla källfiler med en rad för rad-sökning.

I de flesta fall implementerades en namnbytesprocess när filen togs emot för att ge full användning av den här funktionen. Den här ändringen tillhandahåller den namnkonvention som krävs som standard utan att en sekundär process behövs och utan behov.

Så här använder du den nya SiteCatalyst-datafeeden:

1. Bestäm hur den mottagande processen ska hantera det nya filnamnsformatet.

   Standardskriptet för att byta namn/flytta skript som distribueras under implementeringen flyttar filerna med tillägget&quot;.gz&quot; och utför bara ett namnbyte om filnamnet matchar filnamnsformatet med föregående RSID.

   Det nya filnamnsformatet:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Utvärdera de definierade sökvägarna till loggkällan för att bekräfta att alla filer kommer att läsas.

   Om du redan har implementerat ett namnbytesskript definierar du redan dina loggkällor för att läsa det nya filnamnsformatet.

## Korrigeringar {#section-203f917dd6224114a1f801309c4c2cee}

* Tangentkombinationen för att lämna en arbetsyta utan att spara ändringar har uppdaterats till **[!UICONTROL `<Ctrl>`+`<Backspace>`]**. Du har tidigare annullerat ändringar och stängt en arbetsyta genom att trycka på`<Ctrl>`+`<Delete>`.

## Versionsinformation för Data Workbench 6.0.4{#data-workbench-release-notes}

Nya funktioner i Data Workbench 6.0.4, bland annat felkorrigeringar och kända fel.

Om du vill visa tidigare funktioner och korrigeringar som är baserade på den senaste versionen läser du i arkiven [med](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)versionsinformation.

## Nya funktioner {#section-2-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.0.4 innehåller dessa nya funktioner och visualiseringar för extra rapporteringsfunktioner och verktyg för prediktiv analys.

**Visualisering** av benägenhetsbedömning. Data workbench beräknar poängen för varje besökare som en uppskattad sannolikhet att en angiven händelse kan inträffa. Med visualisering av besökarpoäng kan du skapa en poängdimension som ger en sannolikhet för en viss händelse för varje intressant besökare baserat på indatavariablerna.

![](assets/visitor_scoring_visual.png)

Mer information om den här funktionen finns i [Propensitetsbedömning](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) .

## Krav för uppgradering {#section-08bd6fe3da8740fcb19688e8cac6f223}

**Loggkälla-ID måste definieras**. Från och med version 6.04 får du följande fel om inte ID för loggkälla är definierat:

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

Inspelning av rader per loggkälla har lagts till i Data Workbench 6.0 och kan definieras i den anpassade profilen Log Processing.cfg genom att lägga till ett unikt namn för Loggkälla-ID. Om du har ett tomt ID för loggkälla kan du se problem med loggbearbetningen, t.ex. ofullständig läsning av loggkälldata och andra avvikelser.

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**Möjlighet att delegera FSU-resurser**

I [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg]kan du nu ange separata filserverenheter (FSU) för servrarna Normalize och Source List. Dessa tjänster är inte längre knutna till Master FSU.

>[!NOTE]
>
>Om listservern inte anges ärver listservern standardinställningarna för serverkonfigurationen.

Exempel i [!DNL cluster.cfg] filen.

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## Åtgärdade fel {#section-3b4b85a35f534288adf8a5246ef028cc}

* I Data Workbench 6.0 hade Correlation Matrix och Cluster Builder inte stöd för Compute in Background. Detta har nu åtgärdats i version 6.0.4.
* Tidigare kunde en åtkomstöverträdelse uppstå om du hade markerat något på tratten och tagit bort ett steg. Detta har lösts.
* Korrigerade ett möjligt låsningsvillkor i segmentexport som kan orsaka problem under stora lastförhållanden.
