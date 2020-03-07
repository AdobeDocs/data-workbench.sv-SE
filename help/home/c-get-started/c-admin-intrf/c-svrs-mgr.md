---
description: Det verktyg som i första hand används av systemadministratörer är Serverhanteraren.
solution: Analytics
title: Serverhanteraren
topic: Data workbench
uuid: 96c8f060-ffd4-46b9-b039-b2ac024400b6
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Serverhanteraren{#servers-manager}

Det verktyg som i första hand används av systemadministratörer är Serverhanteraren.

Det är huvudgränssnittet för att fastställa den övergripande systemstatusen och för att utföra systemkonfiguration, filhantering och felövervakning.

Serverhanteraren visar en färgad punkt (nod) för varje Data Workbench-server och [!DNL Sensor] installation i ditt system och ger snabb systemstatus för varje installation. Den visar också en nod för Data Workbench-installationen.

Gröna noder representerar aktiva anslutningar, röda noder representerar anslutningar som är inaktiverade eller på annat sätt oåtkomliga och grå noder representerar anslutningar vars lägen inte är bestämda.

![](assets/vis_SysStat_RedGreenDots.png)

Högerklicka på en nod om du vill visa information om den anslutna komponenten och få tillgång till alla relaterade menyer.

Följande tabeller beskriver den information som ges när du högerklickar på en nod för Data Workbench, Data Workbench-servern (inklusive en huvud-Data Workbench-server i ett kluster) eller [!DNL Sensor].

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
   <td colname="col2"> <p>IP-adress till Data Workbench-datorn. </p> <p>Exempel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurera </p> </td> 
   <td colname="col2"> <p>En länk till din <span class="keyword"> Data Workbenchs </span> konfigurationsfil. Klicka på <span class="uicontrol"> Konfigurera </span> &gt; <span class="uicontrol"> Insight.cfg </span> för att visa konfigurationsfönstret för Data Workbench. Alla ändringar du gör och sparar i det här fönstret återspeglas i <span class="filepath"> filen Insight.cfg </span> i installationskatalogen för Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Produkt </p> </td> 
   <td colname="col2"> <p>Produktnamn, version och build-nummer. </p> <p>Exempel: Data Workbench-server 5.3 (0000001) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CN </p> </td> 
   <td colname="col2"> <p>Det vanliga namnet på Data Workbench-serverdatorn. </p> <p>Exempel: <span class="filepath"> myserver1.mycompany.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adress </p> </td> 
   <td colname="col2"> <p>IP-adressen eller det fullständiga domännamnet för servern enligt konfigurationen i adressfilen på datorn och parametern Nätverksplats i <span class="filepath"> Insight.cfg- </span> filen. </p> <p>Exempel: 100.0.0.1 </p> <p>Mer information om filen Addresses finns i <i>Server Products Installation and Administration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Aktuell status för Data Workbench-servern. Det här fältet visas som OK när Data Workbench-servern körs som vanligt. Om ett fel har inträffat och Data Workbench-servernoden är röd, visas felet i fältet (till exempel "403 Ej tillåtet"). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detaljerad status </p> </td> 
   <td colname="col2"> <p>En länk till <span class="keyword"> Data Workbench-serverns </span> detaljerade statusgränssnitt, <span class="wintitle"> </span> som är användbart för felsökning av fel eller andra problem med Data Workbench-servern. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> Gränssnittet</a>Detaljerad status. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fjärrskrivbord </p> </td> 
   <td colname="col2"> <p>Öppnar en <span class="wintitle"> fjärrskrivbordssession </span> på Data Workbench-serverdatorn. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> alternativet Fjärrskrivbord </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverfiler </p> </td> 
   <td colname="col2"> <p>En länk till <span class="wintitle"> Serverfilshanteraren </span>som visar katalogerna och filerna i Data Workbench-serverns installationskatalog. </p> <p>Mer information finns i <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Serverfilshanteraren </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serverövervakare </p> </td> 
   <td colname="col2"> <p>En länk till <span class="wintitle"> Server Monitor- </span> gränssnittet, som är användbart för felsökning och spårning av prestandaparametrar. </p> <p>Mer information finns i Gränssnitt <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> för serverövervakning </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Relaterade servrar </p> </td> 
   <td colname="col2"> <p>Endast för Data Workbench-serverkluster. </p> <p>En meny som visar de vanliga namnen på datorerna som anges i *.address- <span class="filepath"> filen för huvud- </span> Data Workbench-servern. Den här listan innehåller vanligtvis alla bearbetade Data Workbench- <span class="keyword"> servrar </span> i klustret. Den här menyn visas bara om Data Workbench har en kopia av *.address- <span class="filepath"> filen för den överordnade Data Workbench- </span> servern. </p> <p>När du klickar på <span class="uicontrol"> Relaterade servrar </span>kan du antingen klicka på: 
     <ul id="ul_3B28B8579B1945FD80669EDFDFDA84A6"> 
      <li id="li_90094B46CB304C179136BB75FF0D6DBD"> <span class="uicontrol"> Lista över serverövervakare </span>som visar <span class="wintitle"> Server Monitor- </span> gränssnittet med information om alla relaterade servrar </li> 
      <li id="li_CD6FF5BB52874ABCB536C2DE2376587A">Det vanliga namnet på en Data Workbench-server, som visar en snabbmeny där du kan öppna något av följande för den aktuella servern: 
       <ul id="ul_928510D1DE68471583F2EE7547AEB824"> 
        <li id="li_8399338137354A59B9B4D24AF7EEE868"> <span class="uicontrol"> Detaljerad status </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/c-det-stat-interf.md"> det detaljerade statusgränssnittet </a>. </li> 
        <li id="li_0FE569C56B3F4583BC1F3DF3B4F55765"> <span class="uicontrol"> Fjärrskrivbord </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/t-rmt-dsktp-opt.md#task-dc0bdb4630474a17af67b931bc22d9ef"> alternativet Fjärrskrivbord </a>. </li> 
        <li id="li_2B6F8419CB5945C9B411F6A7C2C859FF"> <span class="uicontrol"> Hanteraren för serverfiler </span>. Se <a href="../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4"> Serverfilshanteraren </a>. </li> 
        <li id="li_F22F974EB4DE4F0F93623AE98C7DCEBC"> <span class="uicontrol"> Serverövervakaren </span>. Se gränssnittet <a href="../../../home/c-get-started/c-admin-intrf/c-svr-mtr-intfc.md#concept-3bea7441de20409585e63060d5489f45"> för serverövervakning </a>. </li> 
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
   <td colname="col2"> Det <span class="wintitle"> sensor- </span> ID som anges i <span class="wintitle"> sensorkonfigurationsfilen </span> för den här installationen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>IP </p> </td> 
   <td colname="col2"> <p>IP-adress till den webb- eller programserver där <span class="wintitle"> Sensor </span> är installerat. </p> <p>Exempel: 100.0.0.1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p>Process-ID som tilldelats av operativsystemet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL </p> </td> 
   <td colname="col2"> <p>Om <span class="wintitle"> Sensor </span> och Data Workbench-servern kommunicerar med SSL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tid </p> </td> 
   <td colname="col2"> <p>Tid (HH:MM:SS) som <span class="wintitle"> sensorn </span> senast upprättade en anslutning till Data Workbench-servern. </p> </td> 
  </tr> 
 </tbody> 
</table>
