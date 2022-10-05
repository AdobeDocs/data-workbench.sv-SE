---
description: De booleska åtgärderna kombinerar resultaten av teståtgärderna, som fungerar som underordnade för de booleska åtgärderna.
title: Booleska åtgärder
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Booleska åtgärder{#boolean-operations}

{{eol}}

De booleska åtgärderna kombinerar resultaten av teståtgärderna, som fungerar som underordnade för de booleska åtgärderna.

Mer information om teståtgärderna finns i [Teståtgärder](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). När du definierar en [!DNL boolean] kan du definiera noll eller flera underordnade för åtgärden.

**Lägga till ett underordnat villkor i en Boolean-åtgärd**

1. Högerklicka på namnet eller numret som motsvarar [!DNL Boolean] operation.
1. Klicka **[!UICONTROL Add new child]** och välj en av de tillgängliga villkorstyperna som ska läggas till.
1. Upprepa steg 1 och 2 tills du har lagt till alla underordnade villkor för [!DNL Boolean] operation.

   >[!NOTE]
   >
   >När du högerklickar på namnet eller numret som motsvarar en [!DNL Boolean] ser du [!DNL Add new sibling] menyalternativ. En jämställd är ett annat villkor vid samma relativa position i villkorshierarkin som [!DNL Boolean] åtgärd som du högerklickade på. Lägga till en ny jämställd för en [!DNL Boolean] är samma sak som att lägga till ett nytt villkor genom att högerklicka på [!DNL Condition] eller [!DNL Log Entry Condition] parameter.

**Så här tar du bort ett underordnat villkor från en Boolean-åtgärd:**

1. Högerklicka på namnet på det underordnade villkoret eller numret som motsvarar det underordnade villkoret som du vill ta bort från det [!DNL Boolean] operation.
1. Klicka **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, där tal är talet som motsvarar det underordnade villkoret som du vill ta bort.

I det här avsnittet beskrivs följande villkor:

* [Och](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Ingendera](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [eller](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Och {#section-a14dba4b07cc4ab9aeb20868f773db7c}

The [!DNL And] villkor kan ha noll eller flera underordnade villkor och returnerar true när ingen av dess underordnade noder returnerar false.

The [!DNL And] -villkoret utgör rotåtgärden för alla villkorstestningar i data workbench-servern. Om [!DNL And] villkoret innehåller inga underordnade objekt, villkoret utvärderas till true och den associerade åtgärden fortsätter. Det är därför åtgärder som bara har [!DNL And] villkoret som villkorstestet alltid körs och varför det används som rot för alla villkorstester.

Det här exemplet visar hur en [!DNL And] -villkoret används för att kontrollera att [!DNL Copy] omvandlingen sker när endast datumet för loggposten infaller under 2006 och den begärda sidan infaller [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Ingendera {#section-7e48b61266aa43ecbc48b979bf5e939b}

The [!DNL Neither] villkor kan ha noll eller flera underordnade villkor och returnerar false om något av dess underordnade villkor utvärderas som true. Om [!DNL Neither] villkoret innehåller inga underordnade objekt. Ingen av dess underordnade objekt kan returnera true. Resultatet blev att [!DNL Neither] villkoret utvärderas till true.

I följande exempel visas en [!DNL Neither] villkor med två [!DNL Range] villkor som sina barn. Som definierat [!DNL Neither] -villkoret utesluter loggposter som har inträffat mellan 1 januari 2007 och 10 januari 2007 eller under perioden 12 januari 2007 till 14 januari 2007. Ett sådant villkor kan användas som [!DNL Log Entry Condition] att eliminera transaktioner från en datauppsättning under perioder då det fanns ett känt problem med insamlade data.

![](assets/cfg_Condition_NeitherCondition.png)

## eller {#section-a3aa0f56b6234f2680fa81939228326b}

The [!DNL Or] villkor kan ha noll eller flera underordnade villkor och returnerar true om minst ett av dess underordnade villkor utvärderas som true. Om [!DNL Or] villkoret innehåller inga underordnade objekt. Ingen av dess underordnade objekt kan returnera true. Resultatet blev att [!DNL Or] villkoret utvärderas till false.

I det här exemplet visas [!DNL Or] villkor med [!DNL String Match] villkor och [!DNL Range] -villkor som underordnade. The [!DNL Or] villkoret uppfylls bara om loggposten har [!DNL x-hasproblem] värdet inställt på ja eller så inträffade loggposten under tidsintervallet 1 januari 2007 till 10 januari 2007.

![](assets/cfg_Condition_OrCondition.png)
