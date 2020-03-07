---
description: I det här avsnittet förklaras de olika typerna av dimensioner och hur du konfigurerar dem i DWB.
title: Dimensionsinställningar
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Dimensionsinställningar{#dimension-setup}

I det här avsnittet förklaras de olika typerna av dimensioner och hur du konfigurerar dem i DWB.

## Vad är dimensioner {#section-dac631943df24706827cedc6f0641543}

På den mest grundläggande nivån är dimensioner kategorier där data i datauppsättningen kan delas upp.

God praxis: Dimensioner i dataschemat kan anges med vilket namn som helst. Dimensionsnamn som används och förklaras i den här kursen anses vara bästa praxis. Dimensioner kan namnges på ett annat sätt. När du exponeras för andra datauppsättningar börjar du se skillnader i datauppsättningar. Det är viktigt att förstå syftet med dimensionerna i stället för deras namn. Oavsett om det till exempel heter&quot;Besökare&quot;,&quot;Kund&quot;,&quot;Person&quot;,&quot;Kund&quot; eller&quot;Användare&quot;, är det viktigt att förstå att dessa termer vanligtvis används för att referera till den högsta räkningsbara dimensionen som används för att samla information om en person.

Fullständig information finns i guiden Konfigurera [](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) datauppsättning.

## Typer av dimensioner i DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Det finns två typer av dimensioner i Data Workbench: Utökade dimensioner och härledda dimensioner.

Utökade dimensioner skapas från fält i&quot;raw&quot;-datafiler. Utökade dimensioner används för att kategorisera&quot;rådata&quot; och för att ange de relationer som finns mellan data. Utökade dimensioner skapas av Data Workbench Architects.

Härledda dimensioner skapas av en användare &quot;på klientsidan&quot; efter att datauppsättningen har bearbetats med befintliga utökade dimensionsdefinitioner. Baserat på den befintliga URI-dimensionen kan en användare välja att skapa en härledd sidnamnsdimension, som visar ett användarvänligt sidnamn i stället för en viss URI. Alla dimensioner består av element eller objekt som har kategoriserats (grupperats) tillsammans för att bilda dimensionen. Nedan visas tre dimensioner och deras element.

Många härledda dimensioner skapas automatiskt för att skapa olika typer av visualiseringar. När en användare skapar en plats- eller processkarta skapar DWB-servrar till exempel en Prefix-dimension. Andra, t.ex. måtten för rapporttiden, definieras av filer i katalogen Dimensions för en profil.

>[!NOTE]
>
>Elementen i en given dimension återspeglar endast de värden som finns i poster som har valts för inläsning i datauppsättningen. Om det t.ex. inte finns några data för &quot;12 maj&quot; visas inte den månaden i dimensionen &quot;Månad&quot;.

## Utökade dimensioner {#section-5fc51fa539034941a30a2df606f7d727}

Typer av utökade dimensioner

**1) Räkningsbara dimensioner**

På den högsta nivån finns räkningsbara dimensioner. Räkningsbara dimensioner har två huvudfunktioner. För det första är de dimensioner vars element du vill räkna. Med andra ord besvarar konversationer frågor som:

* &quot;Hur många besökare besökte din hemsida?&quot;
* &quot;Hur många besök kom från google.com?&quot;

Därför används ofta räknetabeller som grundläggande byggsten för att skapa mätvärden.

Den andra större funktionen hos räknare är att de utgör ryggraden i datasetens schemastruktur. Ditt dataschema och alla andra dimensioner är ordnade för att grupperas under och tillhör en räkningsbar enhet. Med andra ord, om vi ser dimensioner som &quot;kategorier&quot;, är räknare det sätt på vilket vi organiserar dessa &quot;kategorier&quot; i grupper.

När dimensioner grupperas under en räkningsbar dimension sägs de vara på&quot;nivån&quot; för den räkningsbara dimensionen. E-postadressen kan till exempel vara på besökarnivå och webbläsaren på besöksnivå. &quot;Överordnad&quot; och &quot;underordnad&quot; avser relationen mellan den räkningsbara och dimensionerna grupperade nedanför den. Besökaren är till exempel&quot;överordnad&quot; till e-postadressen. Omvänt är e-postadressen underordnad besökaren.

**2) Enkla dimensioner**

Den vanligaste av alla dimensioner är Enkla dimensioner. Enkla dimensioner har en 1:N-relation med en överordnad, räkningsbar dimension och används ofta i visualiseringar så att du kan visa elementen i dem. Det innebär att en räkningsbar dimension kan ha ett värde för en enkel dimension, men den enkla dimensionen kan tillhöra en eller flera räkningsbara dimensioner. En kund har till exempel namnet&quot;John&quot;, som kunden bara kan ha ett förnamn, men många andra kunder kan ha namnet&quot;John;. Som ett annat exempel kan bara en webbläsare (t.ex. Firefox) användas för ett visst besök på en webbplats, men den webbläsaren kan användas för många olika besök.

Om räknebara dimensioner är&quot;Hur många?&quot;, så svarar då enkla dimensioner&quot;Vilka?&quot;. Använda samma exempel som används i avsnittet för beräkning av dimensioner. Sidnamn är den enkla dimensionen. Med hjälp av tabellen och den enkla dimensionen, Sidnamn, kan vi besvara frågor som:

* &quot;Vilken sida hade de mest sidvyerna?&quot;
* &quot;Av alla kundvagnssidor, vilka hade mest besök?&quot;

**3) Flera dimensioner**

Många-till-många-dimensioner har en många-till-många-relation med en överordnad räkningsbar dimension. Om en dimension med namnet Extern sökterm till exempel finns på besöksnivå, en given extern sökterm kan användas i ett eller flera besök, och ett visst besök kan innehålla en eller flera externa söktermer. Extern sökterm är alltså en många-till-många-dimension.

**4) Numeriska dimensioner**

Numeriska dimensioner är en typ av enkel dimension som har ett numeriskt värde. Numeriska dimensioner skapas ofta för att användas i mätvärden. Exempel på numeriska dimensioner är Intäkter, Beställningar och Enheter. I exemplet ovan är &#39;Kundorder&#39; en numerisk dimension.
**5) Dekorativa dimensioner** är dimensioner som har en 1:1-relation med en överordnad räkningsbar dimension. Denormala dimensioner används ofta med dimensioner som har hög kardinalitet (många unika element) som identifieringsdata. En besökare kan till exempel bara ha ett användar-ID och ett användar-ID kan bara tillhöra en besökare. Detta är alltså en-till-en-relation och kan vara en normal dimension.

Geometrixx-webbanvändar-ID är till exempel en normal dimension på kundnivå. Eftersom det är normalt har det en-till-en-relation med den överordnade dimensionen, vilket innebär att varje webb-ID har en kund och varje kund bara har ett webb-användar-ID. Därför kan kundens mått bara vara 1 för varje element i Geometrixx-webbanvändar-ID.

**6) Tidsdimensioner**

Med tidsdimensioner kan du skapa en uppsättning periodiska eller absoluta lokala tidsmått baserat på det tidsstämpelfält som du anger. Exempel på tidsdimensioner är &#39;Dag&#39;, &#39;Timme&#39;, &#39;Vecka&#39; och &#39;Timme på dagen&#39;. I exemplet ovan visar tabellen &quot;Timme of Day&quot; hur många besök och sidvisningar som tagits emot under de olika timmarna på dagen.

>[!NOTE]
>
>De %-undantag som används för visningsformatering är samma som standard-C-bibliotekets *starttid*.

## Definiera utökade dimensioner {#section-38ee124ec74b43fb95f13194a9582b97}

Steg för att definiera utökad dimension:

1. Öppna profilhanteraren när du arbetar i datauppsättningsprofilen och klicka på Datauppsättning för att visa innehållet.
1. Öppna filen Transformation.cfg eller filen Transformation Dataset Include som du vill definiera den utökade dimensionen i.
1. Högerklicka på Omvandlingar och klicka på Lägg till ny > `<Extended dimension type>`.
1. Ange lämplig information för den utökade dimensionen. Beskrivningar av omformningstyperna och information om deras parametrar finns i följande avsnitt:

   * [Räknbara dimensioner](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Enkla dimensioner](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Många-till-många-dimensioner](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Numeriska dimensioner](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dekorativa dimensioner](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Tidsdimensioner](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. För alla utökade dimensioner som du definierar kan du lägga till en eller flera kommentarsrader i kommentarsparametern för att ytterligare beskriva dimensionen eller lägga till anteckningar om dess användning. Om du vill lägga till en kommentar högerklickar du på etiketten *Kommentarer* och klickar på* Lägg till ny > Kommentarsrad*.

1. När du har definierat de utökade dimensionerna i konfigurationsfilen sparar du filen lokalt och sparar den i datauppsättningsprofilen på DWB-servern.

## Dölja utökade dimensioner {#section-02339fb51658418eabc10186cd5957d7}

Utökade dimensioner kan döljas så att de inte visas på Dimension-menyn i DWB. Om du vill dölja dimensionen anger du egenskapen Dold till &quot;Sant&quot; i dimensionsdefinitionen.
