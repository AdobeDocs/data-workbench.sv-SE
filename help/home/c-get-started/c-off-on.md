---
description: Information om hur du arbetar med Data Workbench-servern, antingen offline eller online.
solution: Analytics
title: Arbeta offline och online
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Arbeta offline och online{#working-offline-and-online}

Information om hur du arbetar med Data Workbench-servern, antingen offline eller online.

Data Workbench hämtar automatiskt uppdateringar av profilen och dess data från Data Workbench-servern om du har en nätverksanslutning till [!DNL server] och arbetar online. Om du inte har angett att arbeta online läser Data Workbench in profilen och dess data från datorns cache. I det här fallet visar du profilversionen och dess data som hämtades senast du arbetade online med profilen.

Att arbeta offline ger en snabbare bearbetning eftersom du arbetar från det lokala cacheminnet och frågar efter data på din egen dator. När du arbetar online måste alla frågor skickas tillbaka till Data Workbench-servern, som tar längre tid och tvingar dig att konkurrera med andra onlineanvändare om serverresurser. Så länge du har en nätverksanslutning till Data Workbench-servern kommer data Workbench-servern inte att kunna uppdatera profiler eller data på Data Workbench när du arbetar offline, men det hindrar dig inte från att spara objekt på Data Workbench-servern.

Eftersom det går att arbeta offline har Data Workbench-servern en storlek som hanterar en viss mängd realtidstrafilindata och viss mängd data i datauppsättningen, tillsammans med ett visst antal Data Workbench-användare, men den behöver inte ha en storlek som stöder maximalt antal samtidiga användare (vilket i praktiken inte sker ofta). Eftersom användarna oftast letar efter trender och proportioner och utforskar data medan du arbetar, behöver du i de flesta fall inte utföra några exakta räkningar. Om det finns ett behov av att fråga och lösa exakta räkningar med hjälp av aktuella data, kan du arbeta online och få det, men det tar längre tid att lösa frågorna till 100 procent.

**Arbeta online eller offline**

Klicka på **[!UICONTROL Connection]** inställningen i sidorutan och klicka på **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

När du arbetar online ansluter Data Workbench till Data Workbench-servern och synkroniserar informationen på din dator med profilen och dess datauppsättningsinformation som finns på Data Workbench-servern.

Standardkonfigurationen för Data Workbench är att arbeta offline, men enligt beskrivningen i följande avsnitt kan varje användare ändra sin [!DNL Insight.cfg] fil så att instansen av Data Workbench fungerar online som standard.

**Arbeta online som standard**

1. Navigera till installationskatalogen för Insight.
1. Öppna [!DNL Insight.cfg] filen i en textredigerare.
1. Lägg till den markerade raden i filen enligt följande exempel:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

Nästa gång du öppnar Data Workbench ansluter den till Data Workbench-servern och fungerar som standard online.
