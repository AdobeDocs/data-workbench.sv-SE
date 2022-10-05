---
description: Åtkomstnivåer beskriver vilka URI:er på datorn som en grupp användare har behörighet att läsa eller ändra.
title: Om åtkomstnivåer
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 0%

---

# Om åtkomstnivåer{#understanding-access-levels}

{{eol}}

Åtkomstnivåer beskriver vilka URI:er på datorn som en grupp användare har behörighet att läsa eller ändra.

Följ de här riktlinjerna för att definiera åtkomstnivåer som du vill ha för användarna i din organisation:

* Specifika URI:er utan avslutande snedstreck begränsar endast åtkomsten till denna URI. Till exempel: [!DNL /Components/Communications.cfg] ger åtkomst till [!DNL Communications.cfg]endast fil.

* Ett avslutande snedstreck (/), som anger en katalog, ger gruppmedlemmarna åtkomst till alla URI:er som börjar med strängen. Med /Profiles/ får du till exempel tillgång till hela katalogen Profiler.
* Ett avslutande dollartecken ($) begränsar endast åtkomsten till den exakta URI:n, även om det är en katalog. Med /Profiles/$ kan du till exempel läsa huvudkatalogen, men inte läsa filer i den katalogen.

   Du behöver inte använda en efterföljande prenumeration på $ för att få åtkomst till specifika filer.

   Till exempel: [!DNL /Components/Communications.cfg] och [!DNL /Components/Communications.cfg$] ger samma åtkomst.

* En procentsymbol (%) kan användas med CN (Common Name) för att ge åtkomst. Till exempel /Users/%CN%/ tillåter åtkomst till användarkatalogen som matchar SSL-certifikatets vanliga namn för [!DNL Insight] användare. Observera att den här syntaxen bara kan användas en gång i en URI.

URI:erna i de fördefinierade åtkomstkontrollgrupperna har konfigurerats på följande sätt:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gruppnamn </th> 
   <th colname="col2" class="entry"> Skrivskyddad åtkomst </th> 
   <th colname="col3" class="entry"> Läs- och skrivåtkomst </th> 
   <th colname="col4" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administratörer </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Läs- och skrivbehörighet till alla <span class="keyword"> Insight Server</span> kataloger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensorer </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Läsa och skriva till de två filer som <span class="wintitle"> Sensorer</span> använda för att kommunicera med <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användare </p> </td> 
   <td colname="col2"> <p>/Profiler/ </p> <p>/Status/ </p> <p>/Programvara/ </p> <p>/Adresser/ </p> <p>/Användare/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Läs- och skrivåtkomst till användarkatalogen som matchar SSL-certifikatets vanliga namn i <span class="keyword"> Insikt</span> användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avancerade användare </p> </td> 
   <td colname="col2"> <p>/Profiler/$ </p> <p>/Status/ </p> <p>/Programvara/ </p> <p>/Adresser/ </p> <p>/Användare/$ </p> </td> 
   <td colname="col3"> <p>/Profiler/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Power Users ges samma åtkomst som Users, med möjlighet att skriva till katalogen Profiles. Dessa användare kan redigera profiler och aktivera ändringar som uppdateras automatiskt för andra <span class="keyword"> Insikt</span> -användare, till exempel vid distribution av nyligen definierade arbetsytor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klusterservrar </p> </td> 
   <td colname="col2"> <p>/Komponenter för bearbetning av servrar/ </p> <p>/Adresser/ </p> <p>/Profiler/ </p> <p>/Uppslag/ </p> <p>/Åtkomstkontroll/ </p> <p>/Bin/ </p> <p>/Loggar/ </p> </td> 
   <td colname="col3"> <p>/kluster/ </p> </td> 
   <td colname="col4"> <p>Läs- och skrivåtkomst till klusterkatalogen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapportservrar </p> </td> 
   <td colname="col2"> <p>/Profiler/$ </p> <p>/Status/ </p> <p>/Programvara/ </p> <p>/Adresser/ </p> <p>/Användare/$ </p> </td> 
   <td colname="col3"> <p>/Profiler/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Rapportdatorer har samma åtkomst som Power Users, med möjlighet att skriva till <span class="filepath"> ReportStatus.vsp</span> -fil. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Konfigurera åtkomstkontroll**

När du definierar åtkomstkontrollsgrupper måste du inkludera alla systemadministratörer, användare, klusterservrar och rapportserveranvändare som kräver åtkomst till den här [!DNL Insight Server] dator. Du kan bevilja åtkomst med hjälp av IP-adress eller SSL-certifikatinformation, till exempel det vanliga namnet eller organisationen.

>[!NOTE]
>
>När [!DNL Access Control.cfg] filen ändras på [!DNL Insight Server], avslutas alla befintliga anslutningar och tvingas att återansluta. Anslutningar kontrolleras mot behörigheterna i den uppdaterade [!DNL Access Control.cfg] -fil. I serverhanterarens gränssnitt finns [!DNL Insight Server] blir ikonen tillfälligt röd och sedan grön igen eftersom anslutningen har avbrutits och tvingats återansluta tillsammans med alla andra.

1. På [!DNL Admin] > [!DNL Dataset and Profile] klickar du på **[!UICONTROL Servers Manager]** miniatyrbild för att öppna arbetsytan Serverhanteraren.

1. Högerklicka på ikonen för [!DNL Insight Server] du vill konfigurera och klicka på **[!UICONTROL Files]**.

1. I [!DNL Server Files Manager], klicka **[!UICONTROL Access Control]** för att visa innehållet. The [!DNL Access Control.cfg] filen finns i den här katalogen.

1. Högerklicka på bockmarkeringen i dialogrutan *servernamn* kolumn för [!DNL Access Control.cfg] och klicka **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumn för [!DNL Access Control.cfg].

1. Högerklicka på den nya bockmarkeringen i dialogrutan [!DNL Temp] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. I [!DNL Access Control.cfg] fönster, klicka **[!UICONTROL Access Control Groups]** för att visa innehållet.

   ![](assets/access_ctrl_cfg.png)

1. Så här lägger du till en ny åtkomstkontrollgrupp:

   1. Högerklicka **[!UICONTROL Access Control Groups]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Högerklicka **[!UICONTROL Members]** och klicka **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Medlemmarna i standardgrupperna är inte fördefinierade. Som standard ges administratörsåtkomst till 127.0.0.1 (lokal värd) och [!DNL Sensor] IP-åtkomst beviljas:&#42;. Alla andra medlemmar i åtkomstkontrollgruppen måste definieras.

   1. Slutför parametrarna.

1. Så här lägger du till nya medlemmar i en befintlig åtkomstkontrollgrupp:

   1. Högerklicka **[!UICONTROL Members]** under lämplig åtkomstkontrollgrupp och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Spara filen genom att högerklicka **[!UICONTROL (modified)]** längst upp i fönstret och sedan klicka **[!UICONTROL Save]**.

1. Så här sparar du lokalt gjorda ändringar i [!DNL Insight Server] dator, i [!DNL Server Files Manager], högerklicka på bockmarkeringen för [!DNL Access Control.cfg] i [!DNL Temp] kolumn och klicka sedan på **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
