---
description: Om du vill använda Report Portal måste du installera och konfigurera en uppsättning ASP:er (Application Server pages) på IIS.
title: Installerar rapportportalen
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Installerar rapportportalen{#installing-the-report-portal}

Om du vill använda Report Portal måste du installera och konfigurera en uppsättning ASP:er (Application Server pages) på IIS.

**Innan du börjar**

Anvisningarna i det här kapitlet beskriver hur du installerar och konfigurerar [!DNL Report Portal]. För att slutföra dessa procedurer måste du:

* Se till att Microsoft IIS är installerat och att du känner till dess version.
* Lär dig namnen på de rapportuppsättningar vars rapporter visas med [!DNL Report Portal].
* Ta reda på platsen för den katalog där [!DNL Report Server] sparar utdata för dessa rapportuppsättningar. Kontrollera att IIS-programservern har åtkomst till den här katalogen.

>[!NOTE]
>
>* För att kunna visas med [!DNL Report Portal] måste rapporter följa specifika namnkonventioner. Dessutom måste katalogen som rapporter sparas i följa en förskriven struktur. En beskrivning av dessa krav finns i [Kontrollera att dina rapportuppsättningar är kompatibla med rapportportalen...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Lösenord i rapportportalen är nu AES-256-bitarskompatibla. Om du uppgraderar till Report Portal 2.0 ökar du fältstorleken för lösenordsfältet från 50 till 150 i **users.mdb**-databasen. Du måste öka fältstorleken för att kunna hantera lösenord med uppdaterad kryptering.
>* Om du uppgraderar till Report Portal 2.0 ökar du fältstorleken för fältet **Lösenord** från 50 till 150 i databasen users.mdb. Du måste öka fältstorleken för att kunna hantera lösenord med uppdaterad kryptering.
>* Rapportportalen innehåller nu starkare hash-algoritmer med stöd för saltning. Om du uppgraderar till **Report Portal 2.1** lägger du till ett nytt textfält, *PasswordSalt*, med fältstorleken 20 tecken i [!DNL users.mdb]databasen. Det här fältet krävs för att lagra lösenordssaltet.

>


