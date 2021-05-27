---
description: Instruktioner för att konfigurera kommunikation för Insight Server eller Repeater.
title: Inställningar för kommunikationskonfiguration
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# Inställningar för kommunikationskonfiguration{#communications-configuration-settings}

Instruktioner för att konfigurera kommunikation för Insight Server eller Repeater.

Slutför parametrarna i följande fil:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Kontakta Adobe innan du ändrar några parametrar som inte finns med i tabellen.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Åtkomstkontrollfil </td> 
   <td colname="col2"> <p>Sökväg till filen <span class="filepath"> Access Control.cfg </span>. Standardplatsen är mappen <span class="filepath"> Access Control </span> i installationskatalogen för <span class="keyword"> Insight Server </span> eller <span class="wintitle"> Repeater </span>. </p> <p>Exempel: <code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Åtkomstloggkatalog </td> 
   <td colname="col2"> <p>Mappen som du vill mappa granskningsloggarna till. </p> <p>Exempel: <code>Access Log Directory = string: Audit\\</code> </p> <p> <p>Obs!  Du kan mappa granskningsloggar till en annan lokal enhet (exempel: <span class="filepath"> sträng: P:\\Audit\\ </span>), men mappa inte granskningsloggar till en nätverksenhet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utförlig åtkomstlogg </td> 
   <td colname="col2"> Den här parametern kan anges till true eller false. Den används för att aktivera och inaktivera granskningsloggsfiltrering. Om du vill vara säker på att alla begäranden loggas anger du parametern till True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP-gränssnitt </td> 
   <td colname="col2"> <p>IP-adress som ska användas när två nätverkskort är tillgängliga för åtkomst till två olika nätverk. </p> <p>Exempel: <code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Icke-säker (HTTP) port som <span class="keyword"> Insight Server </span> eller <span class="wintitle"> Repeater </span> lyssnar på. Standardporten är 80. Om du anger värdet 0 inaktiveras anslutningar som inte är säkra. </p> <p>Exempel: <code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-cifer </td> 
   <td colname="col2"> I vissa miljöer krävs bättre kommunikationssäkerhet än i andra. Om du vill använda en viss SSL-chiffersvit kan du ange den med den här parametern. <p>Exempel: <code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-port </td> 
   <td colname="col2"> <p>Säker port (via SSL) på vilken <span class="keyword"> Insight Server </span> eller <span class="wintitle"> Repeater </span> lyssnar. Standardporten är 443. Om du anger värdet 0 inaktiveras säkra anslutningar. </p> <p>Exempel: <span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Rubrik för loggningsserverinställningar. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Kundnamn </td> 
   <td colname="col2"> <p>Kundnamn som ska visas för ospecificerade kunder i administrativa aviseringar, som i följande exempel: </p> <p>"Inga data har tagits emot från sensor XYZ för kunden 'Ospecificerad' i 15." </p> <p>Exempel: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>I exemplet ovan skulle administrativa varningar för ospecificerade kunder nu ha följande lydelse: </p> <p>"Inga data har tagits emot från sensor XYZ för kunden"CompanyAB" i 15." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Lokal sökväg = sträng: Loggar\\ </p> </td> 
   <td colname="col2"> <p>Mappen där du vill lagra loggfilerna. </p> <p>Exempel: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>För att kunna komma åt den här mappen från <span class="wintitle">-serverfilshanteraren </span> måste platsen som anges i den här parametern matcha platsen som du anger i parametern Loggsökvägar i filen <span class="filepath"> Log Processing.cfg </span>. Mer information om hur du ändrar loggkatalogen i filen <span class="filepath"> Log Processing.cfg </span> finns i kapitlet om konfigurationsfil för loggbearbetning i <i>konfigurationsguiden för datauppsättningar</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Lokal sökväg = sträng: Granskning\\ </p> </td> 
   <td colname="col2"> <p>Mappen som du vill mappa granskningsloggarna till. </p> <p>Exempel: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Obs!  <p>Du kan mappa granskningsloggar till en annan lokal enhet (exempel: <span class="filepath"> sträng: P:\\Audit\\ </span>), men mappa inte granskningsloggar till en nätverksenhet. </p> <p>Om du vill kunna komma åt den här mappen från <span class="wintitle"> Server Files Manager </span> måste platsen som anges i den här parametern matcha platsen som du har i parametern Åtkomstloggkatalog i den här filen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>Den här parametern gäller bara för <span class="keyword"> Insight Server </span>. </p> <p>Mer information om hur du anger den centraliserade normaliseringsservern för ditt <span class="keyword"> Insight Server </span>-kluster finns i kapitlet om konfigurationsfil för loggbearbetning i <i>konfigurationsguiden för datauppsättningar</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = sträng: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>Den här parametern gäller bara för <span class="keyword"> Insight Server </span>. </p> <p>Gör att du kan visa <span class="keyword">-rapportens </span>-status i gränssnittet Detaljerad status för <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
