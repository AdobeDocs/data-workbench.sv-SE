---
description: Versionsinformation om Data Workbench 6.1 innehåller nya funktioner, uppgraderingskrav, felkorrigeringar och kända fel.
title: Versionsinformation om Data Workbench 6.1
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# Versionsinformation för Data Workbench 6.1{#data-workbench-release-notes}

Versionsinformation om Data Workbench 6.1 innehåller nya funktioner, uppgraderingskrav, felkorrigeringar och kända fel.

## Nya funktioner {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.1 innehåller följande nya funktioner:

| Funktioner | Beskrivning |
|--- |--- |
| Uppgradering till 64-bitars Windows | Data Workbench-servern, rapportservern och klientkomponenterna har uppgraderats så att de bara kan köras på 64-bitars Windows-operativsystem. |
| Propensitetsbedömning | Genom att betygsätta er målgrupp kan ni identifiera kundlojalitet och statistiskt uppfatta vem som kan konvertera en försäljning eller interagera med en berättelse eller kampanj. Propensitetsbedömning inkluderar nu dessa visualiseringar för att visa modeller och visa den föränderliga korrelationen mellan valda mätvärden.<ul><li>I Model Viewer undersöks en logistisk regressionsmodell som har genererats med Propensity Scoring och som visar koefficientvikterna för varje indatavariabel (inklusive den konstanta termen) och deras statistiska felintervall. </li><li>Lyft och förstärkning används för att utvärdera den potentiella ökningen av en poängsatt datamodell.</li><li>Sammanfusionsmatrisen ger fyra tal genom kombinationen av Faktiskt positivt (AP), Faktiskt negativt (AN), Förutsagt positivt (PP) och Förutsagt negativt (PN).</li> <li>Från och med v6.1 har du nu alternativet Spara för att spara benägenhetspoäng baserat på två typer: mått, dimensioner och mätvärden.</li><li>Du kan nu klicka på Ctrl-Alt och dra och släppa för att lägga till element i Propensitetsskalförändring och Klusterbyggaren. Innan du kunde lägga till tabellelement var du tvungen att dra från tabellen till rutan Elements.</li></ul> |
| Data workbench nu på kinesiska | Data Workbench har nu stöd för förenklad kinesiska för klientprogrammet. Data workbench stöder även IME (Input Method Editor) som en sekundär textinmatningsprocess för internationella språk. |
| Matematiska funktioner | Nu kan du lägga till matematiska funktioner i mått, matematiska omformningar och kalkylbladsceller för att ytterligare beräkna datauppsättningar. |
| Statistiska bildtexter | Tabeller erbjuder nu en statistiksammanfattning för måttkolumner. Anropet kan visa medelvärdet, standardavvikelsen, minimi- och maximivärden, variansen och totalantalet för kolumnen. Den kan vägas in i alla urval och utvärderingar. |
| filtret Korrelationsmatris | Korrelationsmatrisen har uppdaterats med ett binärt filter så att du kan begränsa värden för en eller båda korrelerade mätvärden, vilket gör att du kan fokusera jämförelsen bättre. Nu kan du även lägga till element från en matristabell genom att klicka på Ctrl + Alt och dra Dimensioner till den matriskolumn eller Dimension som ska utvärderas. |
| Dölj utfallsetikett i trattvisualisering | Växla mellan att visa och dölja bortfallsetiketter i en trattvisualisering genom att högerklicka på titeln och välja Dölj bortfall. |

## Sortera tabellkolumner{#sorting-table-columns}

Sortera tabellkolumner i bokstavsordning eller efter ordningstal.

Om du bättre vill markera element i en texttabell kan du ordna den första Dimensionen i bokstavsordning eller efter ordningstal genom att välja menyalternativet **[!UICONTROL Sort]**.

Tecknet # visas när en kolumn sorteras efter ordningstal (standard).

**Välj sorteringsalternativ**

Om du vill ändra sorteringsalternativen mellan ordningstalet och alfabetet högerklickar du och väljer **[!UICONTROL Sort]**. Klicka på pilen för att vända ordningen.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Du kan sortera andra kolumner efter ordningstal genom att klicka på kolumnnamnet.

## Dölj utfallsetiketter i tratt

Växla till att öppna utfallsetiketter i en trattvisualisering.

Funnel-visualisering identifierar var en kund överger en marknadsföringskampanj eller byter från en definierad konverteringsväg när han eller hon interagerar med webbplatsen eller en kanalövergripande kampanj. Till vänster om Tratt-visualiseringen visas resultatet av ett besök eller besökare, medan till höger visas&quot;Utfall&quot; för dem som överger en angiven sökväg.

![](assets/c_funnel_hide_fallout.png)

I en **[!UICONTROL Funnel]**-visualisering kan du högerklicka på titeln och välja **[!UICONTROL Hide Fallout]** på menyn för att dölja utfallsetiketterna.

## Kända fel {#section-ff2180c6871c413480e15fa915c253b9}

* När du importerar en arbetsyta visas ett felmeddelande även om importen lyckades.

   Tillfällig lösning: Klicka på OK för att ignorera felet. Arbetsytan har importerats.

**Problem med lokalisering av förenklad kinesiska**

* Dialogrutans titel och meddelande som visas när du har klickat på &quot;Skicka&quot; när du har angett målet i poängvisningen är oläsliga.

   Tillfällig lösning: Ingen.
* När du använder automatisk radbrytning i kalkylbladsvisualisering radbryts inte lokaliserade ord korrekt. Extra skräptecken läggs till i strängen.

   Tillfällig lösning: Ingen
* Det går inte att starta [!DNL Insight.exe] om installationskatalogen har namn med tecken som inte är engelska.

   Tillfällig lösning: Behåll standardnamn eller byt namn med endast engelska tecken i mappsökvägen för att starta körbara filer.
