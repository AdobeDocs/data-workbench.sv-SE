---
description: Ett terrängbildslager visar jordens terrängbilder.
solution: Analytics
title: Terrain image layers
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Terrain image layers{#terrain-image-layers}

Ett terrängbildslager visar jordens terrängbilder.

[!DNL Terrain image layers] lagras i profilen i ett anpassat format. [!DNL Geography] Dessa bildlager kan genereras av Adobe eller Data Workbench-servern kan omvandla dina användartillhandahållna terrängbilder till terränglager som passar för användning i globala visualiseringar.

>[!NOTE]
>
>För att kunna arbeta med [!DNL terrain image layers]måste du installera [!DNL Terrain Images.cfg] filen från Adobe.

Om du vill definiera ett terrängbildlager måste du ha följande:

* **En eller flera terrängbildfiler** som innehåller de bilder som ska visas på jorden.
* **En[!DNL Terrain Images.cfg]fil** som anger vilka terrängbildfiler som ska användas för lagren. Med hjälp av [!DNL Terrain Images.cfg] filen kan du lägga till en eller flera källor för att skapa en [!DNL terrain image layer]. Formatet på terrängbildfilen avgör vilken typ av källa du ska lägga till. Följande tabell innehåller beskrivningar av de tillgängliga källorna till terrängbildlager, inklusive vilka terrängbildfilformat som stöds:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Raw oprojicerad bitmapp </p> </td> 
   <td colname="col2"> <p>Skapar <span class="wintitle"> terrängbildslager</span> från 24-bitars rubrikfria RGB-filer som är justerade i latitud-longitud (oprojicerade), där norr är bildens överkant och öster är höger. </p> <p>Bildformat som stöds: RAW </p> <p> <p>Obs! Den här källan kräver projektionsinformation. Mer information om projektionsformat finns i <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Ange projektionsinformation för Terrain Images</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allmän bild, oprojicerad </p> </td> 
   <td colname="col2"> <p>Skapar <span class="wintitle"> terrängbildslager</span> från 24-bitars, latitud-longitud-justerade (oprojicerade) bildformat, där norr är bildens överkant och öster är höger. </p> <p>Bildformat som stöds: BMP, JPG, PNG, TIFF </p> <p> <p>Obs! Den här källan kräver projektionsinformation. Mer information om projektionsformat finns i <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Ange projektionsinformation för Terrain Images</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bild med inbäddad projektion </p> </td> 
   <td colname="col2"> <p>Skapar <span class="wintitle"> terrängbildslager</span> från bildformat som bäddar in geodetiska data i bildfilen. Projektionsinformationen extraheras från bilden. </p> <p>Bildformat som stöds: Erdas (IMG), GeoTIFF </p> <p> <p>Obs! Den här källan kräver vanligtvis ingen projektionsinformation, men stöder tillägg av sådan information vid behov. Mer information om projektionsformat finns i <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Ange projektionsinformation för Terrain Images</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definiera ett terrängbildlager**

1. Öppna arbetsytan genom att klicka på miniatyrbilden i Data Workbench på **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** -fliken **[!UICONTROL Servers Manager]** . [!DNL Servers Manager] .
1. Högerklicka på ikonen för den önskade Data Workbench-servern i [!DNL Servers Manager] fönstret och klicka på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Terrain Images.cfg] katalogen.
1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Terrain Images.cfg]och klicka sedan på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Terrain Images.cfg].
1. Högerklicka på den nya bockmarkeringen i **[!UICONTROL Temp]** kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Fönstret [!DNL Terrain Images.cfg] visas.
1. Klicka i [!DNL Terrain Images] fönstret **[!UICONTROL component]** för att visa innehållet.
1. Högerklicka **[!UICONTROL Sources]** > **[!UICONTROL Add new]** och välj en av följande källtyper:

   * **[!UICONTROL Raw unprojected bitmap]**. (När den här källtypen har lagts till heter den RawTerrainSource i [!DNL Terrain Images] fönstret.)

   * **[!UICONTROL General image, unprojected]**. (När den här källtypen har lagts till märks den [!DNL GDALTerrainSource] i [!DNL Terrain Images] fönstret.)

   * **[!UICONTROL Image with embedded projection]**. (När den här källtypen har lagts till märks den [!DNL GDALTerrainSource] i [!DNL Terrain Images] fönstret.)

1. Redigera parametrarna för källan efter behov med följande exempelfil och parametertabell som stödlinjer.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>Valfritt för alla källor. Anger gammakorrigering som ska användas på källbilden. Detta kan vara önskvärt på grund av att Data Workbench normalt körs med en hög gammainställning. Standardvärdet är 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Höjd </p> </td> 
   <td colname="col2"> <p>Krävs för oprojicerade oprojicerade bitmappsbilder. Källbildens höjd i pixlar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Projektionsinformation </p> </td> 
   <td colname="col2"> <p>Krävs för oprojicerade oprojicerade bitmappsbilder och allmänna bilder, ej projicerade, men stöds för bilder med inbäddad projektion. Data Workbench har stöd för latitud-longitud-projektioner och Transverse Mercator-projektioner (TM) för terrängbildslager. Standardprojektionsformatet är latitud-longitud-projektionen (LatLonProjection). </p> <p>Mer information om projektionsformat finns i <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Ange projektionsinformation för Terrain Images</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Källbild </p> </td> 
   <td colname="col2"> <p>Krävs för alla källor. Namnet på källbildfilen. Detta kan vara ett filnamn eller ett jokertecken. Det kan vara praktiskt att använda ett mönster om t.ex. bilder för samma område vid olika datum överförs utan att tillhörande metadata ändras. Ett mönster som <span class="filepath"> Tysons Corner *.raw</span> skulle därför skapa lager från <span class="filepath"> Tysons Corner 050211.raw</span>, Tysons Corner 050218.raw <span class="filepath"></span>och så vidare när nya bilder läggs till, utan någon ytterligare konfiguration behövs om parametrarna för filerna annars är identiska. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Komprimeringskvalitet för plattor </p> </td> 
   <td colname="col2"> <p>Valfritt för alla källor. För JPEG-komprimering, ett heltal mellan 0 och 100 som anger hur bildens storlek och kvalitet ska balanseras. (Standardvärdet är noll.) Ett högre värde ger bättre bildkvalitet men ger större bilder och längre hämtningstider för Data Workbench-användare. </p> <p> <p>Obs!  Komprimering av bilder under 70 kan leda till bildförsämring. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattformskompressor </p> </td> 
   <td colname="col2"> <p>Valfritt för alla källor. Anger vilken komprimeringsmetod som används för att skriva utdatafiler. De enda metoder som stöds för närvarande är RAWRGB (standardmetoden, vilket innebär ingen komprimering) och JPEG. Använd JPEG-komprimering om du vill minska storleken på de lager som överförs under profilsynkronisering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bredd </p> </td> 
   <td colname="col2"> <p>Krävs för oprojicerade oprojicerade bitmappsbilder. Källbildens bredd i pixlar. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Redigera parametrarna Source Image Location, Temp Image Storage och Write Layers To med hjälp av följande tabell. De här parametrarna gäller för alla terrängbildskällor som du definierar i avsnittet [!DNL Sources] i den här filen.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Källbildssökväg </p> </td> 
   <td colname="col2"> <p>Obligatoriskt. Katalogen som skannas efter bilder som ska omvandlas till terränglager. Om sökvägen inte är absolut tolkas den i förhållande till Data Workbench-serverns installationskatalog. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temporär bildlagring </p> </td> 
   <td colname="col2"> <p>Valfritt. Namnet på en katalog som används för lagring av temporära filer som används vid översättning av källbilder till terränglager. Om sökvägen inte är absolut tolkas den i förhållande till Data Workbench-serverns installationskatalog. Standardplatsen är <span class="wintitle"> Temp</span> -katalogen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skriv lager till </p> </td> 
   <td colname="col2"> <p>Obligatoriskt. Katalogen som terränglagren ska skrivas ut till. Vanligtvis är detta underkatalogen Maps i en profilkatalog, så att globala visualisering kan hitta lagren. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.
1. Om du vill spara en uppdaterad fil på Data Workbench-serverdatorn [!DNL Server Files Manager]högerklickar du på bockmarkeringen [!DNL Terrain Images.cfg] i [!DNL Temp] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
