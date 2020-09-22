---
description: Filen Access Control.cfg hanterar åtkomsten till vissa funktioner i Insight Server.
solution: Analytics
title: Uppdaterar åtkomstkontrollsfilen
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 1%

---


# Uppdaterar åtkomstkontrollsfilen{#updating-the-access-control-file}

Filen Access Control.cfg hanterar åtkomsten till vissa funktioner i Insight Server.

Den definierar entiteter som kallas AccessGroups. En AccessGroup identifierar en grupp användare som har behörighet att använda vissa funktioner på servern.

Innan du kan ansluta till [!DNL Insight Server] med [!DNL Insight]måste du uppdatera administratörsåtkomstgruppen så att den innehåller en av de [!DNL Insight] licenser som Adobe har utfärdat till din organisation. Den här AccessGroup identifierar användare som har behörighet att utföra administrativa funktioner via [!DNL Insight].

I proceduren nedan beskrivs hur du lägger till en licens i gruppen Administrators AccessGroup. För att kunna utföra den här uppgiften måste du fastställa vilken [!DNL Insight] licens som har administratörsbehörighet för din organisation. (För den första konfigurationen och konfigurationen räcker det att ge administratörsbehörighet till en licens. Du kan ge ytterligare licenser administratörsbehörighet senare.) Du måste också känna till det&quot;vanliga namnet&quot; som tilldelats den här licensen. Om du vill ha det här värdet kan du kontrollera licenscertifikaten för ditt konto på [https://aap.adobe.com](https://aap.adobe.com).

Syftet med den här proceduren är att identifiera en licensierad kopia av [!DNL Insight] som du kan använda för att konfigurera och konfigurera [!DNL Insight Server]. När du har identifierat den här licensen kan du utföra all efterföljande serverkonfiguration (inklusive ytterligare AccessGroup-konfiguration) med den licensierade kopian av [!DNL Insight]. Mer information om hur du styr åtkomst till servern med hjälp av AccessGroups finns i [Konfigurera åtkomstkontroll](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Så här uppdaterar du åtkomstkontrollsfilen**

1. Navigera till mappen [!DNL Access Control] i den katalog där du installerade [!DNL Insight Server].

   Exempel: [!DNL C:\Adobe\Server\Access Control]

1. Öppna [!DNL Access Control.cfg] filen i en textredigerare som Anteckningar.
1. Leta reda på CN-posten i gruppen Administrators AccessGroup och ersätt det befintliga värdet för den här posten med det vanliga namnet som identifierar det [!DNL Insight] som du vill använda för att ställa in och administrera [!DNL Insight Server]. Följande filfragment visar var du infogar det vanliga namnet i [!DNL Access Control.cfg] filen.

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   Om du använder inloggningsbaserad autentisering är några extra poster tillgängliga för konfiguration. Följande poster är:

   * O (organisations-ID): Den här posten representerar organisationens ID. Exempel, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Detta ID finns i Admin Console.
   * PLC - Den här posten ger åtkomst till användare som har etablerats för en viss produktkonfiguration. Den kan användas i format `Organization_Id-PLC`. Exempel, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. De användare som har etablerats för Data Workbench med PLC `DataworkbenchAdminUsers` får åtkomst till sina servrar.
   * E-post - Den här posten ger åtkomst till alla enskilda användare. Dess värde ska vara e-postadressen till den tilldelade användaren. Exempel, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Posterna är skiftlägeskänsliga. Du måste se till att de värden som anges för O, PLC och Email är exakt desamma som de som visas i Admin Console.
   >    * Skriv det vanliga namnet exakt som det visas i certifikatet.
   >    * Använd inte tabbtangenten för att generera tomt utrymme i [!DNL Access Control.cfg] filen (eller i någon annan konfigurationsfil för en Adobe-komponent). Använd bara blanksteg för att skapa tomt utrymme. Ett tabbtecken förhindrar att systemet läser filen korrekt.


1. Spara och stäng filen.

