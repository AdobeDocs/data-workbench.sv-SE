---
description: Använd Workstation för att hantera dina Data Workbench-användare.
title: Självetablering av användare
uuid: e3c10bc4-2fa0-4368-9952-e38a4794aee9
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Självetablering av användare{#self-provisioning-of-users}

Använd Workstation för att hantera dina Data Workbench-användare.

Du kan använda Workstation för att ansluta till Data Workbench Server genom att konfigurera det certifikat som krävs från Adobe. Det här certifikatet underlättar både SSL-kommunikation och behörighet att använda de licensierade resurserna och funktionerna. Vid certifikatbaserad autentisering måste du hämta och konfigurera flera certifikat för användning av arbetsstationen på flera datorer. Dessutom hanteras användaretablering och berättiganden av Adobe och du måste kontakta Adobe för att få nya certifikat eller certifikatåterkallning.

Från och med DWB 6.7 stöder Workstation användarautentisering via användarnamn och lösenord.

Även om certifikatbaserad autentisering/auktorisering fortfarande fungerar för din installation rekommenderar vi att du migrerar till den nyare autentiseringen som baseras på autentiseringsuppgifter. I det nyare tillvägagångssättet autentiseras dina arbetsstationsanvändare via Adobe Identity Management System (IMS). Innan de kan använda arbetsstationen måste de få åtkomst till funktionerna via [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) av organisationens administratör.

Den nya autentiserings- och provisioneringsmodellen för användare hjälper till att:

* Självetablering av användare och grupper via Admin Console. Du behöver inte kontakta Adobe för att lägga till, ta bort eller ändra licensrättigheter för användare.
* Åtkomst till arbetsstation från flera datorer utan att konfigurationstillståndet går förlorat genom att logga in med autentiseringsuppgifter. Den lokala cachen tas bort vid utloggning, den aktuella profilen stängs och konfigurationsprofilen aktiveras.

## Komma igång

Innan du börjar kontaktar du Adobe för att lägga till din organisation i Admin Console. Beroende på vilka tjänster du har köpt tillhandahåller Adobe organisationen åt dig. Organisationer kan till exempel ha tillgång till attribueringstjänsten eller betaversioner, eller både och. När en organisation har konfigurerats kan organisationsadministratören lägga till användare och grupper. Mer information finns i [Hantera Experience Cloud-användare och -produkter](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) i Experience Cloud. Organisationsadministratören kan även konfigurera användningsbegränsningar för olika användare beroende på deras roller. Icke-förhandsversioner behöver till exempel inte åtkomst till betaversioner.

Varje användare som läggs till i den här organisationen via Admin Console har tillgång till Data Workbench. Undertjänsterna kan bara aktiveras eller inaktiveras för varje användare beroende på deras produktåtkomst. När en användare uppgraderas från certifikat till IMS kopieras alla lokala data till den nya IMS-användarkatalogen.

>[!NOTE]
>
>En session varar 6 timmar på servern och 23 timmar på klienten om inte åtkomsttoken uppdateras. När token har uppdaterats kan du använda Klient utan att logga in igen.

Administratören måste skapa minst en produktnivåkonfiguration i Admin Console innan han eller hon kan bevilja åtkomst till en användare.

Den booleska flaggan **Använd IMS** kan läggas till i [!DNL Insight.cfg] certifikatläge. Mer information om hur du konfigurerar åtkomstkontroll för IMS-användare finns i [Uppdatera åtkomstkontrollsfilen](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/install-servers/insight-server-dpu/c-updt-accss-ctrl-file.html).

## Konfliktlösning

När en användare är inloggad på flera datorer med samma IMS-konto i samma profil och är i offlineläge på en av datorerna kan ett formulär och ett popup-fönster informera dig om detta. `.conflict` Detta inträffar när det finns en skillnad i innehåll med andra filer (arbetsytor, dimensioner, filter osv.) synkroniseras på båda datorerna i [!DNL User\Profile\] på servern och klienten. En säkerhetskopia skapas i `.conflict` filen och inga data går förlorade. Med en boolesk flagga i [!DNL Insight.cfg] kan du inaktivera den här popup-rutan för konflikter.

Flagga: Konfliktmeddelanden

Detta gäller arbetsytor, mått, dimensioner osv. i användarmappen.
