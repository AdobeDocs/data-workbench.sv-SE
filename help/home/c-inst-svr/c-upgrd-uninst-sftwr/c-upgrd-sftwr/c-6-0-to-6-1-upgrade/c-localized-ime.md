---
description: Data workbench har nu stöd för IME (Input Method Editor) som en sekundär textinmatningsprocess för internationella språk.
solution: Analytics
title: Installera Indatametodredigeraren
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installera Indatametodredigeraren{#installing-the-input-method-editor}

Data workbench har nu stöd för IME (Input Method Editor) som en sekundär textinmatningsprocess för internationella språk.

Med IME-program kan du ange internationella tecken på ett antal olika sätt som passar ditt lokala språk. Data Workbench innehåller en inmatningsdialogruta där du kan öppna och använda önskat IME-program för textfält.

>[!NOTE]
>
>I version 6.1 av data workbench stöds endast det virtuella förenklade kinesiska tangentbordet. Om du anger andra språk via IME-programmet kan det leda till oväntat beteende.

## Använda en IME {#section-5f008d75a7b24119ab6aebc55454f927}

Så här använder du den flytande IME-textinmatningsfunktionen:

1. Klicka **[!UICONTROL Alt + Space]** för ett textinmatningsområde.
1. Ange värden med hjälp av systemets IME.
1. Stäng inmatningsdialogrutan genom att markera **[!UICONTROL Enter]** eller klicka på **[!UICONTROL OK]** knappen.

   Dialogrutan försvinner och tecknen visas i det markerade fältet.

**Uppdaterar filen Insight.cfg**

Om du vill använda IME-programmet måste du uppdatera [!DNL Insight.cfg] filen med den här inställningen:

```
Localized IME = bool: true
```

Om den här inställningen inte finns i konfigurationsfilen aktiveras inte IME-funktionen när du trycker **[!UICONTROL Alt + Space]** på den.

**Startar Insight på ett annat språk:** För att få bättre stöd för lokaliserade resurser som välkomstskärm och för att kunna hantera flera språk i framtiden, kräver data workbench kommandoradsargument som anger vilket språk som ska läsas in. Standardspråket är engelska.

Om du startar data workbench på kinesiska måste du anropa [!DNL Insight.exe] med argumentet&quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Dessa kommandoradsargument är inte skiftlägeskänsliga.)
