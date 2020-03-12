---
description: Du kan generera rapporter dynamiskt för de dimensionselement som du anger i en uppslagsfil eller för ett visst antal dimensionselement, till exempel för användare med de tio högsta ordersiffrorna.
solution: Analytics
title: Generera rapporter dynamiskt
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generera rapporter dynamiskt{#dynamically-generating-reports}

Du kan generera rapporter dynamiskt för de dimensionselement som du anger i en uppslagsfil eller för ett visst antal dimensionselement, till exempel för användare med de tio högsta ordersiffrorna.

>[!NOTE]
>
>Adobe rekommenderar inte att man skapar dynamiska rapportuppsättningar för daglig (eller oftare) rapportgenerering. Dynamisk rapportgenerering kan vara resurskrävande om du konfigurerar rapporter med stora eller komplexa frågor.

* [Uppslagselementrapporter för fildimension](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Viktigaste dimensionselementrapporter](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Uppslagselementrapporter för fildimension {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Om du vill konfigurera en rapportuppsättning så att den dynamiskt genererar och (valfritt) distribuerar rapporter för elementen i en dimension som anges i en uppslagsfil anger du följande parametrar i [!DNL Report.cfg] filen:

* [!DNL Dimension Name]
* [!DNL Lookup File]

Detaljerade beskrivningar av parametrarna finns i [Report.cfg Parameters](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Skapa en dynamisk rapportuppsättning med en sökfil**

1. Skapa en sökfil med två kolumner för en given dimension. Filen måste innehålla två tabbavgränsade kolumner, utan rubrikrad.

   * Kolumn 1 ska innehålla en lista med dimensionselement.
   * Kolumn 2 ska innehålla rapportmottagarnas e-postadresser. En rapport för ett visst element i kolumn 1 skickas till e-postadresserna på samma rad i kolumn 2. Du kan ange flera e-postadresser genom att separera dem med kommatecken (inga blanksteg).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Om rapporter inte ska skickas med e-post kan kolumn 2 vara tom, men måste finnas.
      >    * Filen kan innehålla tomma rader.




1. Valfritt. Om du vill att rapporter ska kunna skickas med e-post måste du göra följande i [!DNL Mail Report] avsnittet i [!DNL Report.cfg] filen för den aktuella rapportuppsättningen:

   * I parametern SMTP Server anger du den SMTP-server som ska användas för att distribuera rapporter via e-post.
   * I parametern Mottagare anger du minst en e-postadress så att rapporterna kan distribueras via e-post. Rapporterna skickas inte till den angivna adressen. Du anger bara den här parametern så att rapporterna kan skickas via e-post. Detta kan vara en felaktig adress, men måste ha ett tillåtet format (till exempel [!DNL jsmith@company.com]).

1. Spara sökfilen i rapportuppsättningens mapp.
1. Öppna [!DNL Report.cfg] filen för rapportuppsättningen.
1. I parametern Dimensionsnamn skriver du namnet på dimensionen som du vill generera en rapport för dynamiskt.
1. I parametern Sök efter fil skriver du plats och namn för sökfilen som innehåller de dimensionselement som du vill ha i rapporten och mottagarnas e-postadresser.
1. Upprepa dessa steg för ytterligare rapportuppsättningar.

>[!NOTE]
>
>Dynamiska rapporter skickas inte via e-post till mottagarna förrän hela rapportuppsättningen är slutförd.

## Viktigaste dimensionselementrapporter {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Om du vill konfigurera en rapportuppsättning som dynamiskt genererar rapporter för elementen i den översta dimensionen, räknat med det angivna måttet, anger du följande parametrar i [!DNL Report.cfg] filen:

* Dimensionsnamn
* Övre N-mått
* Övre N-värde
* (Valfritt) Förinläsningsfrågefilter

Detaljerade beskrivningar av parametrarna finns i [Report.cfg Parameters](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Skapa en dynamisk rapportuppsättning för de översta elementen**

1. Öppna rapportuppsättningens [!DNL Report.cfg] fil.
1. I parametern Dimensionsnamn skriver du namnet på dimensionen som du vill generera en rapportuppsättning dynamiskt för.
1. I parametern Övre N-mått skriver du namnet på det mätresultat som du vill sortera dimensionen efter.
1. I parametern Övre N-värde anger du antalet dimensionselement som du vill ha i rapportuppsättningen.
1. (Valfritt) Skriv namnet på det önskade filtret i parametern Förhandsladda frågefilter.
1. Upprepa dessa steg för ytterligare rapportuppsättningar.
1. Mer information om hur du använder en dynamisk titelvisualisering med din rapport finns i användarhandboken för *Data Workbench*.
