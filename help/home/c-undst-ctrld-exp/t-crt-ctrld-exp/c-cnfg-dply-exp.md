---
description: När du har definierat mål, hypotes och experimentera samt skapat testinnehållet, måste du konfigurera Sensor för att driftsätta det kontrollerade experimentet.
solution: Analytics,Analytics
title: Konfigurera och distribuera experimentet
topic: Data workbench
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 0%

---


# Konfigurera och distribuera experimentet{#configuring-and-deploying-the-experiment}

När du har definierat mål, hypotes och experimentera samt skapat testinnehållet, måste du konfigurera Sensor för att driftsätta det kontrollerade experimentet.

## Konfigurera filen för experimentkonfiguration {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Om du vill konfigurera experimentet måste du slutföra kalkylbladet för experimentkonfiguration som tillhandahålls av Adobe (namnges [!DNL TestExperiment.xls] som standard). Filen konfigureras [!DNL Sensor] för att experimentera och är Excel-versionen av textfilen som du angav när du [ändrade parametern](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

Den här filen kan innehålla information om flera försök, som kan köras samtidigt eller vid olika tidpunkter och använda olika grupper och procenttal, men dessa experiment korrelerar inte på något sätt.

Användare placeras i en grupp för varje experiment som listas i filen som är konfigurerad att köras just nu.

>[!NOTE]
>
>Varje experiment är oberoende av alla andra experiment. Ändringar som du gör i ett experiment påverkar inte något annat experiment, och även om besökarna kan vara i flera experiment, är resultaten inte relaterade till varandra. Om du tror att det finns ett samband mellan ändringarna i flera experiment måste du skapa ett nytt experiment som testar dessa ändringar tillsammans.

**Konfigurera ditt experiment**

Du bör fylla i den här filen innan experimentet börjar och inte ändra informationen medan experimentet pågår.

>[!NOTE]
>
>Ett försök är omedelbart ogiltigt om definitionen av försöket ändras efter att försöket har börjat.

1. Om du har administratörsåtkomst till dina webb- eller programservrar navigerar du till installationsmappen på valfri [!DNL Sensor] dator i webbklustret för att komma åt [!DNL Sensor] [!DNL TestExperiment.xls] filen. Om du inte har administratörsåtkomst kontaktar du kontohanteraren i Adobe för att begära [!DNL TestExperiment.xls] filen.

1. Öppna [!DNL TestExperiment.xls] filen (du kan ändra namn på filen om du vill) och fyll i följande fält:

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experimentera </td> 
   <td colname="col2"> <p>Ett beskrivande namn för experimentet. Varje experimentnamn måste vara unikt och får inte innehålla blanksteg. </p> <p>Experimentnamn används när resultaten av experiment i <span class="keyword"> Insight visas </span>. Namnen visas som den första halvan av elementnamnen i den kontrollerade experimentella dimensionen. Den andra halvan av elementnamnet är gruppnamnet från gruppfältet i den här filen. Varje grupp namnges i följande format med experimentnamnet följt av gruppnamnet: </p> <p><i>ExperimentName.Group Name</i> </p> <p>Till exempel: <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Starta </td> 
   <td colname="col2"> <p>Det datum och den tidpunkt då du vill att experimentet ska börja. Om du inte anger några värden börjar experimentet omedelbart efter att filen har distribuerats. </p> <p>Format: MM/DD/YYY H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Om du lämnar start- och stopptider tomma körs experimentet oavbrutet. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">Du kan fördefiniera start- och stopptider långt i förväg; Därför kan du konfigurera alla dina experiment för nästa år samtidigt om du vill. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">Start- och stopptider baseras på webbserverns systemtid. Om klockan ändras av någon anledning kan ditt experiment börja eller avslutas oväntat. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Om du vill lägga till ett experiment som en konfigurationsfilspost, men inte vill att experimentet ska köras inom en nära framtid, kan du kommentera i experimentinformationen med hjälp av nummertecknet "#" eller definiera start- och stopptider tidigare. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stoppa </td> 
   <td colname="col2"> <p>Det datum och den tidpunkt då du vill att experimentet ska avslutas. När stoppdatumet och stopptiden inträffar slutar <span class="wintitle"> Sensor </span> att skicka cookie-värdena som identifieras som en testgrupp till test-URI:erna och skickar alla cookies till kontrollgruppens URI:er. </p> <p>Format: MM/DD/YYY H:MM </p> <p>Se anmärkningarna till <span class="wintitle"> Start- </span> fältet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupp </td> 
   <td colname="col2"> <p>Ett beskrivande namn för varje grupp besökare i experimentet. Gruppnamn får inte innehålla blanksteg. </p> <p>Gruppnamn används när resultaten av experiment i <span class="keyword"> Insight visas </span>. Mer information finns i beskrivningen av fältet Experimentera. </p> <p>En kontrollgrupp kan definieras implicit eller explicit baserat på värdet som anges i fältet Procent. </p> <p> <p>Obs!  För att tillgodose det antal besökare som krävs under den definierade tidsperioden för att försöket ska vara statistiskt giltigt kan du behöva antingen minska konfidensnivån eller öka tidsperioden. Om tidsramen till exempel är fem dagar, din konfidensnivå är 98 % och antalet besökare som behövs överstiger det antal som förväntas under den perioden, måste du antingen öka tidsperioden eller minska konfidensnivån tills antalet besökare som förväntas överstiger det antal som krävs för att köra ett statistiskt giltigt experiment. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Procent </td> 
   <td colname="col2"> <p>Procentandel besökare som ska inkluderas i varje definierad grupp. Dessa värden kan uttryckas antingen som procenttal eller som decimalvärden. Dessutom måste båda värdena vara antingen större än eller mindre än ett. </p> <p>Exempel: </p> <p>33,3 % och 66,7 % </p> <p>.99 och .01 </p> <p>Om summan för alla grupper är mindre än 100 blir det odefinierade överskottet som standard en kontrollgrupp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ursprunglig URL </td> 
   <td colname="col2"> <p>URI:n för innehållet som ska mappas om, följt av $. Det här värdet är skiftlägeskänsligt. </p> <p>Format: index.asp$ </p> <p>Ursprungliga URI:er kan anges med ett dollartecken ($) i slutet av URI:n för att ange att en exakt matchning av filnamnet krävs. Uttrycket <span class="filepath"> /product/product_view.asp$ </span> matchar bara den exakta sidan, medan <span class="filepath"> /product </span> matchar alla sidor i <span class="filepath"> /product- </span> katalogen och kan användas för att mappa hela underträdet. Ursprungliga URL-poster som inte anger tecknet $ i slutet av filnamnet ignoreras av experimentet såvida inte parametern ExpPartialMatch har angetts till "on". Mer information om den här parametern finns i Ändra parametern ExpPartialMatch (valfritt) <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> </a>. </p> <p>Den kontrollerade experimentfunktionen ignorerar alla frågesträngar som lagts till i URI-stammen. Till exempel sidan </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> är inte en giltig URI, men sidan <span class="filepath"> /product/product_view.asp </span> är en giltig URI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL som flyttats </td> 
   <td colname="col2"> <p>Det alternativa innehållets URI. </p> <p>Format: index2.asp </p> <p>Se anmärkningarna för fältet Ursprunglig URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

Här följer ett exempel på ett ifyllt [!DNL TextExperiment.xls] kalkylblad:

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>Ändra inte kolumnpositionerna i kalkylbladet.

I det här exemplet anges att &quot;New_Homepage&quot;-experimentet börjar den 1 juni 2006 och slutar den 30 juni 2006. Experimentet innehåller en kontrollgrupp med 50 % av besökarna och en testgrupp med 50 % av besökarna som ser olika innehåll för en URI.

>[!NOTE]
>
>Även om exempelfilen ovan har en explicit kontrollgrupp definierad, är det inte nödvändigt att uttryckligen definiera en kontrollgrupp - experimentet skapar automatiskt kontrollgruppen. Om summan av procentsatserna för alla grupper i ett experiment är mindre än 100 % tilldelas en implicit kontrollgrupp till användare som inte tillhör någon av de explicita grupperna.

1. Om du vill infoga kommentarer som ger ytterligare information om specifika experiment börjar du cellen med ett nummertecken (#) och följer med dina kommentarer. Kommentarer kan infogas var som helst i filen.
1. När du har slutfört variablerna i kalkylbladet för experimentkonfigurationen sparar du ändringarna och sparar sedan filen i tabbavgränsat textformat ( [!DNL *.txt]) med det namn som du angav i parametern ExpFile i [!DNL Sensor] konfigurationsfilen. Se [Ändra parametern](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

   Följande är ett exempel på en textfil för experimentkonfiguration:

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >På grund av flikarna som krävs i den här filen ska du inte redigera testkonfigurationsfilen manuellt. Om du behöver göra ändringar i filen gör du ändringarna i Excel-filen för experimentkonfigurationen och sparar filen på nytt som en tabbavgränsad textfil.

Om du har definierat start- och stopptider finns det ingen anledning att någonsin ta bort ett experiment från experimentets konfigurationsfil. Att behålla alla dina experiment som listas i konfigurationsfilen för experimentet är faktiskt ett bra sätt att registrera hur du definierade varje experiment.

## Distribuera konfigurationsfilen och testa innehåll {#section-34ff29649f584b93bc6129b75084b37c}

Du måste distribuera konfigurationsfilen för experimentet till varje dator i webbklustret som kör ett [!DNL Sensor] och hanterar de sidor som ingår i experimentet. Det kan du göra med hjälp av en manuell procedur eller med ditt befintliga innehållshanteringssystem.

**Distribuera testinnehåll**

* Använd din befintliga publiceringsprocess för att distribuera testinnehållet till rätt plats på varje program- eller webbserver som kör en [!DNL Sensor] som visar sidor som ingår i experimentet.

   Om du till exempel vill publicera testgruppssidan [!DNL index2.asp] till testmappen för webbplatsen ( [!DNL mysite.com]) publicerar du filen till [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >Länka inte till någon av dina testfiler direkt från en sida på webbplatsen. Om du gör det blir testresultaten och indexpoängen ogiltiga.

**Så här använder du ditt experiment**

* På varje program- eller webbserver som kör en [!DNL Sensor] som visar sidor som ingår i experimentet placerar du textfilen för experimentkonfigurationen i den katalog som du angav i parametern ExpFile i [!DNL Sensor] konfigurationsfilen. Se [Ändra parametern](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28)ExpFile.

[!DNL Sensor] väljs webbesökare slumpmässigt för varje grupp baserat på de procentsatser som du har definierat i filen, och test- eller kontrollgruppsinnehållet skickas till dem på lämpligt sätt.
