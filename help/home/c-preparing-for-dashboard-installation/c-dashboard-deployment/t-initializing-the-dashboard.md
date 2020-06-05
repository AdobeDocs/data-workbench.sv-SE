---
description: Det sista steget är att köra kontrollpanelen för första gången så att den kan initieras.
solution: Analytics
title: Initierar kontrollpanelen
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---


# Initierar kontrollpanelen{#initializing-the-dashboard}

Det sista steget är att köra kontrollpanelen för första gången så att den kan initieras.

1. Öppna en webbläsare och ange URL:en till den nyligen distribuerade webbplatsen (till exempel http://localhost/dashboard).
1. När du ansluter för första gången skapas databastabellerna, vilket kan medföra en fördröjning.
1. Inloggningsuppgifterna är:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: lösenord

1. Vid den första inloggningen går du till **[!UICONTROL User]** > **[!UICONTROL Account Settings]** och väljer **[!UICONTROL Change Password]** att ändra administratörslösenordet.

Instrumentpanelsinstallationen är nu klar. Om du inte redan gjort det kan du konfigurera kommunikationen med data workbench-servrar och hantera användare och grupper med hjälp av instruktionerna i avsnittet Förbereda data Workbench i den här handboken.

>[!NOTE]
>
>Instrumentpanelsfel och granskningsloggar finns i [!DNL logs] katalogen i installationssökvägen.

>[!NOTE]
>
>Om du behöver ändra programpoolens identitet till ett annat konto måste du se till att ge åtkomst till databasen och ge identiteten läs- och skrivåtkomst till [!DNL logs] mappen i installationssökvägen.

>[!NOTE]
>
>Om du behöver ändra databasens anslutningssträng behöver du bara redigera värdet med hjälp av **[!UICONTROL IIS Management Console]**.
