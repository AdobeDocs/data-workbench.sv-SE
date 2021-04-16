---
description: Användarna måste ha ett giltigt konto och ange kontonamn och lösenord när de öppnar rapportportalen.
title: Definiera ytterligare konton
uuid: 5ad98b52-267c-4c36-b43a-ae6ad415de8e
exl-id: 1f267217-a389-431a-ba49-9a9eead0ae83
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Definiera ytterligare konton

Användarna måste ha ett giltigt konto och ange kontonamn och lösenord när de öppnar rapportportalen.

Som standard är användarautentisering aktiverat i [!DNL Report Portal].

Listan över giltiga konton för [!DNL Report Portal] finns i databasfilen [!DNL portal.mdb]. [!DNL Report Portal] installeras med ett konto med administratörsbehörighet:

* Kontonamn: test
* Lösenord: användare

>[!NOTE]
>
>Av säkerhetsskäl rekommenderar Adobe att du ändrar lösenordet för det här kontot efter att du har installerat [!DNL Report Portal].

Om du vill lägga till användarkonton i [!DNL Report Portal] eller ändra information som hör till befintliga konton använder du fliken [!DNL Admin] i användargränssnittet för [!DNL Report Portal].

Varje gång du lägger till ett nytt konto eller redigerar ett befintligt konto skickas ett bekräftelsemeddelande via e-post enligt vad som anges i filen [!DNL email.asp] i mappen \*PortalName*\PortalASP. Mer information finns i [Redigera filen Email.asp](../../../home/c-rpt-oview/c-install-rpt-port/t-email-file.md#task-d9f4f306d38e435aa7effab3d94f690b).

Anvisningar om hur du lägger till ytterligare användare finns i [Arbeta med konton](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d).

>[!NOTE]
>
>Du kan även inaktivera användarautentisering och tillåta anonym åtkomst till [!DNL Report Portal]. Anvisningar om hur du gör detta finns i informationen om parametern Session(&quot;In&quot;) i [Redigera sessionskonfigurationsfilen](../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7).
