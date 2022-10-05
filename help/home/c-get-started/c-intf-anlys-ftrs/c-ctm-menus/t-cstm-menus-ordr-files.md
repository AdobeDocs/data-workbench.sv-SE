---
description: Du kan anpassa utseendet på alla menyer genom att redigera filen order.txt som är kopplad till den menyn.
title: Anpassa en meny med order.txt-filer
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---

# Anpassa en meny med order.txt-filer{#customize-a-menu-using-order-txt-files}

{{eol}}

Du kan anpassa utseendet på alla menyer genom att redigera filen order.txt som är kopplad till den menyn.

Stegen i det här avsnittet gäller för alla typer av menyer.

**Så här redigerar du filen order.txt och anpassar en meny**

1. I [!DNL Profile Manager], i *profilnamn* högerklicka på bockmarkeringen för [!DNL order.txt] och klicka på **[!UICONTROL Make Local]**.
1. Högerklicka på bockmarkeringen för [!DNL order.txt] i [!DNL User] kolumn och klicka **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL order.txt] visas.

   ![Steginformation](assets/cfg_ordertxt.png)

1. (Valfritt) Lägg till eller ändra [Inkluderande] eller [Exklusiv] inställningen överst i filen vid behov. Den här inställningen kontrollerar om objekt inte finns med i listan [!DNL order.txt] filen men finns i [!DNL Profile Manager] visas på menyn. Alternativen är:

   * **[Inkluderande]:** Det här är standardinställningen. Den här inställningen resulterar i menyalternativ som inte anges i [!DNL order.txt]filen som visas längst ned på menyn i alfabetisk ordning. Om [!DNL Profile Manager] innehöll ett profilobjekt utöver de som anges i [!DNL order.txt] ovan visas profilen under Data.

   * **[Exklusiv]:** Den här inställningen resulterar i menyalternativ som inte anges i [!DNL order.txt] filen utesluts från menyn. Om [!DNL Profile Manager] innehöll ett profilobjekt utöver de som anges i [!DNL order.txt] ovan visas inte profilen någonstans på menyn.

   * **blank:** Om ingen [Inkluderande] eller [Exklusiv] visas högst upp i filen, Datan Workbench visar menyalternativen som om inställningen var [Inkluderande].

1. Slutför ett eller flera av följande steg:

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> För att utföra den här uppgiften.. </th> 
    <th colname="col2" class="entry"> Gör följande... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Ordna om menyalternativ </p> </td> 
    <td colname="col2"> <p>Skriv objektnamnen i den ordning som du vill att de ska visas i Datan Workbench. </p> <p>Om till exempel varje menyalternativnamn matchar dess motsvarande fil- eller mappnamn resulterar följande i<b> Lägg till tabell</b> visas först, sedan <b>Lägg till visualisering</b>, <b>Lägg till förklaring</b>och <b>Lägg till anteckning</b> visas sist. </p> <p><b>Lägg till tabell </b> </p> <p><b>Lägg till visualisering </b> </p> <p><b>Lägg till förklaring </b> </p> <p><b>Lägg till anteckning </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Byta namn på ett menyalternativ </p> </td> 
    <td colname="col2"> <p>Byt namn på motsvarande fil eller mapp i dialogrutan <span class="wintitle"> Profilhanteraren</span>och sedan ändra namnet på objektet i <span class="filepath"> order.txt</span> -fil. </p> <p>Om du till exempel vill byta namn på Lägg till anteckning till Ny anteckning, byter du namn på mappen Lägg till anteckning i mappen <span class="wintitle"> Profilhanteraren</span> till Ny anteckning och ändra sedan namnet på Lägg till anteckning i dialogrutan <span class="filepath"> order.txt</span> till Ny anteckning. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Dölja ett menyalternativ </p> </td> 
    <td colname="col2"> <p>Om du vill dölja menyalternativet men inte ta bort själva alternativet skriver du ett minustecken (-) i början av namnet. </p> <p>Följande resulterar till exempel i <span class="wintitle"> Lägg till anteckning</span> visas inte på menyn. </p> <p>Lägg till förklaring </p> <p>-Lägg till anteckning </p> <p>Om du vill visa det dolda menyalternativet igen tar du bara bort minustecknet (-) eller använder parametern Visa alla i dialogrutan <span class="filepath"> Insight.cfg</span> -fil, se <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>. </p> <p>Du kan även dölja menyalternativ på följande sätt: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Visa-parametern i en <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span>, eller <span class="filepath"> .dim</span> filer döljer filter, härledda värden och dimensioner samt utökade dimensioner från respektive meny. När du använder det här alternativet visas inte alternativet på menyn, men det finns fortfarande i profilen och kan användas. </p> <p>Om du vill använda den här parametern för att dölja filter och härledda mått och mått lägger du till följande rad i slutet av <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>, eller <span class="filepath"> .filter</span> fil: </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Om du vill använda den här parametern för att dölja utökade dimensioner, se kapitel 10 i <i>Konfigurationshandbok för datauppsättning</i> för instruktioner. </p> <p>Du kan tillfälligt visa dolda objekt med den här metoden genom att ange parametern Visa alla i <span class="filepath"> Insight.cfg</span> -fil. Mer information om den här parametern finns i <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Parametern Dold i <span class="filepath"> Transformation.cfg</span> filen eller någon datauppsättning innehåller filer som döljer de utökade dimensionerna på dimensionsmenyn. När du använder det här alternativet visas inte alternativet på menyn, men det finns fortfarande i profilen och kan användas. <p> <p>Obs! När du döljer utökade dimensioner med den här metoden måste du omforma datauppsättningen för att dimensionerna ska döljas. </p> </p> <p>Du kan tillfälligt visa dolda objekt med den här metoden genom att ange parametern Visa alla i <span class="filepath"> Insight.cfg</span> -fil. Mer information om den här parametern finns i <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>Filer med nollbyte döljer alla typer av alternativ på alla menyer. När du använder det här alternativet döljs en tom (nollbyte) fil med samma namn som innehåller data. Data Workbench hanterar nollbytefiler som om de inte finns. Mer information finns i <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Dölja filer med tomma filer (nollbyte)</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ta bort ett menyalternativ </p> </td> 
    <td colname="col2"> <p>Om den här filen är inställd på att använda alternativet [Exklusiv] kan du helt enkelt ta bort menyalternativet från den här filen. Själva objektet finns fortfarande i profilen, men visas inte på menyn. </p> <p>Om den här filen är inställd på att använda alternativet [Inclusive] måste du ta bort menyalternativets namn från den här filen och antingen ta bort eller nollbyte för motsvarande fil för att ta bort alternativet från menyn. </p> <p>Mer information om hur du tar bort filer finns i <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Tar bort filer från din arbetsprofil</a>. Mer information om nollbytefiler finns i <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Dölja filer med tomma filer (nollbyte)</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Lägg till ett grupphuvud </p> </td> 
    <td colname="col2"> <p>Skriv tre bindestreck före och efter rubriktexten som du vill ska visas. </p> <p>Följande skulle till exempel resultera i en Hantera grupprubrik för en uppsättning relaterade menyalternativ. </p> <p>—Hantera— </p> <p>Profil </p> <p>Datauppsättning </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Lägga till en linje till separata avsnitt på en meny </p> </td> 
    <td colname="col2"> <p>Skriv tre bindestreck där du vill att en linje ska visas. </p> <p>Följande resulterar till exempel i en rad som avgränsar Lägg till anteckning och Lägg till anpassad. </p> <p>Lägg till anteckning </p> <p>— </p> <p>Lägg till anpassad </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Spara och stäng filen.
1. (Valfritt) Om du vill göra ändringarna tillgängliga för alla användare av arbetsprofilen högerklickar du på den vita bockmarkeringen för [!DNL order.txt] i [!DNL User] kolumn och klicka **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
