---
description: Det sista steget är att köra kontrollpanelen för första gången så att den kan initieras.
title: Initierar kontrollpanelen
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Initierar instrumentpanelen{#initializing-the-dashboard}

Det sista steget är att köra kontrollpanelen för första gången så att den kan initieras.

1. Öppna en webbläsare och ange URL:en till den nyligen distribuerade webbplatsen (till exempel http://localhost/dashboard).
1. När du ansluter för första gången skapas databastabellerna, vilket kan medföra en fördröjning.
1. Inloggningsuppgifterna är:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: lösenord

1. Vid den första inloggningen går du till **[!UICONTROL User]** > **[!UICONTROL Account Settings]** och väljer **[!UICONTROL Change Password]** för att ändra administratörslösenordet.

Instrumentpanelsinstallationen är nu klar. Om du inte redan gjort det kan du konfigurera kommunikationen med data workbench-servrar och hantera användare och grupper med hjälp av instruktionerna i avsnittet Förbereda Data Workbench i den här guiden.

>[!NOTE]
>
>Instrumentpanelsfel och granskningsloggar finns i katalogen [!DNL logs] i installationssökvägen.

>[!NOTE]
>
>Om du behöver ändra programpoolens identitet till ett annat konto måste du se till att ge åtkomst till databasen och ge identiteten läs-/skrivåtkomst till mappen [!DNL logs] i installationssökvägen.

>[!NOTE]
>
>Om du behöver ändra anslutningssträngen för databasen behöver du bara redigera värdet med **[!UICONTROL IIS Management Console]**.
