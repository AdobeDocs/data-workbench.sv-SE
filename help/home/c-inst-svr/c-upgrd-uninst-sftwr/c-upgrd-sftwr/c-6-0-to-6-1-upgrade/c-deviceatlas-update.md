---
description: DeviceAtlas JSON-filen kommer nu att distribueras i en .bundle-fil (en namnändrad .tar.gz) tillsammans med filerna DeviceAtlas.dll och DeviceAtlas64.dll.
title: DeviceAtlas-distribution
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# DeviceAtlas-distribution{#deviceatlas-distribution}

{{eol}}

DeviceAtlas JSON-filen kommer nu att distribueras i en .bundle-fil (en namnändrad .tar.gz) tillsammans med filerna DeviceAtlas.dll och DeviceAtlas64.dll.

När administratören uppgraderar Insight Server till version 6.0 inkluderas filen DeviceAtlas.bundle i uppgraderingspaketet i profilen Software and Docs (Softdocs profile) som finns på:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

Filen DeviceAtlas.bundle extraheras till [!DNL Server\Lookups\DeviceAtlas].

Filen DeviceAtlas.bundle ska placeras i en katalog som är synkroniserad med DPU:erna, och filen DeviceAtlas.cfg som motsvarar den nya DeviceAtlasComponent ska placeras i katalogen Components for Processing Servers på synkroniseringsöverordnad. När filen DeviceAtlas.bundle ändras får det allra nästa DeviceAtlas-sökanrop resultat baserat på den uppdaterade API- och/eller JSON-filen.

## Ändra filen Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

DeviceAtlas-omformningar behöver inte längre ange sökvägen till JSON-filen. Alla tidigare DeviceAtlasTransformation som definieras i filen transformation.cfg ska inte längre innehålla parametern File som pekar på den dolda JSON-filen.

Det här exemplet visar Transformation.cfg-filen det File-argument som ska tas bort för att undvika förvirring. (Om du lämnar det där kommer det inte att orsaka någon skada, men bara eventuell förvirring eftersom det kommer att ignoreras.)

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## Ändra filen DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Detta är ett exempel på [!DNL component] argument krävs i filen DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Filen DeviceAtlas.bundle behandlas på samma sätt som en konfigurationsfil i perspektivet för funktionen Profilsynkronisering. Dessutom kommer JSON-data och DLL-filer att användas på komponentnivå i stället för på individuell omformningsnivå.

En ny DeviceAtlasComponent hittar .bundle-konglomationen när den startas, döljer JSON-filen i minnet, extraherar filerna till en tillfällig katalog och läser in rätt DLL-fil för den plattform som körs. Den här komponenten övervakar även ändringar i paketfilen och läser in DLL- och .cfg-filen automatiskt igen om den ändras.

## Kör DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Korrekt konfiguration gör stor skillnad i den tid som krävs för omformning. Omvandlingen kan konfigureras så att den endast körs en gång per besökare och session, vilket gör att DeviceAtlas kan snabba upp processen.

**Om den distribueras med Log Processing.cfg**:

Kör omformningarna två gånger.

1. Slå bara upp [!DNL mobile id] fält, sedan
1. Skapa villkor som ignorerar [!DNL mobile id] och därefter leta upp resten av fälten.

**Om den distribueras med Transformation.cfg**:

Distribuera som i steg 1 i Loggbearbetning ovan, eller använd tvärrader som stöd för en villkorsinställning.

* Korsrader - Ta tag i föregående sessionsnyckel. Identifiera sedan om den aktuella sessionsnyckeln skiljer sig från den som finns med korsrader. I så fall körs DeviceAtlas-omvandlingen bara på en post per session.
