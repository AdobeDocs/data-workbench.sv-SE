---
description: Integrera Data Workbench med Adobe Target. Exportera datasegment och fyll i exportfiler automatiskt.
title: Integrering av Data Workbench med Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%

---

# Integrering av Data Workbench med Adobe Target

{{eol}}

Integrationen av Adobe Data Workbench med Adobe Target har blivit enklare tack vare Datan Workbench som exporterar datasegment och automatiskt fyller i exportfiler.

Adobe Data Workbench är integrerat med Adobe Target för datautbyte och rapportgenerering. Inom Datan Workbench kan ni analysera populationer för meningsfulla segment med hjälp av alla tillgängliga data, inklusive offline-konverteringar via kanaler som telefon, butik och så vidare.

En besökare söker till exempel efter skor på webbplatsen men konverterar inte. Istället laddar besökaren ned en kupong för 20 procent av nästa inköp och köper sedan en skjorta i din butik. Med Data Workbench kan ni samla in data och sedan överföra profildata tillbaka till Target för att visa att besökaren har köpt en skjorta offline. Sedan kan ni rikta in er på en kampanj som ger besökaren en hink, när Target normalt försöker återmarknadsföra skor till den besökaren.

## Konfigurera Data Workbench med Adobe Target

1. Högerklicka på rubriken i [!UICONTROL Detail Table] -fönstret.

   ![](assets/insight-to-tnt.png)

1. Välj **[!UICONTROL New Target Export]** och ange namnet på en ny exportfil under **[!UICONTROL Save As]** på menyn.

1. Klicka på **[!UICONTROL Save Export File]**.

   Ett fönster med exportmallar öppnas.

   All Adobe Target-information fylls i automatiskt. Den skapar parameterlistan baserat på vad du placerar i segmentexporten. När det är klart skickar Datan Workbench data till Adobe Target-servern.

   **Obs!** Mallfilen bör konfigureras av [!UICONTROL Profile Architect]. The [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host]och [!UICONTROL Mbox Name] måste anges. Om du har flera webbplatser kan du fylla i flera mallar och spara dem på servern. Mallarna från Profilhanteraren finns i `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Ange [!UICONTROL mboxPC] frågeparameter.

   Om Datan Workbench-attributets namn är något annat än [!UICONTROL mboxPC]måste du redigera rätt frågeparameter och byta namn på den till _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   När du sparar exportfilen på servern börjar exporten. När du är klar visas [!UICONTROL TnTSend.exe] startas och skickas till Target-kontot.

## Konfigurera Data Workbench för mål

Utför följande uppgifter i Adobe Target:

Datan Workbench skickar användarprofiler till Adobe Target. Om du vill konfigurera för export till Target måste du konfigurera och aktivera dess API och ange **[!UICONTROL clientname]** och **[!UICONTROL domain postfix]** parametrar för exportkonfigurationsfilen (`export.cfg`).

Ett nytt booleskt alternativ anropades **[!UICONTROL Oneshot]** har lagts till i segmentexportfiler. Det här alternativet ingår i mallfilen som distribueras med den nya profilen. If [!UICONTROL Oneshot] är inställd på _true_ och sedan `.export` filen byter namn till `.export.done-TIMESTAMP` när exporten är klar, så att segmentet aldrig exporteras mer än en gång. Detta är viktigt när du exporterar till Adobe Target.

**Obs!** Ett samtal från Datan Workbench till Adobe Target räknas som [!UICONTROL mbox] anrop, kräver ett samtal för varje skickad profil. Följaktligen ökar kostnaderna om det krävs flera samtal mellan de båda lösningarna.

En ofullständig konfiguration ger följande felmeddelande i loggen:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Konfigurera Adobe Target för Data Workbench

Inom Adobe Target behövs ingen specialkonfiguration för att en kund ska kunna skicka profildata. Profilinformationen för en användare skickas vanligtvis i den vanliga [!UICONTROL mbox] förfrågan, och servrarna kommer att göra profilparametrarna tillgängliga för en målinriktad kampanjkonfiguration som standardfunktioner utan ytterligare konfiguration.

Adobe Target har inbyggda funktioner för integrering av Data Workbench, som kan aktiveras från sidan Klientinformation för superanvändare. Om du aktiverar alternativet kommer segment som delas från Datan Workbench i Adobe Target att visas för målinriktning.

## Ange HTTP-loggrapportering i ExportIntegration.exe

Minska långa rapporter till [!UICONTROL HTTP.log] när [!UICONTROL ExportIntegration.exe] för att exportera Adobe Target integreringsfiler.

En ny [!UICONTROL httpLoggingEI.cfg] konfigurationsfil (finns på `server\Admin\Export\httpLoggingEI.cfg`) kan du reducera utförlig loggning till [!UICONTROL HTTP.log] fil för när data exporteras med [!UICONTROL ExportIntegration.exe]. På så sätt kan du stoppa utförlig loggning av begäranden/svar.

Utförlig loggning har redan hämtats in [!UICONTROL TnTSend.log] filer.

_True_ anger utförlig loggning, och _Falskt_ stoppar utförlig loggning till [!UICONTROL HTTP.log] -fil.

I inställningen Falskt skickas endast ett varningsmeddelande till [!UICONTROL HTTP.log] fil (Info-innehållet skickades inte).
