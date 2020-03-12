---
description: På arbetsytan kan du ordna och få tillgång till alla dina arbetsytor och rapporter.
solution: Analytics
title: Worktops
topic: Data workbench
uuid: ae6e475c-fc91-4c76-883b-894c9eb2933c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Worktops{#worktops}

På arbetsytan kan du ordna och få tillgång till alla dina arbetsytor och rapporter.

I de flesta fall [!DNL Worktop] visas filen direkt när du har öppnat Data Workbench. Funktionerna för [!DNL Worktop] är sidofältet och flikgränssnittet. Med sidofältet kan du dessutom lägga till visualiseringar och komma åt funktioner som används ofta.

**Skrivbord**

![](assets/client-wktp.png)

Du kan [!DNL Worktop] också skapa och spara nya och uppdaterade arbetsytor och rapporter, samt publicera arbetsytor och rapporter på Data Workbench-servern så att andra kan komma åt dem.

Elementtabellen [!DNL Worktop] nedan beskriver alla element i [!DNL Worktop].

<table id="table_CB1DBB7DE8E2450A8C57601531BBD689"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Sidebar </td> 
   <td colname="col2"> <p>Sidofältet ger sammanhang och kontroll för arbetsytor, liksom medvetenhet om det aktuella läget för en arbetsyta och tillgång till funktioner som används ofta. Följande funktioner är tillgängliga i sidlisten: </p> <p> <b>Anslutning:</b> En statusindikator som visar onlinestatus. Klicka på anslutningsstatusen för att aktivera eller inaktivera <span class="wintitle"> Work Online</span>. Se <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Arbeta offline och online</a>. </p> <p> <b>Profil:</b> En indikator för den aktuella profilen som används. </p> <p> <b>Från: </b>En statusindikator som visar hur aktuella data är i profilens datauppsättning. Dessa data hämtas och bearbetas från DPU-servern, som bara kan uppstå när du arbetar online. </p> <p> <b>Förtroende för fråga/prov:</b> En indikator för att frågan har slutförts. När statusen frågar till 100 procent har alla data frågats. </p> <p> <b>Lägg till:</b> Gör att du kan lägga till visualiseringar som paneler, teckenförklaringar och tabeller i sidofältet. Se <a href="../../home/c-get-started/c-config-sidebar.md#section-666f70a405db4f8d8eaffa567ffcac06"> Lägga till visualiseringar i sidofältet</a>. </p> <p> <b>Alternativ:</b> Gör att du kan återgå till en tidigare inställning för sidlist och automatiskt dölja sidlisten. </p> <p>Sidofältet sparas i filen <span class="filepath"> sidebar.vw</span> när du stänger Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Underkataloger för tabb och underflik eller nedrullningsbara listor (visas inte) </p> </td> 
   <td colname="col2"> <p>Varje flik som visas på <span class="wintitle"> arbetsytan</span> motsvarar flikens <i>arbetsprofilnamn</i>\Workspaces\<i>tabbnamnsmapp</i> i installationskatalogen för Data Workbench och representerar en viss typ av information, t.ex. Kontrollpaneler, Aktivitet, Hämtning, Besökare osv. Undermapparna i mappen för fliknamn visas som underflikar som standard, men de kan också visas som underkataloger. Se <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc"> Anpassa arbetsflikar</a>. </p> <p> <p>Obs!  Varje Data Workbench-profil levereras med en standarduppsättning med flikar. Eftersom implementeringen kan anpassas helt kan arbetsytorna (och därmed flikarna) som visas skilja sig från vad som beskrivs i den här handboken. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profilstatus </td> 
   <td colname="col2"> Anger anslutningsstatus till Data Workbench-servern och namnet på den inlästa profilen. Datum och tid för data i profilens datauppsättning som visas under onlineindikatorn. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimera, Maximera, Stäng </td> 
   <td colname="col2"> Standardfunktioner i Windows. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Miniatyrbilder </td> 
   <td colname="col2"> <p>En miniatyrbild är en ögonblicksbild av en arbetsyta som visas på <span class="wintitle"> skrivbordet</span>. En ny ögonblicksbild tas varje gång du sparar arbetsytan. Med hjälp av miniatyrbilder kan du snabbt identifiera en viss arbetsyta på <span class="wintitle"> skrivbordet</span>. </p> <p>Om du vill öppna en arbetsyta klickar du på miniatyrbilden. </p> <p> <p>Obs!  Varje Data Workbench-profil levereras med en standarduppsättning av arbetsytor. Eftersom implementeringen kan anpassas helt kan arbetsytorna (och därmed miniatyrbilderna) som visas skilja sig från vad som beskrivs i den här handboken. </p> </p> <p>Mer information om arbetsytor finns i <a href="../../home/c-get-started/c-config-sidebar.md#concept-41db771b302e43018e5a9daa40b397e6"> Konfigurera sidofältet</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Felmeddelanden </td> 
   <td colname="col2"> <p>Felmeddelanden visas i rött under statusen. Beskrivningar av statuskoder finns på <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html" format="http" scope="external"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html</a>. </p> <p>Till exempel: 403_Ej tillåtet. </p> </td> 
  </tr> 
 </tbody> 
</table>
