---
description: Attributprofilen är en ärvd, ifyllningsprofil. I kombination med dataflödet från Adobe SC-profilen och Analytics (SC/Insight) kan profilen användas för att snabbt exponera nya attribueringsmodeller för digitala kanaler.
title: Distribuera attributprofilen
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuera attributprofilen{#deploying-the-attribution-profile}

Attributprofilen är en ärvd, ifyllningsprofil. I kombination med dataflödet från Adobe SC-profilen och Analytics (SC/Insight) kan profilen användas för att snabbt exponera nya attribueringsmodeller för digitala kanaler.

När du har sparat attributprofilen på den primära servern finns det ytterligare två steg som krävs för att integrera den i den aktuella profilen i [!DNL Profile] katalogen: (1) Konfigurera filen Profile.cfg och (2) Deklarera obligatoriska fält.

## Konfigurera filen Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Precis som alla profiler måste attributprofilen läggas till i [!DNL profile.cfg] filen. Eftersom attribueringsprofilen är beroende av Adobe SC-profilen måste Adobe SC-profilen först listas i konfigurationsfilen före attributprofilen.

>[!NOTE]
>
>Dessa steg kräver en omformning av datauppsättningen.

1. Öppna [!DNL profile.cfg] filen i din anpassade profilmapp. (Öppna i [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Om attributprofilen inte finns med i konfigurationsfilen lägger du till den i listan. ![](assets/new_profile_cfg.png)

1. Kontrollera att **[!UICONTROL Attribution]** strängen finns under **[!UICONTROL Adobe SC]** profilsträngen.

1. Spara den uppdaterade [!DNL profile.cfg] filen och spara den sedan på servern från Profilhanteraren.

## Deklarera obligatoriska fält {#section-23d4273af0c34b7a85ae3430e2c9350e}

Attributprofilen innehåller fördefinierade fält och med en serie omformningar visas dessa fält på nya och användbara sätt genom utökade dimensioner. För att ge det mest omedelbara värdet beror attribueringsprofilen på vilka fält som är tillgängliga med Adobe SC-profilen.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Standardvariabler </th> 
   <th colname="col2" class="entry"> Fältnamn och avkodningsposition (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marknadsföringskanaler </td> 
   <td colname="col2"> <p>x-va_close_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orderhändelse </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchase, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intäkter </td> 
   <td colname="col2"> x-intäkt, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enheter </td> 
   <td colname="col2"> <p>x-units, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Kontrollera att dessa fält har deklarerats i avkodargruppen som används för att definiera Adobe Analytics-datakällan. Standardavkodningsgruppen finns under [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Kontrollera att fälten har deklarerats i **[!UICONTROL Fields]** avsnittet i [!DNL SC Fields.cfg] filen. Den här filen finns under [!DNL Dataset\Log Processing\SC Fields.cfg].

## Attributionstillägg och felsökning {#section-168133a8a1a54e1281e532033878d246}

Attributprofilen lade till en konfigurationsfil, [!DNL 0a_Marketing Channels.cfg]som kopierar värdet för [!DNL x-va_closer_detail] till ett nytt fält [!DNL x-marketing-channel]när [!DNL x-va_instance_event] fältet matchar&quot;1&quot;. Både [!DNL x-va_closer_detail] och [!DNL x-va_instant_event] avkodas som standard och skickas från avkodning i de installerade paket som är tillgängliga när du uppdaterar till version 6.2.

Fältet [!DNL x-marketing-channel] används sedan i den enkla dimensionen som kallas marknadsföringskanal.

>[!IMPORTANT]
>
>Om du har ändrat dina profiler genom att ta bort tidigare oanvända fält som nu används, måste du verifiera att [!DNL x-va_closer_detail] - och [!DNL x-va_instance_event] -fälten avkodas och skickas för användning.

Om fält saknas får du ett meddelande med detaljerad status:

```
<b>x-va_closer_detail</b> is not available
```

eller

```
<b>x-va_instance_event</b> is not available
```

