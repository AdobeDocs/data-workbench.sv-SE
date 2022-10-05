---
description: Attributprofilen är en ärvd, ifyllningsprofil. I kombination med dataflödet från Adobe SC-profilen och Analytics (SC/Insight) kan profilen användas för att snabbt exponera nya attribueringsmodeller för digitala kanaler.
title: Distribuera attributprofilen
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 1%

---

# Distribuera attributprofilen{#deploying-the-attribution-profile}

{{eol}}

Attributprofilen är en ärvd, ifyllningsprofil. I kombination med dataflödet från Adobe SC-profilen och Analytics (SC/Insight) kan profilen användas för att snabbt exponera nya attribueringsmodeller för digitala kanaler.

När du har sparat attributprofilen på den primära servern finns det ytterligare två steg som krävs för att integrera den i den aktuella profilen i [!DNL Profile] katalog: (1) Konfigurera filen Profile.cfg och (2) Deklarera obligatoriska fält.

## Konfigurera filen Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Precis som alla profiler måste attributprofilen läggas till i [!DNL profile.cfg] -fil. Eftersom attribueringsprofilen är beroende av Adobe SC-profilen måste Adobe SC-profilen först listas i konfigurationsfilen före attributprofilen.

>[!NOTE]
>
>Dessa steg kräver en omformning av datauppsättningen.

1. Öppna [!DNL profile.cfg] i din anpassade profilmapp. (Öppna i [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Om attributprofilen inte finns med i konfigurationsfilen lägger du till den i listan. ![](assets/new_profile_cfg.png)

1. Se till att **[!UICONTROL Attribution]** strängen visas under **[!UICONTROL Adobe SC]** profilsträng.

1. Spara den uppdaterade [!DNL profile.cfg] och spara den på servern från Profilhanteraren.

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
1. Kontrollera att fälten har deklarerats i **[!UICONTROL Fields]** i [!DNL SC Fields.cfg] -fil. Den här filen finns under [!DNL Dataset\Log Processing\SC Fields.cfg].

## Attributionstillägg och felsökning {#section-168133a8a1a54e1281e532033878d246}

Attributprofilen lade till en konfigurationsfil, [!DNL 0a_Marketing Channels.cfg], som kopierar värdet för [!DNL x-va_closer_detail] till ett nytt fält [!DNL x-marketing-channel], när [!DNL x-va_instance_event] fältet matchar&quot;1&quot;. Båda [!DNL x-va_closer_detail] och [!DNL x-va_instant_event] avkodas som standard och skickas från avkodning i de installerade paket som är tillgängliga när du uppdaterar till version 6.2.

The [!DNL x-marketing-channel] används sedan i den enkla dimensionen Marknadskanal.

>[!IMPORTANT]
>
>Om du har ändrat dina profiler genom att ta bort tidigare oanvända fält som nu används, bör du kontrollera att [!DNL x-va_closer_detail] och [!DNL x-va_instance_event] fält avkodas och skickas för användning.

Om fält saknas får du ett meddelande med detaljerad status:

```
<b>x-va_closer_detail</b> is not available
```

eller

```
<b>x-va_instance_event</b> is not available
```
