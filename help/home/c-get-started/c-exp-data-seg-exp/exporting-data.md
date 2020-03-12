---
description: Nu kan du använda CSV-, TSV-, segmentexport- och segmentexport med Header med hjälp av FTP- och SFTP-protokoll för att exportera segmentfiler från klienten (arbetsstationen) till servern.
title: Exportera ett segment med hjälp av S/FTP-leverans
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Exportera ett segment med hjälp av S/FTP-leverans{#export-a-segment-using-s-ftp-delivery}

Nu kan du använda CSV-, TSV-, segmentexport- och segmentexport med Header med hjälp av FTP- och SFTP-protokoll för att exportera segmentfiler från klienten (arbetsstationen) till servern.

**Konfigurera konfigurationsfiler för S/FTP-export**

För att ställa in exportkonfigurationen lades två nya exportkonfigurationsfiler till för att ställa in en FTP- eller SFTP-anslutning, vilket gör att serverinformationen kan hämtas från *filen FTPServerInfo.cfg* och inloggningsuppgifterna hämtas från mappen *FTPUserCredentials* (motsvarande servernamnet som anges i kommandoargumenten).

* Ange **filen FTPServerInfo.cfg** .

   Ange FTP-serverinformationen och ange tillåtna anslutningsförsök från arbetsstationen. Redigera från arbetsstationen eller servern i **[!DNL FTPServerInfo.cfg]** filen [!DNL Server\Addresses\Export\].

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* Ange **filen FTPUserCredentials.cfg** .

   Ange inloggningsuppgifter för att ansluta till servrar med hjälp av **[!DNL FTPUserCredentials.cfg]** filen [!DNL Server\Admin\Export\]. Den här filen innehåller de inloggningsuppgifter som krävs för att ansluta till servrar och kan bara redigeras från servern och inte från arbetsstationen (klienten).

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >Kontrollera att de SSH-nycklar som du genererar för autentisering har samma format som de som genereras när du använder kommandot SSH-proportioner.
   >
   >Exempel på generering av SSH-nycklar med hjälp av nyckelord:
   >
   >```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Det finns sex parametrar i **filen FTPUserCredentials.cfg** som krävs för olika FTP- eller SFTP-överföringar.

   1. *Användarnamn*
   1. *Lösenord*
   1. *Servernamn*
   1. *Sökväg till offentlig nyckel*
   1. *Sökväg till privat nyckel*
   1. *Lösenfras*
   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protokoll </th> 
      <th colname="col2" class="entry"> Parametrar </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>Ange parametrar 1, 2, 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP med lösenordsautentisering </p> </td> 
      <td colname="col2"> <p>Ange parametrarna 1, 2 och 3 när överföring använder lösenordsautentisering (-p i kommandoargumenten). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP med nyckelautentisering </p> </td> 
      <td colname="col2"> <p>Ange parametrarna 1, 2, 3, 4, 5, 6 när överföringen använder nyckelautentisering (-k i kommandoargumenten). </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Ange exportkommandon för FTP och SFTP**

1. Öppna en exporttabell.

   I arbetsstationen högerklickar du på en *detaljtabell* och väljer en av exporttyperna CSV, TSV, Segmentexport eller Segmentexport med huvud. Eller öppna filen från en kommandotolk och redigera den (se [!DNL .export] Konfigurera segment för export [](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. I *kommandofältet* anger du att den ska peka på den körbara exportfilen:

   ```
   ExportIntegration.exe
   ```

1. Ange fälten *Kommandoargument* enligt nedan för det protokoll och den autentisering som krävs:

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (om lösenord används för autentisering)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** (om nycklar används för autentisering)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

Alla kommandoargument är obligatoriska och måste anges som de visas.

## S/FTP-export med privata/offentliga nycklar {#section-0534424d79a54a47b82594cfa7b3c17f}

Om du vill implementera FTP- och SFTP-export med privata och offentliga nycklar placerar du konfigurationsfilerna i följande mappar:

* Placera **FTPServerInfo.cfg** i [!DNL Server/Addresses/Export/] mappen.
* Placera **FTPUserCredentials.cfg** i [!DNL Server/Admin/Export/] mappen.

Det finns sex parametrar i **filen FTPServerInfo.cfg** :

1. *Användarnamn*
1. *Lösenord*
1. *Servernamn*
1. *Sökväg till offentlig nyckel*
1. *Sökväg till privat nyckel —* Placera sökvägen till den privata nyckeln i konfigurationsfilen utan tillägget, till exempel:

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Lösenfras*

FTP använder parametrarna 1, 2 och 3.

SFTP använder parametrarna 1, 2 och 3 när lösenordsautentisering används i överföringen.

SFTP använder alla sex parametrar när överföringen är klar med nyckelautentisering. Om du till exempel använder nycklar för autentisering:

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

Konfigurationsfilerna måste finnas på rätt plats.

>[!NOTE]
>
>De publika nycklarna måste peka på en **.pem** -fil och inte på en mapplats. Du kan skapa nycklar med hjälp av en SSH-nyckelgenereringsfunktion från program som Cygwin. (Putty genererar nycklar i ett .ppk-format som inte stöds.)
