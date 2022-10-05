---
description: Ställ in filen insight.zbin för att ställa in klientprogrammets språk.
title: Konfigurera lokaliserade språk
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
exl-id: 29624b3a-e26a-48a9-9dcc-21ba829c34d4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Konfigurera lokaliserade språk{#setting-up-localized-languages}

{{eol}}

Ställ in filen insight.zbin för att ställa in klientprogrammets språk.

## Uppdatera serverkomponenterna för data workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

Administratören måste först utföra dessa åtgärder för att uppdatera dessa serverkomponenter:

1. **Uppdatera till data workbench-server 6.x.** Du måste uppdatera data workbench-servern för lokalisering genom att uppdatera [!DNL base\localization\*.zbin] -fil. Detta [!DNL insight.zbin] filen kopieras sedan till klienten.

   An [!DNL insight.zbin] filen finns i installationsmappen bredvid [!DNL insight.exe] -fil. Om du ansluter till en server som inte ger dig språkspecifik [!DNL .zbin] filer kommer data workbench att fortsätta använda den här filen.

   Säkerhetskopian [!DNL insight.zbin] filen kan finnas på vilket språk som helst. Om du använder data workbench på kinesiska och ansluter till en server som inte har stöd för det här språket, kommer din data workbench-klient fortfarande att vara på kinesiska, även om servern ändrar din basprofil och tar bort din [!DNL .zbin] filer från [!DNL Base/Localization] mapp.

1. **Uppdatera rapportservern för data workbench.** The [!DNL insight.zbin] i rotmappen för data workbench-rapportservern kommer att vara på engelska som standard. Som administratör måste du markera och kopiera [!DNL .zbin] från det uppdaterade rapportserverpaketet och placera det i rotkatalogen på data workbench-rapportservern. Precis som klienten kräver rapportservern även rätt argument för det valda språket, som [!DNL Insight.exe -zh-cn]

   1. Stoppa rapportservertjänsterna.
   1. Kopiera [!DNL Localization] från det nya rapportserverpaketet.
   1. Från [!DNL Localization] mapp, kopiera [!DNL Insight.zbin] filen och placera den i rotkatalogen på rapportservern där [!DNL Insight.exe] finns.

   1. Lägg till obligatoriska argument, som [!DNL insight.exe -zh-cn]
   1. Starta om rapportservern.

## Uppdatera data workbench-klienten {#section-9653d3fcaf2a4337a97b685857e7aeac}

När du har uppdaterat servern följer du de här stegen för att uppdatera varje klient.

1. Om du vill vara säker på att klienten inte uppdateras från servern under uppdateringen ställer du in [!DNL Insight.cfg] argument till False.

   ```
   Update Software = bool: false
   ```

1. Starta om klienten.
1. Navigera till profilen Software and Docs (SoftDocs-profilen) och ladda ned den **[!UICONTROL insight.zbin]** från klientpaketet: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Flytta [!DNL insight.zbin] till mappen där [!DNL insight.exe] finns.

1. Om du vill vara säker på att klientfilerna nu uppdateras från servern ändrar du [!DNL Insight.cfg] filargument till True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Klienten synkroniseras med servern och ett meddelande om att den uppdateras visas. När nedladdningen är klar får du ett meddelande där du tillfrågas om du vill starta om klienten.

1. Klicka **OK** för att starta om klienten.

Om du får följande meddelande betyder det [!DNL zbin] filen placerades inte på samma plats som [!DNL Insight.exe].

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
