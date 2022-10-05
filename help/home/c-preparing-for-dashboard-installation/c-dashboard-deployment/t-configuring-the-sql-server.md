---
description: Innan kontrollpanelen kan fungera måste du ge den åtkomst till SQL Server.
title: Konfigurera SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Konfigurera SQL Server{#configuring-the-sql-server}

{{eol}}

Innan kontrollpanelen kan fungera måste du ge den åtkomst till SQL Server.

1. Öppna SQL Management Studio som administratör.
1. Lägg till en ny inloggning genom att högerklicka **[!UICONTROL Logins]** och markera **[!UICONTROL New Login]**.
1. Ange fullständigt identitetsnamn för programpoolen.

   Som standard namnges programpoolens identitet efter programpoolen. Om du väljer `dashboard`, kommer identiteten att namnges `IIS AppPool\dashboard`. 1. Välj **[!UICONTROL Server Roles]** och kontrollera **[!UICONTROL dbcreator]** roll.
1. Klicka **[!UICONTROL OK]** för att lägga till den nya användaren.
