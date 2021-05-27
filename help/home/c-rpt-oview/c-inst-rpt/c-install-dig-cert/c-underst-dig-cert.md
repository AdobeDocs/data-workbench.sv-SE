---
description: Adobe använder digitala X.509-certifikat för att identifiera och autentisera klient- och serverkomponenter som utgör en implementering.
title: Understanding Digital Certificates
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---

# Digitala certifikat{#understanding-digital-certificates}

Adobe använder digitala X.509-certifikat för att identifiera och autentisera klient- och serverkomponenter som utgör en implementering.

När du installerar [!DNL Report Server] måste du installera det digitala certifikatet som auktoriserar en namngiven individ (till exempel Jane Smith) att använda det installerade klientprogrammet.

>[!NOTE]
>
>Om du behöver migrera [!DNL Report Server] till en annan dator eller en annan namngiven användare måste du skaffa ett nytt certifikat från Adobe. Kontakta Adobe kundtjänst om du vill göra det.

[!DNL Report Server] presenterar det här digitala certifikatet för att få åtkomst till en serverkomponent. En administratör för serverkomponenten kan begränsa åtkomsten till serverresurser baserat på de värden för det vanliga namnet eller organisationsenheten som visas i klientens certifikat.

De digitala X.509-certifikat som installeras med Adobe-program gör det även möjligt för dess klient- och serverkomponenter att utbyta information via SSL (Secure Sockets Layer). SSL skyddar överföringar via HTTP med hjälp av ett krypteringssystem för offentlig och privat nyckel. Adobe implementering av SSL stöder 1024-bitars RSA-nycklar och använder en 128-bitars RC4-krypteringsalgoritm.

Förutom säkerhet fungerar det digitala certifikatet som du installerar även som en licensnyckel som gör att du kan köra det installerade [!DNL Report Server]-certifikatet. För att det ska fungera på rätt sätt måste ett digitalt certifikat vara nodlåst och aktuellt, annars startar inte programmet.

## Nodlåsta certifikat {#section-3338f1558e7844888dced8f395888744}

Ett nodlåst certifikat är ett digitalt certifikat som har registrerats på den dator där det är installerat. Nodlåsning associerar ett certifikat permanent med en specifik nodidentifierare (ett värde som unikt identifierar en viss dator). Om du vill låsa certifikatet med nod måste datorn ha Internetåtkomst till licensservern för Adobe eller till en proxyserver som har åtkomst till licensservern.

Om du installerar på en dator som inte har åtkomst till Internet måste du skaffa och installera ett särskilt förlåst certifikat enligt beskrivningen i [Använda digitala certifikat på datorer utan Internet Access](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) på den här sidan.

Om du installerar på en dator som har åtkomst till Internet är ditt digitala certifikat automatiskt nodlåst första gången du startar [!DNL Report Server]. När certifikatet har låsts till en nod kan det inte användas på någon annan dator. Om du behöver migrera [!DNL Report Server] till en annan dator måste du skaffa ett nytt, olåst certifikat från Adobe.

## Aktuella certifikat {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Förutom att vara nodlåst måste ett digitalt certifikat vara aktuellt. För att ditt certifikat ska förbli aktuellt måste det förnyas regelbundet (vanligtvis var 30:e dag, men det kan variera beroende på ditt avtal med Adobe). Om datorn har Internet-åtkomst är valideringsprocessen helt genomskinlig. [!DNL Report Server] ansluter automatiskt till licensservern och förnyar certifikatet vid behov. Om datorn inte har Internet-åtkomst måste du installera uppdaterade certifikat manuellt enligt beskrivningen i följande avsnitt.

## Använda digitala certifikat på datorer utan Internetåtkomst {#section-18cce05e2204407bb2b6b75deab9197d}

Om du installerar på en dator som inte har åtkomst till Internet måste du begära ett förlåst certifikat för din installation av [!DNL Report Server]. Ett förlåst certifikat är ett digitalt certifikat som Adobe manuellt låser till nodidentifieraren för datorn.

Om du vill begära ett förlåst certifikat måste du skicka nodidentifieraren och ditt certifikatnummer till Adobe kundtjänst. Kontakta Adobe Customer Care för att få nodidentifieraren för din dator och be om Adobe [!DNL Node Identifier]-verktyget. Du kan också hämta nodidentifieraren från aviseringen som [!DNL Report Server] utfärdar när det försöker ansluta till licensservern och inte kan. När du får det förlåsta certifikatet installerar du det enligt beskrivningen i de två sista stegen i [Installationsprocedurer för digitalt certifikat](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

När certifikatet behöver valideras på nytt måste du hämta ett nytt validerat certifikat från licensservern och installera om det på datorn (om inte ditt avtal med Adobe tillåter det).
