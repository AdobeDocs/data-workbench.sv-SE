---
description: Inkluderingsfilen för loggbearbetningsdatauppsättning för en ärvd profil innehåller parametrar som är associerade med loggbearbetningsfasen för datauppsättningens konstruktion.
title: Loggbehandlings-datauppsättningen innehåller filer
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---

# Loggbearbetningsdatauppsättningen innehåller filer{#log-processing-dataset-include-files}

Inkluderingsfilen för loggbearbetningsdatauppsättning för en ärvd profil innehåller parametrar som är associerade med loggbearbetningsfasen för datauppsättningens konstruktion.

Den första raden i en [!DNL Log Processing Dataset Include]-fil definierar en typ [!DNL LogProcessingInclude] som stöder parametrarna Avkodargrupper, Fält, Loggpostvillkor, Parametrar, Återbearbetning, Scen och Omformningar. Alla andra parametrar för loggbearbetning måste definieras i filen [!DNL Log Processing.cfg] i datauppsättningsprofilens datauppsättningskatalog. Du kan namnge en [!DNL Log Processing Dataset Include]-fil vad du vill, men filtillägget måste vara [!DNL .cfg]. Filen måste lagras i *det ärvda profilnamnet*\Dataset\Log Processing directory. Eftersom filerna läses in rekursivt under loggbearbetningsfasen när datauppsättningen skapas, kan du lagra [!DNL Log Processing Dataset Include]-filerna på vilken nivå som helst i katalogen (till exempel *ärvt profilnamn*\Dataset\Log Processing\*mappnamn*\*inkluderingsfilnamn*.cfg).

>[!NOTE]
>
>Många webbspecifika konfigurationsparametrar för platsen definieras i [!DNL Log Processing Dataset Include]-filer. Mer information om de här parametrarna finns i [Konfigurationsinställningar för webbdata](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Avkodningsgrupper </td> 
   <td colname="col2"> <p>Krävs om du har definierat loggfiler eller XML-filloggkällor i filen <span class="filepath"> Log Processing.cfg</span>. Den textfil eller de XML-avkodare som du definierar för att extrahera datafält från loggfiler och XML-loggkällor. </p> <p> <b>Lägga till en ny avkodningsgrupp</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Högerklicka på <span class="uicontrol"> Avkodargrupp</span> och klicka på <span class="uicontrol"> Lägg till ny</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> eller <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Ange det önskade namnet på avkodningsgruppen i parametern Namn för den nya gruppen. </li> 
     </ul> </p> <p> <p>Obs!  När du anger en avkodargrupp i filen <span class="filepath"> Log Processing.cfg</span> för datauppsättningsprofilen måste namnet matcha exakt det namn du anger här. Mer information finns i <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Loggfiler</a>. </p> </p> <p> Mer information om avkodare som du kan definiera för varje grupp finns i <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Textfilavkodargrupper</a> eller <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML-avkodargrupper</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fält </td> 
   <td colname="col2"> <p>Här listas fält som definieras i <span class="wintitle"> loggkällor</span> eller <span class="wintitle"> transformeringar</span> i en <span class="wintitle"> loggbearbetningsdatauppsättningskonfiguration</span>-fil som används i transformeringar, villkor eller utökade dimensioner i en <span class="wintitle"> Transformation DataSet Configuration</span>-fil. </p> <p> Varje fält nedan måste listas i en <span class="wintitle">-loggbearbetningsdatauppsättning som innehåller</span>-fil: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Loggpostvillkor </td> 
   <td colname="col2"> <p>Valfritt. Definierar de regler som loggposter ska övervägas för att inkluderas i datauppsättningen. Se <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Loggpostvillkor</a>. </p> <p> <p>Obs!  För att kunna inkluderas i datauppsättningen måste en loggpost uppfylla villkoren <span class="wintitle"> för loggpost</span> i filen <span class="filepath"> Log Processing.cfg</span> och i varje <span class="wintitle"> loggbearbetningsdatauppsättning som innehåller</span>-fil. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametrar </td> 
   <td colname="col2"> Valfritt. En variabel som du kan referera till i andra konfigurationsparametrar. Mer information finns i <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definiera parametrar i datauppsättningen Inkludera filer</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Återbearbeta </td> 
   <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Om du ändrar den här parametern och sparar filen på data workbench-servern initieras databearbetning. </p> <p> Mer information om hur du ombearbetar data finns i <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Återbearbetning och omformning</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scen </td> 
   <td colname="col2"> <p>Valfritt. Namnet på bearbetningsfasen som gäller för den här <span class="wintitle">-loggdatauppsättningen innehåller</span>-filen. Bearbetningsfaserna definieras i parametern Stages i filen <span class="filepath"> Log Processing.cfg</span>. </p> <p> <p>Obs!  När du anger en scen måste namnet på scenen matcha exakt det namn som visas i parametern Stage i filen <span class="filepath"> Log Processing.cfg</span> för datauppsättningsprofilen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Omformningar </td> 
   <td colname="col2"> Valfritt. Definierar de dataomformningar som måste tillämpas under loggbearbetningen. Mer information om tillgängliga omformningstyper finns i <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datatransformeringar</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beskrivningar av parametrarna i filen [!DNL Log Processing.cfg] finns i [Loggbearbetningskonfigurationsfil](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Du bör tänka på följande när du arbetar med [!DNL Log Processing Dataset Include]-filer:

* Om du ändrar någon av parametrarna i den här filen måste alla data bearbetas om.
* Du kan lägga till någon av parametrarna som beskrivs ovan i [!DNL Log Processing Dataset Include]-filen genom att öppna och redigera filen i Anteckningar. Alla ändringar du gör och sparar visas när du öppnar filen på nytt i data workbench. När du lägger till en ny parameter använder du blankstegstangenten (inte tabbtangenten) för att dra in två (2) blanksteg till höger om föregående rubriknivå.
