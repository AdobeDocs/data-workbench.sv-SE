---
description: I Windows certifikatarkiv lagras klientens certifikat och privata nyckel i Windows certifikatarkiv för SSL-kommunikation med servrar.
title: Windows certifikatarkiv
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: tm+mt
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 0%

---


# Windows certifikatarkiv{#windows-certificate-store}

I Windows certifikatarkiv lagras klientens certifikat och privata nyckel i Windows certifikatarkiv för SSL-kommunikation med servrar.

Windows certifikatarkiv för klienten är en ny funktion som gör att du kan lagra SSL-kommunikationscertifikatet och den privata nyckeln i Windows certifikatarkiv i stället för i `Insight/Certificates/<CertName>.pem` filen. Det kan vara bättre att använda Windows certifikatarkiv om du använder certifikatarkivet för andra program och vill hantera certifikat på ett ställe, eller för användare som använder den extra Windows-granskningsloggning som tillhandahålls av Windows certifikatarkiv.

>[!NOTE]
>
>Licensiering med licensservern upprätthålls fortfarande med den befintliga `<Common Name>.pem` filen och certifikatet som hämtas från certifikatarkivet används endast för kommunikation med de servrar som du anger.

## Förutsättningar {#section-69b18600052145ff8e5299b7123e69c5}

1. Du måste ha åtkomst till [!DNL certmgr.msc] filen med möjlighet att importera ett certifikat och en nyckel till **Personal** Store. (Detta bör vara sant som standard för de flesta Windows-användare.)

1. Användaren som utför konfigurationen måste ha en kopia av **kommandoradsverktyget OpenSSL** .
1. Servern och klienten måste redan vara konfigurerade att använda ett anpassat SSL-certifikat, enligt beskrivningen i [Använda anpassade certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd), och ge anvisningar om hur du lagrar klientcertifikatet i Windows certifikatarkiv i stället för att lagra det i **certifikatkatalogen** .

## Konfigurerar Windows certifikatarkiv {#section-3629802122e947d4b4f63e8b732cfe27}

Windows certifikatarkiv för klienter är aktiverat enligt följande:

**Steg 1: Importera användarens SSL-certifikat och privata nyckel till Windows certifikatarkiv.**

I [Använda anpassade certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) omdirigeras du till att placera SSL-certifikatet och nyckeln i följande katalog:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Certifikatets namn är `<Common Name>.pem` (till exempel [!DNL Analytics Server 1.pem] (inte [!DNL trust_ca_cert.pem] filen).

Innan certifikatet och den privata nyckeln kan importeras måste de konverteras från . [!DNL pem] till ett [!DNL .pfx] format, till exempel [!DNL pkcs12.pfx] ).

1. Öppna en kommandotolk eller terminal och navigera till katalogen:

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
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

Filen måste redigeras för att du ska kunna dirigera Data Workbench till Windows certifikatarkivfunktion. [!DNL Insight.cfg] Varje serverpost i den här filen måste ha ytterligare parametrar angivna. Om parametrarna utelämnas används den befintliga certifikatkonfigurationen som standard. Om parametrarna anges men har felaktiga värden, kommer arbetsstationen att gå in i ett feltillstånd och du måste referera till loggfilen för felinformation.

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

Du kan nu starta arbetsstationen (eller koppla från/återansluta till servern). Datan Workbench bör läsa in ditt certifikat och din nyckel från certifikatarkivet och ansluta normalt.

## Loggutdata {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

När ett certifikat inte hittas eller är ogiltigt visas det här felmeddelandet i [!DNL HTTP.log] filen.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>L4-loggningsramverket kan aktiveras genom att du konfigurerar [!DNL L4.cfg] filen (se din kontohanterare för att konfigurera detta).
