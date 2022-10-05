---
description: I Data Workbench visar ett terrängbildslager terrängbilder av jorden.
title: Arbeta med terrängbildlager
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 0%

---

# Arbeta med terrängbildlager{#working-with-terrain-image-layers}

{{eol}}

I Data Workbench visar ett terrängbildslager terrängbilder av jorden.

Lager för terrängbilder lagras i [!DNL Geography] i ett anpassat format. Dessa bildlager kan genereras av Adobe, eller data workbench-servern kan omvandla dina användartillhandahållna terrängbilder till terränglager som är lämpliga att använda för globala visualiseringar.

>[!NOTE]
>
>Om du vill arbeta med terrängbildlager måste du installera [!DNL Terrain Images.cfg] som tillhandahålls av Adobe. Installationsanvisningar finns i [Installerar Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Om du vill definiera ett terrängbildlager måste du ha följande:

* **En eller flera terrängbildfiler** som innehåller de bilder som ska visas på jorden.
* **A Terrain Images.cfg** fil som anger vilka terrängbildfiler som ska användas för lagret/lagren. The [!DNL Terrain Images.cfg] kan du lägga till en eller flera källor för att skapa ett terrängbildlager. Formatet på terrängbildfilen avgör vilken typ av källa du ska lägga till. Följande tabell innehåller beskrivningar av de tillgängliga källorna till terrängbildlager, inklusive vilka terrängbildfilformat som stöds:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Raw oprojicerad bitmapp </td> 
   <td colname="col2"> <p>Skapar terrängbildslager från 24-bitars rubrikfria RGB-filer som är justerade i latitud-longitud (oprojicerade), där norr är bildens överkant och öster är höger. </p> <p>Bildformat som stöds: RAW </p> <p> <p>Obs! Den här källan kräver projektionsinformation. Information om projektionsformat finns i <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Ange projektionsinformation för terrängbilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Allmän bild, oprojicerad </td> 
   <td colname="col2"> <p>Skapar terrängbildslager från 24-bitars, latitud-longitud-justerade (oprojicerade) bildformat, där norr är bildens överkant och öster är höger. </p> <p>Bildformat som stöds: BMP, JPG, PNG, TIFF </p> <p> <p>Obs! Den här källan kräver projektionsinformation. Information om projektionsformat finns i <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Ange projektionsinformation för terrängbilder</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bild med inbäddad projektion </td> 
   <td colname="col2"> <p>Skapar terrängbildslager från bildformat som bäddar in geodetiska data i bildfilen. Projektionsinformationen extraheras från bilden. </p> <p>Bildformat som stöds: Erdas (IMG), GeoTIFF </p> <p> <p>Obs! Den här källan kräver vanligtvis ingen projektionsinformation, men stöder tillägg av sådan information vid behov. Information om projektionsformat finns i <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Ange projektionsinformation för terrängbilder</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Definiera ett terrängbildlager**

1. I data workbench, på [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna [!DNL Servers Manager] arbetsyta.

1. I [!DNL Servers Manager] högerklicka på ikonen för den önskade data workbench-servern och klicka på **[!UICONTROL Server Files]**.

1. I [!DNL Server Files Manager], klicka **[!UICONTROL Components]** för att visa innehållet. The [!DNL Terrain Images.cfg] filen finns i den här katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Terrain Images.cfg]och sedan klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Terrain Images.cfg.]

1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Terrain Images.cfg]visas.

1. I [!DNL Terrain Images] fönster, klicka **[!UICONTROL component]** för att visa innehållet.

1. Högerklicka **[!UICONTROL Sources]** > **[!UICONTROL Add new]** och välj någon av följande källtyper:

   * **[!UICONTROL Raw unprojected bitmap]**. (När den här källtypen har lagts till får den namnet RawTerrainSource i dialogrutan [!DNL Terrain Images] fönster.)

   * **[!UICONTROL General image, unprojected]**. (När den här källtypen har lagts till får den namnet GDALTerrainSource i dialogrutan [!DNL Terrain Images] fönster.)

   * **[!UICONTROL Image with embedded projection]**. (När den här källtypen har lagts till får den namnet GDALTerrainSource i dialogrutan [!DNL Terrain Images] fönster.)

1. Redigera parametrarna för källan efter behov med följande exempelfil och parametertabell som stödlinjer.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> Valfritt för alla källor. Anger gammakorrigering som ska användas på källbilden. Detta kan vara önskvärt på grund av att data workbench normalt körs med en hög gammainställning. Standardvärdet är 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Höjd </td> 
   <td colname="col2"> Krävs för oprojicerade oprojicerade bitmappsbilder. Källbildens höjd i pixlar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Projektionsinformation </td> 
   <td colname="col2"> <p>Krävs för oprojicerade oprojicerade bitmappsbilder och allmänna bilder, ej projicerade, men stöds för bilder med inbäddad projektion. Data workbench<span class="wintitle"> Geografi</span> har stöd för latitud-longitud-projektioner och Transverse Mercator-projektioner (TM) för terrängbildlager. Standardprojektionsformatet är latitud-longitud-projektionen (LatLonProjection). </p> <p>Information om projektionsformat finns i <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Ange projektionsinformation för terrängbilder</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Källbild </td> 
   <td colname="col2">Krävs för alla källor. Namnet på källbildfilen. Detta kan vara ett filnamn eller ett jokertecken. Det kan vara praktiskt att använda ett mönster om t.ex. bilder för samma område vid olika datum överförs utan att tillhörande metadata ändras. Därför är ett mönster som "<span class="filepath"> Tysons Corner *.raw</span>" skulle skapa lager från <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>och så vidare när nya bilder läggs till, utan ytterligare konfiguration krävs om parametrarna för filerna i övrigt är identiska. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Komprimeringskvalitet för plattor </td> 
   <td colname="col2"> <p>Valfritt för alla källor. För komprimering av JPEG anger ett heltal mellan 0 och 100 hur bildens storlek och kvalitet ska balanseras. (Standardvärdet är noll.) Ett högre värde ger bättre bildkvalitet, men ger större bilder och längre hämtningstider för användare av Data Workbench. </p> <p>Komprimering av bilder under 70 kan leda till bildförsämring. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plattformskompressor </td> 
   <td colname="col2"> Valfritt för alla källor. Anger vilken komprimeringsmetod som används för att skriva utdatafiler. De enda metoder som stöds för närvarande är RAWRGB (standardmetoden, vilket innebär ingen komprimering) och JPEG. Använd JPEG-komprimering för att minska storleken på lager som överförs under profilsynkronisering. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bredd </td> 
   <td colname="col2"> Krävs för oprojicerade oprojicerade bitmappsbilder. Källbildens bredd i pixlar. </td> 
  </tr> 
 </tbody> 
</table>

1. Redigera parametrarna Source Image Location, Temp Image Storage och Write Layers To med hjälp av följande tabell. De här parametrarna gäller för alla terrängbildskällor som du definierar i avsnittet Källor i den här filen.

   | Parameter | Beskrivning |
   |---|---|
   | Källbildssökväg | Obligatoriskt. Katalogen som skannas efter bilder som ska omvandlas till terränglager. Om det inte är en absolut sökväg tolkas den i förhållande till installationskatalogen för data workbench-servern. |
   | Temporär bildlagring | Valfritt. Namnet på en katalog som används för lagring av temporära filer som används vid översättning av källbilder till terränglager. Om det inte är en absolut sökväg tolkas den i förhållande till installationskatalogen för data workbench-servern. Standardplatsen är Temp-katalogen. |
   | Skriv lager till | Obligatoriskt. Katalogen som terränglagren ska skrivas ut till. Detta är vanligtvis underkatalogen Maps i en profilkatalog, så att [!DNL Globe] kan hitta lagren. |

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och klicka på **[!UICONTROL Save]**.

1. Om du vill spara uppdaterad fil på data workbench-serverdatorn går du till [!DNL Server Files Manager], högerklicka på bockmarkeringen för [!DNL Terrain Images.cfg] i [!DNL Temp] kolumn och klicka sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
