---
description: Lägga till ett användarkonto
title: Lägga till ett användarkonto
uuid: c322eeaa-a3f4-41e8-b38c-dd892ec29a87
exl-id: c99f3189-4d89-443a-be5b-84352c4ec6e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Lägga till ett användarkonto{#adding-a-user-account}

1. Klicka på **[!UICONTROL Add User]** för att visa **[!UICONTROL New User]**-frågan.

   ![](assets/add_user_account.png)

1. Fyll i de fält som behövs för att fylla i formuläret.
   1. **[!UICONTROL Username]**: Ange användarnamnet.
   1. **[!UICONTROL Password]**: Ange ett lösenord som är längre än 6 tecken.
   1. **[!UICONTROL Confirm Password]**: Ange lösenordet igen.
   1. **[!UICONTROL Authentication Method]**: välj ett alternativ i listrutan.

      | **Forms** | Som standard lagras användarkontot och autentiseras internt på kontrollpanelen. |
      |---|---|
      | **LDAP** | Välj det här alternativet om användaren ska autentiseras via LDAP. (Användaren måste redan finnas i katalogen). |
      | **Windows** | Välj om användaren ska autentiseras med Windows-autentisering (användaren måste redan finnas i Windows-katalogen). |

1. **[!UICONTROL Assigned Groups]**: Välj bland standardgruppen Administratörer och andra grupper som har skapats. Inga grupper krävs för tillfället och användarens gruppmedlemskap kan ändras när som helst.
1. När formuläret har konfigurerats korrekt klickar du på **[!UICONTROL Add User]** för att lägga till användaren i systemet.

   Om åtgärden lyckades visas ett meddelande om att användaren skapades.
