---
description: Information om parametrar för Report Server.cfg.
title: Report Server.cfg-parametrar
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 0%

---

# Report Server.cfg-parametrar{#report-server-cfg-parameters}

Information om parametrar för Report Server.cfg.

Exemplet [!DNL Report Server.cfg] som visas i [Configuring the Connection to Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) innehåller som standard bara de parametrar som finns i filen [!DNL Report Server.cfg].

Om du kontaktar licensservern Adobe via en proxyserver måste du lägga till licensvektorn och dess parametrar i [!DNL Report Server.cfg]. Här följer ett exempel på den här vektorn och dess parametrar som du kan använda som modell för din licensvektor:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Följande tabell innehåller beskrivningar av filparametrarna [!DNL Report Server.cfg]:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel-tillägg </td> 
   <td colname="col2"> <p>Excel-tillägg som stöds är: </p> <p>Excel-tillägg = sträng: <span class="filepath"> .xlsx </span> </p> <p>Excel-tillägg = sträng: <span class="filepath"> .xls </span> (detta är standard) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Teckensnitt </td> 
   <td colname="col2"> <p>Valfritt. En vektor som listar de teckensnitt som <span class="keyword"> Report Server </span> ska använda för att återge UTF8-baserade Unicode-specialtecken. Antalet teckensnitt i listan är obegränsat. </p> <p>Det första teckensnittet ska alltid vara Lucida Sans Console. Om den här parametern inte ingår i <span class="filepath"> Report Server.cfg </span>-filen använder <span class="keyword"> Report Server </span> bara Lucida Sans-konsolen för att visa text. </p> <p> <span class="keyword"> Report Server  </span> använder det första teckensnittet i listan för att återge alla tecken tills ett tecken som inte kan återges påträffas. Sedan används det andra teckensnittet i listan för att återge det tecknet. Om det teckensnittet inte återger tecknet använder <span class="keyword"> Report Server </span> det tredje teckensnittet i listan för att återge tecknet och så vidare, tills det kommer till slutet av teckensnittslistan. Om rätt teckensnitt inte finns med i vektorn visar <span class="keyword"> Report Server </span> tecknets hexadecimala värde. </p> <p> <p>Obs!  Gör inga ändringar i den här parametern när <span class="keyword"> Report Server </span> körs. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gammainställning  </span> för  <span class="filepath"> .png- </span> filutdata. Standardvärdet är 1,6. </p> <p> <p>Obs!  Adobe rekommenderar inte att du ändrar det här värdet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licenser </td> 
   <td colname="col2"> <p>Valfritt. Du behöver bara ändra parametrarna i den här vektorn om du kontaktar Adobe licensserver via en proxyserver. </p> <p>Avsnittsidentifierare för parametrar som du anger ska kontakta Adobe licensserver via en proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyadress </td> 
   <td colname="col2"> Adressen till en proxyserver som <span class="keyword"> Report Server </span> måste använda för att komma åt Adobe licensserver. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxylösenord </td> 
   <td colname="col2"> Valfritt. Lösenordet som är associerat med <span class="wintitle"> proxyanvändarnamnet </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyport </td> 
   <td colname="col2"> Proxyserverns port. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyanvändarnamn </td> 
   <td colname="col2"> Valfritt. Användarnamnet som används för att komma åt proxyservern. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nätverksplats </td> 
   <td colname="col2"> Nätverksplatsen som <span class="keyword">-rapportservern </span> använder för att matcha serverns vanliga namn mot en IP-adress. Nätverksplatser definieras i adressfilen som finns i katalogen Addresses på servern data workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servrar </td> 
   <td colname="col2"> <p>Avsnittsidentifierare för parametrar som du anger för att konfigurera vilka data-workbench-serverdatorer <span class="keyword"> Report Server </span> måste ansluta till för att generera rapporter. Detta inkluderar en siffra som anger hur många objekt som visas i den här vektorn. </p> <p>Lägg till en serverInfo-post för varje server och fyll i parametrarna efter behov. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adress </td> 
   <td colname="col2"> IP-adressen för den data workbench-serverdator som <span class="keyword"> Report Server </span> måste ansluta till för att generera rapporter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Namnet som <span class="keyword"> Report Server </span> använder internt för att identifiera data workbench-servern. Det här är bara en intern etikett, så du kan använda vilket namn du vill. Vi rekommenderar att du använder det vanliga namnet som finns på serverns digitala certifikat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port genom vilken <span class="keyword"> Report Server </span> kommunicerar med data workbench-servern. För säkra anslutningar är det här värdet vanligtvis 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyadress </td> 
   <td colname="col2"> Adressen till en proxyserver som <span class="keyword"> måste använda för att komma åt data workbench-servern. </span> Den här parametern behövs bara när en proxyserver krävs för att ansluta till serverdatorerna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxylösenord </td> 
   <td colname="col2"> Lösenordet till proxyservern. Den här parametern behövs bara när en proxyserver krävs för att ansluta till dina data workbench-serverdatorer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyport </td> 
   <td colname="col2"> Proxyserverns port. Standardvärdet är 8080. Den här parametern behövs bara när en proxyserver krävs för att ansluta till dina data workbench-serverdatorer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyanvändarnamn </td> 
   <td colname="col2"> Användarnamnet till proxyservern. Den här parametern behövs bara när en proxyserver krävs för att ansluta till dina data workbench-serverdatorer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-klientcertifikat </td> 
   <td colname="col2"> Namnet på SSL-certifikatfilen för <span class="keyword">-rapportservern </span>-datorn. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-serverns namn </td> 
   <td colname="col2"> <span class="wintitle"> Serverns allmänna namn  </span> visas på data workbench-serverns digitala certifikat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd SSL </td> 
   <td colname="col2"> Anger om SSL används för säker kommunikation mellan data workbench-servern och <span class="keyword"> Report Server </span>. Alternativen är true eller false. Standardvärdet är true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Resultatminnesgräns (kB) </td> 
   <td colname="col2"> <p>Mängden minne (i kB) som du vill göra tillgängligt för rapporter och aviseringar. Standardvärdet är 50000. </p> <p>När rapporter körs kontrollerar <span class="keyword"> Report Server </span> det här värdet först och kontrollerar sedan värdet i parametern Maximum Slice Size. Om du till exempel anger parametern till 50 000 och den maximala segmentstorleken till 50, kör <span class="keyword"> Report Server </span> bara 50 arbetsytor i taget, även om det finns utrymme för att köra fler arbetsytor. </p> <p> <p>Obs!  Den här gränsen får aldrig överskrida det värde som angetts i parametern Query Memory Limit för data workbench-servern och bör, helst, anges lite lägre än <span class="wintitle"> Query Memory Limit </span> för att ge utrymme till andra användare som kör rapporter samtidigt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maximal segmentstorlek </td> 
   <td colname="col2"> Det maximala antalet rapportarbetsytor som <span class="keyword"> rapportservern </span> kan köra samtidigt. Standardvärdet är 50. Mer information om hur <span class="keyword"> Report Server </span> använder den här inställningen finns i beskrivningen av parametern <span class="wintitle"> Result Memory Limit (KB) </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uppdatera programvara </td> 
   <td colname="col2"> <p>Anger om <span class="keyword">-rapportserverns </span>-programvara ska kunna uppdateras av data workbench-servern. Alternativen är true eller false. Standardvärdet är true. </p> <p>Här följer ett exempel på den här parametern som du kan använda en modell: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd OpenGL-maskinvaruåtergivning </td> 
   <td colname="col2"> <p>Kontrollerar om <span class="keyword"> Report Server </span> använder maskinvaruåtergivning (till exempel datorns grafikkort) för att skapa rapportutdata. Alternativen är true eller false. Standardvärdet är true. </p> <p>Den här parametern ska bara anges till false om du har problem med grafikkortet. Om värdet är false försöker <span class="keyword"> Report Server </span> inte använda maskinvaruåtergivning och använder programvaruåtergivning som standard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapportering </td> 
   <td colname="col2"> Avsnittsidentifierare för parametrar som du anger för att konfigurera rapportering. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervall för slutförandemeddelande </td> 
   <td colname="col2"> <p>Den frekvens (i sekunder) med vilken <span class="keyword"> Report Server </span> skriver ut statusmeddelanden för slutförande när frågor körs under rapport- eller aviseringsgenerering. Standardvärdet är 120 sekunder. </p> <p>Exempel: Arbetsytefrågor har slutförts till 62,145672 %. </p> <p>Slutförandemeddelanden skrivs till <span class="filepath"> rapportserver.log </span> och synkroniseras med servern. Den här inställningen styr <span class="filepath"> status.txt </span>-filerna som skickas fram och tillbaka för varje rapportuppsättning, så att procentandelen slutförd kan visas med miniatyrbilder. Meddelandena skickas när en rapportuppsättning har slutförts eller när intervallet har nåtts, beroende på vilket som inträffar först. Om du anger det här högre värdet påverkas inte den frekvens med vilken du ser rapport som genereras i klientgränssnittet av miniatyrbilderna, men det påverkar hur många mellanliggande meddelanden du ser. Om du anger ett lågt värde kan systemet lägga mycket tid på att synkronisera data, eftersom data synkroniseras från <span class="keyword"> Report Server </span>-servern till profilen, i alla DPU:er och till alla anslutna klienter varje gång ett <span class="filepath"> status.txt </span>-meddelande ändras. </p> <p>Systemet skickar alltid en <span class="filepath"> status.txt </span>-fil när en rapportuppsättning har slutförts, oavsett inställningen för den här konfigurationsparametern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profiler </td> 
   <td colname="col2"> <p>Nummer som anger hur många objekt som visas i den här vektorn. För varje profil som rapporter ska skapas för lägger du till en <span class="wintitle"> ReportProfile </span>-post i profilvektorn och slutför parametrarna Server och Profil. </p> <p> <span class="wintitle"> Server  </span> - Namnet som  <span class="keyword"> rapportservern  </span> använder internt för att identifiera data workbench-servern. Det här namnet måste vara serverns vanliga namn som anges i data workbench-serverns SSL-certifikat. </p> <p> <span class="wintitle"> Profil  </span> - Namnet på den profil som rapporter ska skapas för. Det här namnet måste matcha den namngivna profilen på data workbench-serverdatorn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fel </td> 
   <td colname="col2"> <p>Adress till SMTP-servern som du vill skicka <span class="wintitle"> rapportserverfel från via e-post.</span> </p> <p>Exempel: <span class="filepath"> mail.mycompany.com </span> </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fellösenord </td> 
   <td colname="col2"> <p>Lösenordet för inloggning på SMTP-servern. Den här parametern är valfri om inte inloggning krävs för att skicka e-post. </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fel som skickats från </td> 
   <td colname="col2"> E-postadressen som du vill skicka <span class="wintitle"> rapportserver </span>-fel från. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fel som skickats till </td> 
   <td colname="col2"> <p>Den eller de e-postadresser som varningarna skickas till. </p> <p>Exempel: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fel, användarnamn </td> 
   <td colname="col2"> <p>Användarnamnet för inloggning på SMTP-servern. Den här parametern är valfri om inte inloggning krävs för att skicka e-post. </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Statusintervall </td> 
   <td colname="col2"> <p>Frekvensen (i sekunder) med vilken <span class="wintitle"> Report Server </span> genererar och skickar statusinformation till data workbench-servern som ska visas i <span class="wintitle"> Detailed Status </span>. </p> <p>Standardvärdet är 120 sekunder. Vi rekommenderar inte att du anger det här till ett lågt värde, till exempel två minuter, eftersom det kan ta timmar att köra en rapportkö. I så fall kan du överväga en inställning på 600 till 1 200 sekunder. </p> <p>Mer information om <span class="wintitle"> Detaljerad status </span> finns i kapitlet Administrativa gränssnitt i <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Användarhandbok för Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uppdateringsintervall </td> 
   <td colname="col2"> <p>Frekvensen (i minuter) med vilken <span class="keyword"> Report Server </span> övervakar alla profiler i profilvektorn för nya rapporter och varningar. Standardvärdet är 10 minuter. </p> <p>Den tid du anger delas upp bland alla profiler som visas. Om intervallet till exempel är 10 minuter och du övervakar två profiler, övervakas varje profil i 5 minuter. Om en profil övervakas när en ny eller ändrad rapport eller avisering sparas i profilen är rapporten eller aviseringen omedelbart tillgänglig för generering. </p> <p>Om <span class="wintitle">-uppdateringsintervallet </span> är konfigurerat för att övervaka mer än en profil är det viktigt att den här inställningen är tillräckligt hög för att läsa in alla profiler inom den konfigurerade tiden. I system med många konfigurerade stora dimensioner, till exempel där det kan ta flera minuter att hämta den initiala dataanslutningen med alla elementnamn, måste den här inställningen vara tillräckligt lång för att den fullständiga synkroniseringen ska ske. I annat fall genereras ett profilsynkroniseringsfel. </p> </td> 
  </tr> 
 </tbody> 
</table>
