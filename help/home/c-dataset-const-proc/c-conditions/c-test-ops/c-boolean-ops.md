---
description: De booleska åtgärderna kombinerar resultaten av teståtgärderna, som fungerar som underordnade för de booleska åtgärderna.
title: Booleska åtgärder
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Booleska åtgärder{#boolean-operations}

De booleska åtgärderna kombinerar resultaten av teståtgärderna, som fungerar som underordnade för de booleska åtgärderna.

Mer information om teståtgärderna finns i [Teståtgärder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). När du definierar en [!DNL boolean]-åtgärd kan du definiera noll eller flera underordnade för åtgärden.

**Lägga till ett underordnat villkor i en Boolean-åtgärd**

1. Högerklicka på namnet eller numret som motsvarar [!DNL Boolean]-åtgärden.
1. Klicka på **[!UICONTROL Add new child]** och välj en av de tillgängliga villkorstyperna som ska läggas till.
1. Upprepa steg 1 och 2 tills du har lagt till alla underordnade villkor för åtgärden [!DNL Boolean].

   >[!NOTE]
   >
   >När du högerklickar på namnet eller numret som motsvarar en [!DNL Boolean]-åtgärd visas menyalternativet [!DNL Add new sibling]. Ett syskon är ett annat villkor vid samma relativa position i villkorshierarkin som den [!DNL Boolean]-åtgärd som du högerklickade på. Att lägga till ett nytt jämställda för en [!DNL Boolean]-åtgärd är detsamma som att lägga till ett nytt villkor genom att högerklicka på parametern [!DNL Condition] eller [!DNL Log Entry Condition].

**Så här tar du bort ett underordnat villkor från en Boolean-åtgärd:**

1. Högerklicka på namnet på det underordnade villkoret eller numret som motsvarar det underordnade villkoret som du vill ta bort från åtgärden [!DNL Boolean].
1. Klicka på **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, där tal är numret som motsvarar det underordnade villkoret som du vill ta bort.

I det här avsnittet beskrivs följande villkor:

* [Och](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Ingendera](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [eller](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Och {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Villkoret [!DNL And] kan ha noll eller flera underordnade villkor och returnerar true när ingen av dess underordnade noder returnerar false.

Villkoret [!DNL And] utgör rotåtgärden för alla villkorstestningar i data workbench-servern. Om villkoret [!DNL And] inte innehåller några underordnade objekt utvärderas villkoret till true och den associerade åtgärden fortsätter. Detta är orsaken till att åtgärder som bara har villkoret [!DNL And] som villkorstest alltid körs och varför det används som rot för alla villkorstester.

I det här exemplet visas hur ett [!DNL And]-villkor används för att kontrollera att [!DNL Copy]-omformningen inträffar när endast datumet för loggposten inträffade 2006 och att den begärda sidan var [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Varken {#section-7e48b61266aa43ecbc48b979bf5e939b}

Villkoret [!DNL Neither] kan ha noll eller flera underordnade villkor och returnerar false om något av dess underordnade villkor utvärderas som true. Om [!DNL Neither]-villkoret inte innehåller några underordnade objekt kan inga av dess underordnade objekt returnera true. Därför utvärderas villkoret [!DNL Neither] till true.

I följande exempel visas ett [!DNL Neither]-villkor med två [!DNL Range]-villkor som underordnade. Enligt definition utesluter villkoret [!DNL Neither] loggposter som inträffade mellan 1 januari 2007 och 10 januari 2007 eller under perioden 12 januari 2007 till 14 januari 2007. Ett sådant villkor kan användas som [!DNL Log Entry Condition] för att ta bort transaktioner från en datauppsättning under perioder då ett känt problem med insamlade data uppstod.

![](assets/cfg_Condition_NeitherCondition.png)

## Eller {#section-a3aa0f56b6234f2680fa81939228326b}

Villkoret [!DNL Or] kan ha noll eller flera underordnade villkor och returnerar true om minst ett av dess underordnade villkor utvärderas som true. Om [!DNL Or]-villkoret inte innehåller några underordnade objekt kan inga av dess underordnade objekt returnera true. Därför utvärderas villkoret [!DNL Or] till false.

I det här exemplet visas [!DNL Or]-villkoret med ett [!DNL String Match]-villkor och ett [!DNL Range]-villkor som underordnade villkor. Villkoret [!DNL Or] uppfylls bara om loggposten har värdet [!DNL x-hasproblem] inställt på yes eller om loggposten inträffade under tidsintervallet 1 januari 2007 till 10 januari 2007.

![](assets/cfg_Condition_OrCondition.png)
