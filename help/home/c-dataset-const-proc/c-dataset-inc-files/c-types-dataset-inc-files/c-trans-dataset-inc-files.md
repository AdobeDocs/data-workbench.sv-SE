---
description: Inkluderingsfilen för en ärvd profil innehåller parametrar som är associerade med omformningsfasen för datauppsättningens konstruktion.
title: Omvandlingsdatauppsättningen innehåller filer
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 1%

---

# Omvandlingsdatauppsättningen innehåller filer{#transformation-dataset-include-files}

Inkluderingsfilen för en ärvd profil innehåller parametrar som är associerade med omformningsfasen för datauppsättningens konstruktion.

Den första raden i filen definierar en typ [!DNL TransformationInclude] som stöder parametrarna Extended Dimensions, Parameters, Reprocess, Stage och Transformations. Alla andra parametrar måste definieras i filen [!DNL Transformation.cfg] i datauppsättningsprofilens datauppsättningskatalog.

Om andra parametrar än Extended-Dimensioner, Parametrar, Reprocess, Stage och Transformations inkluderas i en [!DNL Transformation Dataset Include]-fil genereras fel.

Du kan namnge en [!DNL Transformation Dataset Include]-fil vad du vill, men filtillägget måste vara [!DNL .cfg]. Filen måste lagras i *det ärvda profilnamnet*\Dataset\Transformation directory. Eftersom filerna läses in rekursivt under omformningsfasen när datauppsättningen skapas kan du lagra [!DNL Transformation Dataset Include]-filerna på vilken nivå som helst i katalogen (till exempel *ärvt profilnamn*\Dataset\Transformation\*mappnamn*\*inkluderingsfilnamn*.cfg).

>[!NOTE]
>
>Många webbspecifika konfigurationsparametrar för platsen definieras i [!DNL Transformation Dataset Include]-filer. Mer information om de här parametrarna finns i [Konfigurationsinställningar för webbdata](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

I följande tabell beskrivs de parametrar som är tillgängliga i en [!DNL Transformation Dataset Include]-fil:

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Utökade Dimensioner </td> 
   <td colname="col2"> Valfritt. Definierar de utökade dimensionerna. Se <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Utökade Dimensioner</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametrar </td> 
   <td colname="col2"> Valfritt. En variabel som du kan referera till i andra konfigurationsparametrar. Mer information finns i <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definiera parametrar i datauppsättningen Inkludera filer</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Återbearbeta </td> 
   <td colname="col2"> <p>Valfritt. Här kan du ange alla tecken eller teckenkombinationer. Om du ändrar den här parametern och sparar filen initieras omformningen av data. </p> <p> Mer information om hur du ombearbetar data finns i <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Återbearbetning och omformning</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scen </td> 
   <td colname="col2"> <p>Valfritt. Namnet på bearbetningsfasen som gäller för den här <span class="wintitle">-omformningsdatauppsättningen innehåller</span>-filen. Bearbetningsfaserna definieras i parametern Stages i filen <span class="filepath"> Transformation.cfg</span>. </p> <p> <p>Obs! När du anger en scen måste namnet på scenen matcha exakt det namn som visas i parametern Stages i filen <span class="filepath"> Transformation.cfg</span> för datauppsättningsprofilen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Omformningar </td> 
   <td colname="col2"> Valfritt. Definierar de dataomformningar som måste tillämpas under omformningen. Mer information om tillgängliga omformningstyper finns i <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Datatransformeringar</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Beskrivningar av parametrarna i filen [!DNL Transformation.cfg] finns i [Transformation Configuration File](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Du bör tänka på följande när du arbetar med [!DNL Transformation Dataset Include]-filer:

* Om du ändrar någon av parametrarna i den här filen måste data omformas.
* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize]och  [!DNL AppendURI] omformningar fungerar bara när de definieras i en  [!DNL Transformation Dataset Configuration] fil. Mer information om dessa omformningar finns i [Datatransformeringar](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Du kan lägga till någon av parametrarna som beskrivs ovan i [!DNL Transformation Dataset Include]-filen genom att öppna och redigera filen i Anteckningar. Alla ändringar du gör och sparar visas när du öppnar filen på nytt i data workbench. När du lägger till en ny parameter använder du blankstegstangenten (inte tabbtangenten) för att dra in två (2) blanksteg till höger om föregående rubriknivå.

Om du prenumererar på datatjänsten Adobe [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] får du med Adobe en intern profil som består av en uppsättning dataomvandlingar och utökade dimensioner som har skapats specifikt för datatjänsten. Omformningarna och dimensionerna definieras i [!DNL Transformation Dataset Include]-filer som ingår i datauppsättningskatalogen för den interna profilen. Instruktioner om hur du installerar den interna profilen för datatjänsten [!DNL IP Geo-location] eller [!DNL IP Geo-intelligence] finns i *användarhandboken för Datan Workbench*.
