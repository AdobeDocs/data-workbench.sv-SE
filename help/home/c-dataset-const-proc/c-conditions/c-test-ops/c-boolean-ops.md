---
description: De booleska åtgärderna kombinerar resultaten av teståtgärderna, som fungerar som underordnade för de booleska åtgärderna.
solution: Analytics
title: Booleska åtgärder
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Booleska åtgärder{#boolean-operations}

De booleska åtgärderna kombinerar resultaten av teståtgärderna, som fungerar som underordnade för de booleska åtgärderna.

Mer information om teståtgärderna finns i [Teståtgärder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). När du definierar en [!DNL boolean] åtgärd kan du definiera noll eller flera underordnade för åtgärden.

**Lägga till ett underordnat villkor i en Boolean-åtgärd**

1. Högerklicka på namnet eller numret som motsvarar [!DNL Boolean] åtgärden.
1. Klicka på **[!UICONTROL Add new child]** och välj en av de tillgängliga villkorstyperna som du vill lägga till.
1. Upprepa steg 1 och 2 tills du har lagt till alla underordnade villkor för [!DNL Boolean] åtgärden.

   >[!NOTE]
   >
   >När du högerklickar på namnet eller numret för en [!DNL Boolean] åtgärd visas [!DNL Add new sibling] menyalternativet. En jämställd är ett annat villkor vid samma relativa position i villkorshierarkin som den [!DNL Boolean] åtgärd som du högerklickade på. Att lägga till en ny jämställd för en [!DNL Boolean] åtgärd är detsamma som att lägga till ett nytt villkor genom att högerklicka på [!DNL Condition] - eller [!DNL Log Entry Condition] -parametern.

**Så här tar du bort ett underordnat villkor från en Boolean-åtgärd:**

1. Högerklicka på namnet på det underordnade villkoret eller numret som motsvarar det underordnade villkoret som du vill ta bort från [!DNL Boolean] åtgärden.
1. Klicka på **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, där talet motsvarar det underordnade villkoret som du vill ta bort.

I det här avsnittet beskrivs följande villkor:

* [Och](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Ingendera](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [eller](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Och {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Villkoret kan ha noll eller flera underordnade villkor och returnerar true när ingen av dess underordnade noder returnerar false. [!DNL And]

Villkoret utgör [!DNL And] rotåtgärden för alla villkorstestningar på data workbench-servern. Om [!DNL And] villkoret inte innehåller några underordnade objekt utvärderas villkoret till true och den associerade åtgärden fortsätter. Detta är orsaken till att åtgärder som bara har villkoret som [!DNL And] villkorstest alltid körs och varför det används som rot för alla villkorstester.

I det här exemplet visas hur ett [!DNL And] villkor används för att säkerställa att [!DNL Copy] omformningen sker när endast datumet för loggposten infaller under 2006 och att den begärda sidan har [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Ingendera {#section-7e48b61266aa43ecbc48b979bf5e939b}

Villkoret kan ha noll eller flera underordnade villkor och returnerar false om något av dess underordnade villkor utvärderas som true. [!DNL Neither] Om [!DNL Neither] villkoret inte innehåller några underordnade objekt kan ingen av dess underordnade objekt returnera true. Därför utvärderas [!DNL Neither] villkoret till true.

I följande exempel visas ett [!DNL Neither] villkor med två [!DNL Range] villkor som underordnade. Enligt definition utesluter [!DNL Neither] villkoret loggposter som inträffade mellan 1 januari 2007 och 10 januari 2007 eller under perioden 12 januari 2007 till 14 januari 2007. Ett sådant villkor kan användas för [!DNL Log Entry Condition] att eliminera transaktioner från en datauppsättning under perioder då det fanns ett känt problem med de insamlade uppgifterna.

![](assets/cfg_Condition_NeitherCondition.png)

## eller {#section-a3aa0f56b6234f2680fa81939228326b}

Villkoret kan ha noll eller flera underordnade villkor och returnerar true om minst ett av dess underordnade villkor utvärderas som true. [!DNL Or] Om [!DNL Or] villkoret inte innehåller några underordnade objekt kan ingen av dess underordnade objekt returnera true. Därför utvärderas [!DNL Or] villkoret till false.

I det här exemplet visas villkoret med ett [!DNL Or] villkor och ett [!DNL String Match] [!DNL Range] villkor som underordnade. Villkoret är bara uppfyllt om loggposten har [!DNL Or] [!DNL x-hasproblem] värdet yes eller om loggposten inträffade under tidsintervallet 1 januari 2007 till 10 januari 2007.

![](assets/cfg_Condition_OrCondition.png)

