---
description: Information om hur du löser webbserverproblem, t.ex. om webbservern tas bort från rotationen eller om webbservern inte fungerar.
title: Förstå orsakerna
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Förstå orsakerna{#understanding-the-causes}

{{eol}}

Information om hur du löser webbserverproblem, t.ex. om webbservern tas bort från rotationen eller om webbservern inte fungerar.

## När en webbserver tas bort från roteringen {#section-b9f709099cb44b4f9d1acb38ca5330e3}

När en webbserver tas bort från rotationen från en serverpool, men på annat sätt är ansluten till den sändare som skickar periodiska hjärtslag, är från och med-tiden aktuell och ingen åtgärd krävs från någons sida.

## När en webbserver misslyckas {#section-19280cf83ca44bd7b1ee11bfc74494d2}

När en webbserver är helt offline på grund av ett allvarligt fel, eller inte skickar data eller pulsslag, visas tiden på [!DNL data workbench server] stoppar för att garantera att det representerar den senaste gången [!DNL data workbench server] har tagit emot data från ALLA de datakällor som de känner till. Själva systemet fortsätter att bearbeta data, som fortfarande är tillgängliga för analys i Data Workbench, men allt i [!DNL data workbench server] som baseras på att tidpunkten inte fungerar. Från och med-tiden utlöser till exempel rapportering och används för att skapa många härledda dimensioner i systemet. När tidpunkten har stoppats aktiveras inte rapportering och dessa härledda dimensioner är inte tillgängliga.

Om WEB2 till exempel kopplades från den 15 juni och inte skickade några data på fem dagar, skulle tiden vara den 15 juni. Gårdagens dimension skulle till exempel vara den 14 juni trots att dagens datum är den 20 juni.
