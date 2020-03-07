---
description: Information om rapportserverns status och rapportuppsättningens status.
solution: Analytics
title: Status för granskningsrapport
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Status för granskningsrapport{#reviewing-report-status}

Information om rapportserverns status och rapportuppsättningens status.

* [Status för rapportserver](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status för rapportuppsättning](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Status för rapportserver {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Rekommenderad frekvens:** Endast vid behov

[!DNL Report] skickar statusinformation till data workbench-servern varannan minut vad gäller status för [!DNL Report] servern. Den här informationen visas under [!DNL Report Server Status] noden i [!DNL Detailed Status] gränssnittet.

**Så här öppnar du[!DNL Detailed Status]visualiseringen**

1. Högerklicka på en arbetsyta i Data Workbench och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. I [!DNL Servers] gränssnittet högerklickar du på ikonen för den data workbench-server som datorn [!DNL Report] ansluter till och klickar på **[!UICONTROL Detailed Status.]**

1. Klicka på **[!UICONTROL Report Server Status]**.

Om fler än en [!DNL Report] är ansluten till data workbench-servern visas en post för varje [!DNL Report Server] i statusvektorn. Du kan åsidosätta tvåminutersintervallet genom att ange ett värde i parametern Statusintervall (sekunder) i [!DNL Reporting] noden för [!DNL ReportServer.cfg] filen.

Mer information om [!DNL ReportServer.cfg] filen finns i [Konfigurera rapportuppsättningen](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Mer information om hur du konfigurerar [!DNL Report]finns i [Installera rapport](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Mer information om [!DNL Detailed Status]finns i kapitlet Administrativa gränssnitt i *användarhandboken* för Data Workbench.

## Status för rapportuppsättning {#section-8569b94266b74a1f85d2a85106a2aaef}

**Rekommenderad frekvens:** Endast vid behov

[!DNL Report] skickar statusinformation för varje rapportuppsättning till Data Workbench-servern. Grundläggande information, till exempel när en rapportuppsättning skapas och var den distribueras, visas i data workbench ovanför rapportuppsättningen med grön text. När rapporter körs skickar [!DNL Report] Server ett meddelande varannan minut som anger hur många procent av de aktuella frågorna som är slutförda. Du kan åsidosätta det här tvåminutersintervallet genom att ange ett värde i parametern Intervall för slutförandemeddelande (sekunder) i [!DNL Reporting] noden för [!DNL ReportServer.cfg] filen.

![](assets/report_status.png)

>[!NOTE]
>
>Om ett fel uppstod när en rapport kördes visas felet i röd text nedanför miniatyrbilden för den rapporten. Du kan högerklicka på arbetsytan för att visa det fullständiga felmeddelandet.

