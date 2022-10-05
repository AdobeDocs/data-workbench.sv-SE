---
description: Steg för att öppna rapportportalen och se till att du kan visa rapporterna för din profil.
title: Testa rapportportalen
uuid: eee0df5e-78e0-49b2-853c-40f1b332328b
exl-id: 197ff815-9234-4dce-b30f-b9cacf259634
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Testa rapportportalen{#test-the-report-portal}

{{eol}}

Steg för att öppna rapportportalen och se till att du kan visa rapporterna för din profil.

>[!NOTE]
>
>Du kan inte logga in på [!DNL Report Portal] tills rapporter visas i utdatamappen.

1. Öppna [!DNL Report Portal] med följande URI-format:

   https://*ServerAddress*/*PortalName*

   Exempel: [!DNL https://localhost/VisualReportPortal]

1. If [!DNL Report Portal] uppmanar dig att ange inloggningsuppgifter, ange ett kontonamn och ett lösenord (till exempel konto&quot;test&quot; och lösenord&quot;user&quot; för standardkontot).
1. När [!DNL Report Portal] visas kontrollerar du att:

   * Portalen innehåller en flik för varje rapportuppsättning i utdatamappen.
   * På varje flik visas rapportuppsättningens sammanfattningsrapport.
   * Menyn på varje flik listar de enskilda undermapparna (om det finns några) för rapportuppsättningen och visar innehållet i dessa mappar.
