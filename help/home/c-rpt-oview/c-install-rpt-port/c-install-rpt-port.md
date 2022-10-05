---
description: Om du vill använda Report Portal måste du installera och konfigurera en uppsättning ASP:er (Application Server pages) på IIS.
title: Installerar rapportportalen
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Installerar rapportportalen{#installing-the-report-portal}

{{eol}}

Om du vill använda Report Portal måste du installera och konfigurera en uppsättning ASP:er (Application Server pages) på IIS.

**Innan du börjar**

I proceduren i det här kapitlet beskrivs hur du installerar och konfigurerar [!DNL Report Portal]. För att slutföra dessa procedurer måste du:

* Ha Microsoft IIS installerat och veta vilken version det är.
* Lär känna namnen på de rapportuppsättningar vars rapporter visas av [!DNL Report Portal].
* Ta reda på platsen för den katalog där [!DNL Report Server] sparar utdata för dessa rapportuppsättningar. Kontrollera att IIS-programservern har åtkomst till den här katalogen.

>[!NOTE]
>
>* Ska visas med [!DNL Report Portal], måste rapporter följa särskilda namngivningskonventioner. Dessutom måste katalogen som rapporter sparas i följa en förskriven struktur. En beskrivning av dessa krav finns på [Kontrollera att dina rapportuppsättningar är kompatibla med rapportportalen..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* Lösenord i rapportportalen är nu AES-256-bitarskompatibla. Om du uppgraderar till Report Portal 2.0 ökar du fältstorleken för lösenordsfältet från 50 till 150 i dialogrutan **användare.mdb** databas. Du måste öka fältstorleken för att kunna hantera lösenord med uppdaterad kryptering.
>* Om du uppgraderar till Report Portal 2.0 kan du öka fältstorleken för **Lösenord** från 50 till 150 i databasen user.mdb. Du måste öka fältstorleken för att kunna hantera lösenord med uppdaterad kryptering.
>* Rapportportalen innehåller nu starkare hash-algoritmer med stöd för saltning. Om du uppgraderar till **Rapportportal 2.1**, lägga till ett nytt textfält, *PasswordSalt* med en fältstorlek på 20 tecken i [!DNL users.mdb]databas. Det här fältet krävs för att lagra lösenordssaltet.
>

