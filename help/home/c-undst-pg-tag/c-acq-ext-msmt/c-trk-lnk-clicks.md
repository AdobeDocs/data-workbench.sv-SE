---
description: Steg som används för att underlätta samlingen av länkklick med hjälp av taggen för referenssidan.
solution: Analytics
title: Spåra länkklick
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Spåra länkklick{#tracking-link-clicks}

Steg som används för att underlätta samlingen av länkklick med hjälp av taggen för referenssidan.

Genom att distribuera [!DNL Reference Page Tag]är det möjligt att samla in mätdata som betecknar de länkar (eller href-värden) som besökarna klickar på när de besöker vissa sidor. Vanligtvis innebär den här samlingen inte implementering av ytterligare länkidentifierare på dina HTML-sidor.

Gör så här för att underlätta samlingen av Länkklickningar med [!DNL Reference Page Tag]hjälp av:

1. Kopiera följande kod till den befintliga filen med namnet [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Skapa eller placera bildfilen med en pixel i taget med namnet [!DNL zag2.gif] i en katalog som finns på webbservern.
1. Ändra variabeln så att den refererar till rätt domän på webbplatsen från vilken [!DNL lc.src] [!DNL zag2.gif]filen refereras.

1. Kontrollera att rätt cachekontrollhuvuden har skapats för [!DNL zag.gif] och [!DNL zig.js] filer.

1. I de HTML-filer som du vill samla in länkklickvärden från måste [!DNL Reference Page Tag Execution Call] du ändra dem så att de informerar användaren om [!DNL Page Tag Execution Script] att de ska hämta länkklickningar för sidan. Om du vill göra det ändrar du variabelvärdet vlc till &quot;1&quot; enligt följande kodexempel:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Insamlade data | Förklaring | Exempel |
|---|---|---|
| v_ln= | Värde som anger Impression Campaign | v_ln=&quot;Om%20oss&quot; |

