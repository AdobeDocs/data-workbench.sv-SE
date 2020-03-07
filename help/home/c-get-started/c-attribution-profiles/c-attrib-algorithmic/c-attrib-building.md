---
description: Öppna Best Fit Attribution från Premium-menyn och följ de här stegen för att skapa en Best Fit Attribution-modell.
title: Skapa en modell för bästa passform
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Skapa en modell för bästa passform{#build-a-best-fit-attribution-model}

Öppna Best Fit Attribution från Premium-menyn och följ de här stegen för att skapa en Best Fit Attribution-modell.

Se en översikt över [Best Fit Attribution](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1).

1. Öppna **Best Fit Attribution**.

   Öppna en arbetsyta och klicka på **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >Best Fit Attribution är en premiumfunktion i Adobe Analytics som kräver att du aktiverar Premium i din profil. Du måste uppdatera certifikatet och lägga till Premium-profilen i filen profile.cfg. Se [DWB Server upgrade: 6.2 till 6.3](https://docs.adobe.com/content/help/en/data-workbench/using/install/upgrade-dwb/c-6-2-to-6-3-upgrade.html) för DWB 6.3.

1. Ange **[!UICONTROL Success]** måttet.

   >[!NOTE]
   >
   >Du kan antingen dra ett mätvärde från en **[!UICONTROL Finder]** tabell till den vänstra rutan i attribueringsvisualiseringen eller välja på menyn **Indata** .

   Klicka på **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. Måttmenyn öppnas. ![](assets/attrib_set_success_metric.png)

   Välj ett mätvärde som identifierar en lyckad konvertering.

1. (valfritt) Ange **intäktsmått** .

   Ange ett mätvärde för att utvärdera intäkterna under konverteringsprocessen.

1. Ange **pekskärmsmått** .

   >[!NOTE]
   >
   >Du behöver bara ange ett Touch-mått om du försöker att automatiskt skapa Success-mått genom att dra dimensionselement till visualiseringen.

   Klicka på **[!UICONTROL Inputs]** menyn och välj **Ange beröring** eller dra ett mått från Finder. ![](assets/attrib_set_touch.png)

   Detta används för att härleda kanalmått när dimensionselement används som indata.

1. Ange ett fönster för **lyckad** åtgärd.

   Klicka på [!DNL Inputs > Success Window]. Välj ett datumintervall från en tabell och ge sedan fönstret Slutfört ett namn. Klicka **[!UICONTROL Workspace Selection]** så tilldelas de markerade datumen som tidsintervall för mätningen Slutfört.

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >Eftersom fönstret Success är ett val av arbetsstation kan du inkludera alla dimensioner i fönstret Success.

1. Ställ in en **[!UICONTROL Touch Window]**.

   Klicka på [!DNL Inputs > Touch Window]. Välj ett datumintervall från en tabell och ge sedan pekfönstret ett namn. Klicka **[!UICONTROL Workspace Selection]** så tilldelas de markerade datumen som tidsintervall för mätningen Slutfört.

   ![](assets/attrib_set_touch_window.png)

   Som standard ställs **Touch** -fönstret in på samma tidsperiod som **[!UICONTROL Success]** fönstret.

1. (valfritt) Ange ett utbildningsfilter.

   Du kan också ange ett **utbildningsfilter** på arbetsytan för att filtrera besöksdata.

   >[!NOTE]
   >
   >När du ställer in både fönstren Slutfört och Touch kan du använda utbildningsfiltret på de aktuella arbetsytevalen för att ytterligare begränsa dina data.

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >Utbildningsmaterialet hämtas alltid från besökare som uppfyller fönstret Success. Genom att filtrera med filterredigeraren kan du skapa en delmängd av besökarna som rapporteras i fönstret Slutfört.

1. Ange kanalmått som representerar beröringar.

   Dra mätvärden till visualiseringen eller välj dem på menyn [!DNL Inputs] > [!DNL Add Channel] . Om ni inte redan har definierade mätvärden för kampanjer eller kanaler, men har dimensioner som representerar kanaler, kan visualiseringen skapa dem automatiskt med hjälp av en specifikation av ett Touch-mått.

   Om Touch-måttet till exempel är [!DNL Hits], och har fått ett [!DNL dimension] namn [!DNL Media Type] med element som innehåller saker som [!DNL Email], [!DNL Press Release], [!DNL Print Ad]och [!DNL Social Media], genererar visualiseringen kanalmått för formuläret [!DNL Hits where Media Type = Email] när du drar och släpper elementen till visualiseringen.

1. Tryck på **Go**.

   Analysprocessen för bästa passform körs och ett diagram visar attribut per kanal baserat på valda indata.

   >[!NOTE]
   >
   >Högerklicka på **Model Complete** i den färdiga analysen för att se statistik för attribueringsmodellen.

   ![](assets/attrib_visualization.png)

När diagrammet är klart visas en attribueringsmodell som beräknas per kanal och en fördelning av *intäktsmåttet* (om det är angivet). Modellen kan sparas internt eller exporteras till andra system.

>[!NOTE]
>
>**[!UICONTROL Streaming]**, **[!UICONTROL Online]** och **[!UICONTROL Offline]** lägen ger olika effekter när du skapar en attribueringsmodell som baseras på fördröjningen för de data som utvärderas. I direktuppspelningsläge visas **[!UICONTROL Model Complete]** detaljmeddelandet. I online- och offlinelägen **[!UICONTROL Local Model Complete]** visas detaljerna.

## Alternativ-menyn {#section-22288867f6c8483a8a38410f4b948346}

Menyn **Alternativ** innehåller avancerade funktioner för att ställa in och visa analysen för bästa passform.

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Alternativ-menyn </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Ange utbildningsfilter </span> </td> 
   <td colname="col2"> Utbildningsfiltret används med fönstret Slutfört för att filtrera populationen när attribueringsmodellen skapas. Detta ger en delmängd av data som bara innehåller de besökare som du vill analysera. <p>Obs! Erfarna användare kan också utnyttja flexibiliteten i filter för att fokusera bortom tidslinjen i Success och Touch Windows. Förutom att välja ett tidsintervall kan du t.ex. välja en uppsättning med <i>referensdomäner</i> för att endast undersöka attribueringen för användare från dessa domäner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Visa beskrivning av komplext filter </span> </td> 
   <td colname="col2"> Visar filterkoden för utbildningsfiltret, fönstret Slutfört och pekfönstret. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Spara modell </span> </td> 
   <td colname="col2"> Sparar den aktuella attribueringsmodellen för framtida bruk. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Läs in modell </span> </td> 
   <td colname="col2"> Öppnar en tidigare sparad attribueringsmodell. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Presentationsvy </span> </td> 
   <td colname="col2"> Döljer den översta menyraden för presentation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Alternativ &gt; Avancerat</b> innehåller funktioner för att ställa in storleken på utbildningsmaterialet och ange vilken metod som ska användas vid klassobalans. </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Avancerat &gt; Utbildningsstorlek </span> </td> 
   <td colname="col2"> <p>Anger utbildningens uppsättningsstorlek. </p> <p>Obs!  Standardstorleken för utbildning är Stor för 250 000 besökare. </p> 
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD"> 
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Liten = 50 000 </li> 
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">Liten = 75 000 </li> 
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">Normal = 100 000 </li> 
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">Stor = 250,00 </li> 
     <li id="li_34B60233C84F48F1BCB8040C5195411A">Mycket stor = 500 000 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Avancerat &gt; Klasssaldo </b> </td> 
   <td colname="col2"> <p>Identifierar och definierar antalet indataposter som ska genereras för ett klassproblem baserat på datamängdens storlek. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Alternativ för att återställa och ta bort | Beskrivning |
|---|---|
| **[!UICONTROL Reset Model]** | På **[!UICONTROL Reset]** menyn väljer du **[!UICONTROL Reset Model]** att rensa visualiseringen men behålla indatamätningar. |
| **[!UICONTROL Reset All]** | På **[!UICONTROL Reset]** menyn väljer du **[!UICONTROL Reset All]** för att rensa visualiseringen och indatavärdena. |
| **[!UICONTROL Remove]** | Högerklicka på en inmatning och välj **[!UICONTROL Remove]** för att rensa måttet från den valda inmatningen. |
| **[!UICONTROL Remove All]** | Högerklicka på *Kanaler* och välj **[!UICONTROL Remove All]** för att rensa alla indatamått. |

