---
description: Procedur för att starta Insight Server och samtidigt registrera den som en Microsoft Windows-tjänst.
title: Registrerar Insight Server som en Windows-tjänst
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# Registrerar Insight Server som en Windows-tjänst{#registering-insight-server-as-a-windows-service}

Procedur för att starta Insight Server och samtidigt registrera den som en Microsoft Windows-tjänst.

>[!NOTE]
>
>När du startar [!DNL Insight Server] första gången ansluter programmet automatiskt till Adobe License Server för att registrera ditt digitala certifikat. Datorn måste vara ansluten till Internet när du utför följande steg för att registreringsprocessen ska slutföras.

**Starta  [!DNL Insight Server] och registrera den som en Windows-tjänst**

1. Öppna en kommandotolk och navigera till underkatalogen bin i mappen där du installerade [!DNL Insight Server].

   Exempel: [!DNL C:\Adobe\Server\bin]

1. Kör följande kommando i kommandotolken för att starta [!DNL Insight Server] och samtidigt registrera det för att köras som en tjänst i Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Bekräfta att [!DNL Insight Server] körs korrekt genom att klicka på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. Leta reda på posten för **[!DNL Adobe Insight Server]** i tjänstlistan och bekräfta att dess status är Startad och att startmetoden är Automatisk.
   1. Stäng kontrollpanelen Tjänster.

1. Om du vill kontrollera om [!DNL Insight Server] råkade ut för fel under start klickar du på **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Kommandosekvensen kan variera beroende på vilken version av Windows du använder.

   1. Välj loggen **[!UICONTROL Application]** i den vänstra rutan i fönstret [!DNL Event Viewer].
   1. I den högra rutan söker du efter händelser med Adobe i kolumnen [!DNL Source].
   1. Om du hittar ett fel från &quot;Adobe&quot; dubbelklickar du på felet för att visa fönstret [!DNL Event Properties]. Det här fönstret innehåller detaljerad information om felet.

1. När du är klar med granskningen av [!DNL Applications]-loggen stänger du Loggboken.

Du har slutfört installationen av [!DNL Insight Server]. [!DNL Insight Server] är konstruerad för att köras kontinuerligt. Om du startar om datorn startas [!DNL Insight Server] om automatiskt. Om du behöver starta och stoppa [!DNL Insight Server] manuellt kan du göra det med hjälp av kontrollpanelen Tjänster i Windows. Som beskrivs i följande avsnitt kan du välja att konfigurera [!DNL Insight Server]-tjänsten så att den startar om automatiskt regelbundet.

## Konfigurerar tjänsten så att den startas om automatiskt {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] är utformat för att fortsätta köra utan avbrott. Den stoppas eller startas normalt bara när du utför ovanliga uppgifter som programvaruuppgraderingar eller certifikatändringar eller vid vissa systemfel. Det är inte nödvändigt att stoppa eller starta om tjänsten [!DNL Insight Server] under normal systemdrift. Du kan dock konfigurera tjänsten så att den startar om regelbundet (varje dag, varje vecka eller varje månad) för att t.ex. rensa händelsemeddelandena.

**Så här konfigurerar du  [!DNL Insight Server] tjänsten till att starta om automatiskt**

1. Navigera till mappen [!DNL Components] i den katalog där du installerade [!DNL Insight Server].

   Exempel: [!DNL C:\Adobe\Server\Components]

1. Använd en textredigerare som Anteckningar för att skapa en ny fil med namnet [!DNL ScheduledRestart.cfg].
1. Ange följande text i [!DNL ScheduledRestart.cfg]-filen:

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> För det här värdet.. </th> 
      <th colname="col2" class="entry"> Ange </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Månad DD, ÅÅÅÅ HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Den tidpunkt då du vill att <span class="keyword"> Insight Server </span> ska startas om för första gången. </p> <p>Exempel: 13 augusti 2013 kl. 22.30.00 EST </p> <p> <p>Obs!  Du måste ange en tidszon. Tidszonen får inte standardvärdet för systemtid om den inte anges. Om du vill implementera sommartid eller en liknande princip för ändring av klockslag måste du spara filen <span class="filepath">.dst </span> som innehåller rätt regler i Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span>-datorn. En lista med förkortningar av tidszoner som stöds och information om hur du implementerar sommartid finns i <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Tidszonskoder </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frekvens</i> </td> 
      <td colname="col2"> <p>Ett av följande värden: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">månad </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">vecka </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">dag </li> 
       </ul> </p> <p>Anger hur ofta du vill att <span class="keyword"> Insight Server </span> ska startas om efter den inledande tid som anges i Starttid. </p> <p>Om du till exempel vill att <span class="keyword"> Insight Server </span> ska starta om en gång i veckan anger du värdet "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Spara [!DNL ScheduledRestart.cfg]-filen.

   Kontrollera att filen [!DNL ScheduledRestart.cfg] finns i mappen [!DNL Components] i den katalog där du installerade [!DNL Insight Server].
