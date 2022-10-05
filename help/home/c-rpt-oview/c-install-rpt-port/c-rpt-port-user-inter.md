---
description: Rapportuppsättningar måste konfigureras på ett specifikt sätt för att skapa rapporter som visas korrekt via rapportportalen.
title: Anpassa gränssnittet för rapportportalen
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Anpassa gränssnittet för rapportportalen{#customize-the-report-portal-user-interface}

{{eol}}

Rapportuppsättningar måste konfigureras på ett specifikt sätt för att skapa rapporter som visas korrekt via rapportportalen.

Användargränssnittet för [!DNL Report Portal] är utformat för att visa en flik för varje rapportuppsättningsmapp som visas i utdatakatalogen och som listas i [!DNL profiles.xml] och den inbyggda [!DNL Admin] som måste läggas till i [!DNL TopNavigation.xml] fil som ska visas. Mer information om hur du visar de inbyggda [!DNL Admin] flik, se [Länkar en utdatamapp till en flik i användaren..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Kontrollera att dina rapportuppsättningar är kompatibla med rapportportalen..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Länkar en utdatamapp till en flik i användaren..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Kontrollera att dina rapportuppsättningar är kompatibla med rapportportalen {#section-2b141e5d198a4bbea455699126c24706}

En rapportuppsättning definierar ett schemalagt jobb för [!DNL Report]. Den består av två delar:

* En mapp som definierar den samling arbetsytor som du vill använda [!DNL Report] att generera som rapporter.
* En konfigurationsfil ( [!DNL Report.cfg]).

Bland annat [!DNL Report.cfg] filinformation [!DNL Report] när rapporter ska genereras och var utdatafilerna ska sparas. Rapportuppsättningar finns i mappen Rapporter på data workbench-servern. En profil kan visa ett valfritt antal rapportuppsättningar.

För att säkerställa kompatibilitet med [!DNL Report Portal]måste dina rapportuppsättningar uppfylla följande krav:

* Utdatakatalogen för rapportuppsättningarna måste innehålla en konfigurerad [!DNL profiles.xml] -fil.
* Varje rapportuppsättning måste innehålla en rapport på översta nivån med namnet &quot;*ReportSetName* Sammanfattning,&quot; där *ReportSetName* matchar rapportuppsättningens namn. Till exempel följande [!DNL Profile Manager] visar två rapportuppsättningar, &quot;Home&quot; och &quot;Traffic&quot;. Observera att varje rapportuppsättning definierar en sammanfattningsrapport ( [!DNL Home Summary.vw] och [!DNL Traffic Summary.vw]).

![](assets/rptPort_scrn_RptSets.png)

I [!DNL Report Portal]visas sammanfattningsrapporten på rapportuppsättningens flik. Sammanfattningsrapporten kan innehålla valfri arbetsyta, fönster eller visualisering.

* Sammanfattningsrapporten måste vara den enda rapporten i den översta mappen för en rapportuppsättning. Alla andra rapporter måste placeras i undermappar. Om du placerar andra rapporter i mappen på den översta nivån kan du inte visa dem via portalen.

## Länka en utdatamapp till en flik i användargränssnittet {#section-3f6bc47d37ed448e871f4f685f46acee}

Ange vilka flikar du vill använda [!DNL Report Portal] måste du konfigurera en [!DNL TopNavigation.xml] fil för varje profil. Den här filen avgör vilka rapportuppsättningar som visas som flikar i användargränssnittet för en viss profil samt ordningen på dessa flikar. The [!DNL TopNavigation.xml] filen finns i mappen \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Så här redigerar du filen TopNavigation.xml**

1. Öppna [!DNL TopNavigation.xml] i en textredigerare som Anteckningar.
1. Redigera listan med `<TopNav>` så att den definierar namnen och ordningen på de rapportuppsättningar vars utdata du vill ha [!DNL Report Portal] att visa, som i följande exempel:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >The [!DNL Admin] är en inbyggd flik som innehåller ytterligare funktioner. Om du inte tar med den i [!DNL TopNavigation.xml] -fil, den här fliken visas inte och dess funktioner är inte tillgängliga.

1. Skapa en mapp för nästa profil i \*PortalName*\PortalFiles\Core\TopNav\ folder.
1. Kopiera [!DNL TopNavigation.xml] från den första profilmappen och klistra in den i den nya mappen.
1. Redigera [!DNL TopNavigation.xml] Spara sedan filen efter behov.
1. Upprepa steg 3-5 för alla andra profiler som är tillgängliga i portalen.
