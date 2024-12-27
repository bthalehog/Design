---
Title: Colors
Description: About color analysis
Template: analysis
---

> Analys av färgschema för tre webbsidor
=======================

I följande rapport undersöks och jämförs tre webbsidors så kallade laddningshastighet. Undersökningen syftar till att utreda vilka effektiviseringar som kunnat göras för respektive sida för att snabba på laddningshastigheten.

Urval
-----------------------
Urvalet består av tre webbsidor tillhörande svenska universitet/högskolor; Blekinge tekniska högskola (BTH), Dalarnas universitet (DU) samt Luleå tekniska universitet (LTU). Varje sida mäts på tre mätpunkter: startsida, utbildningsöversiktssida samt specifik utbildningssida.				

Metod
-----------------------
Metoden går ut på att analytikern med hjälp av mätverktyget _Page speed insights_ kontrollerar de tre webbsidornas resultat avseenden LCP (Largest Contentful Paint), INP (Interaction to Next Paint), CLS (Cumulative Layout Shift), FCP (First Contentful Paint) samt TTFB (Time to first byte) samt kontrollerar vilka tre föreslagna förbättringar som hade haft störst positiv effekt vid implementering. Mätningar görs för såväl dator- som mobiltelefonmiljön.

_Metodbeskrivning_
De valda sidorna mäts och resultaten förs in i excelark. Mätvärden härleds, där möjligt, till funktion med rekommendation för effektivisering om sådan kan identifieras. Sidornas sämsta  mätpunkt används sedan för att identifiera olika förbättringsförslag och för varje sida sammanställs en kortare presentation som sammanfattar dess resultat. Datatabell finns tillgänglig i slutet av dokumentet. 
Ett medelvärde för tre laddningar av startsidan för respektive analysobjekt görs för att ta fram ett snittvärde avseende LCP (Largest contentful paint).


##_Blekinge tekniska högskola_  

<img class="reportpic" src="../../themes/shared/img/analysis/BTH.png" alt="Blekinge tekniska högskola" width="500" height="auto"></img>

Blekinge tekniska högskola (BTH) är en högskola med teknologikprofil belägen i södra Sverige. BTH har en betydligt ojämnare poängdistribution än övriga analysobjekt generellt är det enda av objekten som i flera fall uppvisar värden lägre än 90, mest sällan når 100 samt uppvisar mätvärden som ligger under gränsvärde. Det svagaste värdet är det uppmätta värdet för datormiljön är BTH:s utbildningssida avseende prestanda (55). Vad gäller mobilmiljön uppvisar utbildningssidan mätvärden under gränsvärde avseende prestanda (36) vilket också är det sämsta uppmätta värdet bland de tre analysobjekten. BTH är vidare det enda analysobjekt som inte når 100 i någon kategori. BTH uppvisar, i relation till övriga analysobjekt, dåliga resultat för sin mobilmiljö där flera värden ligger långt under övriga analysobjekt.
I den mätning som gjordes avseende snittvärde för LCP får BTH ett relativt dåligt resultat med snittvärdet 6,64 sekunder. 

_Förbättringar_
Sidan rekommenderas ta bort resurser som blockerar renderingen vilket skulle innebära en besparing om 4420ms för laddningstiden. Bland rekommendationerna framhålls uppdatering sina API:er då utfasade sådana identifierats under testningen. Vidare uppges sidan använda tredjepartscookies vilket enligt ny standard inte längre än nödvändigt. Dessa två problem är troligen den grundläggande anledningen till den låga poängen på ovan nämnda avvikande mätpunkt.

Mindre besparingar avseende _Kibit_ kan göras genom att reducera Javascript som inte används, minifiera Javascrips samt reducera CSS som inte används och minifiera den som nyttjas.

Det finns ingen tydlig indikator bland förbättringsförslagen som kan förklara varför BTH presterat förhållandevis lågt avseende prestanda, möjligen är det renderingsproblemen som är huvudorsaken. 
Den primära orsaken till det svaga resultatet avseende snittvärde för LCP kan sannolikt förklaras med att headern innehåller en stor högupplöst bild.


##_Dalarnas Universitet_ 

<img class="reportpic" src="../../themes/shared/img/analysis/DU.png" alt="Dalarnas universitet" width="500" height="auto"></img>

Dalarnas universitet (DU) är den enda av lärosätena som inte har teknologiprofil men presterar trots det bättre än BTH vad gäller såväl startsida som funktionssida men uppvisar det sämsta resultatet för datormiljön när det kommer till specifik utbildningssida. Inget av värdena som mätts för sidan har legat under aktuella gränsvärden. DU:s mobiltelefonmiljö uppvisa för alla parametrar sämre mätvärden än DU:s datormiljö.

I den sammanvägda bedömningen uppvisar DU, för datormiljön, resultat över 90 i samtliga fall förutom _best practice_ avseende specifik utbildningssida vilken avviker markant från domänens övriga mätpunkter(56).

I den mätning som gjordes avseende snittvärde för LCP får DU det bästa resultatet bland våra analysobjekt med sitt snittvärde om 2,12 sekunder.

_Förbättringar_
Nedan redovisas de resultat som, mätt i antal _Kibit_, skulle ha störst inverkan på sidan laddningstid.

Sidan bör uppdatera sina API:er då utfasade sådana identifierats under testningen. Vidare uppges sidan använda tredjepartscookies vilket enligt ny standard inte längre än nödvändigt. Dessa två problem är troligen den grundläggande anledningen till den låga poängen på ovan nämnda avvikande mätpunkt.

Ytterligare enkla sätt att förbättra sina resultat kan uppnås genom att öka kontrasten mellan sidkomponenter samt genom att skicka bilder i modernare format och i rätt storlek.


##_Luleå tekniska universitet_

<img class="reportpic" src="../../themes/shared/img/analysis/LTU.png" alt="Luleå tekniska universitet" width="500" height="auto"></img>

Luleå tekniska universitet (LTU) är ett universitet med teknologiprofil och Sveriges nordligaste universitet. LTU uppvisar generellt goda resultat för båda miljöerna samt utmärkta resultat avseende _best practice_ och tillgänglighet. LTU uppvisar bättre resultat avseende mobilmiljön vilket kan bero på att sidan primärt är designad för att nås via sådan plattform. 

LTU sämsta mätvärde för datormiljön är prestandan för specifik utbildningssida (83), i andra fall är sammanvägda mätvärden över 90 i samtliga fall för datormiljön och i mobilmiljön är det bara prestandan som uppvisar lägre resultat i samtliga instanser medan övriga mätvärden speglar de för datormiljön.

I den mätning som gjordes avseende snittvärde för LCP får LTU ett snittvärde på 2,96 sekunder.

_Förbättringar_
Nedan redovisas de resultat som, mätt i antal _Kibit_, skulle ha störst inverkan på sidan laddningstid.

Samtliga rekommendationer för förbättring av prestandan innebär relativt små besparingar avseende _Kibit_ utan att någon tydlig anledning till varför dessa relativt små datamängder ger så stort negativt utslag på mätvärdet. Den specifika funktionssidan rekommenderas använda bilder i rätt storlek, skicka bilder i modernare bildformat samt hanterandet av en "layout-förskjutning" som möjligen också påverkar laddningstiden och som också kan härledas till bildproblematik.

Ytterligare enkla sätt att förbättra sina resultat kan uppnås genom att tillse att länkar som används har beskrivande text samt genom att "undvika enorm nätverksbelastning" om detta är möjligt med de små besparingar som kan göras avseende datamängd sänd.


Analys
-----------------------
Samtliga analysobjekt uppvisar i merparten av mätpunkterna tillfredsställande värden mellan 80-100. BTH utmärker sig som svagast bland objekten, i synnerhet avseende mobilmiljön samt generellt avseende prestanda. LTU uppvisar väldigt höga poäng avseende _best practice_ och SEO vilket gör objektet till det med högst poäng. DU är, trots avsaknandet av teknologiprofil, inte mätningens svagaste kandidat vilket något förvånande faller på BTH. 

Det är inte alltid tydligt vilka mätpunkter som inverkar mest på de lägre resultaten, i flera fall förefaller de besparingar i _Kibit_ som kan göras vara relativt små och det verkar inte helt logiskt varför de mätpuntker som uppvisar sämst resultat inte också uppvisar tydliga tecken på var problemet ligger. 

Samtliga sidor förefaller i första hand varit designade för datormiljon och sedan i olika omfattning ha anpassats för mobilmiljön vilket är logiskt med tanke på hur länge samtliga objekt varit aktiva.

Generellt kan sägas att svenska lärosäten, i den mån de tre analysobjekten är representativa för sådana, uppvisa goda resultat avseende laddningstid, högt åtföljande av standarder, särskilt avseende _best practice_ och SEO.

Laddningstider (LCP) under 3 sekunder upplevs som snabba, vid längre värden än så upplevs sidladdningen inte vara omedelbar och användaren kan visuellt se hur olika delar av sidan inte hinner laddas på samma tid som övrigt innehåll.

Dalarnas universitet är det analysobjekt som uppvisar bäst resultat, möjligen kopplat till att universitetet profilerar sig som ett lärosäte med stor del av utbildningen på distans med internet som medium.

Sammantaget förefaller bilder och rörlig media vara den största bakomliggande orsaken till låg laddningshastighet. Att formatera och beskära bilder till acceptabel kvalitet och lämplig storlek kan därför ha stor inverkan på laddningstiden.
Bildhanteringen är dessutom ett förhållandevis tillgängligt sätt att förbättra prestandan till skillnad från uppmaningar om att "undvika enormt DOM-träd" vilket kan vara svårt att begränsa vid större hemsidor.

Data
--------------------

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vTbDiHCng5TyFrfONMQyUAB06_pjBetzaeGPy9qp7VeFa3HB-Ub0JuR79ZrLgPChH0m0XzFv-Mn5P_e/pubhtml?widget=true&amp;headers=false" height="500px" width="400px"></iframe>

[raw-data](https://docs.google.com/spreadsheets/d/e/2PACX-1vRtbOZ_54GaiuN0dqKr1crjlRz8RNwTzPY7X3jhA816m0KJOWfSdFa8yAIIZtDYPSN1i9FCCyUA4tQE/pubhtml?gid=0&single=true)

Referenser
-----------------------
- https://moz.com/learn/seo/page-speed
- https://pagespeed.web.dev/
- https://www.bth.se/					
- https://www.bth.se/utbildning/program-och-kurser/					
- https://www.bth.se/utbildning/program-och-kurser/dvaam/					
- https://www.du.se/									
- https://www.du.se/sv/Utbildning/									
- https://www.du.se/sv/Utbildning/Program/grafisk-design-och-webbutveckling-kandidatprogram/									
- https://www.ltu.se/							
- https://www.ltu.se/utbildning							
- https://www.ltu.se/utbildning/program/tidag-hogskoleingenjor-datateknik			

Övrigt
-----------------------

Alexander Högfeldt
