---
description: Allmän information om digitala certifikat och procedurer för att hämta och installera dem.
title: Hämta och installera digitala certifikat
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
exl-id: 8aae9b63-7df0-4725-9833-711246bbe746
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# Hämta och installera digitala certifikat{#downloading-and-installing-the-digital-certificates}

Allmän information om digitala certifikat och procedurer för att hämta och installera dem.

* [Understanding Digital Certificates](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [Nodlåsta certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [Aktuella certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [Använda digitala certifikat på datorer utan Internet-åtkomst](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [Installationsprocedurer för digitalt certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Understanding Digital Certificates {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe använder digitala X.509-certifikat för att identifiera och autentisera klient- och serverkomponenter som utgör en implementering.

När du installerar en serverkomponent ( [!DNL Insight Server] eller [!DNL Repeater]) måste du installera det digitala certifikatet som Adobe har utfärdat för komponenten. Om du behöver migrera ditt Adobe-program till en annan dator måste du skaffa ett nytt certifikat från Adobe. Kontakta Adobe kundtjänst om du vill göra det.

Det vanliga namnet som visas på det här certifikatet identifierar servern med ett angivet domännamn (till exempel [!DNL vs001a.mycompany.com]). När en serverklient ansluter till den här servern visar servern det här certifikatet som ett bevis på att det är servern som klienten begärde.

När du installerar en serverklient (till exempel [!DNL Insight] eller [!DNL Report]) måste du på samma sätt installera det digitala certifikatet som tillåter en namngiven individ (till exempel Jane Smith) att använda det installerade klientprogrammet. Om du behöver migrera ditt Adobe-program till en annan dator eller en annan namngiven användare måste du skaffa ett nytt certifikat från Adobe. Kontakta Adobe kundtjänst om du vill göra det.

Klientprogrammet presenterar det här digitala certifikatet för att få åtkomst till en serverkomponent. En administratör för serverkomponenten kan begränsa åtkomsten till serverresurser baserat på de värden för det vanliga namnet eller organisationsenheten som visas i klientens certifikat.

De digitala X.509-certifikat som installeras med Adobe-program gör det även möjligt för dess klient- och serverkomponenter att utbyta information via SSL (Secure Sockets Layer). SSL skyddar överföringar via HTTP med hjälp av ett krypteringssystem för offentlig och privat nyckel. Adobe implementering av SSL stöder 1024-bitars RSA-nycklar och använder en 128-bitars RC4-krypteringsalgoritm.

Förutom säkerhet fungerar de digitala certifikat som du installerar även som licensnycklar som gör att du kan köra det installerade Adobe-programmet. För att det ska fungera på rätt sätt måste ett digitalt certifikat vara nodlåst och aktuellt, annars startar inte programmet.

## Strängkryptering {#section-8abe6b2d95704d38a04137d5c4602f0b}

Se [Strängkryptering](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) för kryptering av lösenord.

## Nodlåsta certifikat {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

Ett nodlåst certifikat är ett digitalt certifikat som har registrerats på den dator där det är installerat. Nodlåsning associerar ett certifikat permanent med en specifik nodidentifierare (ett värde som unikt identifierar en viss dator). Om du vill låsa certifikatet med nod måste datorn ha Internetåtkomst till licensservern för Adobe eller till en proxyserver som har åtkomst till licensservern.

Om du installerar på en dator som inte har åtkomst till Internet måste du skaffa och installera ett särskilt förlåst certifikat enligt beskrivningen i [Använda digitala certifikat på datorer utan Internet Access](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

Om du installerar på en dator som har åtkomst till Internet är ditt digitala certifikat automatiskt nodlåst första gången du startar Adobe. När certifikatet har låsts till en nod kan det inte användas på någon annan dator. Om du behöver migrera din Adobe-produkt till en annan dator måste du skaffa ett nytt, olåst certifikat från Adobe.

## Aktuella certifikat {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Förutom att vara nodlåst måste ett digitalt certifikat vara aktuellt. För att ditt certifikat ska förbli aktuellt måste det förnyas regelbundet (vanligtvis var 30:e dag, men det kan variera beroende på ditt avtal med Adobe). Om datorn har Internet-åtkomst är valideringsprocessen helt genomskinlig. Din Adobe-produkt ansluter automatiskt till licensservern och förnyar certifikatet vid behov. Om datorn inte har Internet-åtkomst måste du installera uppdaterade certifikat manuellt enligt beskrivningen i följande avsnitt.

## Använda digitala certifikat på datorer utan Internetåtkomst {#section-809366329a7d4e198f95fe06c1f534fa}

Om du installerar på en dator som inte har åtkomst till Internet måste du begära ett förlåst certifikat för din installation av [!DNL Insight Server]. Ett förlåst certifikat är ett digitalt certifikat som Adobe manuellt låser till nodidentifieraren för datorn.

Om du vill begära ett förlåst certifikat måste du skicka nodidentifieraren och ditt certifikatnummer till Adobe kundtjänst. Kontakta Adobe Customer Care för att få nodidentifieraren för din dator och be om Adobe Node Identifier-verktyget. Du kan också hämta nodidentifieraren från varningen om att programvaran Adobe utfärdar problem när den försöker ansluta till licensservern och inte kan göra det.

När du får det förlåsta certifikatet installerar du det enligt beskrivningen i de två sista stegen i [Installationsprocedurer för digitalt certifikat](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). När certifikatet behöver omvalideras måste du hämta ett nytt, validerat certifikat från licensservern och installera om det på datorn.

## Installationsprocedurer för digitalt certifikat {#section-19f31676aad344a98e26e4fca1fad03b}

**Hämta och installera det digitala certifikatet**

1. Öppna webbläsaren i [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Din webbläsare kan uppmana dig att presentera ett digitalt certifikat just nu. Om den gör det klickar du bara på **[!UICONTROL Cancel]** för att stänga dialogrutan.

1. På inloggningsskärmen anger du **[!UICONTROL Account Name]** och **[!UICONTROL Password]** som du har fått från Adobe och klickar sedan på **[!UICONTROL login]**.

1. Leta reda på certifikatet som har utfärdats för ditt [!DNL Insight Server] och klicka sedan på ikonen som är associerad med certifikatet.

   >[!NOTE]
   >
   >Anteckna det vanliga namnet som är kopplat till det här certifikatet. Du använder det här namnet i ett senare steg.

1. När du uppmanas att spara certifikatet klickar du på **[!UICONTROL Save]**. (Observera att namnet på filen matchar det vanliga namnet som är kopplat till certifikatet.)
1. Hämta filen till mappen [!DNL Certificates] i den katalog där du installerade [!DNL Insight Server]. Den här mappen innehåller redan en certifikatfil med namnet [!DNL trust_ca_cert.pem]. Den här certifikatfilen måste alltid finnas.

1. Byt namn på den hämtade certifikatfilen till:

[!DNL server_cert.pem]
