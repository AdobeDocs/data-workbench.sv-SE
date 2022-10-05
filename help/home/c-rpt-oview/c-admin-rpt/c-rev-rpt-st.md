---
description: Information om rapportserverns status och rapportuppsättningens status.
title: Status för granskningsrapport
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Status för granskningsrapport{#reviewing-report-status}

{{eol}}

Information om rapportserverns status och rapportuppsättningens status.

* [Status för rapportserver](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status för rapportuppsättning](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Status för rapportserver {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Rekommenderad frekvens:** Endast vid behov

[!DNL Report] skickar statusinformation till data workbench-servern varannan minut vad gäller status för [!DNL Report] Server. Den här informationen visas under [!DNL Report Server Status] noden i [!DNL Detailed Status] gränssnitt.

**Öppna [!DNL Detailed Status] visualisering**

1. Högerklicka på en arbetsyta i Data Workbench och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. I [!DNL Servers] -gränssnittet högerklickar du på ikonen för den data workbench-server som [!DNL Report] datorn ansluter till och klickar på **[!UICONTROL Detailed Status.]**

1. Klicka på **[!UICONTROL Report Server Status]**.

Om mer än en [!DNL Report] är ansluten till data workbench-servern, visas en post för varje [!DNL Report Server] i statusvektorn. Du kan åsidosätta tvåminutersintervallet genom att ange ett värde i parametern Statusintervall (sekunder) i [!DNL Reporting] nod på [!DNL ReportServer.cfg] -fil.

Mer information om [!DNL ReportServer.cfg] -fil, se [Konfigurera rapportuppsättningen](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Mer information om konfiguration [!DNL Report], se [Installerar rapport](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Mer information om [!DNL Detailed Status], se kapitlet om administrationsgränssnitt i *Användarhandbok för Data Workbench*.

## Status för rapportuppsättning {#section-8569b94266b74a1f85d2a85106a2aaef}

**Rekommenderad frekvens:** Endast vid behov

[!DNL Report] skickar statusinformation för varje rapportuppsättning till Datan Workbench. Grundläggande information, till exempel när en rapportuppsättning skapas och var den distribueras, visas i data workbench ovanför rapportuppsättningen med grön text. När rapporter körs [!DNL Report] Servern skickar ett meddelande varannan minut som anger hur många procent av de aktuella frågorna som har slutförts. Du kan åsidosätta det här tvåminutersintervallet genom att ange ett värde i parametern Intervall för slutförandemeddelande (sekunder) i [!DNL Reporting] nod på [!DNL ReportServer.cfg] -fil.

![](assets/report_status.png)

>[!NOTE]
>
>Om ett fel uppstod när en rapport kördes visas felet i röd text nedanför miniatyrbilden för den rapporten. Du kan högerklicka på arbetsytan för att visa det fullständiga felmeddelandet.
