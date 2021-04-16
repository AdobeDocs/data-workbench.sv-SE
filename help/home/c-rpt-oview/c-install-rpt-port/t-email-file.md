---
description: Åtkomst till och behörigheter i rapportportalen styrs med enskilda användar- och gruppkonton.
title: Redigera filen Email.asp
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Redigera filen Email.asp{#edit-the-email-asp-file}

Åtkomst till och behörigheter i rapportportalen styrs med enskilda användar- och gruppkonton.

Varje gång du lägger till ett nytt konto eller redigerar ett befintligt konto kan ett bekräftelsemeddelande skickas till den e-postadress som du anger för det kontot (se [Arbeta med konton](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) och kopieras till de e-postadresser som du anger i filen [!DNL email.asp].

>[!NOTE]
>
>E-postmeddelanden skickas till kontoanvändare endast när du har angett en e-postadress för kontot och konfigurerat [!DNL email.asp]-filen korrekt. Om du inte vill att e-postmeddelanden ska skickas för ett konto lämnar du kontots e-postfält tomt.

Den här filen finns i mappen `\*PortalName*\PortalASP`.

1. Öppna [!DNL email.asp]-filen i en textredigerare, t.ex. Anteckningar, på den dator där IIS körs.
1. Ange följande variabler:

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För den här variabeln . . . </th> 
   <th colname="col2" class="entry"> Ange den här informationen. . . </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>DNS-namn eller IP-adress för SMTP-servern som meddelanden skickas från. </p> <p>Till exempel: <span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> Den port som SMTP-servern lyssnar efter anslutningar på. Detta är vanligtvis port 25. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> skicka </td> 
   <td colname="col2"> <p>Anger hur meddelandet ska skickas. Värdena är: </p> <p>1 - Skicka meddelanden med den lokalt installerade SMTP-tjänsten. Använd det här värdet om SMTP-tjänsten är installerad på den dator där skriptet körs. </p> <p>2 - Skicka meddelanden med hjälp av SMTP-tjänsten i nätverket. Använd det här värdet om SMTP-tjänsten inte är installerad på den dator där skriptet körs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2">Den tid som <span class="wintitle"> ska vänta på ett svar från SMTP-servern innan anslutningen avbryts.</span> </td> 
  </tr> 
 </tbody> 
</table>

1. Ange följande variabler för funktionerna [!DNL NewUserEmail()] och [!DNL UpdateUserEmail()]:

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> För den här variabeln . . . </th> 
      <th colname="col2" class="entry"> Ange den här informationen. . . </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Från </td> 
      <td colname="col2">Den text som du vill ska visas på Från-rubrikraden i bekräftelsemeddelandena. Det här värdet kan vara samma som värdet för <span class="wintitle"> CC</span>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>Valfritt. Den giltiga e-postadressen till den person eller det alias som ska få en kopia av alla meddelanden om nya och ändrade användarkonton. Du kan ange flera e-postadresser genom att separera adresserna med kommatecken (inga blanksteg). </p> <p>Till exempel: <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>Obs!  Mottagarna får kopior av e-postmeddelanden som innehåller användarlösenord. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ämne </td> 
      <td colname="col2"> Den text som du vill ska visas på ämnesraden i bekräftelsemeddelandena. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>Den verkliga vägen till din portal. </p> <p>Till exempel: <span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Brödtext </td> 
      <td colname="col2"> <p>Texten i de automatiskt genererade e-postmeddelandena. </p> <p>Här följer till exempel standardtexten som finns i de e-postmeddelanden som skickas för att ge inloggningsinformation: 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Din inloggningsinformation för webbportalen anges nedan: </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>Användarnamn: användarnamn </p><p>Nytt lösenord: lösenord </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>Du kan komma åt portalen via följande URL: </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">När du har loggat in på portalen kan du ändra ditt lösenord på fliken <span class="wintitle"> Admin</span>. </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Spara och stäng filen.
