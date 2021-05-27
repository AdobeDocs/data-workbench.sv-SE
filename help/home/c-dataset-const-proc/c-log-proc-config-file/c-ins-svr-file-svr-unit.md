---
description: Information om filserverenheter i Insight Server och konfigurationsprocessen för filservern.
title: Konfigurera en filserverenhet för Data Workbench Server
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 0%

---

# Konfigurera en filserverenhet för Data Workbench-{#configuring-a-data-workbench-server-file-server-unit}

Information om filserverenheter i Insight Server och konfigurationsprocessen för filservern.

<!--
c_abt_file_svr_units.xml
-->

Du kan konfigurera data workbench-servern (InsightServer64.exe) så att den körs som en filserverenhet (FSU) genom att slutföra parametrarna i **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]**-noden i [!DNL Log Processing.cfg]-filen. När data workbench-servern är konfigurerad att köras som en FSU, lagras källfiler ( [!DNL .vsl] filer, textfiler eller XML-filer) som du snabbt kan komma åt på flera bearbetningsservrar (DPU). När DPU:erna i ett datameddelande serverkluster får åtkomst till FSU:n för att läsa loggfilerna delar de loggfilerna mellan dem och garanterar att samma fil inte bearbetas mer än en gång.

>[!NOTE]
>
>När du konfigurerar en FSU som betjänar ett data workbench-serverkluster som består av fem till tio DPU:er, bör du göra klustrets överordnad server till FSU.

Mer information om hur du installerar ett datadrivna serverkluster finns i *handboken Installation and Administration av serverprodukter*.

<!--
c_file_svr_config_proc.xml
-->

Om platsen är en fjärrplats ansluter data workbench-servern som bearbetar data till den angivna fjärrdatorn för att läsa loggarna.

På den data workbench-server som är avsedd att köras som FSU kan DPU:erna ansluta till FSU med [!DNL Access Control.cfg]-filen och [!DNL Communications.cfg]-filen mappar platsen för fjärrdatafilerna. Så här konfigurerar du en FSU:

1. I [!DNL Log Processing.cfg]-filen på den överordnad data workbench-servern anger du typ av datakälla och källans plats. Se [Ange datakälla](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. I filen [!DNL Access Control.cfg] på FSU:n kan du redigera behörigheterna så att DPU:erna kan ansluta till FSU:n för att läsa loggdata. Se [Redigera behörigheter på filserverenheten](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. I filen [!DNL Communications.cfg] på FSU redigerar du inställningarna för posterna [!DNL LoggingServer] och [!DNL FileServer] för att ange platsen för loggfilerna. Se [Ange platsen för loggfilerna](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. Om du konfigurerar datauppsättningsprofilen så att den kan köras på ett datamängdsserverkluster måste du också göra klustrets FSU till den server där alla profilens mått skapas:
(Endast för datadrivna Workbench-serverkluster) I filerna [!DNL Communications.cfg] och [!DNL cluster.cfg] på FSU lägger du till poster för en normaliseringsserver för att göra FSU till den server i klustret där alla dimensioner skapas. Se [Skapa en central normaliseringsserver för ett kluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

Instruktioner om hur du konfigurerar en datauppsättningsprofil som ska bearbetas av ett Data Workbench-serverkluster finns i *Installations- och administrationshandboken för serverprodukter*.

>[!NOTE]
>
>I följande anvisningar antas att alla loggfiler finns i standardkatalogen. Om du vill lagra loggar i en annan katalog eller skapa flera loggsökvägar kontaktar du Adobe Consulting Services för att diskutera din konfiguration.

## Ange datakälla {#section-d2b545db7ab142ffb4be32e040395383}

När du anger fjärrdatakällor för en datauppsättning måste du ange typen av datakälla och platsen för loggfilerna på den överordnad data workbench-servern.

**Ange datakällan och dess plats**

1. Öppna filen [!DNL Log Processing.cfg]. Se [Redigera konfigurationsfilen för loggbearbetning](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. Lägg till en [!DNL Sensor]-, loggfil- eller XML-datakälla. Se [Loggfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. Slutför parametern Loggsökvägar. Se [Sensorfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [Loggfiler](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e) eller [XML-loggkällor](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). Var noga med att ange en giltig URI.

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
   <td colname="col2"> <p> <span class="wintitle"> Ett gemensamt </span> servernamn finns på filserverns SSL-certifikat. </p> <p> Den här parametern är valfri om <span class="wintitle"> Använd SSL</span> är inställd på false. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adress </td> 
   <td colname="col2"> <p>Adress till filserverdatorn. Kan lämnas tomt om <span class="wintitle"> Namn</span> matchar <span class="wintitle"> SSL-serverns namn</span>. </p> <p> Till exempel: <span class="filepath"> visual.mincompany.com</span> eller 192.168.1.90. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port som data workbench-serverdatorn kommunicerar med filservern via. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-klientcertifikat </td> 
   <td colname="col2"> Namn på <span class="wintitle"> SSL-certifikatfilen</span> för data workbench-servern (<span class="filepath"> server_cert.pem</span>). </td> 
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

Följande är ett exempel på en definierad [!DNL Log Server] i [!DNL Log Processing.cfg]-filen. Loggkälla nr 1 är en LogFile-källa som pekar på en katalog som heter Logs (notera den URI som anges i parametern Log Paths) på datorn som heter FSU01.

![](assets/cfg_LogProcessing_LogServer.png)

## Redigera behörigheter på filserverenheten {#section-b4a54b591b4e4435a728a67f194057ef}

I föregående process konfigurerade du en profil för en viss datauppsättning för att läsa loggfiler från en FSU. Nu måste du redigera behörigheterna på FSU:n för att tillåta anslutningar från de DPU:er som kör profilen. I följande steg får du hjälp med att redigera behörighetsfilen [!DNL Access Control.cfg].

**Så här redigerar du behörigheter på FSU:n**

1. Öppna [!DNL Server Files Manager] för den data workbench-serverdator som du konfigurerar som din FSU och klicka på **[!UICONTROL Access Control]** för att visa dess innehåll.

   Mer information om hur du öppnar och arbetar med [!DNL Server Files Manager] finns i *Datans Workbench användarhandbok*.

1. I fönstret [!DNL Server Files Manager] klickar du på **[!UICONTROL Access Control]** för att visa innehållet. Filen [!DNL Access Control.cfg] finns i den här katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Access Control.cfg] och klicka sedan på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Access Control.cfg].

1. Högerklicka på den nya bockmarkeringen under kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. I fönstret [!DNL Access Control] klickar du på **[!UICONTROL Access Control Groups]** för att visa innehållet.

1. Högerklicka på den numeriska etiketten för den sista [!DNL AccessGroup] i listan och klicka på **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. Ange [!DNL Name] som ny [!DNL AccessGroup]. Exempel: Ansluter servrar.

1. Högerklicka på **[!UICONTROL Member]** under den nya [!DNL AccessGroup] och klicka sedan på **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Ange IP-adressen för den Data Workbench-serverns DPU som ansluter till den här filservern.
1. Upprepa steg 4 och 5 för alla andra DPU:er för data workbench-servrar som ansluter till den här FSU:n, inklusive DPU:er för data workbench-servern i ett kluster som måste komma åt loggfilerna.
1. Högerklicka på **[!UICONTROL Read-Only Access]** under den nya [!DNL AccessGroup] och klicka sedan på **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. Ange platsen för de lagrade loggfilerna på filserverdatorn. Använd snedstreck (/) i sökvägsspecifikationen. Standardplatsen är /Logs/.
1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka sedan på **[!UICONTROL Save]**.

1. I fönstret [!DNL Server Files Manager] högerklickar du på bockmarkeringen för [!DNL Access Control.cfg] i kolumnen [!DNL Temp] och klickar sedan på **[!UICONTROL Save to]** > **[!UICONTROL server name]** för att spara de lokalt gjorda ändringarna i FSU för data workbench-servern.

## Ange platsen för loggfilerna {#section-f9a649bf1b2544feb10ad8820384edb0}

Du måste redigera filen [!DNL Communications.cfg] på FSU:n för att ange platsen för loggfilerna.

**Ange platsen för loggfilerna**

1. I fönstret [!DNL Server Files Manager] klickar du på **[!UICONTROL Components]** för att visa innehållet. Filen [!DNL Communications.cfg] finns i den här katalogen.

1. Högerklicka på bockmarkeringen i servernamnskolumnen för [!DNL Communications.cfg] och klicka sedan på **[!UICONTROL Make Local]**. En bock visas i kolumnen [!DNL Temp] för [!DNL Communications.cfg].

1. Högerklicka på den nya bockmarkeringen under kolumnen [!DNL Temp] och klicka på **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. I fönstret [!DNL Communications.cfg] klickar du på **[!UICONTROL component]** för att visa innehållet.

1. I fönstret [!DNL Communications.cfg] klickar du på **[!UICONTROL Servers]** för att visa innehållet. Flera servrar kan visas: Filservrar, loggningsservrar, initieringsservrar, statusservrar, skicka-servrar eller replikeringsservrar.

1. (Endast för [!DNL Sensor]-loggkällor) Sök efter [!DNL LoggingServer], där [!DNL Sensor] skriver sina loggfiler som ska bearbetas av data workbench-servern, och klicka sedan på dess nummer för att visa menyn. Redigera parametern Loggkatalog så att den återspeglar loggfilernas önskade plats. Standardloggkatalogen är loggmappen i Data Workbench-serverns installationskatalog.

   Ändra inga andra parametrar för [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. Hitta den FileServer som anger platsen för loggfilerna. Det kan finnas flera filservrar under Servrar, så du kan behöva visa innehållet för många av dem (genom att klicka på servernumret) för att hitta den önskade servern.
1. Redigera parametrarna [!DNL Local Path] och URI för FileServer så att de återspeglar platsen för loggfilerna. I följande exempel visas att loggfilerna finns i mappen Logs i Data Workbench-serverns installationskatalog:

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >Om parametrarna [!DNL Local Path] och URI fylls i så som visas kan du komma åt loggfilerna på FSU:n från valfri data workbench-server genom att klicka på [!DNL Logs] i [!DNL Server Files Manager].

1. Högerklicka på **[!UICONTROL (modified)]** högst upp i konfigurationsfönstret och klicka sedan på **[!UICONTROL Save]**.

1. I fönstret [!DNL Server Files Manager] högerklickar du på bockmarkeringen för [!DNL Communications.cfg] i kolumnen [!DNL Temp] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* för att spara de lokalt gjorda ändringarna i FSU för data workbench-servern.

## Skapar en central normaliseringsserver för ett kluster {#section-2c1f57b683f94cc193bc069e886bba28}

Om du konfigurerar datauppsättningsprofilen så att den körs på ett datalägesserverkluster bör du göra klustrets FSU till den server där alla profilens mått skapas.

Adobe rekommenderar starkt att klustrets FSU fungerar som klustrets överordnad server och dess centraliserade normaliseringsserver.

Om du vill göra FSU till en central normaliseringsserver måste du öppna och redigera filerna [!DNL Communications.cfg] och [!DNL Cluster.cfg] på FSU:n.

**Så här gör du FSU till en central normaliseringsserver**

1. Lägg till en [!DNL NormalizeServer]-post i [!DNL Communications.cfg]-filen på FSU:n.

   >[!NOTE]
   >
   >Om du har installerat det fullständiga versionspaketet för data workbench-servern v5.0 eller senare bör [!DNL Communications.cfg]-filen på din FSU redan ha en [!DNL NormalizeServer]-post. Följ stegen nedan för att bekräfta att posten finns.

   1. Öppna filen [!DNL Communications.cfg] i data workbench enligt beskrivningen i [Ange platsen för loggfilerna](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. Klicka på **[!UICONTROL component]** för att visa innehållet.
   1. Högerklicka på **[!UICONTROL Servers]** och klicka på **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. I URI-parametern för [!DNL NormalizeServer] skriver du [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. Högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**.

   1. I fönstret [!DNL Server Files Manager] högerklickar du på bockmarkeringen för [!DNL Communications.cfg] i kolumnen [!DNL Temp] och klickar sedan på **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* för att spara de lokalt gjorda ändringarna i FSU:n för data workbench-servern.

1. Definiera den centraliserade normaliseringsservern i [!DNL Cluster.cfg]-filen på den överordnad servern i Data Workbench Server-klustret.

   >[!NOTE]
   >
   >Om den FSU som du konfigurerar den centraliserade normaliseringsservern på inte är den överordnad data workbench-servern i ditt kluster, måste du lägga till IP-adresserna för DPU:erna i klustret i [!DNL Cluster Servers]-åtkomstgruppen i FSU:ns [!DNL Access Control.cfg]-fil. Instruktioner om hur du lägger till servrar i gruppen [!DNL Cluster Servers] finns i Uppdatera åtkomstkontrollsfilen för ett kluster i *handboken Installation and Administration av serverprodukter.*

   1. Öppna [!DNL Profile Manager] i datauppsättningsprofilen och klicka sedan på **[!UICONTROL Dataset]** för att visa innehållet. Filen [!DNL Cluster.cfg] finns i den här katalogen.

   1. Högerklicka på bockmarkeringen bredvid [!DNL Cluster.cfg] och klicka sedan på **[!UICONTROL Make Local]**. En bock för den här filen visas i kolumnen [!DNL User].

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
      >När du anger det vanliga namnet på FSU för parametern Gemensamt namn för SSL-servern använder FSU filen [!DNL .address] för att matcha det vanliga namnet. Mer information om filen [!DNL .address] finns i *Installations- och administrationshandboken för serverprodukter*.

   1. Spara filen.
   1. I [!DNL Profile Manager] högerklickar du på bockmarkeringen för [!DNL Cluster.cfg] i kolumnen [!DNL User] och klickar sedan på **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** för att spara de lokalt gjorda ändringarna i datauppsättningsprofilen.
