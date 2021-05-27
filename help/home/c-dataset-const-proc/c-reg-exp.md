---
description: Reguljära uttryck används i alla sökfält i en workbench för data, inklusive frågans entitetspaneler.
title: Reguljära uttryck
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 1%

---

# Reguljära uttryck{#regular-expressions}

Reguljära uttryck används i alla sökfält i en workbench för data, inklusive frågans entitetspaneler.

* [Om reguljära uttryck](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologi för reguljära uttryck](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Om Literal Matching](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Använda metatecken](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Mönsterextrahering](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Om reguljära uttryck {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Ett reguljärt uttryck är ett textmönster som består av en kombination av alfanumeriska tecken och specialtecken, så kallade metatecken, som lokaliserar mönster och extraherar delsträngar från text. Reguljära uttryck används ofta i datamodeller och är en viktig del av språk som Perl.

För att identifiera och extrahera komplexa strängmönster använder data workbench-servern reguljära uttryck i vissa omformningar och villkor. Här följer en kort guide till reguljära uttryck.

Denna bilaga är inte en omfattande introduktion till reguljära uttryck. En särskilt bra referens är O&#39;Reilly-publikationen *Mastering Regular Expressions, andra utgåvan* av Jeffrey E. F. Friedl.

## Terminologi för reguljära uttryck {#section-80b0d54f731e448391532ab3eb3c525c}

| Term | Definition |
|---|---|
| Literal | En litteral är ett tecken som vi använder i ett reguljärt uttryck för att hitta en specifik teckensekvens. Om du till exempel vill hitta en produkt i [!DNL shop/products.html] är strängprodukten en litteral, eller det vi bokstavligen letar efter i strängen. |
| Metatecken | Ett metatecken är ett specialtecken som har en unik tolkning i samband med reguljära uttryck. Exempel: punkt (.) är ett metatecken som används för att matcha alla tecken. |
| Escape-sekvens | En escape-sekvens är bara ett sätt att tala om för motorn för reguljära uttryck att vi vill använda ett av metatecknen som en litteral. Escape-sekvenser börjar alltid med ett omvänt snedstreck (`\`). Genom att placera det omvända snedstrecket (som också är ett metatecken) framför ett metatecken tolkar motorn för reguljära uttryck det escape-metatecken som en litteral. Om du till exempel vill matcha metateckenperioden (`.`) måste du använda en escape-sekvens. Om du vill matcha en av punkterna i strängen 168.196.0.11 kan du använda det reguljära uttrycket som består av ett omvänt snedstreck och en punkt (`\.`). |
| Mönster | Det här är en kortfattad terminologi för det reguljära uttrycket. Ett reguljärt uttryck är ett mönster som du försöker matcha mot målsträngen. |
| Målsträng | Den här termen hänvisar till strängen som vi söker i för att hitta det önskade mönstret. |

## Om Literal Matching {#section-ec4497e3160c47ba9b828d939761b3e0}

Litteral matchning tar en litteral sträng utan escape-tecken och söker i målsträngen för att se om det är en delsträng av målsträngen.

I det här exemplet ser du hur literal matchning fungerar. Tänk på en situation där data samlas in från webbplatstrafiken och fältet cs(reference) innehåller följande värde:

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

För att avgöra om referenten representerar någon som klickat på någon av annonserna måste du se om referenten innehåller strängannonsen. Du kan helt enkelt använda strängen literal för att söka efter målsträngen och avgöra om en annons användes för att dirigera trafiken till webbplatsen. Detta skulle matcha målsträngen, men skulle matcha på två platser och är därför tvetydigt och kan leda till falskt positiva resultat.

Följande URL innehåller strängen och på två olika platser:

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Om du försöker avgöra vilka sessioner som inleddes till följd av en viss annonskampanj räcker det alltså inte att bara använda literalannonsen eftersom det reguljära uttrycket är helt klart inte. Om du ändrar literalen till &quot;ad=&quot; tas den här tvetydigheten bort, vilket resulterar i att uttrycket bara gör en enda matchning. Även detta kanske inte räcker för att se till att den som hänvisar till ska vara en del av annonskampanjen. Tänk på följande hänvisare:

`http://www.xyz.com/hello.html?pad=something`

Du har ingen kontroll över de URL:er som andra kan använda för att skapa länkar till webbplatsen. Litteral matchning är en för enkel mekanism för att hitta sessioner som startats som ett resultat av annonskampanjen. I följande avsnitt beskrivs hur du kan använda metatecken för mer flexibel och kraftfull matchning.

## Använda metatecken {#section-e29a804336304ea1ba33d40d60139aa2}

Ett metatecken är ett specialtecken i ett program eller datafält som ger information om andra tecken.

| metatecken | description |
|---|---|
| . (punkt) | Matchar ett enskilt tecken, till exempel: `re:x.z` matchar &quot;xyz&quot; eller &quot;xxz&quot;. |
| * (stjärna) | Matchar ett eller flera tecken, till exempel: `re:Z*` matchar&quot;ZZZ&quot;. |
| ? (jokertecken) | Matchar 0 eller 1 av föregående uttryck för att framtvinga minimal matchning, till exempel: `xy?z` matchar &quot;xy&quot; och &quot;xyz&quot;. |

Ytterligare vanliga reguljära uttryck kan också användas för att skapa mer komplexa söksträngar.

**Listor, intervall och OR**

Med litteral matchning kan du söka efter en enda sträng, men med hakparenteser, streck och rör kan du definiera en lista med saker som ska sökas efter i målsträngen.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För det här metatecknet.. </th> 
   <th colname="col2" class="entry"> Processor för reguljära uttryck kommer att... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Hakparenteser ([ ]) </td> 
   <td colname="col2"> Matcha något av tecknen inom parentesen med en enda teckenposition. Till exempel är [AB] en instruktion att matcha antingen bokstaven A eller bokstaven B och [0123456789] säger matcha något tecken i intervallet 0 till 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Streck (-) </td> 
   <td colname="col2"> <p>Matcha ett intervall med tecken. I stället för att skriva [0123456789] kunde vi helt enkelt skriva [0-9]. </p> <p> Detta kan utökas till intervall med tecken och till flera intervall inom en uppsättning hakparenteser. Till exempel matchar [0-9A-C] tecknen 0 till 9 och A till C. </p> <p> <p>Obs!  Om du vill testa ett bindestreck (-) som en litteral inuti parenteserna måste det komma först eller sist. Till exempel testar [-0-9] för - och 0 till 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pipe (|) </td> 
   <td colname="col2"> Matcha ett av två alternativ till en angiven målsträng. Exempel: b|nat matchar antingen bat eller nat. </td> 
  </tr> 
 </tbody> 
</table>

Titta på följande exempel:

| Mönster | Sträng | Matcha |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 1 |
| Lektion`[A-Z]` | Lektion | Ingen matchning eftersom&quot;a&quot; med lägre placering inte ligger inom intervallet för&quot;A till och med Z&quot;. |

**Negation**

Negation är ett sätt att säga att du vill matcha vad som helst förutom de angivna tecknen. negationsmetatecknet, cirkumflex eller cirkumflex (`^`), används som det första tecknet inom hakparenteser för att ange att matchningen ska vara vad som helst utom de återstående tecknen inom hakparenteserna. Om du till exempel vill matcha ett tecken men ett semikolon (`;`) skriver du

[`^;`]

Detta skulle matcha alla tecken utom semikolon.

**Positionering**

Om du vill tvinga fram en matchning till början eller slutet av en målsträng, används ett av två metatecken.

| För det här metatecknet.. | Processor för reguljära uttryck kommer att... |
|---|---|
| Cirkumflex eller Caret (`^`) | Matcha mot början av strängen. ^`[Tt]`han skulle till exempel matcha målsträngen &quot;Början&quot;, men inte &quot;Detta är början.&quot; |
| Dollartecken (`$`) | Matcha mot strängens slut. `[Ee]`nd$ skulle till exempel matcha&quot;This is the end&quot;, men skulle inte matcha&quot;The end is a special time&quot;. |

>[!NOTE]
>
>När det reguljära uttrycket innehåller ^ i början och $ i slutet, måste hela målsträngen matcha det reguljära uttrycket.

**Matcha vad som helst**

Perioden (.) är ett metatecken som matchar alla tecken i målsträngen. Det reguljära uttrycket `^…$` matchar alla målsträngar som är exakt tre tecken långa. Det reguljära uttrycket &quot;..&quot; matchar alla målsträngar som innehåller minst tre tecken.

**Upprepade mönster**

Med iterationsmetatecken kan du matcha ett mönster mer än en gång.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> För det här metatecknet.. </th> 
   <th colname="col2" class="entry"> Processor för reguljära uttryck kommer att... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Frågetecken (?) </td> 
   <td colname="col2"> Matcha inga instanser eller en instans av tecknet direkt före metatecknet (?). Mönsterområdet?d matchar rött och läst. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asterisk (*) </td> 
   <td colname="col2"> Matcha noll eller flera förekomster av tecknet direkt före metatecknet (*). Mönstret [0-9]* matchar till exempel valfritt antal tecken från 0 till 9 (ett heltal). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Matcha en eller flera förekomster av föregående tecken eller intervall. Mönstret där+ matchar till exempel tre men inte igenom. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Matcha det inledande tecknet eller intervallet exakt n gånger. Följande mönster matchar telefonnummer från USA: <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Det är inte ett optimalt mönster, men det avgör om målsträngen har rätt format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Matcha föregående tecken minst n gånger och högst m gånger. fo{1,2}d matchar till exempel mat och mat, men inte mat. </td> 
  </tr> 
 </tbody> 
</table>

## Mönsterextrahering {#section-4389779653b64f6cb7c47615b25c1a79}

Mönstermatchning är bara en del av kraften i reguljära uttryck. Med reguljära uttryck kan du även extrahera viktiga delar av en målsträng. Detta görs med vänster och höger parentes. Dessa extraheringar används vanligtvis som indata i en annan process och nås via *%position%*, där position är ett heltal som refererar till antalet parenteser som matchades.

Titta på följande exempel på mönsterextrahering:

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mönster </th> 
   <th colname="col2" class="entry"> Sträng </th> 
   <th colname="col3" class="entry"> Matcha </th> 
   <th colname="col4" class="entry"> Extrahering </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> lektion([A-Z]) </td> 
   <td colname="col2"> Lektion </td> 
   <td colname="col3"> Ingen matchning eftersom"a" med lägre placering inte ligger inom intervallet för"A" till"Z" </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>
