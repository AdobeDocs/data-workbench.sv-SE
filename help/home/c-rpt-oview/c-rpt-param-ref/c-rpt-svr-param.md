---
description: Information om parametrar för Report Server.cfg.
title: Report Server.cfg-parametrar
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Report Server.cfg-parametrar{#report-server-cfg-parameters}

{{eol}}

Information om parametrar för Report Server.cfg.

Provet [!DNL Report Server.cfg] visas i [Konfigurera anslutningen till Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) innehåller endast de parametrar som ingår i [!DNL Report Server.cfg] som standard.

Om du kontaktar Adobe licensserver via en proxyserver måste du lägga till licensvektorn och dess parametrar i [!DNL Report Server.cfg]. Här följer ett exempel på den här vektorn och dess parametrar som du kan använda som modell för din licensvektor:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

Följande tabell innehåller beskrivningar av [!DNL Report Server.cfg] filparametrar:

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
   <td colname="col2"> <p>Excel-tillägg som stöds är: </p> <p>Excel-tillägg = sträng: <span class="filepath"> .xlsx </span> </p> <p>Excel-tillägg = sträng: <span class="filepath"> .xls </span> (det här är standard) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Teckensnitt </td> 
   <td colname="col2"> <p>Valfritt. Vektor som listar teckensnitten som <span class="keyword"> Rapportserver </span> bör använda för att återge UTF8-baserade Unicode-specialtecken. Antalet teckensnitt i listan är obegränsat. </p> <p>Det första teckensnittet ska alltid vara Lucida Sans Console. Om den här parametern inte ingår i <span class="filepath"> Report Server.cfg </span> fil, <span class="keyword"> Rapportserver </span> använder bara Lucida Sans-konsolen för att visa text. </p> <p> <span class="keyword"> Rapportserver </span> I används det första teckensnittet i listan för att återge alla tecken tills ett tecken som inte kan återges påträffas. Sedan används det andra teckensnittet i listan för att återge det tecknet. Om det teckensnittet inte återger tecknet, <span class="keyword"> Rapportserver </span> använder det tredje teckensnittet i listan för att återge det tecknet, och så vidare, tills det kommer till slutet av teckensnittslistan. Om rätt teckensnitt inte finns med i vektorn <span class="keyword"> Rapportserver </span> visar det hexadecimala värdet för tecknet. </p> <p> <p>Obs! Gör inga ändringar i den här parametern när <span class="keyword"> Rapportserver </span> är igång. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma </span> inställning för <span class="filepath"> .png </span> filutdata. Standardvärdet är 1,6. </p> <p> <p>Obs! Adobe rekommenderar inte att du ändrar det här värdet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licenser </td> 
   <td colname="col2"> <p>Valfritt. Du behöver bara ändra parametrarna i den här vektorn om du kontaktar Adobe licensserver via en proxyserver. </p> <p>Avsnittsidentifierare för parametrar som du anger ska kontakta Adobe licensserver via en proxyserver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyadress </td> 
   <td colname="col2"> Adressen till en proxyserver som <span class="keyword"> Rapportserver </span> måste använda för att få åtkomst till Adobe licensserver. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxylösenord </td> 
   <td colname="col2"> Valfritt. Lösenordet som är kopplat till <span class="wintitle"> Proxyanvändarnamn </span>. </td> 
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
   <td colname="col2"> Nätverksplatsen som <span class="keyword"> Rapportserver </span> används för att matcha serverns namn mot en IP-adress. Nätverksplatser definieras i adressfilen som finns i katalogen Addresses på servern data workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Servrar </td> 
   <td colname="col2"> <p>Avsnittsidentifierare för parametrar som du anger för att konfigurera vilka data workbench-serverdatorer <span class="keyword"> Rapportserver </span> måste ansluta för att generera rapporter. Detta inkluderar en siffra som anger hur många objekt som visas i den här vektorn. </p> <p>Lägg till en serverInfo-post för varje server och fyll i parametrarna efter behov. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adress </td> 
   <td colname="col2"> IP-adress till den data workbench-serverdator till vilken <span class="keyword"> Rapportserver </span> måste ansluta för att generera rapporter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> Namnet som <span class="keyword"> Rapportserver </span> använder internt för att identifiera data workbench-servern. Det här är bara en intern etikett, så du kan använda vilket namn du vill. Vi rekommenderar att du använder det vanliga namnet som finns på serverns digitala certifikat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port som <span class="keyword"> Rapportserver </span> kommunicerar med data workbench-servern. För säkra anslutningar är det här värdet vanligtvis 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxyadress </td> 
   <td colname="col2"> Adressen till en proxyserver som <span class="keyword"> Rapportserver </span> måste använda för att komma åt data workbench-servern. Den här parametern behövs bara när en proxyserver krävs för att ansluta till serverdatorerna. </td> 
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
   <td colname="col2"> Namn på SSL-certifikatfilen för <span class="keyword"> Rapportserver </span> dator. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-serverns namn </td> 
   <td colname="col2"> <span class="wintitle"> Serverns namn </span> som anges på data workbench-serverns digitala certifikat. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd SSL </td> 
   <td colname="col2"> Anger om SSL används för säker kommunikation mellan data workbench-servern och <span class="keyword"> Rapportserver </span>. Alternativen är true eller false. Standardvärdet är true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Resultatminnesgräns (kB) </td> 
   <td colname="col2"> <p>Mängden minne (i kB) som du vill göra tillgängligt för rapporter och aviseringar. Standardvärdet är 50000. </p> <p>När rapporter körs <span class="keyword"> Rapportserver </span> kontrollerar det här värdet först och kontrollerar sedan värdet i parametern Maximal segmentstorlek. Om du till exempel anger parametern till 50 000 och den maximala segmentstorleken till 50, <span class="keyword"> Rapportserver </span> kör bara 50 arbetsytor i taget, även om det finns utrymme för att köra fler arbetsytor. </p> <p> <p>Obs! Den här gränsen får aldrig överskrida det värde som angetts i parametern Query Memory Limit för data workbench-servern, och bör, helst, anges lite lägre än <span class="wintitle"> Gräns för frågeminne </span> för att ge lite utrymme till andra användare som kan köra rapporter samtidigt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maximal segmentstorlek </td> 
   <td colname="col2"> Högsta antal rapportarbetsytor som <span class="keyword"> Rapportserver </span> kan köras samtidigt. Standardvärdet är 50. Mer information om hur <span class="keyword"> Rapportserver </span> använder den här inställningen, se <span class="wintitle"> Resultatminnesgräns (kB) </span> parameterbeskrivning. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uppdatera programvara </td> 
   <td colname="col2"> <p>Anger om detta ska tillåtas <span class="keyword"> Rapportserverns </span> som ska uppdateras av data workbench-servern. Alternativen är true eller false. Standardvärdet är true. </p> <p>Här följer ett exempel på den här parametern som du kan använda en modell: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Använd OpenGL-maskinvaruåtergivning </td> 
   <td colname="col2"> <p>Kontrollerar om <span class="keyword"> Rapportserver </span> använder maskinvaruåtergivning (till exempel datorns grafikkort) för att skapa rapportutdata. Alternativen är true eller false. Standardvärdet är true. </p> <p>Den här parametern ska bara anges till false om du har problem med grafikkortet. Om värdet är false <span class="keyword"> Rapportserver </span> försöker inte använda maskinvaruåtergivning och använder programvaruåtergivning som standard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rapportering </td> 
   <td colname="col2"> Avsnittsidentifierare för parametrar som du anger för att konfigurera rapportering. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervall för slutförandemeddelande </td> 
   <td colname="col2"> <p>Frekvensen (i sekunder) med vilken <span class="keyword"> Rapportserver </span> skriver ut statusmeddelanden om slutförande när frågor körs under rapport- eller aviseringsgenerering. Standardvärdet är 120 sekunder. </p> <p>Exempel: Arbetsytefrågor har slutförts till 62,145672 %. </p> <p>Slutförandemeddelanden skrivs till <span class="filepath"> reportserver.log </span> och synkroniseras med servern. Den här inställningen styr <span class="filepath"> status.txt </span> filer som skickas fram och tillbaka för varje rapportuppsättning, så att procentandelen slutförd kan visas med miniatyrbilder. Meddelandena skickas när en rapportuppsättning har slutförts eller när intervallet har nåtts, beroende på vilket som inträffar först. Om du anger det här högre värdet påverkas inte den frekvens med vilken du ser rapport som genereras i klientgränssnittet av miniatyrbilderna, men det påverkar hur många mellanliggande meddelanden du ser. Om du anger ett lågt värde kan systemet lägga mycket tid på att synkronisera data, eftersom data synkroniseras från <span class="keyword"> Rapportserver </span> till profilen, för alla DPU:er och för alla anslutna klienter varje gång en <span class="filepath"> status.txt </span> meddelandet ändras. </p> <p>Systemet skickar alltid en <span class="filepath"> status.txt </span> när en rapportuppsättning har slutförts, oavsett inställningen för den här konfigurationsparametern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profiler </td> 
   <td colname="col2"> <p>Nummer som anger hur många objekt som visas i den här vektorn. Lägg till en <span class="wintitle"> ReportProfile </span> i profilvektorn och fyll i parametrarna Server och Profil. </p> <p> <span class="wintitle"> Server </span> - Namnet som <span class="keyword"> Rapportserver </span> använder internt för att identifiera data workbench-servern. Det här namnet måste vara serverns vanliga namn som anges i data workbench-serverns SSL-certifikat. </p> <p> <span class="wintitle"> Profil </span> - Namnet på den profil som rapporter ska skapas för. Det här namnet måste matcha den namngivna profilen på data workbench-serverdatorn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fel </td> 
   <td colname="col2"> <p>Adress till SMTP-servern som du vill skicka från <span class="wintitle"> Rapportserver </span> fel via e-post. </p> <p>Exempel: <span class="filepath"> mail.mycompany.com </span> </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fellösenord </td> 
   <td colname="col2"> <p>Lösenordet för inloggning på SMTP-servern. Den här parametern är valfri om inte inloggning krävs för att skicka e-post. </p> <p>Det krävs en SMTP-server för att de angivna funktionerna ska kunna användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP-server för fel som skickats från </td> 
   <td colname="col2"> E-postadressen som du vill skicka från <span class="wintitle"> Rapportserver </span> fel. </td> 
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
   <td colname="col2"> <p>Frekvensen (i sekunder) med vilken <span class="wintitle"> Rapportserver </span> genererar och skickar statusinformation till data workbench-servern som ska visas i <span class="wintitle"> Detaljerad status </span>. </p> <p>Standardvärdet är 120 sekunder. Vi rekommenderar inte att du anger det här till ett lågt värde, till exempel två minuter, eftersom det kan ta timmar att köra en rapportkö. I så fall kan du överväga en inställning på 600 till 1 200 sekunder. </p> <p>Mer information om <span class="wintitle"> Detaljerad status </span>, se kapitlet om administrationsgränssnitt i <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Användarhandbok för Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uppdateringsintervall </td> 
   <td colname="col2"> <p>Frekvensen (i minuter) med vilken <span class="keyword"> Rapportserver </span> Övervakar alla profiler som listas i profilvektorn för nya rapporter och varningar. Standardvärdet är 10 minuter. </p> <p>Den tid du anger delas upp bland alla profiler som visas. Om intervallet till exempel är 10 minuter och du övervakar två profiler, övervakas varje profil i 5 minuter. Om en profil övervakas när en ny eller ändrad rapport eller avisering sparas i profilen är rapporten eller aviseringen omedelbart tillgänglig för generering. </p> <p>Om <span class="wintitle"> Uppdateringsintervall </span> är konfigurerad för att övervaka mer än en profil är det viktigt att den här inställningen är tillräckligt hög för att läsa in alla profiler inom den konfigurerade tiden. I system med många konfigurerade stora dimensioner, till exempel där det kan ta flera minuter att hämta den initiala dataanslutningen med alla elementnamn, måste den här inställningen vara tillräckligt lång för att den fullständiga synkroniseringen ska ske. I annat fall genereras ett profilsynkroniseringsfel. </p> </td> 
  </tr> 
 </tbody> 
</table>
