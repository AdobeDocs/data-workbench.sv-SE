---
description: Med öppna funktioner kan du öppna objekt som dokument eller URI:er i externa program som en textredigerare eller webbläsare.
solution: Analytics
title: Konfigurera öppna funktioner
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera öppna funktioner{#configure-open-functionality}

Med öppna funktioner kan du öppna objekt som dokument eller URI:er i externa program som en textredigerare eller webbläsare.

Öppningsfunktionen är för närvarande endast konfigurerad i [!DNL Site] programmet och endast för att öppna URI:er. I det här avsnittet finns information om hur du konfigurerar Open URI-funktioner för [!DNL Site]. Kontakta Adobes konsulttjänster om du vill ha information om hur du konfigurerar Open-funktioner för ett annat program eller om du vill öppna andra objekt.

I [!DNL Site]kan du högerklicka på en URI från en sidövertäckning eller tabell för att visa URI:n i programmet som den formaterades för. Från en URI-tabellvisualisering kan du till exempel klicka på en URI för att visa en webbsida i en webbläsare.

Om du vill öppna en URI från en visualisering måste du först redigera [!DNL Open URI.cfg] filen för URI-dimensionen för att identifiera plats- och namnkonventioner som Data Workbench använder för att öppna URI:n. Om du vill visa en URI i sitt ursprungliga format (t.ex. HTML) måste Data Workbench ha tillgång till den refererade platsen och det program som behövs för att öppna objektet. Om du till exempel vill visa en webbsida måste Data Workbench ha tillgång till Internet och en webbläsare installerad.

**Redigera öppen URI.vw**

1. I [!DNL Profile Manager]klickar du på **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Högerklicka på bockmarkeringen bredvid [!DNL Open URI.vw]filen i URI-mappen och klicka på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.
1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]** om filen är en [!DNL .cfg] fil eller **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** om det är en [!DNL .vw] fil.
1. Klicka **[!UICONTROL Command]** och sedan **[!UICONTROL Parameters]** för att visa innehållet i filen.
1. Ändra [!DNL Site] parametern och mallparametern efter behov:

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
   <td colname="col2"> <p>De parametrar som Data Workbench ska använda för att hitta och öppna URI:erna. </p> <p>Exempel: <span class="filepath"> http://%Site%%URI%</span> </p> <p>Standardmallen som visas i exemplet anger för Data Workbench att öppna en webbläsare, söka efter den plats som definieras i parametern <span class="wintitle"> Plats</span> och leta sedan reda på det URI-dimensionselement som du försöker öppna. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Spara filen.
1. Om du vill göra den här ändringen tillgänglig för alla användare av arbetsprofilen högerklickar du på bockmarkeringen för [!DNL .vw] filen i [!DNL User] kolumnen och klickar på **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

