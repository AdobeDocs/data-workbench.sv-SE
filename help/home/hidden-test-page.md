---
title: Dold testsida
description: Den här sidan är dold för sökning och från innehållsförteckningen
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Ladda ned Premium"
badgeExam: label="tentamen ADO-E903" type="neutral"
exl-id: 25669153-b90c-4cf6-81aa-cabcbf2cbcb6
source-git-commit: 3480cc9b82a5561a364a88f3d09c14cca56a0c7a
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Dold testsida

## Problem med förhandsgranskning

Följande stycke återges inte korrekt i VSC-förhandsvisning. Jag är inte säker på varför.

Om ditt lösenord hanteras av [!DNL Adobe]kan du [ändra lösenordet i ditt Adobe-konto](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## Anteckningstyper

Alla anteckningstyper som stöds.

>[!NOTE]
>
>Det här är ett vanligt NOTE-block.

>[!TIP]
>
>Det här är ett standardtips.

>[!IMPORTANT]
>
>Detta är en viktig anteckning.

>[!WARNING]
>
>Det här är en varning.

>[!CAUTION]
>
>Det här är en försiktighet.

>[!ADMIN]
>
>Det här är en administratörsanteckning som återges som ADMINISTRATION. Endast EXL.

>[!AVAILABILITY]
>
>Det här är en tillgänglighetsanteckning. Endast EXL.

>[!PREREQUISITES]
>
>Detta är en kravnotering. Endast EXL.

>[!INFO]
>
>Det här är en Info note. Endast EXL.

>[!ERROR]
>
>Det här är en felanteckning. Endast EXL.

>[!SUCCESS]
>
>Detta är en Success note. Endast EXL.

>[!MORELIKETHIS]
>
>* Sida 1
>* Sidan 2

## Badges

Ett märke är en färgad etikett som används som innehållsindikator. Du kan till exempel lägga till ett märke för att markera en artikel som _Beta_ eller ett avsnitt som _Premium_. Du kan ändra färg på ett märke och koppla en URL och ett verktygstips.

[!BADGE Exempel på badge]

Det finns två typer av emblem med olika syntax:

* **Metadata** - Visar märket nära en sidas överkant
* **Textbunden** - Visar märket där syntaxen finns

### Metadata-emblem

Om du lägger till märkordssyntax i metadata placeras ett märke ovanför sidrubriken (H1) i artikeln.

Du kan till exempel namnge emblem med _badge1_ eller _badge2_. Eller så kan du vara mer kreativ (förutsatt att namnet börjar med _bricka_).

Exempel på metadata:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** I det här exemplet visas ett Premium-märke med en URL och ett funktionsbeskrivning.

* **badgeExam:** I det här exemplet visas ett mörkt märke med ett ID-nummer för tentamen.

#### Infogade emblem

Ange information om emblem på sin egen rad eller i en rubrik, tabell eller något annat sidelement.

Här är syntaxen för ett infogat märke med en betaetikett, blå färg, URL-adress och verktygstips:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Tillgängliga märkordsfärger

För märken används färger som definieras i Adobe Spectrum:

| Typ | Badge |
|---|---|
| Informativ (standard) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positiv | [!BADGE Ny funktion]{type=Positive url="https://www.example.com" tooltip="Gå till example.com"} |
| Negativ | [!BADGE Avbruten]{type=negative tooltip="Den här funktionen är nu inte längre aktiv"} |
| Neutral | [!BADGE Kanske]{type=Neutral tooltip="En ryttare föll av hästen..."} |
| Varning | [!BADGE Attention]{type=Caution tooltip="Gul status"} |

Exempel på syntax

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Krav för emblem

* Endast två märken tillåts i metadata. Den här regeln kan konfigureras, så berätta för oss om du behöver ett undantag.
* Endast etiketten krävs. The `type`, `url`och `tooltip` parametrar är valfria. The `type` -parametern bestämmer färgen. The `url` kan användarna klicka på märket för att öppna en artikel eller sida. The `tooltip` -parametern visar verktygstipstexten när muspekaren förs över.
* Lägga till ett märke i `TOC.md` filen visar märket på alla artiklar i guiden. Om du anger en URL-adress där emblemet ska hoppa till en artikel måste du använda en rotlänk (t.ex. `/help/guide/article.md`) inte är en relativ länk (t.ex. `article.md`) för att ta hänsyn till artiklar i olika mappar.
* Lägga till ett märke till `metadata-new.md` visar märket på alla artiklar i ett svar.
* Se till att alla värden är omslutna av citattecken för metadatamärken. För infogade emblem måste du se till att `url` och `tooltip` är omslutna av citattecken.
* Giltiga typvärden är *Informativ* (standard, blå), *Positiv* (grönt), *Negativ* (röd), *Neutral* (mörkgrå), och *Varning* (gult).
* Märkesetiketter är lokaliserade.
* Om flera metadatamärkningar anges visas märken i alfabetisk ordning baserat på märkordsnamnet, till exempel `badge1:` eller `badgeWeb`.
* Om du vill att URL:en ska öppnas på en ny flik använder du den här syntaxen:

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  Återgiven:

  [!BADGE Öppna på ny flik]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Öppna adobe.com på en ny flik"}

## Textmarkering

Workfront-teamet bad om att få använda gula markeringar för att visa hur man förhandsgranskar kommande funktioner. Så här fungerar det.

Exempel 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Återgiven:

Hela stycket ska INTE markeras. <span class="preview"> Det här ordet är **fet** inuti en markerad mening.</span> Och det här är bara den sista meningen.

Exempel 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

Återgiven:

Markeringen ska börja efter det här stycket.

<div class="preview">

DIV börjar.

Det här är ett nytt stycke och sedan en bild

![image](/help/home/assets/analytics-icon-24.png)

Senast markerat objekt.

</div>

Ej markerad

## Syntaxmarkering för kodblock

Experience League har stöd för syntaxmarkering för kodblock. Se till att du anger ett språk som `java` efter den första uppsättningen bakåttickningar för att säkerställa att syntaxen är korrekt markerad. En lista över giltiga språk finns på [https://prismjs.com](https://prismjs.com/#supported-languages). Om några språk saknas, logga en jira-biljett.

### Radnumrering i kodblock

Lägg till `{line-numbers="true"}` efter språket för att aktivera radnumrering.

Exempel med radnummer (&amp;grav;&amp;grav;&amp;grav;;)`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Börja numrera på rad _**

Lägg till `start-number="n"` efter radnummersyntax för att starta numreringen på ett annat nummer än 1.

Exempel med ny startrad (&amp;grav;&amp;grav;&amp;grav;);`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Markering av rader i kodblock

Lägg till `highlight="n"` efter radnummersyntax för att markera rader i ett kodblock. Ange `11-13, 16` markerar raderna 11 till 13 och 16.

Exempel med radmarkering (&amp;grav; &amp;grav;&amp;grav;;;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
