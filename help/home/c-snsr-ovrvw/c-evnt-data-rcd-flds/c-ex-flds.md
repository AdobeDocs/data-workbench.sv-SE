---
description: Sensorn kan, när den används på en server, samla in fält med händelsedata från en giltig HTTP-begäran eller ett giltigt svarshuvud eller variabel som är tillgänglig för den via serverns API.
title: Utbyggbara fält
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
exl-id: e783d073-cf06-4415-80e1-567b55fdee12
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# Utbyggbara fält{#extensible-fields}

Sensorn kan, när den används på en server, samla in fält med händelsedata från en giltig HTTP-begäran eller ett giltigt svarshuvud eller variabel som är tillgänglig för den via serverns API.

Om du vill samla in sådana datafält måste du ange önskade rubrikfält eller variabler i [!DNL txlogd.conf]-konfigurationsfilen för [!DNL Sensor].

* [Begäranrubriker](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f)
* [Servervariabler](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Begäranrubriker {#section-22766692b45546d8bfc93dbe3bc9368f}

Här följer syntaxen för att ange ett begäranrubrikfält som ska samlas in (till exempel Värd, Acceptera-kodning, Håll ihop, o.s.v.) i [!DNL txlogd.conf]:

```
LogHeader RequestHeaderName
```

De insamlade data spelas in av [!DNL Sensor] till ett fält med namnet&quot;cs(RequestHeaderName)&quot; i [!DNL .vsl]-filerna som skapas av [!DNL data workbench server]. Om du till exempel vill samla in det specifika begäranrubriksvärdet från begärandehuvudet &quot;Host&quot;, skriver du &quot;LogHeader Host&quot; i [!DNL txlogd.conf]. Data registreras i fältet&quot;cs(Host)&quot; i händelsedataposten.

## Servervariabler {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] kan samla in datafält från svarshuvuden eller API-tillgängliga servervariabler med SpecialLogField-poster som du inkluderar i  [!DNL txlogd.conf] filen. Du kan också använda poster av typen&quot;SpecialLogField&quot; förutom eller istället för posterna&quot;LogHeader&quot; för att samla in begäranrubriker. Se [Begäranrubriker](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). Alternativet för begäranrubriker är fortfarande tillgängligt för bakåtkompatibilitet.

Följande är syntaxen för att ange ett SpecialLogField i [!DNL txlogd.conf]:

```
SpecialLogField cs(log field) = serverVariable stage
```

Följande tabell innehåller beskrivningar av komponenterna i en SpecialLogField-post.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponent </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(loggfält) </td> 
   <td colname="col2"> Namnet på det fält där insamlade data registreras i händelsedataposten och <span class="filepath"> .vsl </span>-filerna som skapas av <span class="keyword">-data workbench-servern </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Alla servervariabler som är tillgängliga för <span class="wintitle">-sensorn </span> via serverns API </p> <p>Exempel: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>Antingen vys_log eller vys_cookie </p> <p>Om du anger scenen måste du känna till vilka servervariabler som är tillgängliga för vys_log och vys_cookie. </p> <p>Exempel: För serverVariable response.p3p anger du vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

Kontakta Adobe Consulting Services om du behöver hjälp med att konfigurera [!DNL Sensor] för att samla in utökningsbara händelsedatapostfält.
