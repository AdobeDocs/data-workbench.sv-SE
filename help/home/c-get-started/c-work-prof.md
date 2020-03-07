---
description: Data Workbench hämtar profiler till din dator.
title: Profiler
uuid: 8ea36138-9839-40e5-89e2-4b120f1dd7aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Profiler{#profiles}

Data Workbench hämtar profiler till din dator.

Om du läser in en profil för första gången måste du ha en nätverksanslutning till servern [!DNL Data Workbench server] och arbeta online så att Data Workbench kan hämta de nödvändiga filerna från [!DNL Data Workbench server].

Det kan ta flera minuter att hämta profilen. Du bör inte börja arbeta med profilen förrän datacachen börjar fylla, men du behöver inte vänta tills den är full. Du kan spåra förloppet för datacachen, förloppet för profilsynkroniseringen samt datum och tid för de senast bearbetade data genom att titta på statusfälten när profilen läses in.

>[!NOTE]
>
>Du kan inte se data i visualiseringar som du lägger till förrän datacachen börjar fyllas.

Nästa gång du läser in profilen hämtas bara profiluppdateringar och data om du har en nätverksanslutning till [!DNL Data Workbench server] och arbetar online. Om du arbetar offline läses profilen och dess data in från datorns cache. I det här fallet visar du vilken version av profilen och vilka data som hämtades senast du arbetade online med profilen. Mer information om att arbeta online eller offline finns i [Arbeta offline och online](../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

När du behöver ändra din profil (med hjälp av [!DNL Profile Manager] eller [!DNL Server Files Manager]) bör du arbeta online för att säkerställa att du har den senaste versionen av profilen. Mer information om [!DNL Profile Manager] och [!DNL Server Files Manager]finns i [Administrativa gränssnitt](../../home/c-get-started/c-admin-intrf/c-admin-intrf.md#concept-855c1a91e1a948969fab592adca15f74).

Om du inte kan komma åt eller läsa in en profil kan du behöva bekräfta följande:

* Du har en nätverksanslutning till den dator som profilen finns på [!DNL Data Workbench server] .
* Du har behörighet att komma åt profilen.

Kontakta systemadministratören om du behöver hjälp.

## Läsa in eller växla profiler {#section-c50499d7d8084d7cadfada52df33f5f4}

1. Starta Data Workbench.
1. Klicka på profilnamnet i sidlisten och klicka på **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*, där *profilnamnet* är den profil som du vill arbeta med.

   ![](assets/sidebar_profile.png)

Om det här är första gången du läser in den valda profilen kan det ta flera minuter att hämta tillräckligt med data för att fylla i en visualisering.

## Åtkomst till en profil i ett kluster {#section-189a0ac04a8f46099c11c0f4f77b6dbb}

Data Workbench-användare som har åtkomst till en profil som körs på en

Data workbench-serverklustret identifierar bara master Data Workbench Server i Data Workbench-konfigurationsfilen ( [!DNL Insight.cfg]). Ur Data Workbench-användarens perspektiv är profilen bara tillgänglig på en Data Workbench Server (Master Data Workbench Server). Frågebegäranden från analytiker kan dock dirigeras till någon av Data Workbench-servrarna i klustret.

Mer information om profiler som körs på ett Data Workbench Server-kluster finns i *Server Products Installation and Administration Guide*.
