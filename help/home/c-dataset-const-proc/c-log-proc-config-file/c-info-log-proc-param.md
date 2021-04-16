---
description: Länkar till ytterligare information om specifika parametrar i filen Log Processing.cfg.
title: Loggbehandlingsparametrar
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 1%

---

# Loggbehandlingsparametrar{#log-processing-parameters}

Länkar till ytterligare information om specifika parametrar i filen Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Datafilter {#data-filters}

De filter som definieras i [!DNL Log Processing.cfg]-filen innehåller följande:

* Sluttid
* Hash-tröskelvärde
* Starttid

Den filtrering som definieras av de här parametrarna sker efter att loggposter lämnar avkodare och efter omformningar, men innan de utvärderas av [!DNL Log Entry Condition]. Om du ändrar någon av de här parametrarna ändras datasetens komposition.

Den rekommenderade tekniken för att använda [!DNL Sensor]-datakällor för att skapa en datauppsättning som täcker en viss tidsperiod är att använda parametrarna Starttid och Sluttid för datauppsättningen.

Du bör använda parametrarna Starttid och Sluttid framför andra tekniker, till exempel flytta loggfiler så att de separeras med katalog. Genom att ställa in start- och sluttider för datauppsättningen, använder data workbench-servern automatiskt endast de loggposter som inträffade inom det angivna intervallet. Om sluttiden redan är inne, uppdaterar data workbench-servern vanligtvis datauppsättningen med samma uppsättning loggposter, även om datauppsättningen uppdateras genom att till exempel lägga till en ny omvandling.

<!--
c_log_entry_con.xml
-->

## Loggpost

Det är i själva verket en filtreringsprocess för de tillgängliga loggposterna. Om [!DNL Log Entry Condition] returnerar värdet false filtreras loggposten bort från den tillgängliga uppsättningen loggposter.

[!DNL Log Entry Condition] beskrivs genom användning av villkorsåtgärder (se [Villkor](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) och kan använda alla inmatningsfält som samlats in av [!DNL Sensor] (se *Data Workbench [!DNL Sensor] Guide* ) eller alla utökade fält som skapats av omformningar i [!DNL Log Processing.cfg]-filen för att definiera testvillkoren. [!DNL Log Entry] villkor används under loggbearbetning och kan eventuellt användas under omformningen.

I det här exemplet visas hur du använder [!DNL log entry condition] för webbplatsdata. Du kan använda [!DNL Log Entry Condition] för att skapa datauppsättningar som fokuserar på en viss del av webbplatsen eller besökare som utför en viss åtgärd på webbplatsen.

[!DNL Log Entry Condition] i det här exemplet skapar en datauppsättning som endast innehåller de loggposter som är en del av webbplatsens butik. Genom att använda [!DNL RECondition test] med det matchande mönstret [!DNL "/store/.*"] och fältet [!DNL cs-uri-stem] som indata i det reguljära uttrycket inkluderas endast webbsidor som börjar med strängen [!DNL "/store/"] i datauppsättningen.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Nyckeldelning {#key-split}

Antalet spårnings-ID i datauppsättningen ökas artificiellt, men det totala antalet loggposter som bearbetas av data workbench-servern ökas inte artificiellt, vilket bevarar det totala antalet räkningsbara händelser i datauppsättningen. När data för ett enskilt element har delats kopplas dessa data för gott med två olika spårnings-ID:n och kan inte relateras.

Om du till exempel arbetar med webbdata representerar varje spårnings-ID en unik besökare. Om du aktiverar nyckeldelning delas besökarna i datauppsättningen med stora mängder händelsedata upp i flera besökare. Även om antalet besökare i datauppsättningen ökas på ett konstlat sätt, ökas inte det totala antalet räkningsbara händelser som sidvisningar eller bokningar på ett konstlat sätt. När delning har gjorts kan data för underbesökarna inte relateras.

Nyckeldelning använder en sannolikhetsalgoritm. Därför finns det en kompromiss mellan minnesanvändning, sannolikhet för fel, tröskelvärde för nyckeldelning ( [!DNL Split Key Bytes]) och datauppsättningsstorlek. Med de rekommenderade inställningarna (se nedan) är felfrekvensen låg. Av de element vars händelsedata överskrider tröskelvärdet för nyckeldelning kommer ungefär 1 av 22 000 (vanligtvis mindre än 1 per datauppsättning) att få en del data trunkerade i stället för att delas upp.

De rekommenderade värdena för varje parameter (utan och med tangentdelning) visas i följande tabell.

| Parameter | Ingen tangentdelning | Nyckeldelning |
|---|---|---|
| Högsta antal nyckelbyte för grupp | 1e6 | 2e6 |
| Split Key Bucket Space | 6e6 | 6e6 |
| Dela nyckelbyte | 0 | 1e6 |
| Dela nyckelutrymmesförhållande | 10 | 10 |

[!DNL Group Maximum Key Bytes] Anger den maximala mängden händelsedata som kan bearbetas för ett enda spårnings-ID. Data som överskrider denna gräns filtreras från datauppsättningens konstruktionsprocess. [!DNL Split Key Bytes] representerar antalet byte där ett enda spårnings-ID delas upp i flera element. Elementen delas vid ungefär detta antal byte enligt en sannolikhetsfördelning. [!DNL Split Key Space Ratio] och  [!DNL Split Key Bucket Space] styr minnesanvändningen och felfrekvensen för nyckeldelning.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes],  [!DNL Split Key Bytes],  [!DNL Split Key Space Ratio]och  [!DNL Split Key Bucket Space] alla måste deklareras för att nyckeldelningen ska fungera korrekt. Ändra inte värdena för de här parametrarna utan att rådfråga Adobe.
