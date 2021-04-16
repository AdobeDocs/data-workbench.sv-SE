---
description: Om nätverkets brandväggar inte förhindrar åtkomst till den upprepade servern från Insight-datorer kan du skapa en anslutning mellan den upprepade servern och Insight så att du kan hantera den upprepade servern med Insight.
title: Skapa en anslutning mellan Insight och Repeater
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Skapa en anslutning mellan Insight och Repeater{#creating-a-connection-between-insight-and-repeater}

Om nätverkets brandväggar inte förhindrar åtkomst till den upprepade servern från Insight-datorer kan du skapa en anslutning mellan den upprepade servern och Insight så att du kan hantera den upprepade servern med Insight.

**Skapa en anslutning mellan  [!DNL Insight] och den upprepade servern**

1. På fliken [!DNL Insight] klickar du på miniatyrbilden för **[!UICONTROL Configure Connections to Servers]** för att öppna arbetsytan Konfigurera anslutningar till servrar.[!DNL Admin]
1. I fönstret [!DNL Insight.cfg] högerklickar du på **[!UICONTROL Servers]** och klickar på **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Slutför följande parametrar för den nya servern:

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För den här parametern.. </th> 
   <th colname="col2" class="entry"> Ange... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2">(Valfritt) Namnet som du vill att denna <span class="keyword"> Insight</span> ska använda för att representera den upprepade servern i användargränssnittet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adress </td> 
   <td colname="col2"> <p>Värdnamnet eller den numeriska IP-adressen för den upprepade servern. </p> <p>Exempel: <span class="filepath"> Repeater.mycompany.com</span> eller 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL-klientcertifikat </td> 
   <td colname="col2"> <p>Valfritt om du inte har fler än ett certifikat. Namnet på filen som innehåller det digitala certifikatet för den här kopian av <span class="keyword"> Insight</span>. (Det här är filen som du hämtade när du installerade <span class="keyword"> Insight</span>.) </p> <p>Exempel: <span class="filepath"> Samantha Smith.pem</span></p> <p>Om du lämnar den här parametern tom används det certifikat som finns i <span class="keyword"> Insight</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL-server </p> <p>Gemensamt namn </p> </td> 
   <td colname="col2">Det vanliga namn som tilldelats den upprepande servern. Namnet måste matcha det vanliga namn som tilldelats den upprepade servern i dess licenscertifikat. Om du har åtkomst till den upprepandes certifikatfil (<span class="filepath"> Certificates\server_cert.pem</span>) kan du hitta det vanliga namnet genom att öppna filen med en textredigerare som Anteckningar. Det vanliga namnet identifieras i fältet CN i certifikatet. </td> 
  </tr> 
 </tbody> 
</table>

1. Spara filen genom att högerklicka på **[!UICONTROL (modified)]** högst upp i fönstret och klicka på **[!UICONTROL Save]**. [!DNL Insight] kommer att försöka ansluta till den upprepade servern med de inställningar du har angett. Om en anslutning upprättas visas en grön serverikon i [!DNL Servers Manager]-gränssnittet. Om det inte går att upprätta en anslutning visas en röd ikon.

   Mer information om gränssnittet [!DNL Servers Manager] finns i användarhandboken * [!DNL Insight].*
