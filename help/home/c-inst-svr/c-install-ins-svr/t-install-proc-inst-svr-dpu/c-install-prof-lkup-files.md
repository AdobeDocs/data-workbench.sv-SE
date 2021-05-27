---
description: De profiler och sökfiler som Adobe har utvecklat för just ditt program är interna profiler som innehåller mått, dimensioner och arbetsytor som gör det möjligt att analysera datauppsättningen.
title: Installera profiler och sökfiler
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Installerar profiler och sökfiler{#installing-profiles-and-lookup-files}

De profiler och sökfiler som Adobe har utvecklat för just ditt program är interna profiler som innehåller mått, dimensioner och arbetsytor som gör det möjligt att analysera datauppsättningen.

Precis som med alla andra interna profiler från Adobe bör dessa profiler inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Adobe distribuerar profil- och sökfiler för programmet som en [!DNL .zip]-fil. Varje zip-fil namnges för det program vars profil och sökningsfiler den innehåller. (Till exempel innehåller [!DNL Site52.zip] profilfilerna för Site v5.2.) Filen [!DNL .zip] innehåller två mappar ( [!DNL Lookups] och [!DNL Profiles]).

>[!NOTE]
>
>Om du inte redan har installationsfilen som innehåller profilerna och sökfilerna för programmet kan du hämta dem från FTP-platsen i Adobe innan du börjar.

Du måste installera profilen och dess sökfiler på den [!DNL Insight Server]-dator som du bearbetar och kör datauppsättningsprofilen på. Om du kör ett [!DNL Insight Server]-kluster måste du installera filerna på den överordnad servern. Mer information om datauppsättningsprofiler finns i *Konfigurationshandboken för datauppsättningar*.

**Så här installerar du profiler för ditt Adobe-program**

1. Öppna mappen [!DNL Profiles] från filen [!DNL .zip] som du har fått från Adobe.

1. Kopiera alla mappar i mappen [!DNL Profiles] i filen [!DNL .zip] till mappen [!DNL Profiles] i installationskatalogen för [!DNL Insight Server]. Du vill avsluta med  [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>*-mappar på [!DNL Insight Server] enligt följande exempel. De faktiska profilnamnen kan variera.

   ![](assets/win_installprofiles.png)

1. Navigera till mappen  [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* i den katalog där du installerade [!DNL Insight Server] och leta reda på filen [!DNL profile.cfg] i den här katalogen.

   >[!NOTE]
   >
   >Om du installerar profiler för första gången kan du använda den medföljande exempelprofilen som datauppsättningsprofil. Du kan hitta filen [!DNL profile.cfg] (den kan ha namnet [!DNL profile.cfg.offline]) för exempelprofilen i mappen [!DNL Profiles\Sample] i installationskatalogen för [!DNL Insight Server].

1. Öppna [!DNL profile.cfg]-filen med en textredigerare som Anteckningar och gör följande:

   1. Lägg till poster för de interna profilerna i katalogvektorn. Profilnamnen motsvarar namnen på katalogerna som du kopierade till mappen [!DNL Profiles] på datorn [!DNL Insight Server].

   1. Uppdatera antalet kataloger efter behov.
   1. Lägg till serverns vanliga namn på raden Gemensamt namn i den här filen, vilket markeras nedan:

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >Det *serverCommonName*-namn som du anger för det vanliga namnet i [!DNL profile.cfg]-filen motsvarar serverns allmänna namn för den [!DNL Insight Server]-dator där du bearbetar och kör datauppsättningsprofilen. Instruktioner om hur du uppdaterar [!DNL profile.cfg] så att datauppsättningsprofilen körs i ett [!DNL Insight Server]-kluster finns i [Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Spara filen. Spara filen som [!DNL profile.cfg] om den har ett annat namn.

**Så här installerar du sökfiler för Adobe-programmet**

1. Öppna mappen [!DNL Lookups] från filen [!DNL .zip] som du har fått från Adobe.

1. Kopiera alla mappar i mappen [!DNL Lookups] i filen [!DNL .zip] till mappen [!DNL Lookups] i installationskatalogen för [!DNL Insight Server]. Du vill avsluta med  [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>*-mappar på [!DNL Insight Server] enligt följande exempel. De faktiska profilnamnen kan variera.

   ![](assets/win_installLookups.png)
