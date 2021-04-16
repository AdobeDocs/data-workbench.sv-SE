---
description: Det första steget är att aktivera IIS-rollen på instrumentpanelsservern.
title: Aktiverar IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---

# Aktiverar IIS{#enabling-iis}

Det första steget är att aktivera IIS-rollen på instrumentpanelsservern.

1. Öppna **[!UICONTROL Server Manager]** under **[!UICONTROL Administrative Tools]**.
1. Högerklicka på menyalternativet Roller i den vänstra delen av fönstret **[!UICONTROL Server Manager]**.
1. Välj **[!UICONTROL Add Roles]**.
1. Välj **[!UICONTROL Web Server (IIS)]** och fortsätt med **[!UICONTROL Add Roles Wizard]**. Kontrollera att följande rolltjänster är aktiverade:

   | Vanliga HTTP-funktioner |
   |---|
   | Statiskt innehåll |
   | Standarddokument |
   | Katalogbläddring |
   | HTTP-fel |
   | HTTP-omdirigering |

   | Programutveckling |
   |---|
   | ASP.NET |
   | .NET-utbyggbarhet |
   | ISAPI-tillägg |
   | ISAPI-filter |

   | Hälsa och diagnostik |
   |---|
   | HTTP-loggning |
   | Loggningsverktyg |
   | Begär övervakare |
   | Kalkering |
   | Anpassad loggning |

   | Säkerhet |
   |---|
   | Grundläggande autentisering |
   | Windows-autentisering |
   | URL-autentisering |
   | Begärandefiltrering |
   | IP- och domänbegränsningar |

   | Hanteringsverktyg |
   |---|
   | IIS-hanteringskonsolen |
   | IIS-hanteringsskript och -verktyg |
   | Management Service |

1. Följ guiden för att slutföra installationen.
