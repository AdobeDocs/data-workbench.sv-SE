---
description: Webbplatsen använder cookies för att unikt identifiera besökare på webbplatsen och spåra deras beteende över tid.
title: Förstå v1st-cookien
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# Förstå v1st-cookien{#understanding-the-v-st-cookie}

Webbplatsen använder cookies för att unikt identifiera besökare på webbplatsen och spåra deras beteende över tid.

Första gången en viss webbläsare (som betraktas som besökare) gör en begäran på din webbplats, använder [!DNL Sensor] din webbserver för att ange en beständig cookie, cs(cookie)(v1st), som tolkas internt i systemet som x-trackingid. Den här beständiga cookien ställs in utöver eventuella andra cookies som webbplatsen annars kan ställa in. Denna cookie optimerar möjligheten att spåra besökare över flera sessioner, vilket möjliggör många typer av analyser som annars är omöjliga.

[!DNL Sensor] tilldelar en 64-bitars numerisk nyckel i cookien för att identifiera nya besökare som gör en begäran om webbplatsen till en unik identifierare. När [!DNL Sensor] ser en begäran från en webbläsare kontrollerar den om &quot;cs(cookie)(v1st)&quot;, en beständig cookie som är inställd på [!DNL Sensor] från första part, finns i begärandata. Om cs(cookie)(v1st) inte finns anger [!DNL Sensor], via webbservern, att webbläsaren ska ställa in den. Till skillnad från andra lösningar kan [!DNL Sensor] ange den här cookien på besökarens första begäran.

Nedan visas den vanliga beständiga cookie-rubriken som skickas till webbläsaren på din första begäran av webbplatsen av webbservern, i riktningen [!DNL Sensor]. Formatet kan definieras vid konfigurationstidpunkten om du vill ha ett annat namn eller ett annat utgångsdatum. Exempel:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Den här cookie-filen ställs bara in en gång på den första begäran som besökaren gjort till din webbplats. Den samlas sedan in från besökaren varje gång webbläsaren gör en begäran (antingen sida eller inbäddade objektbegäranden) om webbplatsen i framtiden. Cookien är mycket liten för att minimera den bandbredd som används för att överföra den till dina servrar med varje begäran från den webbläsaren till din webbplats.

Det är webbläsaren som bestämmer om en beständig cookie ska godkännas. De flesta webbanvändare förstår vad cookies gör och inser också att cookies från första part ger dem en värdefull fördel genom att tillåta att webbplatsinnehåll anpassas efter deras önskemål. Dessa cookies från första part blockeras inte av standardsäkerhetsinställningarna för de populära webbläsarna. Om en användare väljer att blockera cookies från första part loggas fortfarande deras sidvisningsbegäranden, men mätdata från dessa begäranden kan inte på ett tillförlitligt sätt korreleras till en viss besökare eller deras sessioner på webbplatsen. Många webbplatser, särskilt avancerade dynamiska webbplatser, använder redan cookies från första part, som i många fall är nödvändiga för att webbprogram ska kunna fungera för besökaren. Ett steg tillbaka från en beständig cookie är en sessionscookie som gör att en serie begäranden kan slås ihop till en session, men som inte tillåter uppföljning av besökare mellan sessioner. [!DNL Site] kan samla besöksdata baserat på sessionscookies eller IP-nummer, men båda metoderna minskar avsevärt de typer och det värde av analys som kan utföras med  [!DNL Site] eller andra system för analys och rapportering av webbaktiviteter.
