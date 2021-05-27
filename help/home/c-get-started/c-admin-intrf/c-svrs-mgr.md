---
description: Det verktyg som i första hand används av systemadministratörer är Serverhanteraren.
title: Serverhanteraren
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
exl-id: e8b22d9f-3f1b-4a97-942a-85786bd3c547
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---

# Serverhanteraren{#servers-manager}

Det verktyg som i första hand används av systemadministratörer är Serverhanteraren.

Det är huvudgränssnittet för att fastställa den övergripande systemstatusen och för att utföra systemkonfiguration, filhantering och felövervakning.

Serverhanteraren visar en färgad punkt (nod) för varje Data Workbench och [!DNL Sensor]-installation i systemet och tillhandahåller snabb systemstatus för varje installation. Den visar även en nod för Datans Workbench installation.

Gröna noder representerar aktiva anslutningar, röda noder representerar anslutningar som är inaktiverade eller på annat sätt oåtkomliga och grå noder representerar anslutningar vars lägen inte är bestämda.

![](assets/vis_SysStat_RedGreenDots.png)

Högerklicka på en nod om du vill visa information om den anslutna komponenten och få tillgång till alla relaterade menyer.

I följande tabeller beskrivs den information som ges när du högerklickar på en nod för Data Workbench, Data Workbench-server (inklusive en server för överordnad Data Workbench i ett kluster) eller [!DNL Sensor].

<table id="table_C459CAAB07D34144B5BFFCCC84C2BB37"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktnamn, version och build-nummer. </p> <p>Exempel: Data Workbench 5.3 (0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adress </p> </td> 
   <td colname="col2"> <p>Datans Workbench IP-adress. </p> <p>Exempel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurera </p> </td> 
   <td colname="col2"> <p>En länk till <span class="keyword">-Datans Workbench </span>-konfigurationsfil. Klicka på <span class="uicontrol"> Konfigurera </span> &gt; <span class="uicontrol"> Insight.cfg </span> för att visa konfigurationsfönstret för Datan Workbench. Alla ändringar du gör och sparar i det här fönstret återspeglas i filen <span class="filepath"> Insight.cfg </span> i Datans Workbench installationskatalog. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktnamn, version och build-nummer. </p> <p>Exempel: Data Workbench server 5.3 (0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Datans Workbench namn. </p> <p>Exempel: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adress </p> </td> 
   <td colname="col2"> <p>IP-adressen eller det fullständiga domännamnet för servern enligt konfigurationen i adressfilen på datorn och parametern Nätverksplats i filen <span class="filepath"> Insight.cfg </span>. </p> <p>Exempel: 100.0.0.1 </p> <p>Mer information om adressfilen finns i <i>Installations- och administrationshandboken för serverprodukter</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Aktuell status för Data Workbench-servern. I det här fältet visas OK när Datan Workbench körs normalt. Om ett fel har inträffat och Datans Workbench servernod är röd, visas felet i fältet (t.ex. "403 Ej tillåtet"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detaljerad status </p> </td> 
   <td colname="col2"> <p>En länk till gränssnittet <span class="keyword"> Data Workbench </span> <span class="wintitle"> Detaljerad status </span>, som är användbart för felsökning eller andra problem med Datan Workbench. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Det detaljerade statusgränssnittet</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fjärrskrivbord </p> </td> 
   <td colname="col2"> <p>Öppnar en <span class="wintitle">-session för fjärrskrivbord </span> på Data Workbench-serverdatorn. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Alternativet Fjärrskrivbord </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverfiler </p> </td> 
   <td colname="col2"> <p>En länk till <span class="wintitle"> Server Files Manager </span>, som visar katalogerna och filerna i Data Workbench Servers installationskatalog. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Serverfilshanteraren </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverövervakare </p> </td> 
   <td colname="col2"> <p>En länk till gränssnittet <span class="wintitle"> Server Monitor </span>, som är användbart för felsökning och spårning av prestandaparametrar. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Serverövervakningsgränssnittet </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Relaterade servrar </p> </td> 
   <td colname="col2"> <p>Endast för serverkluster med Data Workbench. </p> <p>En meny som innehåller de vanliga namnen på datorerna som anges i den överordnad <span class="filepath">-Datans Workbench *.address </span>-fil. Den här listan innehåller vanligtvis alla <span class="keyword">-Data Workbench </span> som bearbetas i klustret. Den här menyn visas bara om Datan Workbench har en kopia av den överordnad <span class="filepath">-Datans Workbench *.address </span>-fil. </p> <p>När du klickar på <span class="uicontrol">-relaterade servrar </span> kan du antingen klicka på: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Lista över serverövervakare  </span>som visar information om  <span class="wintitle"> serverövervakarens  </span> gränssnitt för alla relaterade servrar </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Det vanliga namnet på en serverserver, som visar en snabbmeny där du kan öppna något av följande för Datan Workbench: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detaljerad status  </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Det detaljerade statusgränssnittet </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Fjärrskrivbord  </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> Alternativet Fjärrskrivbord </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Hanteraren för serverfiler  </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Serverfilshanteraren </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Serverövervakaren  </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> Serverövervakningsgränssnittet </a>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_5BFA0AFE2D9A4337BF04343879DAD03B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktnamn, version och build-nummer. </p> <p>Exempel: Sensor 3.76; J3.67 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> Det <span class="wintitle">-sensor </span>-ID som anges i konfigurationsfilen <span class="wintitle"> sensor </span> för den här installationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP-adress till den webb- eller programserver där <span class="wintitle"> sensor </span> är installerad. </p> <p>Exempel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>Process-ID som tilldelats av operativsystemet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Om <span class="wintitle">-sensorn </span> och Data Workbench-servern kommunicerar med SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tid </p> </td> 
   <td colname="col2"> <p>Tid (HH:MM:SS) som <span class="wintitle">-sensorn </span> senast upprättade en anslutning till Datan Workbench. </p> </td> 
  </tr> 
 </tbody> 
</table>
