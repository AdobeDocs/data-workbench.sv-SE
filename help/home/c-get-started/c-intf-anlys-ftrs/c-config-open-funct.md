---
description: Med öppna funktioner kan du öppna objekt som dokument eller URI:er i externa program som en textredigerare eller webbläsare.
title: Konfigurera öppna funktioner
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Konfigurera öppna funktioner{#configure-open-functionality}

{{eol}}

Med öppna funktioner kan du öppna objekt som dokument eller URI:er i externa program som en textredigerare eller webbläsare.

Öppen funktion är för närvarande konfigurerad endast i [!DNL Site] och bara för att öppna URI:er. Det här avsnittet innehåller information om hur du konfigurerar Open URI-funktioner för [!DNL Site]. Kontakta Adobe Consulting Services om du vill ha information om hur du konfigurerar Open-funktioner för ett annat program eller om du vill öppna andra objekt.

I [!DNL Site]kan du högerklicka på en URI från en sidövertäckning eller tabell för att visa URI:n i programmet som den formaterades för. Från en URI-tabellvisualisering kan du till exempel klicka på en URI för att visa en webbsida i en webbläsare.

Om du vill öppna en URI från en visualisering måste du först redigera [!DNL Open URI.cfg] fil för URI-dimensionen för att identifiera plats- och namnkonventioner som Datan Workbench använder för att öppna URI:n. Om du vill visa en URI i sitt ursprungliga format (till exempel HTML) måste Datan Workbench ha tillgång till den refererade platsen och det program som behövs för att öppna objektet. Om Datan Workbench till exempel vill visa en webbsida måste den ha tillgång till Internet och en webbläsare installerad.

**Redigera öppen URI.vw**

1. I [!DNL Profile Manager], klicka **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. I URI-mappen högerklickar du på bockmarkeringen bredvid [!DNL Open URI.vw]och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumn.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]** om filen är en [!DNL .cfg] fil eller **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** om det är en [!DNL .vw] -fil.
1. Klicka **[!UICONTROL Command]** sedan **[!UICONTROL Parameters]** om du vill visa innehållet i filen.
1. Ändra [!DNL Site] parameter och mallparametern efter behov:

<table id="table_CDB316DB271F476AB9F9B557B86AFD25">
 <thead>
  <tr>
   <th colname="col1" class="entry"> För den här parametern.. </th>
   <th colname="col2" class="entry"> Ange den här informationen... </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <p>Plats </p> </td>
   <td colname="col2"> <p>Platsen för de URI:er som du vill öppna. </p> <p>Exempel: mysite.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Mall </p> </td>
   <td colname="col2"> <p>De parametrar som Datan Workbench ska använda för att hitta och öppna URI:erna. </p> <p>Exempel: <span class="filepath"> https://%Site%%URI%</span> </p> <p>Standardmallen som visas i exemplet anger för Datan Workbench att öppna en webbläsare, leta efter den plats som definierats i <span class="wintitle"> Plats</span> söker du efter det URI-dimensionselement som du försöker öppna. </p> </td>
  </tr>
 </tbody>
</table>

1. Spara filen.
1. Om du vill göra den här ändringen tillgänglig för alla användare av arbetsprofilen högerklickar du på bockmarkeringen för [!DNL .vw] i [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
