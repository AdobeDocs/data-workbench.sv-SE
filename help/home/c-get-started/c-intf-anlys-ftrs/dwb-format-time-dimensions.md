---
description: Konfigurera tidsdimensionerna så att de visas korrekt för språkområdet.
title: Lokalisera tidsdimensioner
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Lokalisera tidsdimensioner{#localizing-time-dimensions}

Konfigurera tidsdimensionerna så att de visas korrekt för språkområdet.

Du kan konfigurera det visade formatet för tidsdimensioner baserat på språkområde i **[!DNL Standard Time Dimensions.cfg]** filen (finns som standard i **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimensions.cfg]**).

I Nordamerika kan du till exempel ange datumet 3 maj 2015 som 5/3/15 eller **`%m/%d/%y`**. I andra delar av världen kan detta dock tolkas som `%d/%m/%y`den 5 mars 2015 på grund av en oklar värdeberäkning. För att undvika den här situationen kanske en administratör vill ändra det visade formatet så att det matchar förväntningarna hos användarna i ett språkområde.

## 1. Åsidosätt standardtidsdimensioner i standardtidsdimensioner.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Om du vill aktivera den här funktionen måste administratören åsidosätta standardvärdena genom att antingen redigera de befintliga tidsdimensionerna eller skapa nya tidsdimensioner med ytterligare parametrar.

Ett exempel på en ändrad tidsdimension följer.

Standardvärdena för **Format** för Vecka, Timme, Dag, Månad och Timme på dagen anges i exemplet.

>[!NOTE]
>
>Om raderna utelämnas ändras inte Data Workbenchs beteende och dimensionen kompileras med standardinställningarna.

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. Konfigurera filen meta.cfg {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Dessutom måste paketadministratören lägga till de här parametrarna och deras standardvärden är profilens **[!DNL meta.cfg]** fil. Detta gör att du kan redigera från arbetsstationen.

Här är ett utdrag från en konfigurerad **[!DNL meta.cfg]** fil.

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

Här är ett exempel på en **[!DNL meta.cfg]** fil i arbetsstationen:

![](assets/dwb_time_format.png)

Administratören kan sedan gå till **Filhanteraren**, öppna filen/filerna där tidsmåtten är konfigurerade (t.ex. **[!DNL Standard Time Dimensions.cfg]**) och redigera dem i arbetsstationen.
