---
description: Information om filserverenheter i Insight Server och konfigurationsprocessen för filservern.
solution: Analytics
title: Konfigurera en Data Workbench Server-filserverenhet
topic: Data workbench
uuid: ccb65952-f017-4434-b2f8-74c274450834
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Konfigurera en Data Workbench Server-filserverenhet{#configuring-a-data-workbench-server-file-server-unit}

Information om filserverenheter i Insight Server och konfigurationsprocessen för filservern.

<!--
c_abt_file_svr_units.xml
-->

Du kan konfigurera data workbench-servern (InsightServer64.exe) så att den körs som en filserverenhet (FSU) genom att slutföra parametrarna i noden **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** i [!DNL Log Processing.cfg] filen. När data workbench-servern är konfigurerad att köras som en FSU, lagras källfiler ( [!DNL .vsl] filer, textfiler eller XML-filer) som du snabbt kan komma åt på flera bearbetningsservrar (DPU). När DPU:erna i ett datameddelande serverkluster får åtkomst till FSU:n för att läsa loggfilerna delar de loggfilerna mellan dem och garanterar att samma fil inte bearbetas mer än en gång.

>[!NOTE]
>
>När du konfigurerar en FSU som betjänar ett Data Workbench-serverkluster som består av fem till tio DPU:er, bör du göra klustrets huvudserver till FSU.

Mer information om hur du installerar ett Data Workbench-serverkluster finns i *Server Products Installation and Administration Guide*.

<!--
c_file_svr_config_proc.xml
-->

Om platsen är en fjärrplats ansluter data workbench-servern som bearbetar data till den angivna fjärrdatorn för att läsa loggarna.

På den data workbench-serverdator som är avsedd att köras som FSU kan [!DNL Access Control.cfg] [!DNL Communications.cfg] filen ansluta DPU:er till FSU:n och filen mappar platsen för fjärrdatafilerna. Så här konfigurerar du en FSU:

1. Ange typ av datakälla och källans plats i filen på den [!DNL Log Processing.cfg] överordnade data-workbench-servern. Se [Ange datakälla](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. I filen på FSU:n redigerar du behörigheterna så att DPU:erna kan ansluta till FSU:n för att läsa loggdata. [!DNL Access Control.cfg] Se [Redigera behörigheter på filserverenheten](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. I [!DNL Communications.cfg] filen på FSU redigerar du inställningarna för [!DNL LoggingServer] och [!DNL FileServer] posterna för att ange platsen för loggfilerna. Se [Ange plats för loggfilerna](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Om du konfigurerar datauppsättningsprofilen så att den kan köras på ett datamängdsserverkluster måste du också göra klustrets FSU till den server där alla profilens mått skapas:
(Gäller endast data workbench-serverkluster) Lägg till poster för en &quot;normalize server&quot; i [!DNL Communications.cfg] - och [!DNL cluster.cfg] -filerna på FSU:n för att göra FSU:n till den server i klustret där alla dimensioner skapas. Se [Skapa en central normaliseringsserver för ett kluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Instruktioner om hur du konfigurerar en datauppsättningsprofil som ska bearbetas av ett Data Workbench-serverkluster finns i *Server Products Installation and Administration Guide*.

>[!NOTE]
>
>I följande anvisningar antas att alla loggfiler finns i standardkatalogen. Om du vill lagra loggar i en annan katalog eller skapa flera loggsökvägar kontaktar du Adobe Consulting Services för att diskutera din specifika konfiguration.

## Ange datakälla {#section-d2b545db7ab142ffb4be32e040395383}

När du anger fjärrdatakällor för en datauppsättning måste du ange typen av datakälla och platsen för loggfilerna på huvuddata-workbench-servern.

**Ange datakällan och dess plats**

1. Öppna [!DNL Log Processing.cfg] filen. Se [Redigera konfigurationsfilen](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)för loggbearbetning.

1. Lägg till en [!DNL Sensor], en loggfil eller en XML-datakälla. Se [Loggfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Slutför parametern Loggsökvägar. Se [Sensorfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [Loggfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)eller [XML-loggkällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Var noga med att ange en giltig URI.

1. Fyll i loggserverparametrarna som definieras i följande tabell:

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Namn som identifierar fjärrfilservern. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-serverns namn </td> 
   <td colname="col2"> <p> <span class="wintitle"> Serverns namn</span> visas på filserverns SSL-certifikat. </p> <p> Den här parametern är valfri om <span class="wintitle"> Använd SSL</span> är inställt på false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adress </td> 
   <td colname="col2"> <p>Adress till filserverdatorn. Kan lämnas tomt om <span class="wintitle"> Namn</span> matchar <span class="wintitle"> SSL-serverns namn</span>. </p> <p> Till exempel: <span class="filepath"> visual.mycompany.com</span> eller 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port som data workbench-serverdatorn kommunicerar med filservern via. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-klientcertifikat </td> 
   <td colname="col2"> Namnet på <span class="wintitle"> SSL-certifikatfilen</span> för data workbench-servern (<span class="filepath"> server_cert.pem</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd SSL </td> 
   <td colname="col2"> Sant eller falskt. True anger att filservern använder <span class="wintitle"> SSL</span>. </td> 
  </tr> 
 </tbody> 
</table>

Om en proxyserver krävs för att DPU:erna ska kunna ansluta till FSU:n måste du slutföra följande parametrar:

| Parameter | Beskrivning |
|---|---|
| Proxyadress | Adress till en proxyserver som data workbench-servern måste använda för att få åtkomst till filservern. |
| Proxylösenord | Valfritt. Lösenordet till proxyservern. |
| Proxyport | Proxyserverns port. Standardvärdet är 8080. |
| Proxyanvändarnamn | Valfritt. Användarnamnet för proxyservern. |

Följande är ett exempel på en definition [!DNL Log Server] i [!DNL Log Processing.cfg] filen. Loggkälla nr 1 är en LogFile-källa som pekar på en katalog som heter Logs (notera den URI som anges i parametern Log Paths) på datorn som heter FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Redigera behörigheter på filserverenheten {#section-b4a54b591b4e4435a728a67f194057ef}

I föregående process konfigurerade du en profil för en viss datauppsättning för att läsa loggfiler från en FSU. Nu måste du redigera behörigheterna på FSU:n för att tillåta anslutningar från de DPU:er som kör profilen. I följande steg får du hjälp med att redigera behörighetsfilen [!DNL Access Control.cfg].

**Så här redigerar du behörigheter på FSU:n**

1. Öppna filen [!DNL Server Files Manager] för den data workbench-serverdator som du konfigurerar som din FSU och klicka på **[!UICONTROL Access Control]** för att visa dess innehåll.

   Mer information om hur du öppnar och arbetar med [!DNL Server Files Manager]filen finns i *användarhandboken* för Data Workbench.

1. Klicka i [!DNL Server Files Manager] fönstret **[!UICONTROL Access Control]** för att visa dess innehåll. Filen finns i den här [!DNL Access Control.cfg] katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Access Control.cfg]och klicka sedan på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Access Control.cfg].

1. Högerklicka på den nya bockmarkeringen under [!DNL Temp] kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Klicka i [!DNL Access Control] fönstret **[!UICONTROL Access Control Groups]** för att visa dess innehåll.

1. Högerklicka på den numeriska etiketten för den sista [!DNL AccessGroup] i listan och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Ange en [!DNL Name] för den nya [!DNL AccessGroup]. Exempel: Ansluter servrar.

1. Högerklicka **[!UICONTROL Member]** under det nya [!DNL AccessGroup]och klicka sedan **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Ange IP-adressen för den Data Workbench-serverns DPU som ansluter till den här filservern.
1. Upprepa steg 4 och 5 för alla andra DPU:er för data workbench-servrar som ansluter till den här FSU:n, inklusive DPU:er för data workbench-servern i ett kluster som måste komma åt loggfilerna.
1. Högerklicka **[!UICONTROL Read-Only Access]** under det nya [!DNL AccessGroup]och klicka sedan **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Ange platsen för de lagrade loggfilerna på filserverdatorn. Använd snedstreck (/) i sökvägsspecifikationen. Standardplatsen är /Logs/.
1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

1. I [!DNL Server Files Manager] fönstret högerklickar du på bockmarkeringen för [!DNL Access Control.cfg] i [!DNL Temp] -kolumnen och klickar sedan på **[!UICONTROL Save to]** > **[!UICONTROL server name]** för att spara de lokalt gjorda ändringarna i FSU för data workbench-servern.

## Ange platsen för loggfilerna {#section-f9a649bf1b2544feb10ad8820384edb0}

Du måste redigera [!DNL Communications.cfg] filen på FSU för att ange platsen för loggfilerna.

**Ange platsen för loggfilerna**

1. Klicka i [!DNL Server Files Manager] fönstret **[!UICONTROL Components]** för att visa dess innehåll. Filen finns i den här [!DNL Communications.cfg] katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Communications.cfg]och klicka sedan på **[!UICONTROL Make Local]**. En bock visas i [!DNL Temp] kolumnen för [!DNL Communications.cfg].

1. Högerklicka på den nya bockmarkeringen under [!DNL Temp] kolumnen och klicka **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. Klicka i [!DNL Communications.cfg] fönstret **[!UICONTROL component]** för att visa dess innehåll.

1. Klicka i [!DNL Communications.cfg] fönstret **[!UICONTROL Servers]** för att visa dess innehåll. Flera servrar kan visas: Filservrar, loggningsservrar, initieringsservrar, statusservrar, skicka-servrar eller replikeringsservrar.

1. (Endast för [!DNL Sensor] loggkällor) Sök efter [!DNL LoggingServer], där [!DNL Sensor] loggfilerna som ska bearbetas av data workbench-servern skrivs, och klicka sedan på dess nummer för att visa menyn. Redigera parametern Loggkatalog så att den återspeglar loggfilernas önskade plats. Standardloggkatalogen är loggmappen i Data Workbench-serverns installationskatalog.

   Ändra inte några andra parametrar för [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Hitta den FileServer som anger platsen för loggfilerna. Det kan finnas flera filservrar under Servrar, så du kan behöva visa innehållet för många av dem (genom att klicka på servernumret) för att hitta den önskade servern.
1. Redigera parametrarna [!DNL Local Path] och URI för FileServer så att de återspeglar platsen för loggfilerna. I följande exempel visas att loggfilerna finns i mappen Logs i Data Workbench-serverns installationskatalog:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Om parametrarna [!DNL Local Path] och URI fylls i så som visas kan du komma åt loggfilerna på FSU:n från valfri data workbench-server genom att klicka [!DNL Logs] i [!DNL Server Files Manager].

1. Högerklicka **[!UICONTROL (modified)]** högst upp i konfigurationsfönstret och klicka sedan på **[!UICONTROL Save]**.

1. I [!DNL Server Files Manager] fönstret högerklickar du på bockmarkeringen för [!DNL Communications.cfg] i [!DNL Temp] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* för att spara de lokalt gjorda ändringarna i FSU:n för data workbench-servern.

## Skapa en central normaliseringsserver för ett kluster {#section-2c1f57b683f94cc193bc069e886bba28}

Om du konfigurerar datauppsättningsprofilen så att den körs på ett datalägesserverkluster bör du göra klustrets FSU till den server där alla profilens mått skapas.

Adobe rekommenderar att klustrets FSU fungerar som klusterhuvudserver och dess centraliserade normaliseringsserver.

Om du vill göra FSU till en central normaliseringsserver måste du öppna och redigera filerna [!DNL Communications.cfg] och [!DNL Cluster.cfg] filerna på FSU:n.

**Så här gör du FSU till en central normaliseringsserver**

1. Lägg till en [!DNL NormalizeServer] post i [!DNL Communications.cfg] filen på FSU:n.

   >[!NOTE]
   >
   >Om du har installerat det fullständiga versionspaketet för data workbench-servern v5.0 eller senare bör filen på din FSU redan ha en [!DNL Communications.cfg] [!DNL NormalizeServer] post. Följ stegen nedan för att bekräfta att posten finns.

   1. Öppna [!DNL Communications.cfg] filen i data workbench enligt beskrivningen i [Ange platsen för loggfilerna](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. Klicka **[!UICONTROL component]** för att visa innehållet.
   1. Högerklicka **[!UICONTROL Servers]** och klicka **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. I URI-parametern för [!DNL NormalizeServer], type [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Högerklicka **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan **[!UICONTROL Save]**.

   1. I [!DNL Server Files Manager] fönstret högerklickar du på bockmarkeringen för [!DNL Communications.cfg] i [!DNL Temp] kolumnen och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* name för att spara de lokalt gjorda ändringarna i FSU:n för data workbench-servern.

1. Definiera den centraliserade normaliseringsservern i [!DNL Cluster.cfg] filen på huvudservern i ditt Data Workbench Server-kluster.

   >[!NOTE]
   >
   >Om den FSU som du konfigurerar den centraliserade normaliseringsservern på inte är huvuddata-workbench-servern i ditt kluster, måste du lägga till IP-adresserna för DPU:erna i klustret till [!DNL Cluster Servers] åtkomstgruppen i FSU:s [!DNL Access Control.cfg] fil. Instruktioner om hur du lägger till servrar i [!DNL Cluster Servers] gruppen finns i Uppdatera åtkomstkontrollsfilen för ett kluster i *Server Products Installation and Administration Guide.*

   1. Öppna filen [!DNL Profile Manager] i datauppsättningsprofilen och klicka sedan på **[!UICONTROL Dataset]** för att visa innehållet. Filen finns i den här [!DNL Cluster.cfg] katalogen.

   1. Högerklicka på bockmarkeringen bredvid [!DNL Cluster.cfg]och klicka sedan på **[!UICONTROL Make Local]**. En bock för den här filen visas i [!DNL User] kolumnen.

   1. Högerklicka på den nya bockmarkeringen och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. Lägg till texten som är markerad i följande filfragment:

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >När du anger det vanliga namnet på FSU för parametern Gemensamt namn för SSL-servern använder FSU:n dess [!DNL .address] fil för att matcha det vanliga namnet. Mer information om [!DNL .address] filen finns i *Server Products Installation and Administration Guide*.

   1. Spara filen.
   1. I [!DNL Profile Manager]högerklickar du på bockmarkeringen för [!DNL Cluster.cfg] i [!DNL User] kolumnen och klickar sedan på **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** för att spara de lokalt gjorda ändringarna i datauppsättningsprofilen.
