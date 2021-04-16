---
description: Datauppsättningskonfigurationen avser processen att redigera de konfigurationsfiler vars parametrar innehåller reglerna för datauppsättningens konstruktion.
title: Om datauppsättningskonfiguration
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# Om datauppsättningskonfiguration{#understanding-dataset-configuration}

Datauppsättningskonfigurationen avser processen att redigera de konfigurationsfiler vars parametrar innehåller reglerna för datauppsättningens konstruktion.

Den konstruerade datauppsättningen finns fysiskt i den [!DNL temp.db]-fil som lagras på data workbench-serverdatorn, men konfigurationsfilerna för datauppsättningen finns i en katalog för en profil. En profil innehåller en uppsättning konfigurationsfiler som konstruerar en datauppsättning (inklusive dess utökade mått) för ett specifikt analyssyfte. Dessutom innehåller en profil definitioner av enheter som mått, härledda dimensioner, arbetsytor, rapporter och visualiseringar som gör att analytiker kan interagera med datauppsättningen och få information från den.

Den profil vars datauppsättningskonfigurationsfiler du redigerar kallas för din datauppsättningsprofil. En datauppsättningsprofil refererar till flera ärvda profiler, som kan vara vilka profiler som helst som du skapar och underhåller så att du kan konfigurera ditt Adobe-program så att det passar dina analysbehov bäst. En datauppsättningsprofil kan också referera till interna profiler som medföljer ditt Adobe-program för att utgöra grunden för alla funktioner som finns i ditt program.

Mer information om de olika profiltyperna som är tillgängliga för Adobe-program finns i *Datans Workbench användarhandbok*.

<!--
c_req_config_files.xml
-->

En datauppsättningsprofil för ett Adobe-program måste innehålla följande konfigurationsfiler på Insight Server-datorn:

* **Profile.cfg:** Visar de ärvda profilerna och bearbetningsservrarna för profilen. Bearbetningsservrar är Insight Server-DPU:er som bearbetar data för profilen. Om du har installerat ett Insight Server-kluster kan du ange att flera Insight Server-datorer ska köra en enda profil.

   Instruktioner om hur du lägger till ärvda profiler i en datauppsättningsprofils [!DNL Profile.cfg]-fil finns i *Installations- och administrationshandbok för serverprodukter*. Information om hur du installerar ett Insight Server-kluster eller konfigurerar en datauppsättningsprofil som ska köras på ett Insight Server-kluster finns i *handboken Server Products Installation and Administration*.

* **DataSet\Log Processing.cfg:** Controls the log processing phase of the data set building process. Se [Loggbearbetning](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Mer information om filen [!DNL Log Processing.cfg] finns i [Loggbearbetningskonfigurationsfil](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **Dataset\Transformation.cfg:** Styr omformningsfasen i datauppsättningsprocessen. Se [Omvandling](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). Filen [!DNL Transformation.cfg] konfigurerar vanligtvis datauppsättningen för profilspecifik analys. Mer information om filen [!DNL Transformation.cfg] finns i [Transformation Configuration File](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **Datauppsättningen innehåller filer:** En  [!DNL dataset include] fil innehåller en deluppsättning av parametrarna i datauppsättningsprofilen  [!DNL Log Processing.cfg] eller  [!DNL Transformation.cfg] filen, men lagras och hanteras i en ärvd profil. [!DNL Dataset include] filer kompletterar de viktigaste datauppsättningskonfigurationsfilerna. Mer information finns i [Inkludera datauppsättningar](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Den datauppsättningsprofil som du får när du implementerar ditt Adobe-program innehåller en uppsättning datauppsättningskonfigurationsfiler som du kan öppna, redigera och spara med [!DNL Profile Manager].

Mer information om [!DNL Profile Manager] finns i *användarhandboken för Insight*.

<!--
c_addl_config_files.xml
-->

Även om det inte krävs för alla datauppsättningar kan du med de här filerna styra andra aspekter av datauppsättningsprocessen:

* **Loggbehandlingsläge.cfg:** Med  [!DNL Log Processing Mode.cfg] filen kan du pausa bearbetningen av data till en datauppsättning, ange offlinekällor eller ange med vilken frekvens som data workbench-servern sparar sina tillståndsfiler. Se [Ytterligare konfigurationsfiler](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** Filen  [!DNL Server.cfg] anger standardstorleken för datacache (i byte) för data workbench-datorer som ansluter till data workbench-servern. Se [Ytterligare konfigurationsfiler](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg och Transform Mode.cfg:** De här filerna är bara tillgängliga om du har licensierat dataomvandlingsfunktionen att använda med ditt Adobe-program. Filen [!DNL Transform.cfg] innehåller de parametrar som definierar loggkällor och dataomformningar för omformningsfunktioner. De omformningar som du definierar ändrar källdata och skapar ett format som du anger. Med [!DNL Insight Transform Mode.cfg]-filen kan du pausa bearbetningen av data till en datauppsättning, ange offlinekällor eller ange den frekvens med vilken omformningsfunktionen sparar sina tillståndsfiler. Se [Omformningsfunktion](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Om du vill ha information om specifika konfigurationsuppgifter för datauppsättningar använder du tabellen nedan för att leta reda på och läsa mer om de uppgifter som är av intresse för dig:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Om du vill.. </th> 
   <th colname="col2" class="entry"> Se.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definiera loggkällor </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Loggkällor  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ta reda på vilka loggposter som matar in datauppsättningen under loggbearbetningen </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Datafilter</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Loggpostvillkor</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aktivera delning av spårnings-ID:n med stora mängder händelsedata </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Nyckeldelning</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurera en Insight Server som ska köras som en filserverenhet </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfigurera en Insight Server som ska köras som en central normaliseringsserver </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Konfigurera en filserverenhet för Insight Server  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ange den tidszon som ska användas för att skapa tidsdimensioner och göra tidskonverteringar </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Tidszoner </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gör mindre ändringar i datauppsättningens konfigurationsfiler som ingår i de interna profilerna som tillhandahålls av Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Redigera befintlig datauppsättning Inkludera filer  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ange nya fält med data som ska skickas från loggbearbetning till omvandling </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Skapar en ny datauppsättning med inkluderade filer  </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Loggbehandlings-datauppsättningen innehåller filer  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definiera omformningar </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Dataomvandlingar  </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Skapar en ny datauppsättning med inkluderade filer  </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Omvandlingsdatauppsättningen innehåller filer  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skapa utökade dimensioner </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Utökade Dimensioner  </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Skapar en ny datauppsättning med inkluderade filer  </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Omvandlingsdatauppsättningen innehåller filer  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definiera parametrar som ska användas i hela loggbearbetningen eller omvandlingen </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definiera parametrar i datauppsättningen inkluderar filer  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lär dig mer om Insight-gränssnitten som gör att du kan övervaka eller hantera din datauppsättning </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Arbeta med gränssnitt för datauppsättningskonfiguration  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dölj vissa utökade dimensioner så att de inte visas på dimensionsmenyn i Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Döljer datauppsättningskomponenter  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Åsidosätt vissa datauppsättningskonfigurationsfiler i en profil som du inte kan eller inte vill ändra </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Döljer datauppsättningskomponenter  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bearbeta datauppsättningen igen </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Ombearbetning och omformning  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
