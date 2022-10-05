---
description: Du kan skapa ett segment av elementen i valfri räkningsbar dimension och sedan exportera data för det segmentet på batchbasis eller i realtid till en tabbavgränsad fil.
title: Konfigurera segment för export
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Konfigurera segment för export{#configure-segments-for-export}

{{eol}}

Du kan skapa ett segment av elementen i valfri räkningsbar dimension och sedan exportera data för det segmentet på batchbasis eller i realtid till en tabbavgränsad fil.

Varje gång du exporterar ett segment genereras mått- eller dimensionsdata för alla dimensionselement som ingår i segmentet. Du kan styra hur utdata formateras så att andra system enkelt kan läsa in data.

>[!NOTE]
>
>Du kan inte exportera rapporteringsdimensioner eftersom de använder en [!DNL report time.metric] fil för referens. Du kan lösa det genom att placera en hårdkodad [!DNL report time.metric] i profilen kan segmentexporten använda den som referenspunkt för att rapportera dimensioner. Men [!DNL report time.metric] uppdateras inte automatiskt baserat på profilens Efter tid, så när du vill ändra rapporteringsdimensionsreferensen måste du ändra den hårdkodade [!DNL report time.metric] -fil.

Om du vill konfigurera ett segment för export måste du öppna och redigera en [!DNL .export] -fil.

1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Export]** i [!DNL File] -kolumn för att visa dess innehåll.

       Om exportkatalogen inte finns skapar du den på följande sätt:
   
   1. Gå till Datans Workbench installationskatalog.
   1. Öppna katalogen för den profil som du arbetar med.
   1. Skapa en ny katalog med namnet&quot;Export&quot; i profilkatalogen.

1. I [!DNL Profile Manager]högerklickar du på den tomma cellen i [!DNL User] -kolumn för exportkatalogen och klicka sedan på **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   En fil med namnet [!DNL New Segment Export.export] visas i [!DNL File] -kolumn för Export.

1. Byt namn på den nya filen genom att högerklicka i dialogrutan [!DNL User] -kolumnen för filen och skriver det nya namnet i parametern File.
1. Öppna den nya filen genom att högerklicka i [!DNL User] kolumn för filen och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   Konfigurationsfönstret för [!DNL .export] filen visas.

1. Klicka **[!UICONTROL Query]** och sedan ändra fälten i [!DNL .export] enligt följande tabell:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange den här informationen... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Kommando </td> 
   <td colname="col2"> <p>Valfritt. Ett program som ska köras när utdatafilen har skapats. Det här fältet måste referera till en körbar fil (en <span class="filepath"> .exe </span> -fil), inte ett kommando. </p> <p>Obs! Segmentexporten misslyckas om det finns ett blanksteg i kommandoparametern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filter </td> 
   <td colname="col2"> <p>Valfritt. Ett namngivet filter eller ett filteruttryck. Du kan antingen skapa ett namngivet filter med en filterredigerare och sedan skriva namnet på filtret här, eller också kan du skriva in ett filteruttryck själv. </p> <p>Mer information om filterredigerare finns i <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Filterredigerare </a>. Mer information om filteruttryckssyntax finns i <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntax för filteruttryck </a>. </p> <p>Element av Nivå som matchar filtret exporteras, men inte alla andra element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nivå </td> 
   <td colname="col2"> <p>Den räkningsbara dimensionen vars element ska exporteras. </p> <p>Exempel: En besökarnivå exporterar en rad med data för varje besökare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdatafil </td> 
   <td colname="col2"> <p>Sökväg och filnamn för exporterade data. Om Datan Workbench körs i ett serverkluster skriver varje Data Workbench en utdatafil som innehåller en del av informationen. </p> <p>Installationskatalogen för Data Workbench-servern innehåller en exportkatalog där du kan spara utdatafilen. Du kan till exempel skriva <span class="filepath"> Exporterar\Visitor Segment.txt </span>, där <span class="filepath"> Besökarsegment.txt </span> är namnet på filen som innehåller exporterade data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utdataformat </td> 
   <td colname="col2"> Mått eller dimensionsdata som ska exporteras för varje nivåelement. Om utdata är en tabbavgränsad fil bör fälten avgränsas med tabbtecken och formatet avslutas med motsvarande radbrytningstecken. Mer information finns i <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Om utdataformatet </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schemats sluttid </td> 
   <td colname="col2"> <p>Valfritt. Schemats slutdatum och sluttid, inklusive tidszonen. </p> <p>Format: YYY-MM-DD hh:mm tidszon </p> <p>Exempel: 2013-08-01 12:01 EDT </p> <p>Schemalagd export avbryts vid denna tidpunkt. Utdatafilen genereras dock fortfarande om när definitionen ändras. Det här fältet är meningslöst utan att definiera Schedule Every. Mer information om tidszonsinställningar finns i <i>Konfigurationshandbok för datauppsättning</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schemalägg varje </td> 
   <td colname="col2"> Valfritt. Den frekvens med vilken utdatafilen ska genereras om. Värden som stöds är timme, dag, vecka och månad. Utdatafilen genereras fortfarande om när definitionen ändras. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schemalägg starttid </td> 
   <td colname="col2"> <p>Valfritt. Startdatum och starttid för schemat, inklusive tidszonen. </p> <p>Format: YYY-MM-DD hh:mm tidszon </p> <p>Exempel: 2013-08-01 12:01 EDT </p> <p>Den schemalagda exporten startar just nu och schemat är relativt till den här tiden. Det här fältet har ingen betydelse utan att definiera <span class="wintitle"> Schemalägg varje </span>. Mer information om tidszonsinställningar finns i <i>Konfigurationshandbok för datauppsättning</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tidsgräns (sek) </td> 
   <td colname="col2"> Valfritt. Den maximala tid som tillåts förflyta när en segmentexport genereras. Om det angivna intervallet överskrids startar exporten om. Om du anger värdet 0 (noll) tas gränsen bort. Standardvärdet är 600 sekunder. </td> 
  </tr> 
 </tbody> 
</table>

1. Högerklicka **[!UICONTROL (New)]** längst upp i fönstret och klicka sedan på **[!UICONTROL Save]**.
1. Om du vill göra den här filen tillgänglig för alla användare i arbetsprofilen högerklickar du på bockmarkeringen för den skapade filen [!DNL .export] i [!DNL User] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Sparar [!DNL .export] -filen till Datan Workbench gör att exporten körs en gång omedelbart, även om Schemalägg starttid är inställt på ett framtida datum och en framtida tidpunkt.

   Följande är ett exempel [!DNL .export] -fil.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >The [!DNL Visitor Segment.export] filen som visas i exemplet refererar till Visitor-segmentfiltret. Om du ändrar definitionen för det här filtret ändras definitionen för exporten.
