---
description: När du har installerat programfilerna för Insight måste du ladda ned och installera det digitala certifikatet från Adobe.
title: Hämta och installera det digitala certifikatet
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hämta och installera det digitala certifikatet{#downloading-and-installing-the-digital-certificate}

När du har installerat programfilerna för Insight måste du ladda ned och installera det digitala certifikatet från Adobe.

## Hämta och installera det digitala certifikatet {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

När du har installerat programfilerna för Insight måste du ladda ned och installera det digitala certifikatet från Adobe.

## Understanding Digital Certificates {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe använder digitala X.509-certifikat för att identifiera och autentisera klient- och serverkomponenter som utgör en implementering.

<!--
c_undst_dgtl_crtf.xml
-->

När du installerar Insight måste du installera det digitala certifikatet som tillåter en namngiven individ (till exempel Jane Smith) att använda det installerade klientprogrammet.

>[!NOTE]
>
>Om du behöver migrera Insight till en annan dator eller en annan namngiven användare måste du skaffa ett nytt certifikat från Adobe. Kontakta Adobes kundtjänst om du vill göra det.

Insight presenterar det här digitala certifikatet för att få åtkomst till en serverkomponent. En administratör för en serverkomponent kan begränsa åtkomsten till serverresurser baserat på de värden för det vanliga namnet eller organisationsenheten som visas i användarens certifikat.

De digitala X.509-certifikat som installeras med Adobe-program gör det även möjligt för dess klient- och serverkomponenter att utbyta information via SSL (Secure Sockets Layer). SSL skyddar överföringar via HTTP med hjälp av ett krypteringssystem för offentlig och privat nyckel. Adobes implementering av SSL stöder 1024-bitars RSA-nycklar och använder en 128-bitars RC4-krypteringsalgoritm.

Förutom säkerhet fungerar det digitala certifikatet som du installerar även som en licensnyckel som gör att du kan köra Insight. För att det ska fungera på rätt sätt måste ett digitalt certifikat vara nodlåst och aktuellt, annars startar inte programmet.

## Nodlåsta certifikat {#section-984aa8f2f5a1448cadc4afea978aedc9}

Ett nodlåst certifikat är ett digitalt certifikat som har registrerats på den dator där det är installerat. Nodlåsning associerar ett certifikat permanent med en specifik nodidentifierare (ett värde som unikt identifierar en viss dator). Om du vill låsa certifikatet med nod måste datorn ha Internetåtkomst till Adobe License Server eller till en proxyserver som har åtkomst till licensservern.

Om du installerar på en dator som inte har åtkomst till Internet måste du skaffa och installera ett särskilt förlåst certifikat enligt beskrivningen i [Använda digitala certifikat på datorer utan Internet-åtkomst](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1).

Om du installerar på en dator som har åtkomst till Internet kommer ditt digitala certifikat att låsas automatiskt första gången du startar Insight. När certifikatet har låsts till en nod kan det inte användas på någon annan dator. Om du behöver migrera Insight till en annan dator måste du skaffa ett nytt, olåst certifikat från Adobe.

## Aktuella certifikat {#section-0816b031df3e415ab3f0205b720c723e}

Förutom att vara nodlåst måste ditt digitala certifikat vara aktuellt. För att ditt certifikat ska förbli aktuellt måste det förnyas regelbundet (vanligtvis var 30:e dag, men det kan variera beroende på ditt avtal med Adobe). Om datorn har Internet-åtkomst är valideringsprocessen helt genomskinlig. Insight ansluter automatiskt till licensservern och förnyar certifikatet vid behov. Om datorn inte har Internet-åtkomst måste du installera ett uppdaterat certifikat manuellt enligt beskrivningen i följande avsnitt.

## Använda digitala certifikat på datorer utan Internet-åtkomst {#section-d3c060131d7f45cda27f68848b704fa1}

Om du installerar på en dator som inte har åtkomst till Internet måste du begära ett förlåst certifikat för din installation av Insight. Ett förlåst certifikat är ett digitalt certifikat som Adobe manuellt låser till datorns nodidentifierare.

Om du vill begära ett förlåst certifikat måste du skicka nodidentifieraren och ditt certifikatnummer till Adobes kundtjänst. Kontakta Adobes kundtjänst om du vill ha nodidentifieraren för din dator för att få tillgång till Adobes [!DNL Node Identifier] verktyg. Du kan också hämta nodidentifieraren från varningen som Insight utfärdar när det försöker ansluta till licensservern och inte kan. När du får det förlåsta certifikatet installerar du det enligt beskrivningen i de två sista stegen i [Installera digitala certifikat](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38).

När certifikatet behöver valideras på nytt måste du hämta ett nytt, validerat certifikat från licensservern och installera om det på datorn (om inte avtalet med Adobe medger något annat).

## Installera digitala certifikat {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Hämta och installera det digitala certifikatet**

1. Öppna webbläsaren i [!DNL http:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Din webbläsare kan uppmana dig att presentera ett digitalt certifikat just nu. Om så är fallet klickar du på **[!UICONTROL Cancel]** för att stänga dialogrutan.

1. På inloggningsskärmen anger du det [!DNL Account Name] och [!DNL Password] det du fick från Adobe och klickar sedan på **[!UICONTROL login]**.
1. Leta reda på certifikatet som har utfärdats för din instans av Insight ( *ditt namn*.pem) och klicka på den ![](assets/btn_save_certificatedownload.PNG) ikon som är kopplad till certifikatet.
1. När du uppmanas att spara certifikatet klickar du på **[!UICONTROL Save]**.
1. Ladda ned filen till [!DNL Certificates] mappen i den katalog där du installerade Insight.

   Den här mappen innehåller en certifikatfil med namnet [!DNL trust_ca_cert.pem]. Båda certifikatfilerna måste alltid finnas för att Insight ska fungera.

## Windows certifikatarkiv {#concept-4acb13b7de9340ea8cde8ad84b93358d}

I Windows certifikatarkiv lagras klientens certifikat och privata nyckel i Windows certifikatarkiv för SSL-kommunikation med servrar.

<!--
crypto-api.xml
-->

Windows certifikatarkiv för klienten är en ny funktion som gör att du kan lagra SSL-kommunikationscertifikatet och den privata nyckeln i Windows certifikatarkiv i stället för i `Insight/Certificates/<CertName>.pem` filen. Det kan vara bättre att använda Windows certifikatarkiv om du använder certifikatarkivet för andra program och vill hantera certifikat på ett ställe, eller för användare som använder den extra Windows-granskningsloggning som tillhandahålls av Windows certifikatarkiv.

>[!NOTE]
>
>Licensiering med licensservern upprätthålls fortfarande med den befintliga `<Common Name>.pem` filen och certifikatet som hämtas från certifikatarkivet används endast för kommunikation med de servrar som du anger.

## Förutsättningar {#section-69b18600052145ff8e5299b7123e69c5}

1. Du måste ha åtkomst till [!DNL certmgr.msc] filen med möjlighet att importera ett certifikat och en nyckel till **Personal** Store. (Detta bör vara sant som standard för de flesta Windows-användare.)

1. Användaren som utför konfigurationen måste ha en kopia av **kommandoradsverktyget OpenSSL** .
1. Servern och klienten måste redan vara konfigurerade att använda ett anpassat SSL-certifikat, och ger instruktioner om att lagra klientcertifikatet i Windows certifikatarkiv i stället för att lagra det i **certifikatkatalogen** .

## Konfigurerar Windows certifikatarkiv {#section-3629802122e947d4b4f63e8b732cfe27}

Windows certifikatarkiv för klienter är aktiverat enligt följande:

**Steg 1: Importera användarens SSL-certifikat och privata nyckel till Windows certifikatarkiv.**

I [Använda anpassade certifikat i Data Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) omdirigeras du till att placera SSL-certifikatet och nyckeln i följande katalog:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Certifikatets namn är `<Common Name>.pem` t.ex. Analytics Server 1.pem (inte filen trust_ca_cert.pem.)

Innan certifikatet och den privata nyckeln kan importeras måste de konverteras från . [!DNL pem] till ett [!DNL .pfx] format, till exempel [!DNL pkcs12.pfx] ).

1. Öppna en kommandotolk eller terminal och navigera till katalogen:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Kör [!DNL openssl] med följande argument (med det faktiska [!DNL .pem] filnamnet):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Om du uppmanas till det trycker du på **Enter** för att hoppa över att ange ett exportlösenord.

1. Kör [!DNL certmgr.msc] från körningsprompten, startmenyn eller kommandoraden.
1. Öppna det **personliga** certifikatarkivet för den aktuella användaren.

   ![](assets/6_5_crypto_api_0.png)

1. Högerklicka på **Certifikat** och klicka på **Alla åtgärder** > **Importera**.

   Kontrollera att alternativet **Aktuell användare** är markerat och klicka sedan på **Nästa**.

   ![](assets/6_5_crypto_api_4.png)

1. Klicka på **Bläddra** och markera den `<CommonName>.pfx` fil du skapade tidigare. Du måste ändra listrutan för filtillägg från ett X.509-certifikat till **Personal Information Exchange** eller till **Alla filer** för att kunna se det.

   Markera filen, klicka på **Öppna** och sedan på **Nästa**.

1. Ange inget lösenord och se till att endast alternativen **Markera den här nyckeln som exporterbar** och **Inkludera alla utökade egenskaper** är markerade.

   ![](assets/6_5_crypto_api_3.png)

   Klicka på **Nästa**.

1. Kontrollera att **Placera alla certifikat i följande arkiv** är markerat och att det angivna certifikatarkivet är **Personligt**. (Om du är en avancerad användare kan du välja en annan butik just nu, men du måste ändra konfigurationen senare.)

1. Klicka på **Nästa** och sedan på **Slutför**. En dialogruta visas som anger att importen lyckades och att ditt certifikat finns i mappen Certifikat i butiken.

   >[!NOTE]
   >
   >Var särskilt uppmärksam på fälten **Utfärdat till** och **Utfärdat av** . Du kommer att behöva de här i nästa steg.

**Steg 2: Redigera filen Insight.cfg.**

Filen måste redigeras för att du ska kunna ange att Data Workbench ska använda funktionen Windows certifikatarkiv. [!DNL Insight.cfg] Varje serverpost i den här filen måste ha ytterligare parametrar angivna. Om parametrarna utelämnas används den befintliga certifikatkonfigurationen som standard. Om parametrarna anges men har felaktiga värden, kommer arbetsstationen att gå in i ett feltillstånd och du måste referera till loggfilen för felinformation.

1. Öppna filen **Insight.cfg** (finns i installationskatalogen för **Insight** ).

1. Bläddra ned till den serverpost som du vill konfigurera. Om du vill använda Windows certifikatarkiv för varje server måste du göra dessa ändringar för varje post i [!DNL serverInfo] objektvektorn.
1. Lägg till de här parametrarna i deras [!DNL Insight.cfg] fil. Du kan göra detta från arbetsstationen eller manuellt genom att lägga till följande parametrar till [!DNL serverInfo] objektet. (Se till att använda blanksteg i stället för tabbtecken och gör inga andra typografiska fel eller syntaxfel i den här filen. )

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   Den booleska funktionen aktiverar eller inaktiverar funktionen. Certifikatnamnet matchar **utfärdare till** i certifikatshanteraren. Certifikatutfärdarens namn matchar **Utfärdat av** och **Butiksnamnet** måste matcha certifikatarkivets namn.

   >[!NOTE]
   >
   >Namnet &quot;Personal&quot; i certifikatshanteraren (certmgr.msc) refererar till certifikatarkivet med namnet **My.** Om du importerar SSL-kommunikationscertifikatet och nyckeln (.PFX) till det **personliga** certifikatarkivet enligt rekommendation måste du ange **SSL CryptoAPI Cert Store-namnsträngen** till &quot;My&quot; (Mitt). Det går inte att ange den här parametern som &quot;Personlig&quot;. Detta är en egenskap i Windows certifikatarkiv.

   En fullständig lista över de fördefinierade systemarkiven finns här: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Systemet kan ha ytterligare certifikatarkiv. Om du vill använda ett annat arkiv än &quot;Personal&quot; (till exempel **Min**) måste du hämta det kanoniska namnet på certifikatarkivet och ange det i [!DNL Insight.cfg] filen. (Systemarkivnamnet &quot;My&quot; (Mitt) kallas inkonsekvent för &quot;My&quot; och &quot;MY&quot; i Windows-dokumentationen. Parametern verkar inte vara skiftlägeskänslig.)

1. När du har lagt till de här parametrarna och verifierat att värdena matchar listan i Windows Certifikatshanterare sparar du [!DNL Insight.cfg] filen.

Du kan nu starta arbetsstationen (eller koppla från/återansluta till servern). Data Workbench bör läsa in ditt certifikat och din nyckel från certifikatarkivet och ansluta normalt.

## Loggutdata {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

När ett certifikat inte hittas eller är ogiltigt visas det här felmeddelandet i [!DNL HTTP.log] filen.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>L4-loggningsramverket kan aktiveras genom att du konfigurerar [!DNL L4.cfg] filen (se din kontohanterare för att konfigurera detta).

## Använda anpassade certifikat i Data Workbench {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Instruktioner för hur du använder anpassade certifikat.

<!--
using-custom-certificates-DWB.xml
-->

Ett certifikat som används av Data Workbench-klienten eller servern måste signeras av en betrodd certifikatutfärdare (Certificate Authority). Data Workbench-kunder får certifikat som är signerade av Visual Sciences CA. Dessa certifikat är betrodda av Data Workbench-programmet, eftersom [!DNL trust_ca_cert.pem] (som tillhandahålls tillsammans med Insight-programmet och lagras i **certifikatkatalogen** för både servrar och klienter) innehåller ett *rotcertifikatutfärdarcertifikat* för Visual Sciences CA. Dessa certifikat används både för licensiering av programvaran och autentisering när klienter och servrar kommunicerar med varandra med SSL. Endast certifikat som utfärdats av Visual Sciences CA kan användas för licensiering, men andra certifikat kan användas för kommunikation och autentisering. Certifikat som utfärdats av andra certifikatutfärdare än Visual Sciences kallas nedan *anpassade certifikat.*

**Viktigt:** För servrar och klienter använder Data Workbench de certifikatfiler som är installerade i klientens eller serverns **certifikatkatalog** eller certifikat som uttryckligen identifieras i dess konfiguration. Du kan dock även använda Windows certifikatarkiv för klienter.

Följande instruktioner beskriver de procedurer som ska följas för att använda anpassade certifikat för kommunikation mellan Data Workbench-klienter och -servrar. Alla detaljer är inte ett svårt krav och olika processvariationer kan användas. Anvisningarna nedan har dock testats så att de fungerar.

## Konfigurera anpassade klientcertifikat {#section-2083fd41973e451fa404e7a4ae4da591}

1. Lägg till certifikatet för den utfärdande certifikatutfärdaren i [!DNL trust_cert_ca.pem], som är installerat i **certifikatkatalogen** för klienten och certifikatet för alla servrar i varje kluster som ska användas med det här anpassade certifikatet.

1. Hämta ett anpassat certifikat för varje server i klustret med följande villkor:

   1. Certifikatet är formaterat som ett [!DNL .pem] certifikat.
   1. Certifikatet innehåller dess nyckel och är okrypterat (det har alltså ingen lösenord/lösenordsfras).

      Ett certifikat innehåller en nyckel med en av följande rader:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Ett sätt att ta bort lösenordsfrasen från ett [!DNL .pem] certifikat:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certifikatet har CN, O, OU osv. som krävs för den här klienten i serverns [!DNL Access Control.cfg] fil.
   1. Certifikatet utfärdades i *syfte **** av *klienten* (eller både *server* **och** *klient*).

      Följande kommandon kan användas för att verifiera att ett certifikat har en avsedd kod som server och/eller klient:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      För ett servercertifikat bör båda kommandona ge:

      ```
      custom_communications_cert.pem: OK
      ```

      För ett klientcertifikat krävs bara det andra kommandot för att ge det [!DNL OK].

1. Placera certifikatet i klientens **certifikatkatalog** .
1. Kontrollera [!DNL Insight.cfg] under *serverInfo* för varje kluster som du vill använda det här certifikatet att det *anpassade klientcertifikatet* har ett namn, till exempel:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:  
     <my_custom_client_cert.pem>
   ```

## Konfigurera anpassade servercertifikat {#setting-up-custom-server-certificates}

I det här avsnittet förutsätts att du har ett kluster som körs med certifikat som utfärdats av Visual Sciences och att konfigurationen följer vanliga rutiner (som katalogen *Komponenter för att bearbeta servrar* på huvudservern synkroniseras med *komponentkatalogerna* för alla DPU:er).

1. Lägg till certifikatet för den utfärdande certifikatutfärdaren till den [!DNL trust_cert_ca.pem] som är installerad på alla servrar i klustret och alla klienter som behöver kommunicera med det här klustret.
1. Skaffa ett anpassat certifikat för varje server i klustret med följande krav:

   1. Anpassat certifikat är formaterat som ett [!DNL .pem] certifikat.
   1. Certifikatet innehåller dess nyckel och är okrypterat (det har alltså ingen lösenord/lösenordsfras).

      Ett certifikat innehåller en nyckel om det har en rad som:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Ett sätt att ta bort lösenordsfrasen från ett [!DNL .pem] certifikat:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Certifikatet har samma CN som den [!DNL server_cert.pem] som är installerad på servern.
   1. Certifikatet utfärdades i syfte att *skapa server* och *klient*.

      Följande kommandon kan användas för att verifiera att ett certifikat har en avsedd kod som server och/eller klient:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      För ett servercertifikat bör båda kommandona ge:

      ```
      custom_communications_cert.pem: OK
      ```

      För ett klientcertifikat krävs bara det andra kommandot för att ge det [!DNL OK].

1. Installera varje servers anpassade certifikat i **certifikatkatalogen** på servern som [!DNL custom_communications_cert.pem].

1. Med en textredigerare lägger du till följande rad i **filen Communications.cfg** i både *Components* och *Components för att bearbeta serverkataloger* , direkt under den första raden ( [!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Starta om alla servrar.

**Om certifikatfelsvarning**

När Insight-servern eller -klienten söker efter ett **licenscertifikat** i **certifikatkatalogen** försöker den validera alla certifikat (utom [!DNL trust_ca_cert.pem]) mot en hårdkodad kopia av Insight CA-certifikatet, som inte kan validera något anpassat certifikat i katalogen. Servern utfärdar den här varningen:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Den här varningen kan ignoreras.

## Strängkryptering {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Kryptera lösenord och andra strängar vid kommunikation mellan klienten och servern.

<!--
string_encryption.xml
-->

När du kommunicerar mellan Data Workbench-klienten (arbetsstation) och servern kan du spara en Value-parameter (till exempel ett lösenord) med typen *EncryptedString*. Parametern döljs och strängen sparas i *Windows Credential Store* på servern med motsvarande nyckel returnerad. Detta lagrar i första hand inloggningsuppgifter som används vid export, men kan användas för att kryptera alla parametrar.

* En ny mapp lades till på servern\**EncryptStrings**.

   Här anger du att konfigurationsfilen ska kryptera strängar.

* En ny konfigurationsfil har lagts till på Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent: 
     Path = Path: EncryptStrings\\*.cfg
   ```

   Filen söker efter krypteringskonfigurationsfiler i mappen *Server*\*EncryptStrings*.

**Så här krypterar du en sträng**:

1. Skapa en **EncryptedStrings.cfg** -konfigurationsfil för en sträng med följande fält:

   ```
   Names = vector: 1 items 
    0 = NameEncryptValuePair: 
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server 
     Name = string: // Name for identifier  
     Value = string: // Value to be encrypted
   ```

   * *Värde* - Det här fältet innehåller den vanliga textsträng som behöver krypteras.

      Detta är endast kryptering på serversidan. Inställningen *Värde* krypteras bara på serverdatorn.

   * *Namn* - Det här fältet innehåller ett värde som identifierar den krypterade strängen.
   * *EncryptValue* - Det här fältet lämnas tomt i indatakonfigurationsfilen. Det krypterade värdet returneras i det här fältet.
   Du kan lägga till flera **NameEncryptValuePair** -värden för olika fält för kryptering.

   >[!NOTE]
   >
   >Alla tomma värdefält tas bort.

1. Spara filen **EncryptedStrings.cfg** i mappen Server\**EncryptStrings**.

**Utdatafil**

En utdatafil genereras med samma namn som indatafilen med ett &lt;*filnamn*>.*krypterat* tillägg. Om indatafilen till exempel heter *sample.cfg* får utdatafilen namnet *sample.cfg.encrypted*.
