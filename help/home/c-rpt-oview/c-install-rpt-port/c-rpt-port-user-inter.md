---
description: Rapportuppsättningar måste konfigureras på ett specifikt sätt för att skapa rapporter som visas korrekt via rapportportalen.
solution: Analytics
title: Anpassa gränssnittet för rapportportalen
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Anpassa gränssnittet för rapportportalen{#customize-the-report-portal-user-interface}

Rapportuppsättningar måste konfigureras på ett specifikt sätt för att skapa rapporter som visas korrekt via rapportportalen.

Användargränssnittet för [!DNL Report Portal] är utformat för att visa en flik för varje rapportuppsättningsmapp som visas i utdatakatalogen och finns i [!DNL profiles.xml] filen samt den inbyggda [!DNL Admin] fliken, som måste läggas till i den [!DNL TopNavigation.xml] fil som ska visas. Mer information om hur du visar den inbyggda [!DNL Admin] fliken finns i [Länka en utdatamapp till en flik i Användare..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Kontrollera att dina rapportuppsättningar är kompatibla med rapportportalen..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Länkar en utdatamapp till en flik i användaren..](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Kontrollera att dina rapportuppsättningar är kompatibla med rapportportalen {#section-2b141e5d198a4bbea455699126c24706}

En rapportuppsättning definierar ett schemalagt jobb för [!DNL Report]. Den består av två delar:

* En mapp som definierar samlingen av arbetsytor som du vill generera [!DNL Report] som rapporter.
* En konfigurationsfil ( [!DNL Report.cfg]).

Filen anger bland annat [!DNL Report.cfg] när rapporterna ska genereras [!DNL Report] och var utdatafilerna ska sparas. Rapportuppsättningar finns i mappen Rapporter på data workbench-servern. En profil kan visa ett valfritt antal rapportuppsättningar.

För att säkerställa kompatibilitet med [!DNL Report Portal]måste rapportuppsättningarna uppfylla följande krav:

* Utdatakatalogen för rapportuppsättningarna måste innehålla en konfigurerad [!DNL profiles.xml] fil.
* Varje rapportuppsättning måste innehålla en rapport på översta nivån med namnet&quot;*ReportSetName* Summary&quot;, där *ReportSetName* matchar rapportuppsättningens namn. I följande exempel [!DNL Profile Manager] visas två rapportuppsättningar, &quot;Hem&quot; och &quot;Trafik&quot;. Observera att varje rapportuppsättning definierar en sammanfattningsrapport ( [!DNL Home Summary.vw] respektive [!DNL Traffic Summary.vw]).

![](assets/rptPort_scrn_RptSets.png)

I [!DNL Report Portal]visas sammanfattningsrapporten på rapportuppsättningens flik. Sammanfattningsrapporten kan innehålla valfri arbetsyta, fönster eller visualisering.

* Sammanfattningsrapporten måste vara den enda rapporten i den översta mappen för en rapportuppsättning. Alla andra rapporter måste placeras i undermappar. Om du placerar andra rapporter i mappen på den översta nivån kan du inte visa dem via portalen.

## Länka en utdatamapp till en flik i användargränssnittet {#section-3f6bc47d37ed448e871f4f685f46acee}

Om du vill ange vilka flikar du vill visa måste du konfigurera en [!DNL Report Portal] [!DNL TopNavigation.xml] fil för varje profil. Den här filen avgör vilka rapportuppsättningar som visas som flikar i användargränssnittet för en viss profil samt ordningen på dessa flikar. Filen finns [!DNL TopNavigation.xml] i mappen \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Så här redigerar du filen TopNavigation.xml**

1. Öppna filen i en textredigerare, t.ex. Anteckningar, på den dator där IIS körs. [!DNL TopNavigation.xml]
1. Redigera listan med `<TopNav>` [!DNL Report Portal] element så att den definierar namnen och ordningen på de rapportuppsättningar vars utdata du vill visa, som i följande exempel:

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
   >Fliken [!DNL Admin] är en inbyggd flik som innehåller ytterligare funktioner. Om du inte inkluderar den i [!DNL TopNavigation.xml] filen visas inte den här fliken och dess funktioner är inte tillgängliga.

1. Skapa en mapp för nästa profil i \*PortalName*\PortalFiles\Core\TopNav\ folder.
1. Kopiera [!DNL TopNavigation.xml] filen från den första profilmappen och klistra in den i den nya mappen.
1. Redigera filen efter [!DNL TopNavigation.xml] behov och spara den sedan.
1. Upprepa steg 3-5 för alla andra profiler som är tillgängliga i portalen.

