---
description: Det här är en snabbguide som ger dig de steg som krävs för att validera den interna och externa FTP-konfigurationen.
title: Validering av interna och externa FTP-servrar
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Validering av interna och externa FTP-servrar{#validation-of-internal-and-external-ftp-servers}

Det här är en snabbguide som ger dig de steg som krävs för att validera den interna och externa FTP-konfigurationen.

En intern FTP används när en konsult/arkitekt som är intern för Adobe måste ansluta till FTP-platsen för filöverföring eller filhämtning, medan en extern FTP huvudsakligen är till för dig som användare för att överföra de datafiler som krävs.

Mer information om hur du konfigurerar FTP-servrar finns i [Filöverföringsprotokoll](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html).

## Valideringssteg - extern FTP {#section-24428111b5c542ce81a765cd63424b97}

1. Öppna en kommandotolk. (Windows+R och skriv cmd)
1. Type ftp `<ftp server>`
1. Ange användarnamn och lösenord. ![](assets/dwb_impl_ftp1.png)

1. Ändra lokal katalog varifrån en fil kan flyttas. Använd det här kommandot:

[!DNL ftp> lcd C:\Users\andixit\Desktop]

lokal katalog nu [!DNL C:\Users\andixit\Desktop].

1. Kopiera fil från lokal till fjärransluten plats. ![](assets/dwb_impl_ftp2.png)

1. Logga ut från fjärrservern. (Använd under-kommando)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Ett annat sätt att validera FTP är att använda Filezilla. Ange värdnamn, användarnamn, lösenord och port. Den högra sidan av panelen är en fjärrplats och den vänstra sidan är en lokal plats. Validera FTP genom att dra och släppa filer från den lokala platsen till fjärrplatsen och v.v.

![](assets/dwb_impl_ftp3.png)

## Valideringssteg - intern FTP {#section-b1f7a789ad6848cf9027f7953d81066e}

Följ stegen ovan för att validera intern ftp från valfri Adobe-server.
