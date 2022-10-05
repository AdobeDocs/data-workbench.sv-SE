---
description: Information om webbspecifika inställningar som definieras i Transformation DataSet innehåller filer som levereras med Adobe-profiler för Site.
title: Webbspecifika inställningar för omvandling
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 0%

---

# Webbspecifika inställningar för omvandling{#web-specific-settings-for-transformation}

{{eol}}

Information om webbspecifika inställningar som definieras i Transformation DataSet innehåller filer som levereras med Adobe-profiler för Site.

De villkor, dimensioner och parametrar som definieras av de här inställningarna skapas under datauppsättningens omformningsfas.

* [Sidvisningsvillkor](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI-Dimension](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimensionen Referent](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Sessionsparametrar](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Sidvisningsvillkor {#section-cc2807a12a88492f8b64a43234a1f835}

The [!DNL Page View Condition] är en villkorsåtgärd som avgör om en viss loggpost (d.v.s. en sidförfrågan) ska inkluderas i de data som samlas in om en besökares sidvisningshistorik. När loggposten uppfyller [!DNL Page View Condition]blir det ett element i sidvyns räkningsbara dimension. Om en loggpost inte uppfyller [!DNL Page View Condition], är dess datafält fortfarande tillgängliga med andra dimensioner. Förutom sidvisningsdimensionen kan följande dimensioner påverkas av resultatet av [!DNL Page View Condition]:

* **[!DNL URI]och [!DNL Page]:** Dessa mått påverkas direkt av [!DNL Page View Condition]. Om den angivna sidan inte godkänns av [!DNL Page View Condition,] den ingår inte i URI- eller siddimensionerna.

* **[!DNL Visitor Page Views]och [!DNL Session Page Views]:** Dimensionerna för sidvyer och sidvyer för besökare är antalet sidor som visas av en besökare till eller under en viss session. Sidor som filtrerats bort av [!DNL Page View Condition] ingår inte i det här antalet.

* **Sessionsnummer:** The [!DNL Page View Condition] har en indirekt effekt på dimensionen Sessionsnummer. Sessionsnummerdimensionen skapas före [!DNL Page View Condition]; därför, när man överväger [!DNL Session Number] i förhållande till [!DNL Page Views]kan du ha sessioner utan sidvyer.

Din standardimplementering av [!DNL Site] innehåller [!DNL Transformation Dataset Include] fil där sidvyns räkningsbara dimension och den relaterade [!DNL Page View Condition] är definierade.

Mer information om räkningsbara dimensioner finns i [Utökade Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Så här redigerar du konfigurationsinställningarna för sidvisningsvillkoren**

1. Öppna [!DNL Profile Manager] i din datauppsättningsprofil och öppna [!DNL Dataset\Transformation\Traffic\Page View.cfg] -fil.

   >[!NOTE]
   >
   >Om du har anpassat implementeringen av [!DNL Site]kan filen som innehåller dessa konfigurationsinställningar skilja sig från den plats som beskrivs.

1. Granska eller redigera parametervärdena för [!DNL Page View Condition] efter behov. Använd följande exempel som guide. I den här filen är [!DNL Page View Condition] definieras av [!DNL Copy] omformning. Observera att den här filen även innehåller definitionen av den räkningsbara sidvisningsdimensionen.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Mer information om räkningsbara dimensioner finns i [Utökade Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Mer information om [!DNL Copy] omformning, se [Dataomvandlingar](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka sedan på **[!UICONTROL Save]**.

1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

## URI-Dimension {#section-348f7e9099d049d197a7cdcbc8a6c234}

Om du arbetar med [!DNL Site]måste du definiera den URI-dimension vars element är URI-matningar för de visade webbplatssidorna. Standardimplementeringen innehåller en [!DNL Transformation Dataset Include] filen som den enkla URI-dimensionen definieras i.

Mer information om enkla dimensioner finns i [Utökade Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Redigera konfigurationsinställningarna för URI-dimensionen**

1. Öppna [!DNL Profile Manager] i din datauppsättningsprofil och öppna [!DNL Dataset\Transformation\Traffic\URI.cfg] -fil.

   >[!NOTE]
   >
   >Om du har anpassat implementeringen av [!DNL Site]kan filen som innehåller dessa konfigurationsinställningar skilja sig från den plats som beskrivs.

1. Granska eller redigera parametervärdena för filen efter behov. Använd följande exempel och information som stödlinjer.

![](assets/cfg_WebParameters_URI.png)

Konfigurationsinställningarna för URI-dimensionen innehåller följande två parametrar:

* **Skiftlägeskänslig:** Sant eller falskt. Om värdet är true beaktas skiftläge för bokstäver (övre/nedre) när unika sidor identifieras. Standardvärdet är true.
* **Maximalt antal element:** Det högsta antalet element (dvs. URI:er) för URI-dimensionen. Standardvärdet är 32768.

   >[!NOTE]
   >
   >Om du ändrar det här värdet kan det orsaka allvarliga prestandaproblem. Ändra inte det här värdet utan att rådfråga Adobe.

* Spara [!DNL URI.cfg] genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka sedan på **[!UICONTROL Save]**.

* Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

## Dimensionen Referent {#section-8a97ec34d18b4814b5f95495ac4f8638}

Om du arbetar med [!DNL Site]måste du definiera referensdimensionen vars element består av domänerna på den andra nivån för referenterna för de första loggposterna i alla sessioner. Standardimplementeringen innehåller en [!DNL Transformation Dataset Include] filen som den enkla referensdimensionen är definierad i.

Mer information om enkla dimensioner finns i [Utökade Dimensioner](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Så här redigerar du konfigurationsinställningarna för referensdimensionen**

1. Öppna [!DNL Profile Manager] i din datauppsättningsprofil och öppna [!DNL Dataset\Transformation\Traffic\Referrer.cfg] -fil.

   >[!NOTE]
   >
   >Om du har anpassat implementeringen av [!DNL Site]kan filen som innehåller dessa konfigurationsinställningar skilja sig från den plats som beskrivs.

1. Granska eller redigera parametervärdena för filen efter behov. Använd följande exempel och information som stödlinjer.

   ![](assets/cfg_WebParameters_Referrer.png)

   Konfigurationsinställningarna för referensdimensionen inkluderar parametern Maximum Elements, som anger det maximala antalet element (det vill säga referenter) för referensdimensionen. Standardvärdet är 32768.

   >[!NOTE]
   >
   >I exemplet ovan är [!DNL Maximum Elements] parametern är inställd på 0. När den här parametern är inställd på 0 använder data workbench-servern det interna standardvärdet 32768.

1. Spara [!DNL Referrer.cfg] genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka sedan på **[!UICONTROL Save]**.

1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

## Sessionsparametrar {#section-0a209b0c504041a5801f7f71a963c8b1}

Om du arbetar med [!DNL Site]kan du ange parametrar som definierar gränserna för en besökarsession på en webbplats. Dessa parametrar är bara giltiga när de definieras i en [!DNL Transformation Dataset Include] i [!DNL Site] implementering.

Följande parametrar är unika eftersom de kan vara medlemmar i [!DNL Transformation Dataset Include] fil [!DNL Parameters] eller så kan de listas som enskilda parametrar i [!DNL Transformation.cfg]-fil. En parameter kan definieras exakt en gång, så dessa parametrar definieras antingen i [!DNL Transformation.cfg]eller i [!DNL Parameters] -vektorn för datauppsättningen innehåller -filen, inte i båda filerna.
**Maximal sessionstid och tidsgräns för session**

Maximal sessionstid och tidsgräns för session är strängparametrar som definierar längden på en besökares session. De här parametrarna fungerar med parametern Internal Domains för att bestämma sessionslängden.

Maximal sessionsvaraktighet anger den längsta sessionslängden innan en ny session startas. På så sätt kan webbsidor med automatiskt innehåll uppdateras från att du skapar sessioner som är godtyckligt långa. Om referenten för ett klick är inställd på en av posterna i parametern Internal Domains, används den här tidsgränsen för att definiera slutet av en session. Ingen session får vara längre än den angivna maximala sessionslängden, oavsett hur många klick den innehåller. Rekommenderat värde är 48 timmar.

Sessionstimeout anger den tid som måste förflyta mellan loggposterna för en viss besökare för att avgöra slutet av en session och början av en ny session (d.v.s. den vanliga tidsgränsen som används för att definiera en användarsession). Det rekommenderade värdet för den här parametern är 30 minuter. Om referenten för ett klick inte är inställd på en av referenserna i parametern Internal Domains, används den här tidsgränsen för att definiera sessionen. Om cs(referer-domain) för en loggpost finns i listan över interna domäner avgör Maximal sessionstid om den aktuella loggposten är en del av en befintlig session eller om en ny session påbörjas.

Tänk dig en situation där en besökare anropas bort från datorn under en längre tid än tidsgränsen för sessionen när han eller hon befinner sig mitt i surfandet. När han kommer tillbaka fortsätter han att surfa där han slutade. Eftersom besökaren aldrig lämnar webbplatsen eller stänger webbläsaren är cs(referrer-domain) för nästa klickning densamma som den interna domänen, och den ursprungliga sessionen förblir aktiv så länge inställningen för Maximal sessionstid inte nås. Om webbplatsens domän listas som en intern domän och den maximala tidsgränsen inte nås, visas besökarens interaktion som en enda session och inte som två separata sessioner. Om besökaren återgår till sin dator och nästa klickning har en extern (eller tom) referent, startar en ny session.

>[!NOTE]
>
>The [!DNL Sessionize] omformningar [!DNL Timeout Condition] spelar också en roll när det gäller att bestämma längden på en besökarsession. Om Timeout för session och Maximal sessionslängd inte gäller, visas [!DNL Timeout Condition] är markerad för att avgöra om en loggpost ska anses vara början av en ny session. Mer information finns i [Dataomvandlingar](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Så här redigerar du parametrarna Maximal sessionstid och Timeout för session**

Om du arbetar med [!DNL Site], är standardimplementeringen förmodligen en [!DNL Transformation Dataset Include] filen där namnen och de rekommenderade värdena för parametrarna anges.

1. Öppna [!DNL Profile Manager] i din datauppsättningsprofil och gå till [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Om du har anpassat implementeringen av [!DNL Site]kan filen som parametrarna definieras i skilja sig från den plats som beskrivs.

1. Redigera parametervärdena efter behov. Var noga med att ange önskade enheter (minuter, timmar och så vidare).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Spara [!DNL Session Parameters.cfg] genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.

**[!DNL Internal Domains]**

[!DNL Internal Domains] är en vektorparameter som listar domännivåvärdar (interna referenter) som ska behandlas som en del av en viss webbplats. Värdarna tas bort från referensdimensionen (som är en lista över extern referensinformation). När cs(referer-domain) matchar någon av strängarna som anges i uppsättningen med interna domäner, ignoreras timeout för session och Maximal sessionstid används för att bestämma sessionslängden.

Parametern Interna domäner kan också användas för att förhindra att en ny session inleds när besökare förflyttar sig mellan ett företags flera domäner som är kopplade på ett sätt som överskrider tidsgränsen för sessioner. Ta till exempel ett företag som har delar av sin webbplats delade i två domäner: en loggas ( [!DNL xyz.com]) och den andra inte loggas ( [!DNL xyz-unlogged.com]). Om dessa webbplatser är integrerade på ett sätt som underlättar den sömlösa trafikrörelsen över de två domänerna är det inte önskvärt att generera olika sessioner varje gång besökaren flyttas från [!DNL xyz-unlogged.com] tillbaka till [!DNL xyz.com] domän. Lista [!DNL xyz-unlogged.com] som en intern domän inte kan dela sessioner i flera sessioner som ett resultat av trafik över dessa två domäner så länge som inställningen för Maximal sessionstid inte nås.

**Lägga till en intern domän**

Om du arbetar med [!DNL Site], din standardimplementering innehåller [!DNL Transformation Dataset Include] för att definiera parametern Internal Domains. I den här filen heter parametern: Du anger bara de interna domäner som du vill inkludera och sparar den uppdaterade filen.

1. Öppna [!DNL Profile Manager] i din datauppsättningsprofil och gå till [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Om du har anpassat implementeringen av [!DNL Site]den fil i vilken parametern för interna domäner definieras kan skilja sig från den plats som beskrivs.

1. Högerklicka **[!UICONTROL Value]** för vektorparametern för interna domäner och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Redigera värdena efter behov.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Spara [!DNL Internal Domains.cfg] genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Om du vill att de lokalt gjorda ändringarna ska gälla går du till [!DNL Profile Manager]högerklickar du på bockmarkeringen för filen i dialogrutan [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, där profilnamnet är namnet på datauppsättningsprofilen eller den ärvda profilen som datauppsättningsfilen tillhör.

   >[!NOTE]
   >
   >Spara inte den ändrade konfigurationsfilen i någon av de interna profilerna som tillhandahålls av Adobe, eftersom ändringarna skrivs över när du installerar uppdateringar för de här profilerna.
