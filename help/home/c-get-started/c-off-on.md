---
description: Information om hur du arbetar med Datan Workbench offline eller online.
title: Arbeta offline och online
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Arbeta offline och online{#working-offline-and-online}

Information om hur du arbetar med Datan Workbench offline eller online.

Datan Workbench hämtar automatiskt uppdateringar av Datan Workbench och dess data från profilservern om du har en nätverksanslutning till [!DNL server] och arbetar online. Om du inte har angett att du ska arbeta online läser Datan Workbench in profilen och dess data från datorns cache. I det här fallet visar du profilversionen och dess data som hämtades senast du arbetade online med profilen.

Att arbeta offline ger en snabbare bearbetning eftersom du arbetar från det lokala cacheminnet och frågar efter data på din egen dator. När du arbetar online måste alla frågor skickas tillbaka till Datan Workbench, vilket tar längre tid och tvingar dig att konkurrera med andra onlineanvändare om serverresurser. Så länge du har en nätverksanslutning till Datan Workbench kommer Datan Workbench inte att kunna uppdatera profilerna eller data på Datan Workbench när du arbetar offline, men det hindrar dig inte från att spara objekt på Datan Workbench.

På grund av möjligheten att arbeta offline är Datan Workbench stor att hantera en viss mängd realtidstrafik och en viss mängd data i datauppsättningen, tillsammans med ett visst antal användare, men behöver inte ha stöd för maximalt antal samtidiga användare (vilket i praktiken inte sker så ofta). Eftersom användarna oftast letar efter trender och proportioner och utforskar data medan du arbetar, behöver du i de flesta fall inte utföra några exakta räkningar. Om det finns ett behov av att fråga och lösa exakta räkningar med hjälp av aktuella data, kan du arbeta online och få det, men det tar längre tid att lösa frågorna till 100 procent.

**Arbeta online eller offline**

Klicka på inställningen **[!UICONTROL Connection]** i sidofältet och klicka på **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

När du arbetar online ansluter Datan Workbench till Datan Workbench och synkroniserar informationen på datorn med profilen och dess datauppsättningsinformation som finns på Datan Workbench.

Standardkonfigurationen för Data Workbench är att arbeta offline, men enligt beskrivningen i följande avsnitt kan varje användare ändra sin [!DNL Insight.cfg]-fil så att instansen av Data Workbench fungerar online som standard.

**Arbeta online som standard**

1. Navigera till installationskatalogen för Insight.
1. Öppna [!DNL Insight.cfg]-filen i en textredigerare.
1. Lägg till den markerade raden i filen enligt följande exempel:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Nästa gång du öppnar Datan Workbench ansluts den till Datan Workbench och fungerar som standard online.
