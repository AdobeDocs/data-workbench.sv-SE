---
description: Med Serverfilhanteraren kan du fjärradministrera och hantera Data Workbench från alla behöriga Data Workbench genom att ge åtkomst till alla kataloger och filer i produktens installationskatalog, inklusive konfigurations- och sökningsfiler.
title: Serverfilhanteraren
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 0%

---

# Hanteraren för serverfiler{#server-files-manager}

Med Serverfilhanteraren kan du fjärradministrera och hantera Data Workbench från alla behöriga Data Workbench genom att ge åtkomst till alla kataloger och filer i produktens installationskatalog, inklusive konfigurations- och sökningsfiler.

Du kan komma åt [!DNL Server Files Manager] via menyn [!DNL Admin] och högerklicka på noden på serverdatorn i [!DNL Servers Manager] och klicka på **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Du kan skapa nya serverfilhanterare som visar valda kataloger. Se [Skapa nya serverfilshanterare](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

I den vänstra kolumnen i [!DNL Server Files Manager] visas fil- och mappnamn. Kryssmarkeringarna i kolumnerna mitt och höger anger var i filstrukturen katalogerna och filerna finns.

Om en fil finns i produktens installationskatalog innehåller kolumnen *servernamn* (till exempel Data Workbench server) en bock. Om en fil finns på Datans Workbench dator i *Datans Workbench installationskatalog*\Temp innehåller kolumnen [!DNL Temp] en bockmarkering. Färgen på bockmarkeringarna anger om de filer som finns på olika platser har ändrats samtidigt.

* En röd bockmarkering i servernamnskolumnen anger att Datan Workbench eller filen finns på serverdatorn.
* En röd bockmarkering i kolumnen [!DNL Temp] anger att den lokala kopian av filen eller mappen har samma ändringsdatum och -tid som filen eller Datan Workbench på serverdatorn.
* En vit bockmarkering i kolumnen [!DNL Temp] anger att filen eller mappen i *Datans Workbench installationskatalog*\Temp har ett annat ändringsdatum och -klockslag än filen eller Datan Workbench på serverdatorn.

I följande bild visas [!DNL Server Files Manager] med både röda och vita bockmarkeringar:

![](assets/vis_FileManager_RedWhiteChecks.png)

**Hantera kataloger och filer med[!DNL Server Files Manager]**

Du kan använda [!DNL Server Files Manager] för att ändra kataloger och filer på en Data Workbench.

I följande tabell visas de uppgifter som kan utföras med [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För att utföra den här uppgiften.. </th> 
   <th colname="col2" class="entry"> Gör det här.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visa filerna i en katalog </p> </td> 
   <td colname="col2"> <p>Klicka på katalognamnet för att visa dess innehåll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här döljer du innehållet i en katalog </p> </td> 
   <td colname="col2"> <p>Klicka på katalognamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa information om en katalog </p> </td> 
   <td colname="col2"> <p>Högerklicka på cellen bredvid katalogen i antingen servernamnet eller i kolumnen <span class="wintitle"> Temp</span>. Följande information finns: </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Bana. Katalogens sökväg. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. Katalogens namn. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">Från. Platsen för katalogen, Remote eller Temp. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Datum (endast tillfällig kolumn). Skapad den lokala kopian eller den senaste versionen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här visar du information om en fil </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen bredvid filen i antingen servernamnet eller i kolumnen <span class="wintitle"> Tillfällig</span>. Följande information finns: </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Bana. Filens sökväg. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Fil. Filens namn. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">Från. Platsen för katalogen, Remote eller Temp. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Datum. Datum för den senaste versionen av filen. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Storlek. Filens storlek. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här hämtar du en katalog till din lokala dator </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen i kolumnen <i>servernamn</i> för den här katalogen och klicka på <span class="uicontrol"> Gör katalog lokal</span>. En bock för katalogen visas i kolumnen <span class="wintitle"> Temp</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här hämtar du en fil till den lokala datorn </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen i kolumnen <i>servernamn</i> för den här filen och klicka på <span class="uicontrol"> Gör lokal</span>. En bock för filen visas i kolumnen <span class="wintitle"> Temp</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här hämtar du den sista delen av en loggfil till den lokala datorn </p> </td> 
   <td colname="col2"> <p>För att undvika att behöva ladda ned en hel loggfil (särskilt när du vet att felmeddelandet ligger nära filens slut) högerklickar du på bockmarkeringen i filens servernamnskolumn, klickar på <span class="uicontrol"> Tail</span> och väljer storleken på den del som du vill hämta. En bock för filen visas i kolumnen <span class="wintitle"> Temp</span>. Den lokala filen innehåller bara den datamängd som du har angett, med början i filslutet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Öppna en katalog </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen för katalogen i kolumnen <span class="wintitle"> Temp</span> och klicka på <span class="uicontrol"> Öppna</span> &gt; <span class="uicontrol"> mapp</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Så här öppnar du en fil </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen för filen i kolumnen <span class="wintitle"> Temp</span>, klicka på <span class="uicontrol"> Öppna</span>, klicka sedan i <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> i Anteckningar</span> eller <span class="uicontrol"> mapp</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spara en lokal kopia av en katalog på Data Workbench-servern </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen för katalogen i kolumnen <span class="wintitle"> Temp</span> och klicka på <span class="uicontrol"> Spara katalog till</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spara en lokal kopia av en fil på Data Workbench-servern </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen för filen i kolumnen <span class="wintitle"> Temp</span> och klicka på <span class="uicontrol"> Spara till</span> &gt; <i>&lt;<span class="uicontrol"> profilnamn</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta bort en lokal kopia av en katalog eller fil </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen för katalogen eller filen i kolumnen <span class="wintitle"> Temp</span> och klicka på <span class="uicontrol"> Ta bort</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kopiera och klistra in en fil som en e-postbilaga i Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Högerklicka på bockmarkeringen för filen i kolumnen <span class="wintitle"> Temp</span> och klicka på <span class="uicontrol"> Kopiera</span>. Bifoga filen genom att trycka på Ctrl+V i e-postmeddelandets brödtext. </p> </td> 
  </tr> 
 </tbody> 
</table>
