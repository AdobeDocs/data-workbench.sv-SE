---
description: De mapp- och filnamn som ingår i implementeringen visas till vänster i Profilhanteraren.
title: Profilhanteraren
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Profilhanteraren{#profile-manager}

{{eol}}

De mapp- och filnamn som ingår i implementeringen visas till vänster i Profilhanteraren.

De profiler som programmet består av visas som de enskilda kolumnerna i [!DNL Profile Manager]. Dessa profiler innehåller flera ärvda profiler och en enda arbetsprofil.

>[!NOTE]
>
>Din arbetsprofil (antingen en datauppsättningsprofil eller en rollspecifik profil) är den profil som du läser in när du öppnar Data Workbench.

Kryssmarkeringarna (och deras färger) anger profilmappen/profilmapparna på den Data Workbench- och Data Workbench-dator där varje fil finns, om det finns flera kopior av en fil och om dessa flera kopior har samma ändringsdatum och -tid. De här filerna synkroniseras mellan Data Workbench- och Data Workbench-datorerna vid hämtning av profiler.

Här följer ett exempel [!DNL Profile Manager] HBX implementering:

![](assets/client-prof.png)

Från [!DNL Profile Manager] kan du öppna någon av de andra hanterarna (t.ex. [!DNL Dimensions Manager] eller [!DNL Reports Manager]), som endast visar vissa delar av [!DNL Profile Manager]. Du kan också skapa nya profilhanterare. Se [Skapa nya profilhanterare](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

En bockmarkering bredvid ett filnamn i en viss kolumn anger att en fil med det namnet finns i den mapp som heter i den kolumnen (profilen). Gå till höger i [!DNL Profile Manager], har filerna företräde framför dem till vänster, d.v.s. varje ärvd profil bygger på profilerna till vänster i dialogrutan [!DNL Profile Manager]. Om du till exempel har en fil med samma namn och på samma plats i [!DNL Base] profil (kolumn) och i [!DNL User] profil (kolumn), filen i [!DNL User] används i stället för filen i [!DNL Base] profil.

## Sök efter profiler {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

I Data Workbench 5.5 har ett sökfält lagts till för att hitta de profiler som krävs i [!DNL Profile Manager].

![](assets/client-prof2.png)

Följande typer av kolumner visas i [!DNL Profile Manager]:

* The *ärvt profilnamn* kolumner innehåller markeringar för filer som finns i varje profilmapp. Ärvda profiler innehåller interna profiler från Adobe samt företagsspecifika eller rollspecifika profiler som du skapar och underhåller. I exemplet ovan innehåller de interna profilerna Base, Traffic, Value, Marketing och så vidare. Internt [!DNL Base] profiler, som innehåller de grundläggande byggstenarna och den konfigurationsinformation som behövs för att köra ditt Adobe-program, medföljer alla implementeringar. De andra interna profilerna innehåller element (arbetsytor, mått, härledda dimensioner och så vidare) som rör särskilda typer av information, som webbtrafik eller marknadsföring. Adobe tillhandahåller bara de profiler som är lämpliga för den typ av data som du analyserar och för din bransch.

   >[!NOTE]
   >
   >Som standard kan inte interna profiler (de som tillhandahålls av Adobe) ändras. All anpassning måste ske i datauppsättningen, rollspecifika profiler eller andra profiler som du skapar. Om du skapar ett nytt program och behöver ändra en intern profil måste du ändra parametern Ändra interna profiler i dialogrutan [!DNL Insight.cfg] -fil. Se [Insight Configuration Parameters](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) för mer information. Kontakta Adobe Consulting Services innan du gör det.

* The *arbetsprofilsnamn* kolumnen, som alltid är nästa till sista kolumnen, innehåller markeringar för filer som finns i den aktuella arbetsprofilens mapp. I exemplet ovan är arbetsprofilen datauppsättning. Din arbetsprofil är antingen en datauppsättningsprofil eller en rollspecifik profil. Filerna i den här mappen har företräde framför filer med samma namn i alla ärvda profilmappar.
* The [!DNL User] kolumnen, som alltid är den sista kolumnen, innehåller markeringar för filer och mappar som finns som lokala filer i mappen User\*profile name*. Mappens katalogstruktur liknar arbetsprofilens katalogstruktur, och varje mapp med användarprofilens namn* innehåller lokala kopior av arbetsytor, mått och konfigurationsfiler för den aktuella profilen. Dessa lokala kopior har företräde framför alla filer med samma namn i alla ärvda mappar eller mappar med arbetsprofiler. Filerna i [!DNL User] kolumnen skapades och sparades antingen bara i mappen User\*profile name*, eller så finns de i en intern profil eller arbetsprofil och i mappen User\*profile name*. Filerna i varje mapp kan vara identiska eller inte och kan ha samma ändringsdatum och -tid eller inte.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * För att undvika att datauppsättningen endast ändras lokalt ignoreras de lokala Datan Workbench av [!DNL profile.cfg] och alla filer i mapparna Datauppsättning eller Exportera i mappen User\*profilnamn*. Ignorerade filer identifieras med en röd bakgrund i [!DNL User] och en&quot;Ignorerad i användarkatalogen&quot;-varning på snabbmenyn. Om du vill implementera de ändringar du gör i dina lokala kopior av dessa filer måste du spara dem i din arbetsprofil så att de kan synkroniseras med Datan Workbench. Anvisningar om hur du sparar filer i din arbetsprofil finns i [Publicera filer i din arbetsprofil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
   >    
   >    * Ett bindestreck (-) i stället för en bock i en kolumn identifierar en tom (nollbyte) fil. Data Workbench behandlar nollbytefiler som icke-existerande, vilket gör att du kan använda dem för att dölja filer som ingår i en profil till vänster. Se [Dölja filer med tomma filer (nollbyte)](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Bestämma filversioner {#section-225d732246b94cbe87acdfa9c881d6af}

Som vi nämnt i föregående avsnitt är markeringarna i [!DNL Profile Manager] är färgkodade så att du enkelt kan identifiera var en fil finns och om flera kopior av en fil ändrades vid olika tillfällen.

Om en fil eller en komprimerad katalog är exakt densamma som filen eller katalogen till vänster om den, har den samma färgbock som filen eller katalogen i den kolumnen (profilen). Om den skiljer sig från en fil eller katalog till vänster, eller om filen eller katalogen bara finns i [!DNL User] är bockmarkeringen vit.

![](assets/vis_ProfMgr_LocalFiles.png)

The [!DNL Profile Manager] som visas i exemplet ovan anger följande:

* En vit bock för [!DNL A New Metric.metric] filen bara visas i [!DNL User] , vilket anger att du bara har en lokal kopia av den filen. Den har inte publicerats (eller överförts) på Data Workbench-servern så att andra användare av Datan Workbench kan komma åt den.

* Kontrollera markeringar för [!DNL Average Score.metric] filnamnet visas i filmerna och [!DNL User] kolumner. bockmarkeringen i [!DNL User] -kolumnen har samma färg som bockmarkeringen i kolumnen Filmer, som anger att den lokala kopian av filen har samma ändringsdatum och -tid som filen i mappen Filmer.

* Kontrollera markeringar för [!DNL Average Score Error.metric] filnamnet visas i filmerna och [!DNL User] kolumner. bockmarkeringen i [!DNL User] -kolumnen är vit, vilket anger att den lokala kopian av filen har ett annat ändringsdatum eller -klockslag än filen i mappen Filmer.

