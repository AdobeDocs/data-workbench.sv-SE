---
description: Kryptera lösenord och andra strängar vid kommunikation mellan klienten och servern.
title: Strängkryptering
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Strängkryptering{#string-encryption}

Kryptera lösenord och andra strängar vid kommunikation mellan klienten och servern.

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
