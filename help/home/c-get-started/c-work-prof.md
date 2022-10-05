---
description: Datan Workbench hämtar profiler till datorn.
title: Profiler
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
exl-id: a140f549-448c-4e34-8eae-ad154fa01f1f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Profiler{#profiles}

{{eol}}

Datan Workbench hämtar profiler till datorn.

Om du läser in en profil för första gången måste du ha en nätverksanslutning till [!DNL Data Workbench server] och arbeta online så att Datan Workbench kan hämta de filer som behövs från [!DNL Data Workbench server].

Det kan ta flera minuter att hämta profilen. Du bör inte börja arbeta med profilen förrän datacachen börjar fylla, men du behöver inte vänta tills den är full. Du kan spåra förloppet för datacachen, förloppet för profilsynkroniseringen samt datum och tid för de senast bearbetade data genom att titta på statusfälten när profilen läses in.

>[!NOTE]
>
>Du kan inte se data i visualiseringar som du lägger till förrän datacachen börjar fyllas.

Nästa gång du läser in profilen hämtas bara uppdateringar av profilen och dess data om du har en nätverksanslutning till [!DNL Data Workbench server] och arbetar online. Om du arbetar offline läses profilen och dess data in från datorns cache. I det här fallet visar du vilken version av profilen och vilka data som hämtades senast du arbetade online med profilen. Mer information om att arbeta online eller offline finns i [Arbeta offline och online](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

När du behöver ändra din profil (med [!DNL Profile Manager] eller [!DNL Server Files Manager]) bör du arbeta online för att säkerställa att du har den senaste versionen av profilen. Mer information om [!DNL Profile Manager] och [!DNL Server Files Manager], se [Administrativa gränssnitt](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Om du inte kan komma åt eller läsa in en profil kan du behöva bekräfta följande:

* Du har en nätverksanslutning till [!DNL Data Workbench server] datorn där profilen finns.
* Du har behörighet att komma åt profilen.

Kontakta systemadministratören om du behöver hjälp.

## Läsa in eller växla profiler {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Starta Datan Workbench.
1. Klicka på profilnamnet i sidofältet och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, där *profilnamn* är den profil som du vill arbeta med.

   ![](assets/sidebar_profile.png)

Om det här är första gången du läser in den valda profilen kan det ta flera minuter att hämta tillräckligt med data för att fylla i en visualisering.

## Åtkomst till en profil i ett kluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench som har åtkomst till en profil som körs på en

Data Workbench-serverklustret identifierar bara den överordnad Datan Workbench Server i konfigurationsfilen för Datan Workbench ( [!DNL Insight.cfg]). Från Datans Workbench perspektiv är profilen bara tillgänglig på en Data Workbench-server (den överordnad Data Workbench-servern). Frågebegäranden från analytiker kan dock dirigeras till någon av Datan Workbench i klustret.

Mer information om profiler som körs på ett Data Workbench Server-kluster finns i *Installations- och administrationshandbok för serverprodukter*.
