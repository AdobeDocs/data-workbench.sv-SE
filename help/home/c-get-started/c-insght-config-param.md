---
description: Ange parametrarna i filen Insight.cfg för att ange inställningarna för nätverksanslutningen och Data Workbench-konfigurationen.
solution: Analytics
title: Konfigurationsparametrar
topic: Data workbench
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Konfigurationsparametrar{#configuration-parameters}

Ange parametrarna i filen Insight.cfg för att ange inställningarna för nätverksanslutningen och Data Workbench-konfigurationen.

Följande exempel innehåller som standard bara de parametrar som finns i [!DNL Insight.cfg] filen.

**Ny layoutvy**

![](assets/config_tree_new_layout.png)

**Ursprunglig layoutvy**

![](assets/cfg_Workstation_AddServer.png)

Vissa av de parametrar som är tillgängliga i den nya [!DNL Insight.cfg] filen kanske inte är tillgängliga i din version av [!DNL Insight.cfg] filen. Om en av dessa parametrar behövs måste du lägga till den i [!DNL Insight.cfg] filen med [!DNL Add Custom Key]genom att högerklicka på en parameter och sedan ange namn och typ. Du kan också lägga till parametrar genom att öppna [!DNL .cfg] filen (som finns i installationskatalogen för Data Workbench) med en textredigerare.

Här följer ett exempel på alla parametrar som är tillgängliga för [!DNL Insight.cfg] filen och som du kan använda som modell för att lägga till parameterposter:

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

Följande tabell innehåller beskrivningar av de tillgängliga [!DNL Insight.cfg] filparametrarna i alfabetisk ordning.

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adress </p> </td> 
   <td colname="col2"> <p>Värdnamnet eller den numeriska IP-adressen för Data Workbench-serverdatorn. </p> <p>Exempel: vsServer.mycompany.com <span class="filepath"> eller 192.168.1.90</span> </p> <p>Om <span class="wintitle"> Adress</span> inte anges använder <span class="keyword"> klienten</span> det vanliga namn som anges i parametern Gemensamt namn för SSL-server när Använd adressfil är inställd på false. </p> <p> <p>Obs! Om parametern Använd adressfil är inställd på true kan texten som anges i parametern Address tas bort efter att den första profilen har öppnats på <span class="keyword"> klienten</span>. Sedan avgör inställningen för parametern Nätverksplats vilka adresser från adressfilen för klustret som används för att ansluta till huvudservern. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Färguppsättning </p> </td> 
   <td colname="col2"> <p>Anger bakgrundsfärgen för ditt <span class="keyword"> klientprogram</span>. Alternativen är följande: </p> <p>0 = svart </p> <p>1 = vit </p> <p>2 = monokrom </p> <p>Standardvärdet är 0, svart. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standardnivå online </p> </td> 
   <td colname="col2"> <p>Valfritt. Gör att du kan få din instans av Data Workbench att fungera som standard som direktuppspelning, offline eller online varje gång den öppnas. Alternativen är Direktuppspelning, Online eller Offline. Standardkonfigurationen för Data Workbench är att arbeta offline. </p> <p> <p>Obs! Innan du bestämmer dig för att arbeta online som standard, se till att väga fördelarna och konsekvenserna som beskrivs i <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Arbeta offline och online</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Teckensnitt </p> </td> 
   <td colname="col2"> <p>Valfritt. Vektor som listar teckensnitten som <span class="keyword"> klienten</span> ska använda för att återge UTF8-baserade Unicode-specialtecken. Antalet teckensnitt i listan är obegränsat. </p> <p>Det första teckensnittet ska alltid vara Lucida Sans Console. Om den här parametern inte ingår i <span class="filepath"> filen Insight.cfg</span> används bara Lucida Sans-konsolen för att visa text i Data Workbench. </p> <p> Data Workbench använder det första teckensnittet i listan för att återge alla tecken tills det påträffar ett tecken som det inte kan återge. Det använder det andra teckensnittet i listan för att återge det tecknet. Om det teckensnittet inte återger tecknet använder Data Workbench det tredje teckensnittet i listan för att återge det tecknet, och så vidare, tills det kommer till slutet av teckensnittslistan. Om rätt teckensnitt inte finns med i vektorn visas det hexadecimala värdet för tecknet i Data Workbench. </p> <p> <p>Obs!  Ändra inte den här parametern medan Data Workbench körs. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Gammainställning för visning av Data Workbench. Standardvärdet är 1,6. Adobe rekommenderar inte att du ändrar det här värdet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licenser </p> </td> 
   <td colname="col2"> <p>Valfritt. Du behöver bara ändra parametrarna i licensvektorn om du kontaktar Adobes licensserver via en proxyserver. </p> <p>Avsnittsidentifierare för parametrar som gör att din <span class="keyword"> klient</span> kan kontakta Adobe License Server via en proxyserver. Expandera licensieringsnoden och fyll i följande parametrar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyadress </p> </td> 
   <td colname="col2"> <p>Valfritt. Adress till den proxyserver som <span class="keyword"> klienten</span> måste använda för att få åtkomst till Adobe License Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyport </p> </td> 
   <td colname="col2"> <p>Valfritt. Proxyserverns port. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyanvändarnamn </p> </td> 
   <td colname="col2"> <p>Valfritt. Användarnamnet för proxyservern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxylösenord </p> </td> 
   <td colname="col2"> <p>Valfritt. Lösenordet som är kopplat till proxyanvändarnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximal provstorlek (MB) </p> </td> 
   <td colname="col2"> <p>Anger den största tillåtna storleken i datacachen som används av <span class="keyword"> klienten</span> som körs på en enskild dator. </p> <p>Parametern Sample Bytes i filen <span class="filepath"> Server.cfg</span> anger datacachestorleken för alla <span class="keyword"> klienter</span> som ansluter till en Data Workbench-server (250e6 byte som standard), men parametern Maximum Sample Size gör att du kan begränsa datacachestorleken ytterligare för en viss dator. Detta är användbart när klienten är installerad på en dator med begränsad lagringskapacitet eller datorkraft. </p> <p> <p>Obs! Den här parametern begränsar storleken på ett lokalt dataexempel som efterfrågas lokalt av klientprogrammet. Filen cache.db <span class="filepath"></span> innehåller däremot data för varje profil som klienten ansluter till, plus elementnamnen och deras dimensioner. Dessa elementnamn och dimensioner i <span class="filepath"> cache.db</span> -filerna krävs för att köra lokala frågor. Det finns alltså inget annat sätt att begränsa dess storlek än att minska antalet element i datauppsättningen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Namn </p> </td> 
   <td colname="col2">Valfritt. Namnet som <span class="keyword"> klienten</span> använder för att identifiera <span class="keyword"> servern</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nätverksplats </p> </td> 
   <td colname="col2"> <p>Valfritt. Nätverksplatsen som <span class="keyword"> klienten</span> använder för att matcha Data Workbench-serverns vanliga namn mot en IP-adress. De tillgängliga nätverksplatserna definieras i adressfilen på servern. Mer information finns i <i>Server Products Installation and Administration Guide</i>. </p> <p>Om du inte anger en nätverksplats, kommer klienten <span class="keyword"></span> att matcha vanliga namn med standardnätverksplatsen "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port </p> </td> 
   <td colname="col2"> <p>Den port som <span class="keyword"> klienten</span> skickar begäranden till. Portnumret måste matcha den port som Data Workbench-servern lyssnar efter begäranden på. Detta är vanligtvis 443 för säkra anslutningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyadress </p> </td> 
   <td colname="col2"> <p>Om en proxyserver krävs för att ansluta till Data Workbench-serverdatorerna måste du slutföra åtminstone den här parametern och proxyportparametern. Du kan också slutföra parametrarna Proxyanvändarnamn och Proxyanvändarlösenord. </p> <p>Adress till den proxyserver som <span class="keyword"> klienten</span> måste använda för att få åtkomst till Data Workbench-servern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxylösenord </p> </td> 
   <td colname="col2"> <p>Valfritt. Lösenordet till proxyservern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyport </p> </td> 
   <td colname="col2"> <p>Proxyserverns port. Standardvärdet är 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxyanvändarnamn </p> </td> 
   <td colname="col2"> <p>Valfritt. Användarnamnet för proxyservern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sök </p> </td> 
   <td colname="col2"> <p>I <span class="filepath"> Insight.cfg</span> (eller en annan <span class="filepath"> .cfg</span> -fil) kan du söka efter nyckelnamn, nyckeltyp eller värde för att snabbt hitta en post, för att ta bort behovet av att bläddra igenom expanderade stora filer för kapslad information. Du kan hitta dimensionsnamn, servernamn och så vidare. </p> <p>Skriv en sökfras i det här fältet för att hitta data. Beroende på om en matchning lyckades ändras fältfärgen. Matchningar visas markerade och icke-matchningar är nedtonade. Om det inte finns några träffar blir bakgrunden i sökfältet röd. När du trycker på Retur expanderar config-trädet varje plats där det finns en matchning och komprimerar där det inte finns någon matchning. </p> <p>Du kan också använda reguljära uttryck i fältet <span class="wintitle"> Sök</span> . Du kan till exempel använda följande: <span class="filepath"> *zip.*</span> för alla tävlingsbidrag som innehåller ordet "zip". </p> <p>Om du vill ta bort en sökning trycker du på <span class="uicontrol"> Esc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servrar </p> </td> 
   <td colname="col2"> <p>Vektorrubrik för <span class="keyword"> klient</span> -till- <span class="keyword"> server</span> -anslutningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-klientcertifikat </p> </td> 
   <td colname="col2"> <p>Valfritt om du inte har fler än ett certifikat. Namnet på filen som innehåller det digitala certifikatet för den här kopian av Data Workbench. Det här är filen som du hämtade när du hämtade och installerade det digitala certifikatet. </p> <p>Exempel: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Om du lämnar den här parametern tom använder <span class="keyword"> klienten</span> det certifikat som finns. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-serverns namn </p> </td> 
   <td colname="col2"> <p>Det vanliga namnet på Data Workbench-servern (som tilldelats på dess digitala certifikat). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ikoner i verktygsfältet </p> </td> 
   <td colname="col2"> <p>Falskt stänger av ikonerna i arbetsstationens användargränssnitt och visar text i verktygsfältet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd adressfil </p> </td> 
   <td colname="col2"> <p>Anger om några inställningar i adressfilen åsidosätter inställningen för parametern Address. Alternativen är true eller false. Om värdet är true åsidosätter inställningarna i adressfilen, om sådana finns, inställningen för parametern Address. Standardvärdet är true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd SSL </p> </td> 
   <td colname="col2">Anger om SSL används för säker kommunikation mellan Data Workbench-servern och <span class="keyword"> klienten</span>. Alternativen är true eller false. Standardvärdet är true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visa alla </p> </td> 
   <td colname="col2"> <p>Valfritt. Gör att du tillfälligt kan visa alla mått, dimensioner och filter som har dolts med någon av följande funktioner: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">Inställningen [Exklusiv] i <span class="filepath"> order.txt</span> -filer </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Dölj alternativ i <span class="filepath"> order.txt</span> -filer </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Visa parametern i <span class="filepath"> .metric</span>-, <span class="filepath"> .dim</span>- och <span class="filepath"> .filter</span> -filer. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Dold parameter i <span class="filepath"> Transformation.cfg</span> -filen. </li> 
     </ul> </p> <p>Mer information om de här metoderna finns i <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Dölj ett menyalternativ</a>. </p> <p>Alternativen är true eller false. Standardinställningen är false. Ändra den här parametern till true om du tillfälligt vill visa dolda mått, dimensioner och filter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lås upp </p> </td> 
   <td colname="col2"> <p>Valfritt. Anger om du får låsa upp låsta arbetsytor. Alternativen är true och false. True gör att du kan låsa upp låsta arbetsytor, men false gör det inte. Standardvärdet är false. Mer information om låsta arbetsytor finns i <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Lås upp en arbetsyta</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uppdatera programvara </p> </td> 
   <td colname="col2"> <p>Valfritt. Anger om detta <span class="keyword"> </span>klientprogram ska kunna uppdateras av Data Workbench-servern. Alternativen är true eller false. Standardvärdet är true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användarmapp </p> </td> 
   <td colname="col2"> <p>Valfritt. Anger namn och plats för mappen som innehåller lokala kopior av arbetsytor, mått, dimensioner eller konfigurationsfiler för varje profil. Standardinställningen är User\\, som anger användarmappen i installationskatalogen för Data Workbench. </p> <p>Om du ändrar den här inställningen kan det vara praktiskt när två användare delar samma dator. Om du vill att båda användarna ska få plats kan du ange en delad mapp som båda användarna har åtkomst till. </p> </td> 
  </tr> 
 </tbody> 
</table>

