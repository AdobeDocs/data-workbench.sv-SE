---
description: En uppsättning standardprofiler för varje program har skapats så att en eller flera av profilerna kan installeras vid en given tidpunkt.
title: Baslinjeprofiler
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
exl-id: f1bd5c1d-5f79-4b8c-9928-97169d553631
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Baslinjeprofiler{#baseline-profiles}

En uppsättning standardprofiler för varje program har skapats för att göra det möjligt att installera en eller flera av profilerna samtidigt.

Dessa baslinjeprofiler innehåller definitioner av standardmått, dimensioner, filter, rapporter, arbetsytor och kontrollpaneler. Adobe uppdaterar dessa profiler kontinuerligt och gör dem tillgängliga för sina licenstagare via sitt program för programsupport. Dessutom kan användare av Adobe-program definiera ytterligare profiler och använda dem med eller i stället för de profiler som tillhandahålls av Adobe.

Med hjälp av profilhanteringssystemet kan du åsidosätta en profils konfigurationer med profiler på högre nivå. Använd den här funktionen när du vill åsidosätta någon av de definitioner som ingår i de här profilerna när de har installerats. Om nya versioner av dessa profiler installeras skrivs alla tidigare versioner över. Det innebär att ändringar som görs direkt i dessa profiler skrivs över när de nya profilerna installeras.

Profiler för vertikala marknader eller särskilda typer av företag eller branscher kan också vara tillgängliga från Adobe ClientCare. Här följer beskrivningar av baslinjeprofilerna:

* **Basprofilen** innehåller konfigurationsfiler som levereras med Insight Server. Basprofilen bör inte ändras av användaren eller administratören. Alla ändringar som görs i basprofilen kan skrivas över när Adobe släpper en nästa version av Insight Server eller något annat program.
* **Trafikprofilen** innehåller en uppsättning grundläggande mått, dimensioner och filter för webbanalys. Det innehåller också mallarbetsytor, rapporter och kontrollpaneler som gör det lättare att analysera, rapportera om och förstå aktivitetstrender och mönster för webbplatser som helhet. Den här profilen fungerar&quot;utanför ramarna&quot; med en baslinjeinstallation av Site.
* **Värdeprofilen** innehåller en uppsättning mått och dimensioner samt mallarbetsytor, rapporter och kontrollpaneler som är kopplade till det inbyggda affärsvärdet och konverteringsmodellen för webbplatsen. Med den här profilen kan användare identifiera värdehändelser på webbplatsen och associera ett penningvärde till dessa händelser.

   Den här profilen utökar funktionerna för webbplatsanalys genom att tillhandahålla en affärsvärdesmodell, en avancerad metod för att mäta och spåra den mängd värde som genereras av din webbplats. Värdehändelser och deras relativa värden definieras via ett enkelt dra och släpp-gränssnitt inom Site. Webbplatsen använder dessa definitioner för att beräkna det affärsvärde som genereras av varje session, och den här informationen används i sin tur för att definiera mått som värde, värdehändelser, konvertering och så vidare. Med dessa mätvärden kan du svara på frågor som:

   * Vilken är den mest lönsamma vägen genom sajten?
   * Vilken hänvisare eller kampanj har genererat mest värde?
   * Vilket är det genomsnittliga antalet köp på webbplatsen per dag? (Hur många värdehändelser inträffar per dag i genomsnitt?)

   När du har definierat en affärsvärdesmodell på webbplatsen kan du använda värdemätningar och mått i din analys.

* **Marknadsföringsprofilen** innehåller en uppsättning mätvärden och dimensioner samt mallarbetsytor, rapporter och kontrollpaneler som är kopplade till analys av Internetmarknadsföringskampanjer, inklusive sökanalys och utökad referensanalys.

Adobe har även följande valfria profiler att använda:

* Profilen **IP Geo-location** innehåller dimensioner och lagerfiler som är relaterade till analysen av besökarnas platser, baserat på IP-geoplatsdata som tillhandahålls Adobe av Quova, Inc. och som ingår i data workbench.
* IP-profilen för geointelligens innehåller dimensioner och lagerfiler som är relaterade till analysen av besökarens platser baserat på IP-geointelligensdata som tillhandahålls Adobe av Digital Envoy, Inc. och som ingår i data workbench.

Om du vill ha information om IP-geo-location- och IP Geo-Intelligence-profiler kontaktar du Adobe support. I följande avsnitt beskrivs de mått och mått som definieras i respektive baslinjeprofil.
