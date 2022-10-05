---
description: Kryptera lösenord och andra strängar vid kommunikation mellan klienten och servern.
title: Strängkryptering
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Strängkryptering{#string-encryption}

{{eol}}

Kryptera lösenord och andra strängar vid kommunikation mellan klienten och servern.

När du kommunicerar mellan Data Workbench-klienten (arbetsstation) och servern kan du spara en Value-parameter (till exempel ett lösenord) med Type of *EncryptedString*. Detta döljer parametern och sparar strängen i *Windows-autentiseringsuppgiftslager* på servern med motsvarande nyckel returnerad. Detta lagrar i första hand inloggningsuppgifter som används vid export, men kan användas för att kryptera alla parametrar.

* En ny mapp lades till på servern\**EncryptStrings**.

   Här anger du att konfigurationsfilen ska kryptera strängar.

* En ny konfigurationsfil lades till på Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Den här filen avfrågar *Server*\*Mappen EncryptStrings* för krypteringskonfigurationsfiler.

**Kryptera en sträng**:

1. Skapa en **EncryptedStrings.cfg** konfigurationsfil för en sträng med följande fält:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Värde* - Det här fältet innehåller den vanliga textsträng som behöver krypteras.

      Detta är endast kryptering på serversidan. The *Värde* inställningen är bara krypterad på serverdatorn.

   * *Namn* - Det här fältet innehåller ett värde som identifierar den krypterade strängen.
   * *EncryptValue* - Det här fältet lämnas tomt i indatakonfigurationsfilen. Det krypterade värdet returneras i det här fältet.

   Du kan lägga till flera **NameEncryptValuePair** värden för olika fält för kryptering.

   >[!NOTE]
   >
   >Alla tomma värdefält tas bort.

1. Spara **EncryptedStrings.cfg** till servern\**EncryptStrings** mapp.

**Utdatafil**

En utdatafil genereras med samma namn som indatafilen med ett &lt;*filnamn*>.*krypterad* tillägg. Om indatafilen till exempel har ett namn *sample.cfg* namnger utdatafilen *sample.cfg.encrypted*.
