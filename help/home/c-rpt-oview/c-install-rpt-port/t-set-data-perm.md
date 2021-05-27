---
description: Om du vill att rapportportalen ska kunna skriva till databasen som innehåller information som behövs för att autentisera användare, måste du ange rätt behörigheter för databasen.
title: Ange behörighet för databasen
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---

# Ange behörigheter för databasen{#set-permissions-for-the-database}

Om du vill att rapportportalen ska kunna skriva till databasen som innehåller information som behövs för att autentisera användare, måste du ange rätt behörigheter för databasen.

1. Navigera till \*PortalName*\data\users.mdb på den dator där IIS körs.
1. Högerklicka på filen **[!UICONTROL users.mdb]** och välj **[!UICONTROL Properties]**.
1. På fliken [!DNL Security] i Grupper eller användarnamn klickar du på **[!UICONTROL Users]**.
1. I [!DNL Permission for User] väljer du **[!UICONTROL Allow]** på raden Skriv.
1. Klicka på **[!UICONTROL OK]** och stäng dialogrutan [!DNL Properties].
