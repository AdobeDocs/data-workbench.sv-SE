---
description: Innan kontrollpanelen kan fungera måste du ge den åtkomst till SQL Server.
solution: Analytics
title: Konfigurera SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurera SQL Server{#configuring-the-sql-server}

Innan kontrollpanelen kan fungera måste du ge den åtkomst till SQL Server.

1. Öppna SQL Management Studio som administratör.
1. Lägg till en ny inloggning genom att högerklicka **[!UICONTROL Logins]** och välja **[!UICONTROL New Login]**.
1. Ange fullständigt identitetsnamn för programpoolen.

   Som standard namnges programpoolens identitet efter programpoolen. Om du väljer `dashboard`får identiteten ett namn `IIS AppPool\dashboard`. 1. Markera **[!UICONTROL Server Roles]** och kontrollera **[!UICONTROL dbcreator]** rollen.
1. Klicka **[!UICONTROL OK]** för att lägga till den nya användaren.
