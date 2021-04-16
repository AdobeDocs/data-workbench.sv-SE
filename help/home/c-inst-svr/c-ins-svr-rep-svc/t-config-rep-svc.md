---
description: Du måste konfigurera målservern/målservrarna för Insight för att hämta data från den repeater där de ursprungliga händelsedata lagras.
title: Konfigurerar replikeringstjänsten
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
exl-id: ae189089-fd5d-41cb-ad10-2b8c2032dafc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 0%

---

# Konfigurerar replikeringstjänsten{#configuring-the-replication-service}

Du måste konfigurera målservern/målservrarna för Insight för att hämta data från den repeater där de ursprungliga händelsedata lagras.

Om du vill konfigurera hämtning av data från en [!DNL Repeater] till ett mål [!DNL Insight Server] måste du redigera [!DNL Replicate.cfg]-filen som finns i mappen [!DNL Components] på målet [!DNL Insight Server(s)] enligt följande procedur:

**Konfigurera  [!DNL Replication Service] på måldatorn**

1. I [!DNL Insight], på fliken [!DNL Admin] > [!DNL Dataset and Profile], klickar du på miniatyrbilden för **[!UICONTROL Servers Manager]** för att öppna arbetsytan Serverhanteraren.
1. Högerklicka på ikonen för målet [!DNL Insight Server] som du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. Klicka på **[!UICONTROL Components]** i [!DNL Server Files Manager] för att visa innehållet. Filen [!DNL Replicate.cfg] finns i den här katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *servernamn* för [!DNL Replicate.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Replicate.cfg].
1. Högerklicka på den nya bockmarkeringen i kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL Replicate.cfg] öppnas.
1. Klicka på **[!UICONTROL Replicate.cfg]** i fönstret [!DNL Replicate.cfg] och **[!UICONTROL component]** för att visa innehållet.
1. Redigera parametrarna med följande exempel och tabell som stödlinjer:

   ![Steginformation](assets/cfg_ReplicateFile.png)

   <table id="table_F32D4BFA2D834BBB81DF8F84417CA969"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> För den här parametern.. </th> 
      <th colname="col2" class="entry"> Ange... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Kataloger </td> 
      <td colname="col2"> <p>Kataloger på <span class="wintitle"> Repeater</span> som ska kopieras (replikeras) till målet <span class="keyword"> Insight Server</span>. Med <span class="wintitle">-replikeringstjänsten</span> kan du replikera flera kataloger från en enda <span class="wintitle">-repeater</span>. </p> <p>Om du vill lägga till en ny katalog högerklickar du på <span class="uicontrol"> Kataloger</span> och klickar på <span class="uicontrol"> Lägg till ny</span> &gt; <span class="uicontrol"> Katalog</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Förenkla banor </td> 
      <td colname="col2"> <p>Sant eller falskt. Den åtgärd som definieras av den här parameterns inställning beror på inställningen för parametern Recursive i den här filen: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Om Rekursiv är false har Förenkla banor ingen effekt. Endast filerna på den översta nivån i katalogen som anges av parametern Fjärr-URI replikeras. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Om Rekursiv är true och Förenkla sökvägar är false dupliceras katalogstrukturen för fjärrkatalogen (<span class="wintitle"> Repeater</span>) exakt i den lokala sökvägen på målet <span class="keyword"> Insight Server</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Om både Rekursiv och Förenkla banor är true skapas inga underkataloger i den lokala sökvägen. I stället placeras alla filer från fjärrkatalogträdet på den översta nivån i den lokala katalogen. </li>
      </ul></p> <p> <p>Obs! Om både Förenkla banor och Rekursiv är true och filer i de olika underkatalogerna på fjärrdatorn har samma namn, kan <span class="wintitle">-replikeringstjänsten</span> sluta eller andra odefinierade beteenden inträffa. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Lokal sökväg </td> 
      <td colname="col2">Lagringsplatsen för de filer som hämtats från <span class="wintitle"> Repeater</span>. Sökvägen är relativ till installationskatalogen för <span class="keyword"> Insight Server</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rekursiv </td> 
      <td colname="col2"> Sant eller falskt. Om värdet är false replikeras bara de filer på den översta nivån i katalogen som anges av parametern Fjärr-URI. Se Förenkla banor i den här tabellen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fjärr-URI </td> 
      <td colname="col2">URI:n, inklusive en filmask, för åtkomst till <span class="wintitle"> Repeaters</span>-filarkiv. Filen <span class="filepath"> Communications.cfg</span> på <span class="wintitle"> Repeater</span> bör konfigureras så att händelsedata kan nås med denna URI. Se <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Övervaka händelsens datautrymme</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parametrar för den <span class="wintitle"> upprepare</span> som målet <span class="keyword"> Insight Server</span> hämtar händelsedatafiler från. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Namn </td> 
      <td colname="col2">Valfritt. Namnet som ska identifiera <span class="wintitle">-uppreparen</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-serverns namn </td> 
      <td colname="col2">Krävs endast om Använd SSL är inställt på true. Gemensamt namn på den <span class="wintitle"> upprepare</span> som händelsedata lagras på. Det här namnet måste matcha det vanliga namnet som anges i kommunikationscertifikatet för datorn. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adress </td> 
      <td colname="col2">Värdnamn eller numerisk IP-adress för den <span class="wintitle"> repeater</span> som händelsedata lagras på. Serverns namn är inte en giltig post. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Port som används för dataöverföring. Standardporten är 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-klientcertifikat </td> 
      <td colname="col2">Krävs endast om Använd SSL är inställt på true. Namnet på det licenscertifikat som används för att ansluta till <span class="wintitle">-upprepade</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Använd SSL </td> 
      <td colname="col2"> <p>Avgör om SSL används för dataöverföringen. Alternativen är true eller false och standardvärdet är false. </p> <p> <p>Obs! Du bör inte använda SSL eftersom det kan påverka prestandan negativt. Observera att SSL inte krävs om inte nätverket som ansluter <span class="wintitle">-repliken</span> till måldatorerna är osäkert. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Sluttid, starttid </td> 
      <td colname="col2"> <p>(Valfritt) Begränsar uppsättningen händelsedatafiler som kopieras till målet <span class="keyword"> Insight Server</span> till de som innehåller data i det intervall som definieras av Starttid och Sluttid. Om Starttid anges kopieras inte händelsedatafiler där alla loggposter kommer från tidigare än den angivna starttiden. Om Sluttid anges kopieras inte händelsedatafiler där alla loggposter från den angivna tiden eller senare inte. Om endast en del av data i en fil finns i det angivna intervallet kopieras hela filen till måldatorn. </p> <p>Adobe rekommenderar att du använder något av följande format för tillfället: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 januari 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 januari 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Obs! Du måste ange en tidszon. Tidszonen får inte standardvärdet för systemtid om den inte anges. Om du vill implementera sommartid eller en liknande princip för ändring av klockslag måste du spara filen <span class="filepath">.dst</span> som innehåller rätt regler i Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span>-datorn. En lista med förkortningar av tidszoner som stöds och information om hur du implementerar sommartid finns i <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Tidszonskoder</a>. </p> </p> <p> <p>Obs!  Om du vill använda de här inställningarna måste namnen på händelsedatafilerna börja med ett ISO-datum (ÅÅÅÅMMDD) och varje fil måste innehålla data för 24-timmarsperioden som börjar kl. 12.00 GMT det datumet. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.
   1. I [!DNL Server Files Manager] högerklickar du på bockmarkeringen för filen i kolumnen [!DNL Temp] och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

I det här exemplet visas hur filer kopieras om parametrarna Förenkla banor och Rekursiv är inställda på true.

Anta att fjärr-URI är [!DNL /RemoteRoot/] och den lokala sökvägen är [!DNL E:\LocalRoot\]. På fjärrdatorn ( [!DNL Repeater]) ordnas filerna så här:

* [!DNL /RemoteRoot/fileA.txt]
* [!DNL /RemoteRoot/Dir1/fileB.txt]
* [!DNL /RemoteRoot/Dir2/Subdir3/fileC.txt]

När replikeringen är klar har den lokala katalogen följande filer:

* [!DNL E:\LocalRoot\fileA.txt]
* [!DNL E:\LocalRoot\fileB.txt]
* [!DNL E:\LocalRoot\fileC.txt]

I den lokala katalogen skapas inga underkataloger och alla filer från fjärrkatalogträdet placeras på den översta nivån i den lokala katalogen.

>[!NOTE]
>
>Om filer i de olika underkatalogerna på fjärrdatorn har samma namn kan [!DNL Replication Service] sluta eller något annat odefinierat beteende inträffa.
