---
description: Du måste installera och köra Sensor på varje webbserver som skickar innehållet till din plats för att samla in alla förfrågningar som visas av dessa servrar.
title: Hur skaffar jag dessa data?
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Hur skaffar jag dessa data_{#how-do-i-acquire-this-data}

Du måste installera och köra Sensor på varje webbserver som skickar innehållet till din plats för att samla in alla förfrågningar som visas av dessa servrar.

Dessa förfrågningar utgör 90 % eller mer av de förfrågningar som görs till din webbplats och 90 % eller mer av de data som behövs för den fullständiga analysen av webbplatsens trafik. [!DNL Page Tags] ska sedan användas för att samla in återstående 10 % eller mindre av de trafikdata som inte är kända för dina webbservrar. Följande konfigurationer är dock giltiga för insamling av webbförfrågningsdata från din webbplats, i prioritetsordning, baserat på vår erfarenhet:

1. [!DNL Sensor] installeras på varje webbserver som du kontrollerar och som har stöd för din plats. Innehåll från tredjepartswebbplatser, innehåll som hanteras från cacheminne och vissa typer av dynamiskt innehåll bör taggas, och sådana sidtaggar bör skicka data som de samlar in till en webbserver på din plats som kör [!DNL Sensor]. Du kan lägga till ytterligare en webbserver om sidtaggens begärandetrafik motiverar det, eller i särskilda fall avsätta en webbserver för att samla in dessa sidtaggsförfrågningar.
1. [!DNL Sensor] installeras på två webbservrar, som också kallas datainsamlingsservrar i den här handboken, på din plats där du samlar in data från taggade sidor. Allt innehåll på din webbplats är taggat och alla sidtaggar dirigeras till de två datainsamlingsservrarna.
1. [!DNL Sensor’s] datainsamlingstjänsterna tillhandahålls av en outsourcer som kör datainsamlingsservrar för att samla in alla dina webbförfrågningsdata. I det här fallet taggas allt innehåll på din webbplats och sidtaggarna skickar data till de outsourcade datainsamlingsservrarna.

   Mer information om [!DNL Sensor] finns i *Datan Workbench [!DNL Sensor] Guide*.
