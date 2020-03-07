---
description: Ställ in filen insight.zbin för att ställa in klientprogrammets språk.
solution: Analytics
title: Konfigurera lokaliserade språk
topic: Data workbench
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera lokaliserade språk{#setting-up-localized-languages}

Ställ in filen insight.zbin för att ställa in klientprogrammets språk.

## Uppdatera serverkomponenterna för data workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Administratören måste först utföra dessa åtgärder för att uppdatera dessa serverkomponenter:

1. **Uppdatera till data workbench-server 6.x.** Du måste uppdatera data workbench-servern för lokalisering genom att uppdatera [!DNL base\localization\*.zbin] filen. Den här [!DNL insight.zbin] filen kopieras sedan till klienten.

   En [!DNL insight.zbin] fil inkluderas i installationsmappen bredvid [!DNL insight.exe] filen. Om du ansluter till en server som inte ger dig språkspecifika [!DNL .zbin] filer fortsätter data workbench att använda den här filen.

   Säkerhetskopian kan [!DNL insight.zbin] finnas på vilket språk som helst. Om du använder data workbench på kinesiska och ansluter till en server som inte har stöd för det här språket, kommer din data workbench-klient fortfarande att vara på kinesiska, även om servern ändrar din basprofil och tar bort dina [!DNL .zbin] filer från [!DNL Base/Localization] mappen.

1. **Uppdatera rapportservern för data workbench.** Mappen [!DNL insight.zbin] i rotmappen för data workbench-rapportservern är som standard på engelska. Som administratör måste du markera och kopiera [!DNL .zbin] filen från det uppdaterade rapportserverpaketet och placera den i rotkatalogen för data workbench-rapportservern. Precis som klienten kräver rapportservern även rätt argument för det valda språket, som [!DNL Insight.exe -zh-cn]

   1. Stoppa rapportservertjänsterna.
   1. Kopiera [!DNL Localization] mappen från det nya rapportserverpaketet.
   1. Kopiera från [!DNL Localization] mappen [!DNL Insight.zbin] filen och placera den i rotkatalogen på rapportservern där den [!DNL Insight.exe] finns.

   1. Lägg till obligatoriska argument, som [!DNL insight.exe -zh-cn]
   1. Starta om rapportservern.

## Uppdatera data workbench-klienten {#section-9653d3fcaf2a4337a97b685857e7aeac}

När du har uppdaterat servern följer du de här stegen för att uppdatera varje klient.

1. Om du vill vara säker på att klienten inte uppdateras från servern under uppdateringen anger du värdet False för ditt [!DNL Insight.cfg] argument.

   ```
   Update Software = bool: false
   ```

1. Starta om klienten.
1. Navigera till profilen Software and Docs (SoftDocs-profilen) och hämta den nödvändiga **[!UICONTROL insight.zbin]** filen från klientpaketet: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Flytta [!DNL insight.zbin] filen till den mapp där [!DNL insight.exe] den finns.

1. Om du vill vara säker på att klientfilerna nu uppdateras från servern ändrar du argumentet [!DNL Insight.cfg] file till True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Klienten synkroniseras med servern och ett meddelande om att den uppdateras visas. När nedladdningen är klar får du ett meddelande där du tillfrågas om du vill starta om klienten.

1. Klicka på **OK** för att starta om klienten.

Om du får följande meddelande betyder det att [!DNL zbin] filen inte placerades på samma plats som [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Lokaliserade välkomstskärmar**

Data workbench söker efter följande välkomstskärmsfiler:

* Engelska (standard): [!DNL Base/Images/<version_product> Splash.png]
* Kinesiska (när den startas med -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Om en välkomstskärm begärs men saknas kommer data workbench att få åtkomst till den engelska välkomstskärmen som standard.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

