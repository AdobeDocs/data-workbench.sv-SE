---
description: Steg för att redigera befintliga användarkonton.
solution: Analytics
title: Redigera befintliga användare
topic: Data workbench
uuid: 5c01f0f9-0d30-4526-a4fb-43c7e1cb076f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Redigera befintliga användare{#editing-existing-users}

Steg för att redigera befintliga användarkonton.

1. Klicka på [!DNL Report Portal]fliken **[!UICONTROL Admin]** . Sidan visas [!DNL Admin] .

   ![](assets/report_admintag2.png)

1. Klicka på den bokstav som motsvarar den första bokstaven i kontonamnet som du vill redigera. Om du till exempel vill redigera kontot&quot;Marknadsföring&quot; klickar du på bokstaven&quot;M.&quot;

   En lista med kontonamn som börjar med det brevet visas.

1. Markera det kontonamn som du vill redigera och klicka sedan på **[!UICONTROL select]** knappen. Sidan visas [!DNL Edit Account Info] .

   ![Steginformation](assets/rptPort_scrn_AdminTab_editUser.png)

1. Ändra bara de fält på den här sidan som behöver uppdateras. Följande tabell innehåller beskrivningar av vart och ett av dessa fält:

   | I det här fältet . . . | Ange . . . |
   |---|---|
   | e-post | Användarens e-postadress. |
   | gammalt lösenord | Det aktuella lösenordet som behövs för att fortsätta när du redigerar ett administratörskonto eller när du återställer lösenordet för ett icke-administratörskonto. |
   | nytt lösenord | Det nya lösenordet som användaren måste ange när han/hon loggar in på [!DNL Report Portal]. |
   | bekräfta lösenord | Det nya lösenordet som användaren måste ange när han/hon loggar in på [!DNL Report Portal]. |
   | profilåtkomst | De profiler som den här användaren har åtkomst till (till exempel ProductSales). Om du vill tillåta åtkomst till flera profiler avgränsar du namnen med kommatecken. Om användaren har behörighet att komma åt alla profiler som är kopplade till [!DNL Report Portal]skriver du&quot;ALL&quot;. |
   | flikåtkomst | Flikarna som den här användaren har åtkomst till (till exempel [!DNL Admin]). Om du vill tillåta åtkomst till flera flikar avgränsar du namnen med kommatecken. Om användaren har åtkomst till alla flikar i [!DNL Report Portal]skriver du&quot;ALL&quot;. Det här fältet tillsammans med kontotypsfältet är mycket användbart när du definierar åtkomsträttigheter för grupper. |
   | kontotyp | Anger om det här kontot är för en individ eller en grupp. Med enskilda konton kan användare återställa sina lösenord, men inte grupper. En administratör är den enda personen som kan återställa lösenordet för ett gruppkonto. |
   | status | Om det här kontot är aktivt eller inaktivt. Standardvärdet är aktivt. Om du vill inaktivera ett användarkonto väljer du **[!UICONTROL inactive]**. |
   | admin | Anger om användaren ska kunna skapa, uppdatera och ta bort användarkonton samt redigera anteckningar som är kopplade till varje rapport. Standardinställningen är false. Välj true om du vill göra detta till en administratörsanvändare. |
   | förfallodatum | Det datum, i formatet MM/DD/ÅÅÅÅ, som den här användaren får använda [!DNL Report Portal]. |

1. Klicka på **[!UICONTROL update]**.