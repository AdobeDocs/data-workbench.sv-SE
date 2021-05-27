---
description: Steg för att registrera och köra Report Server.
title: Registrerar rapportservern som en Windows-tjänst
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Registrerar rapportservern som en Windows-tjänst{#registering-report-server-as-a-windows-service}

Steg för att registrera och köra Report Server.

Innan du utför den här proceduren måste du identifiera det Windows-konto som [!DNL Report Server]-tjänsten ska köras under. Se till att det här kontot har rätt behörighet att komma åt den plats där genererade rapporter lagras (d.v.s. använd inte [!DNL Local System Account]).

Använd proceduren nedan för att starta [!DNL Report Server]. När du startar [!DNL Report Server] första gången registreras det automatiskt som en Windows-tjänst.

När du startar [!DNL Report Server] första gången ansluter programmet automatiskt till Adobe License Server för att registrera ditt digitala certifikat. Datorn måste vara ansluten till Internet när du utför följande steg för att registreringsprocessen ska slutföras.

1. I Windows navigerar du till den katalog där du installerade [!DNL Report Server].

   Exempel: D:\Adobe\Report

1. Dubbelklicka på **[!UICONTROL ReportServer.exe]**.
1. Bekräfta att [!DNL Report Server] körs korrekt genom att klicka på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.
1. Leta reda på posten för [!DNL Report Server] i tjänstlistan och bekräfta att dess status är Startad och att startmetoden är Automatisk.
1. Gör följande för att ange vilket användarkonto som [!DNL Report Server] ska köras under:

   1. Dubbelklicka på **[!UICONTROL Report Server]** för att öppna fönstret [!DNL Properties].

   1. Välj fliken **[!UICONTROL Log On]**.
   1. Markera alternativknappen **[!UICONTROL This account]**.
   1. Skriv eller bläddra efter kontonamnet. Det här kontot måste ha behörighet att komma åt den plats där genererade rapporter lagras.

      >[!NOTE]
      >
      >Om [!DNL Report Server] distribuerar rapporter som Microsoft Excel-filer ( [!DNL .xls] eller [!DNL .xlsx]) kontrollerar du att kontot även har behörighet att köra Microsoft Excel.

   1. Ange och bekräfta lösenordet för kontot.
   1. Klicka på **[!UICONTROL OK]**.

1. Högerklicka på tjänsten [!DNL Report Server] och välj **[!UICONTROL Restart]** för att starta om tjänsten under det angivna kontot.
1. Om du vill kontrollera om [!DNL Report Server] råkade ut för fel under start klickar du på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. Välj programloggen i den vänstra rutan i fönstret [!DNL Event Viewer].
   1. I den högra rutan söker du efter händelser med Adobe i kolumnen [!DNL Source].
   1. Om du hittar ett fel från Adobe dubbelklickar du på felet för att visa fönstret [!DNL Event Properties]. Det här fönstret innehåller detaljerad information om felet.

      >[!NOTE]
      >
      >När tjänsten [!DNL Report Server] har startats skapas filen [!DNL ReportServer.log] i katalogen Report Server [!DNL Trace]. Den här filen är också användbar för felsökning av problem med [!DNL Report Server].

Du har slutfört installationen av [!DNL Report Server]. [!DNL Report Server] är konstruerad för att köras kontinuerligt. Om du startar om datorn startas [!DNL Report Server] om automatiskt. Om du behöver starta och stoppa [!DNL Report Server] manuellt kan du göra det med hjälp av kontrollpanelen [!DNL Services] i Windows.
