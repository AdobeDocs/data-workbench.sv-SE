---
description: Steg för att säkerställa att ombearbetningen eller omformningen går smidigt och avslutas i tid så att användare av Data Workbench kan börja arbeta igen
title: Förbereda för ombearbetning eller omformning
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Förbereda för ombearbetning eller omformning{#preparing-for-reprocessing-or-retransformation}

{{eol}}

Steg för att säkerställa att ombearbetningen eller omformningen går smidigt och avslutas i tid så att användare av Data Workbench kan börja arbeta igen

1. Bestäm förfluten tid för föregående bearbetning eller omformning genom att kontrollera datauppsättningsprofilens [!DNL Processing Mode History] i [!DNL Detailed Status] gränssnitt.

   1. Öppna dialogrutan [!DNL Detailed Status] gränssnitt.
   1. Klicka **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** om du vill visa förflutna tid för tidigare bearbetning eller omformning.

      * Snabb inmatning är den totala tid som behövs för loggbearbetning.
      * Snabbsammanfogning är den totala tid som krävs för omformning.
      * Summan av de två gånger (snabb inmatning + snabb sammanslagning) är den totala tid som behövs för att bearbeta datauppsättningen.

      Exemplet nedan visar att loggbearbetningen tog cirka 43 sekunder, medan omvandlingen tog mindre än 2 minuter.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Mer information om [!DNL Detailed Status] -gränssnittet finns i *Användarhandbok för Data Workbench*.


1. Schemalägg och planera ombearbetningen. Eftersom användare av Data Workbench inte har tillgång till data under loggbearbetningsfasen måste du schemalägga ombearbetningen så att den sker under en lämplig tid, t.ex. över helgen.
1. Övervaka förloppet för ombearbetningen och omformningen med hjälp av fälten i [!DNL Processing Legend.] Mer information om [!DNL Processing Legend], se *Användarhandbok för Data Workbench*.
