---
description: Information om rapportserverns status och rapportuppsättningens status.
title: Status för granskningsrapport
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Status för granskningsrapport{#reviewing-report-status}

Information om rapportserverns status och rapportuppsättningens status.

* [Status för rapportserver](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Status för rapportuppsättning](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Rapportserverstatus {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Rekommenderad frekvens:** Endast när det behövs

[!DNL Report] skickar statusinformation till data workbench-servern varannan minut om  [!DNL Report] serverns status. Den här informationen visas under noden [!DNL Report Server Status] i gränssnittet [!DNL Detailed Status].

**Så här öppnar du  [!DNL Detailed Status] visualiseringen**

1. Högerklicka på en arbetsyta i Data Workbench och klicka på **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Högerklicka på ikonen för den data workbench-server som [!DNL Report]-datorn ansluter till i gränssnittet [!DNL Servers] och klicka på **[!UICONTROL Detailed Status.]**

1. Klicka på **[!UICONTROL Report Server Status]**.

Om mer än en [!DNL Report] är ansluten till data workbench-servern visas en post för varje [!DNL Report Server] i statusvektorn. Du kan åsidosätta tvåminutersintervallet genom att ange ett värde i parametern Statusintervall (sekunder) i noden [!DNL Reporting] i filen [!DNL ReportServer.cfg].

Mer information om filen [!DNL ReportServer.cfg] finns i [Konfigurera rapportuppsättningen](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Mer information om hur du konfigurerar [!DNL Report] finns i [Installera rapport](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Mer information om [!DNL Detailed Status] finns i kapitlet Administrativa gränssnitt i *Datans Workbench användarhandbok*.

## Rapportuppsättningsstatus {#section-8569b94266b74a1f85d2a85106a2aaef}

**Rekommenderad frekvens:** Endast när det behövs

[!DNL Report] skickar statusinformation för varje rapportuppsättning till Datan Workbench. Grundläggande information, till exempel när en rapportuppsättning skapas och var den distribueras, visas i data workbench ovanför rapportuppsättningen med grön text. När du kör rapporter skickar [!DNL Report]-servern ett meddelande varannan minut som anger hur många procent av de aktuella frågorna som har slutförts. Du kan åsidosätta det här tvåminutersintervallet genom att ange ett värde i parametern för slutförandemeddelandeintervall (sekunder) i noden [!DNL Reporting] i filen [!DNL ReportServer.cfg].

![](assets/report_status.png)

>[!NOTE]
>
>Om ett fel uppstod när en rapport kördes visas felet i röd text nedanför miniatyrbilden för den rapporten. Du kan högerklicka på arbetsytan för att visa det fullständiga felmeddelandet.
