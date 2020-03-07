---
description: Det första steget är att aktivera IIS-rollen på instrumentpanelsservern.
solution: Analytics
title: Aktiverar IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aktiverar IIS{#enabling-iis}

Det första steget är att aktivera IIS-rollen på instrumentpanelsservern.

1. Öppna **[!UICONTROL Administrative Tools]** under **[!UICONTROL Server Manager]**.
1. Högerklicka på menyalternativet Roller i den vänstra delen av **[!UICONTROL Server Manager]** fönstret.
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
