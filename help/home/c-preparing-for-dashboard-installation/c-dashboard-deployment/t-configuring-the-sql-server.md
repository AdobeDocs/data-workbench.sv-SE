---
description: Innan kontrollpanelen kan fungera måste du ge den åtkomst till SQL Server.
title: Konfigurera SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Konfigurera SQL Server{#configuring-the-sql-server}

Innan kontrollpanelen kan fungera måste du ge den åtkomst till SQL Server.

1. Öppna SQL Management Studio som administratör.
1. Lägg till en ny inloggning genom att högerklicka på **[!UICONTROL Logins]** och välja **[!UICONTROL New Login]**.
1. Ange fullständigt identitetsnamn för programpoolen.

   Som standard namnges programpoolens identitet efter programpoolen. Om du väljer `dashboard` får identiteten namnet `IIS AppPool\dashboard`. 1. Välj **[!UICONTROL Server Roles]** och kontrollera rollen **[!UICONTROL dbcreator]**.
1. Klicka på **[!UICONTROL OK]** för att lägga till den nya användaren.
