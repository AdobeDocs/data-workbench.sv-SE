---
description: De profiler och sökfiler som Adobe har utvecklat för just ditt program är interna profiler som innehåller mått, dimensioner och arbetsytor som möjliggör analys av din datauppsättning.
solution: Insight
title: Installera profiler och sökfiler
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Installera profiler och sökfiler{#installing-profiles-and-lookup-files}

De profiler och sökfiler som Adobe har utvecklat för just ditt program är interna profiler som innehåller mått, dimensioner och arbetsytor som möjliggör analys av din datauppsättning.

Precis som med alla andra interna profiler från Adobe bör dessa profiler inte ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar.

Adobe distribuerar profil- och sökfiler för ditt program som en [!DNL .zip] fil. Varje zip-fil namnges för det program vars profil och sökningsfiler den innehåller. (Innehåller till exempel [!DNL Site52.zip] profilfilerna för platsen v5.2.) Filen [!DNL .zip] innehåller två mappar ( [!DNL Lookups] och [!DNL Profiles]).

>[!NOTE]
>
>Om du inte redan har installationsfilen som innehåller profilerna och sökfilerna för programmet kan du hämta dem från Adobes FTP-plats innan du börjar.

Du måste installera profilen och dess sökfiler på den dator som du bearbetar och kör datauppsättningsprofilen på [!DNL Insight Server] . Om du kör ett [!DNL Insight Server] kluster måste du installera filerna på huvudservern. Mer information om datauppsättningsprofiler finns i konfigurationsguiden för *datauppsättningar*.

**Installera profiler för ditt Adobe-program**

1. Öppna [!DNL Profiles] mappen från den [!DNL .zip] fil du fått från Adobe.

1. Kopiera alla mappar i [!DNL Profiles] mappen i [!DNL .zip] filen till [!DNL Profiles] mappen i din [!DNL Insight Server] installationskatalog. Du vill avsluta med [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>* mappar på din dator [!DNL Insight Server] som i följande exempel. De faktiska profilnamnen kan variera.

   ![](assets/win_installprofiles.png)

1. Gå till mappen [!DNL Profiles\]*&lt;[!DNL dataset profile name]>* i den katalog där du installerade [!DNL Insight Server] och leta reda på [!DNL profile.cfg] filen i den här katalogen.

   >[!NOTE]
   >
   >Om du installerar profiler för första gången kan du använda den medföljande exempelprofilen som datauppsättningsprofil. Du kan hitta [!DNL profile.cfg] filen (den kan ha ett liknande namn [!DNL profile.cfg.offline]) för exempelprofilen i [!DNL Profiles\Sample] mappen i din [!DNL Insight Server] installationskatalog.

1. Öppna [!DNL profile.cfg] filen med en textredigerare som Anteckningar och gör följande:

   1. Lägg till poster för de interna profilerna i katalogvektorn. Profilnamnen motsvarar namnen på katalogerna som du kopierade till [!DNL Profiles] mappen på [!DNL Insight Server] datorn.

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
      >Det *serverCommonName* som du anger för det allmänna namnet i [!DNL profile.cfg] filen motsvarar serverns allmänna namn för den dator som du bearbetar och kör datauppsättningsprofilen på [!DNL Insight Server] . Instruktioner om hur du uppdaterar [!DNL profile.cfg] så att datauppsättningsprofilen körs i ett [!DNL Insight Server] kluster finns i [Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. Spara filen. Spara filen som [!DNL profile.cfg] om den har ett annat namn.

**Så här installerar du sökfiler för ditt Adobe-program**

1. Öppna [!DNL Lookups] mappen från den [!DNL .zip] fil du fått från Adobe.

1. Kopiera alla mappar i [!DNL Lookups] mappen i [!DNL .zip] filen till [!DNL Lookups] mappen i din [!DNL Insight Server] installationskatalog. Du vill avsluta med [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>* mappar på din dator [!DNL Insight Server] som i följande exempel. De faktiska profilnamnen kan variera.

   ![](assets/win_installLookups.png)

