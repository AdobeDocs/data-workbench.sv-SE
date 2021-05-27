---
description: Steg för att lägga till nya konton.
title: Lägga till nya konton
uuid: 32081bc3-9050-42a2-95ad-85e7736fe5c4
exl-id: dabd1dd5-fcbf-4612-a240-89cafed2cf2e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# Lägger till nya konton{#adding-new-accounts}

Steg för att lägga till nya konton.

1. Klicka på fliken **[!UICONTROL Admin]** i [!DNL Report Portal]. Sidan [!DNL Admin] visas.

   ![](assets/report_admintag2.png)

1. Klicka på **[!UICONTROL new account]** till höger på sidan. Sidan [!DNL Create New Account] visas.

   ![Steginformation](assets/rptPort_scrn_AdminTab_createUser.png)

1. Fyll i alla fält på den här sidan enligt följande tabell:

   | I det här fältet . . . | Ange . . . |
   |---|---|
   | kontonamn | Namnet på kontot som användaren måste ange när han/hon loggar in på [!DNL Report Portal]. |
   | e-post | Användarens eller gruppens e-postadress. |
   | lösenord | Det lösenord som användaren måste ange när han/hon loggar in på [!DNL Report Portal]. |
   | bekräfta lösenord | Det lösenord som användaren måste ange när han/hon loggar in på [!DNL Report Portal]. |
   | profilåtkomst | De profiler som den här användaren har åtkomst till (till exempel ProductSales). Om du vill tillåta åtkomst till flera profiler avgränsar du namnen med kommatecken. Om användaren har behörighet att komma åt alla profiler som är associerade med [!DNL Report Portal] skriver du &quot;ALL&quot;. |
   | flikåtkomst | Flikarna som den här användaren har åtkomst till (till exempel [!DNL Admin]). Om du vill tillåta åtkomst till flera flikar avgränsar du namnen med kommatecken. Om användaren har åtkomst till alla flikar i [!DNL Report Portal] skriver du &quot;ALL&quot;. Det här fältet tillsammans med kontotypsfältet är mycket användbart när du definierar åtkomsträttigheter för grupper. |
   | kontotyp | Anger om det här kontot är för en individ eller en grupp. Med enskilda konton kan användare återställa sina lösenord, men inte grupper. En administratör är den enda personen som kan återställa lösenordet för ett gruppkonto. |
   | status | Om det här kontot är aktivt eller inaktivt. Standardvärdet är aktivt. Om du vill inaktivera ett användarkonto väljer du Inaktiv. |
   | admin | Anger om användaren ska kunna skapa, uppdatera och ta bort användarkonton samt redigera anteckningar som är kopplade till varje rapport. Standardinställningen är false. Välj true om du vill göra detta till en administratörsanvändare. |
   | förfallodatum | Det datum, i formatet MM/DD/ÅÅÅÅ, till vilket den här användaren tillåts använda [!DNL Report Portal]. |

1. Klicka på **[!UICONTROL insert]**.
