---
description: Mätvärden, dimensioner och filter utgör ett ramverk inom vilket beräkningar görs av data som bearbetas till en data workbench-datamängd.
title: Data Workbench Metrics, Dimensions, and Filters
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
exl-id: 687d9695-e70c-49ff-ac11-1537e6309e16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Data Workbench Metrics, Dimensions, and Filters{#data-workbench-metrics-dimensions-and-filters}

{{eol}}

Mätvärden, dimensioner och filter utgör ett ramverk inom vilket beräkningar görs av data som bearbetas till en data workbench-datamängd.

Resultaten av beräkningarna som definieras med det här ramverket visas i arbetsytor, kontrollpaneler, rapporter eller andra utdata. Kort och gott: alla tal som du ser i eller från ett program är resultatet av en fråga i en datauppsättning som innehåller ett mått, en dimension och ett filter.

På den mest grundläggande nivån beskriver ett mätresultat vad som beräknas från och om datauppsättningen, en dimension delar upp data i datauppsättningen i kategorier och ett filter beskriver en vald del eller deluppsättning av data i datauppsättningen.

När Data Workbench Server bearbetar data för att skapa en datauppsättning skapas datamängder och uppdateras sedan kontinuerligt allt eftersom nya data läses och bearbetas av servern. Mätvärden och filter beräknas utifrån dessa datamängder.

>[!CAUTION]
>
>Om du definierar om ett internt mått kommer systemet att uppträda oväntat på grund av fel värde. Dina rapporter genereras bara om ett mätvärde är 100 %. Vi rekommenderar att du inte ändrar måttdefinitioner.

## Ett exempel {#section-ecc465d1a5e34d559c1983e96fa409ec}

Tänk dig en datauppsättning som innehåller information om alla personer i världen. Den här datauppsättningen innehåller åtminstone alla människor i världen och deras ålder. Ett användbart mätvärde att beräkna utifrån den här datauppsättningen skulle vara medelåldern. Utvärderingen av det här måttet resulterar i ett tal: medelåldern på världens befolkning.

Om du lägger till en dimension i datauppsättningen blir informationen mer användbar och hanterbar. Om datauppsättningen också innehåller varje persons bosättningsland, skulle det vara ett sätt att gruppera personerna i grupper för varje land i världen om man definierar en landdimension. En utvärdering av medelåldern över landdimensionen skulle resultera i en lista med siffror, ett för varje land, som representerar den genomsnittliga åldern för befolkningen i det landet.

Användning av ett filter (eller urvalsfilter) i en metrisk formel kan ge mer detaljerad information eller tillåta definition av ett nytt mått baserat på befintliga mått och mått. En utvärdering av medelåldern med ett filter med&quot;där landet är lika med Sverige&quot; resulterar i ett tal: den genomsnittliga åldern hos människor i Sverige. Ett mått baserat på det här filtret kan vara svensk genomsnittlig ålder.

Exempel:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Hur mått, Dimensioner och filter relaterar {#section-28622596124140b280e6b993b174ef84}

Om du utvärderar ett mått över en dimension utvärderas det måttet för varje dimensionselement (eller -element). I exemplet ovan har landdimensionen ett element för varje land i världen. En utvärdering av genomsnittlig ålder över land skulle ge den genomsnittliga åldern för var och en av elementen (länderna), inklusive elementet Sverige.

Observera att när du utvärderar ett mätresultat över en dimension får du samma numeriska resultat för ett visst dimensionselement, oavsett om du utvärderar mätvärdet för hela dimensionen eller definierar ett filter som motsvarar det specifika dimensionselementet. När man i det föregående exemplet söker efter genomsnittsåldern hos människor i Sverige skulle någon av följande metoder ge identiska resultat:

* Utvärdera medelåldern över landdimensionen och titta sedan på numret för dimensionselementet Sverige.
* Utvärdera medelåldern med ett filter med &quot;personer i Sverige&quot; (uttryckt som [!DNL Average_Age[Country='Sweden']]).

Filter är syntaktiska uttryck som refererar till en eller flera dimensioner och dimensionselement. Som du såg i ovanstående exempel använder du uttrycket [!DNL] [dimension=element]] är ett enkelt sätt att ange ett filter.

Det är lika enkelt att använda ett sådant filter för att definiera ett nytt mätvärde med hjälp av ett uttryck som [!DNL New_Metric=Metric[Filter]]. Ett sådant filter kan användas för att definiera ett nytt mått baserat på ett visst dimensionselement. Om du vill använda exemplet ovan [!DNL Average_Age[Country='Sweden']]anger ett mått för den genomsnittliga personåldern i Sverige. Om vi ger det här måttet ett namn, som Swedish_Average_Age, kan vi använda det i andra beräkningar som ett mått. Exempel: utvärdera [!DNL Swedish_Average_Age/Average_Age] skulle resultera i ett enda tal: förhållandet mellan den genomsnittliga åldern hos människor i Sverige och den i resten av världen.

Om datauppsättningen med information om alla människor i världen också innehåller en dimensionseye-färg, uttrycket [!DNL Swedish_Average_Age[Eye_Color='green']] skulle resultera i en genomsnittlig ålder av svenskar med gröna ögon. Du kan även få samma resultat utan att använda en mellanliggande metrisk definition genom att använda ett annat filter: [!DNL Average_Age[Country='Sweden' AND Eye_Color='green']]. I det här fallet [!DNL AND] -operatorn anger ett filteruttryck med två andra grundläggande filteruttryck.
