---
description: Du måste konfigurera målservern/målservrarna för Insight för att hämta data från den repeater där de ursprungliga händelsedata lagras.
solution: Insight
title: Konfigurerar replikeringstjänsten
uuid: 93931b1d-d1fd-4e98-aa88-f7962eea92a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurerar replikeringstjänsten{#configuring-the-replication-service}

Du måste konfigurera målservern/målservrarna för Insight för att hämta data från den repeater där de ursprungliga händelsedata lagras.

Om du vill konfigurera hämtning av data från ett mål [!DNL Repeater] till ett mål [!DNL Insight Server]måste du redigera den [!DNL Replicate.cfg] fil som finns i [!DNL Components] mappen på målet [!DNL Insight Server(s)] enligt följande procedur:

**Konfigurera[!DNL Replication Service]på måldatorn**

1. Öppna arbetsytan Serverhanteraren genom att klicka på [!DNL Insight]miniatyrbilden på [!DNL Admin] > [!DNL Dataset and Profile] **[!UICONTROL Servers Manager]** -fliken.
1. Högerklicka på ikonen för det mål [!DNL Insight Server] du vill konfigurera och klicka på **[!UICONTROL Server Files]**.
1. Klicka på [!DNL Server Files Manager]för **[!UICONTROL Components]** att visa innehållet. Filen finns i den här [!DNL Replicate.cfg] katalogen.
1. Högerklicka på bockmarkeringen i kolumnen *Servernamn* för [!DNL Replicate.cfg] och klicka på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Replicate.cfg].
1. Högerklicka på den nya bockmarkeringen i [!DNL Temp] kolumnen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Fönstret [!DNL Replicate.cfg] öppnas.
1. Klicka i [!DNL Replicate.cfg] fönstret **[!UICONTROL Replicate.cfg]** och sedan **[!UICONTROL component]** för att visa innehållet.
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
      <td colname="col2"> <p>De kataloger på <span class="wintitle"> Repeater</span> som ska kopieras (replikeras) till <span class="keyword"> Insight Server</span>. Med <span class="wintitle"> replikeringstjänsten</span> kan du replikera flera kataloger från en enda <span class="wintitle"> repeater</span>. </p> <p>Om du vill lägga till en ny katalog högerklickar du på <span class="uicontrol"> Kataloger</span> och klickar på <span class="uicontrol"> Lägg till ny</span> &gt; <span class="uicontrol"> Katalog</span>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Förenkla banor </td> 
      <td colname="col2"> <p>Sant eller falskt. Den åtgärd som definieras av den här parameterns inställning beror på inställningen för parametern Recursive i den här filen: 
      <ul id="ul_D4BF3C22FBEF41C290ED938EB57E0F27">
      <li id="li_CB85E5AF9E1B4441AA38C2DB8D4F1800">Om Rekursiv är false har Förenkla banor ingen effekt. Endast filerna på den översta nivån i katalogen som anges av parametern Fjärr-URI replikeras. </li>
      <li id="li_8FDB351102344E3995035557445354BB">Om Rekursiv är true och Förenkla banor är false dupliceras katalogstrukturen för fjärrkatalogen (<span class="wintitle"> Repeater</span>) exakt i den lokala sökvägen på <span class="keyword"> målservern</span>. </li>
      <li id="li_3114B191C73744658799E112C61AB004">Om både Rekursiv och Förenkla banor är true skapas inga underkataloger i den lokala sökvägen. I stället placeras alla filer från fjärrkatalogträdet på den översta nivån i den lokala katalogen. </li>
      </ul></p> <p> <p>Obs! Om både Förenkla banor och Rekursiv är true och filer i de olika underkatalogerna på fjärrdatorn har samma namn, kan <span class="wintitle"> replikeringstjänsten</span> stoppas eller andra odefinierade beteenden inträffa. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Lokal sökväg </td> 
      <td colname="col2">Lagringsplatsen för de filer som hämtats från <span class="wintitle"> Repeater</span>. Sökvägen är relativ till installationskatalogen för <span class="keyword"> Insight Server</span> . </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rekursiv </td> 
      <td colname="col2"> Sant eller falskt. Om värdet är false replikeras bara de filer på den översta nivån i katalogen som anges av parametern Fjärr-URI. Se Förenkla banor i den här tabellen. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fjärr-URI </td> 
      <td colname="col2">URI:n, inklusive en filmask, för åtkomst till <span class="wintitle"> Repeaters</span> filarkiv. Filen <span class="filepath"> Communications.cfg</span> på <span class="wintitle"> Repeater</span> bör konfigureras så att händelsedata kan nås med denna URI. Se <a href="../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440"> Övervaka händelsens datautrymme</a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Server </td> 
      <td colname="col2">Parametrar för den <span class="wintitle"> Repeater</span> som <span class="keyword"> målservern</span> hämtar händelsedatafiler från. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Namn </td> 
      <td colname="col2">Valfritt. Namnet som ska identifiera <span class="wintitle"> Repeater</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-serverns namn </td> 
      <td colname="col2">Krävs endast om Använd SSL är inställt på true. Gemensamt namn på den <span class="wintitle"> Repeater</span> som händelsedata lagras på. Det här namnet måste matcha det vanliga namnet som anges i kommunikationscertifikatet för datorn. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Adress </td> 
      <td colname="col2">Värdnamn eller numerisk IP-adress för den <span class="wintitle"> Repeater</span> där händelsedata lagras. Serverns namn är inte en giltig post. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Port </td> 
      <td colname="col2"> Port som används för dataöverföring. Standardporten är 80. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> SSL-klientcertifikat </td> 
      <td colname="col2">Krävs endast om Använd SSL är inställt på true. Namnet på det licenscertifikat som används för att ansluta till <span class="wintitle"> Repeater</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Använd SSL </td> 
      <td colname="col2"> <p>Avgör om SSL används för dataöverföringen. Alternativen är true eller false och standardvärdet är false. </p> <p> <p>Obs! Du bör inte använda SSL eftersom det kan påverka prestandan negativt. Observera att SSL inte krävs om inte nätverket som ansluter <span class="wintitle"> Repeater</span> till måldatorerna är osäkert. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Sluttid, starttid </td> 
      <td colname="col2"> <p>(Valfritt) Begränsar uppsättningen händelsedatafiler som kopieras till mål- <span class="keyword"> Insight-servern</span> till de som innehåller data i det intervall som definieras av Start-tid och Sluttid. Om Starttid anges kopieras inte händelsedatafiler där alla loggposter kommer från tidigare än den angivna starttiden. Om Sluttid anges kopieras inte händelsedatafiler där alla loggposter från den angivna tiden eller senare inte. Om endast en del av data i en fil finns i det angivna intervallet kopieras hela filen till måldatorn. </p> <p>Adobe rekommenderar att du använder något av följande format för tillfället: 
      <ul id="ul_AE15A159A4C043398B37AD56FDFD9DCA">
      <li id="li_4DEF0F13D13E43E39CBD1A0F32765F32">1 januari 2013 HH:MM:SS EDT </li>
      <li id="li_E3275312E93D4C1FAA028543DC21B51A">1 januari 2013 HH:MM:SS GMT </li>
      </ul></p> <p> <p>Obs! Du måste ange en tidszon. Tidszonen får inte standardvärdet för systemtid om den inte anges. Om du vill implementera en policy för sommartid eller liknande policy för ändring av klockslag, måste du spara <span class="filepath"> .dst</span> -filen som innehåller rätt regler i Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server</span> -datorn. En lista med förkortningar av tidszoner som stöds och information om hur du implementerar sommartid finns i <a href="../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Tidszonskoder</a>. </p> </p> <p> <p>Obs!  Om du vill använda de här inställningarna måste namnen på händelsedatafilerna börja med ett ISO-datum (ÅÅÅÅMMDD) och varje fil måste innehålla data för 24-timmarsperioden som börjar kl. 12.00 GMT det datumet. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Spara ändringarna på servern genom att göra följande:

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.
   1. I [!DNL Server Files Manager]högerklickar du på bockmarkeringen för filen i [!DNL Temp] kolumnen och väljer **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

<!-- <a id="example_A60DE2383CA341DCB512E52DE76ADA89"></a> -->

I det här exemplet visas hur filer kopieras om parametrarna Förenkla banor och Rekursiv är inställda på true.

Anta att fjärr-URI är [!DNL /RemoteRoot/] och att den lokala sökvägen är [!DNL E:\LocalRoot\]. På fjärrdatorn ( [!DNL Repeater]) är filerna ordnade på följande sätt:

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
>Om filer i de olika underkatalogerna på fjärrdatorn har samma namn kan det hända att filerna [!DNL Replication Service] stoppas eller att andra odefinierade beteenden inträffar.
