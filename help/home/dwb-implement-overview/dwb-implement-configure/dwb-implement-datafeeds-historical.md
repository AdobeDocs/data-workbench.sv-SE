---
description: En snabbguide för de steg som minst krävs för att validera och konfigurera historiska dataflöden.
title: Validerar datafeeds för historik
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Validerar datafeeds för historik{#validating-historical-data-feeds}

En snabbguide för de steg som minst krävs för att validera och konfigurera historiska dataflöden.

## Valideringssteg för konsekvens i dataflöden {#section-777b2c627a354627a02feb9461e23038}

1. Logga in på *tänder* (https://oasis.omniture.com/drteeth/)
1. Gå till SiteCatalyst Admin -> Dataflödesdefinition (ny)
1. Gå till serverplatsen (t.ex. Dallas, London..) Beroende på var din organisation finns.
1. Ange RSID och välj flödestypen Insight och klicka på *sökningen*.

   ![](assets/dwb_impl_historical.png)

1. Identifiera det faktiska feed-namnet för klienten.
1. Klicka på Historik i avsnittet Åtgärder. ![](assets/dwb_impl_historical1.png)

   Kontrollera om det finns några fel i statusfältet. Om en del av feeden är i feltillstånd markerar du feeden och klickar på Bearbeta igen. Om felet inträffar för flera begäranden skickar du ett e-postmeddelande till *`dataworkbench@adobe.com`* med information om feed-ID och rapportsviten för att bearbeta om.

1. Efter valideringen kontrolleras loggarna i NAS-platsens Raw-mapp.

