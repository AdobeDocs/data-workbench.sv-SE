---
description: Integrera Data Workbench med Adobe Target. Exportera datasegment och fyll i exportfiler automatiskt.
title: Integrering av Data Workbench med Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%

---

# Integrering av Data Workbench med Adobe Target

Integrationen av Adobe Data Workbench med Adobe Target har blivit enklare tack vare Datan Workbench som exporterar datasegment och automatiskt fyller i exportfiler.

Adobe Data Workbench är integrerat med Adobe Target för datautbyte och rapportgenerering. Inom Datan Workbench kan ni analysera populationer för meningsfulla segment med hjälp av alla tillgängliga data, inklusive offline-konverteringar via kanaler som telefon, butik och så vidare.

En besökare söker till exempel efter skor på webbplatsen men konverterar inte. Istället laddar besökaren ned en kupong för 20 procent av nästa inköp och köper sedan en skjorta i din butik. Med Data Workbench kan ni samla in data och sedan överföra profildata tillbaka till Target för att visa att besökaren har köpt en skjorta offline. Sedan kan ni rikta in er på en kampanj som ger besökaren en hink, när Target normalt försöker återmarknadsföra skor till den besökaren.

## Konfigurera Data Workbench med Adobe Target

1. Högerklicka på rubriken i [!UICONTROL Detail Table]-fönstret.

   ![](assets/insight-to-tnt.png)

1. Välj **[!UICONTROL New Target Export]** och ange namnet på en ny exportfil under kommandot **[!UICONTROL Save As]** på menyn.

1. Klicka på **[!UICONTROL Save Export File]**.

   Ett fönster med exportmallar öppnas.

   All Adobe Target-information fylls i automatiskt. Den skapar parameterlistan baserat på vad du placerar i segmentexporten. När det är klart skickar Datan Workbench data till Adobe Target-servern.

   **Obs!** Mallfilen bör konfigureras av  [!UICONTROL Profile Architect]. Du måste ange [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] och [!UICONTROL Mbox Name]. Om du har flera webbplatser kan du fylla i flera mallar och spara dem på servern. Mallarna från Profilhanteraren finns i `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Ange frågeparametern [!UICONTROL mboxPC].

   Om namnet på attributet Data Workbench är något annat än [!UICONTROL mboxPC] måste du redigera rätt frågeparameter och ändra dess namn till _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   När du sparar exportfilen på servern börjar exporten. När det är klart startas [!UICONTROL TnTSend.exe]-programmet och data skickas till Target-kontot.

## Konfigurera Data Workbench för mål

Utför följande uppgifter i Adobe Target:

Datan Workbench skickar användarprofiler till Adobe Target. Om du vill konfigurera för export till Target måste du konfigurera och aktivera dess API och ange parametrarna **[!UICONTROL clientname]** och **[!UICONTROL domain postfix]** för exportkonfigurationsfilen (`export.cfg`).

Ett nytt booleskt alternativ med namnet **[!UICONTROL Oneshot]** har lagts till i segmentexportfiler. Det här alternativet ingår i mallfilen som distribueras med den nya profilen. Om [!UICONTROL Oneshot] är inställt på _true_ ändras namnet på `.export`-filen till `.export.done-TIMESTAMP` när exporten är slutförd, så att segmentet aldrig exporteras mer än en gång. Detta är viktigt när du exporterar till Adobe Target.

**Obs!** Ett anrop från Data Workbench till Adobe Target räknas som ett  [!UICONTROL mbox] samtal, vilket kräver ett anrop för varje skickad profil. Följaktligen ökar kostnaderna om det krävs flera samtal mellan de båda lösningarna.

En ofullständig konfiguration ger följande felmeddelande i loggen:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Konfigurera Adobe Target för Data Workbench

Inom Adobe Target behövs ingen specialkonfiguration för att en kund ska kunna skicka profildata. Profilinformationen för en användare skickas vanligtvis i den vanliga [!UICONTROL mbox]-begäran, och servrarna gör profilparametrarna tillgängliga för en målinriktad kampanjkonfiguration som standardfunktioner utan ytterligare konfiguration.

Adobe Target har inbyggda funktioner för integrering av Data Workbench, som kan aktiveras från sidan Klientinformation för superanvändare. Om du aktiverar alternativet kommer segment som delas från Datan Workbench i Adobe Target att visas för målinriktning.

## Ange HTTP-loggrapportering i ExportIntegration.exe

Minska den långa rapporteringen till [!UICONTROL HTTP.log] när du använder [!UICONTROL ExportIntegration.exe] för att exportera Adobe Target-integreringsfiler.

Med en ny [!UICONTROL httpLoggingEI.cfg]-konfigurationsfil (som finns på `server\Admin\Export\httpLoggingEI.cfg`) kan du minska den utförliga loggningen till [!UICONTROL HTTP.log]-filen när du exporterar data med [!UICONTROL ExportIntegration.exe]. På så sätt kan du stoppa utförlig loggning av begäranden/svar.

Utförlig loggning har redan hämtats i [!UICONTROL TnTSend.log]-filer.

_Truesets_ loggar utförligt och  __ Flash stoppar utförligt loggning till  [!UICONTROL HTTP.log] fil.

I inställningen Falskt skickas bara ett varningsmeddelande till filen [!UICONTROL HTTP.log] (Info-innehåll skickas inte).
