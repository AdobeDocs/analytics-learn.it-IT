---
title: Best practice di implementazione per le applicazioni a pagina singola (SPA)
description: Scopri alcune best practice per l’implementazione di Adobe Analytics nelle applicazioni a pagina singola (SPA). Ciò include l’utilizzo dei tag di Experience Platform, il metodo di implementazione consigliato.
feature: Implementation Basics
topics: spa
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1389
topic: SPA
role: Developer, Data Engineer
level: Intermediate
exl-id: 8fe63dd1-9629-437f-ae07-fe1c5a05fa42
source-git-commit: d78c3351d2a98704396ceb8f84d123dd463befe5
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Best practice di implementazione per le applicazioni a pagina singola (SPA) {#implementation-best-practices-for-single-page-appliations}

Scopri alcune best practice per l’implementazione di [!DNL Adobe Analytics] su applicazioni a pagina singola (SPA). Ciò include l&#39;utilizzo di [!DNL Experience Platform Tags], il metodo di implementazione consigliato.

NOTE INIZIALI:

* Il contenuto seguente fa riferimento all&#39;uso di [!DNL Experience Platform Tags] per implementare Adobe Analytics sul tuo sito. Queste considerazioni si applicano se [!DNL Experience Platform Tags] non viene utilizzato, pertanto devi adattarli al metodo di implementazione.
* Ci sono differenze in SPA, quindi, è necessario regolare il vostro approccio di conseguenza per soddisfare al meglio le vostre esigenze.

## Diagramma semplice dell’uso delle applicazioni a pagina singola in [!DNL Experience Platform Tags] {#simple-diagram-of-working-with-spas-in-tags}

![SPA per l’analisi nei tag](assets/spa_for_analyticsinlaunch.png)

**NOTA:** Questo è un diagramma semplificato del modo in cui SPA pagine vengono gestite in un’implementazione Adobe Analytics utilizzando [!DNL Experience Platform Tags]. Le sezioni seguenti identificano i passaggi e i problemi da considerare.

## Imposta il livello dati {#set-the-data-layer}

Quando viene caricato un nuovo contenuto o quando si verifica un&#39;azione su una pagina SPA, *aggiorna prima il livello dati*. Questo deve accadere **prima** un evento personalizzato che attiva l&#39;esecuzione di una regola in [!DNL Experience Platform Tags]. In questo modo i valori corretti dal livello dati vengono inviati a Tags e quindi Adobe Analytics.

Di seguito è riportato un livello di dati di esempio. Uno qualsiasi di questi elementi può variare in base alla visualizzazione iniziale o alla successiva modifica della visualizzazione, in base a un&#39;azione eseguita sulla pagina di SPA. Ad esempio, in caso di modifica della visualizzazione a maggioranza o a pieno titolo, è necessario trasmettere un valore univoco &quot;[!DNL pageName]&quot; per differenziare le visualizzazioni nel reporting di Adobe Analytics.

```JavaScript
<script>
    digitalData = {
        pageInstanceID: "Launch Demo Site",
        page:{
            pageInfo:{
                pageID: '2745374',
                pageName: 'acs demo - product listing page'
            },
            attributes:{
                project: "Experience Platform Launch Project"
            }
        },
        user : [ {
          "profile" : [ {
            "attributes" : {
              "gender" : "male",
              "age" : "35"
            }
          } ]
        }],
        libraries : {
          adobe : {
            launch : {
              state : 0, // 0 = not loaded , 1 = loaded
              domain : "assets.adobedtm.com"
            }
          }
        }

     };
    </script>
```

## Imposta eventi personalizzati e ascolta questi eventi in [!DNL Experience Platform Tags] {#setting-custom-events-and-listening-in-tags}

Quando viene caricato un nuovo contenuto o si verifica un’azione nella pagina di SPA, è necessario informare i Tag di Experience Platform per eseguire una regola che invia i dati a [!DNL Analytics]. Ci sono un paio di approcci per questo: [!UICONTROL Direct Call rules] o Eventi personalizzati.

* [!UICONTROL Direct Call rules]: Imposta un [!UICONTROL direct call rule] che viene eseguito quando viene chiamato direttamente dalla pagina. Se il caricamento o l’azione della pagina è semplice o univoco e può eseguire ogni volta un set specifico di istruzioni (ad esempio, imposta [!DNL eVar4] a X e attivare [!DNL event2] ogni volta), allora questo approccio è adatto. Fai riferimento a [!DNL Experience Platform Tags] documentazione per maggiori dettagli sulla creazione [!UICONTROL direct call rules].
* Eventi personalizzati: Se devi allegare dinamicamente un payload con valori univoci per gli eventi che si verificano sulle pagine SPA, utilizza eventi JavaScript personalizzati e ascoltali in [!DNL Experience Platform Tags]. Utilizza il payload per impostare gli elementi dati e le variabili Analytics in Tag. Questo metodo è considerato la best practice, in quanto questa necessità è generalmente prevalente per SPA. Gli esempi seguenti utilizzano il metodo degli eventi personalizzati.

**Esempi:** [In questo](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html) documentazione, sono presenti collegamenti a siti di SPA di esempio che implementano [!DNL Analytics] e altre soluzioni di Experience Cloud. In questi esempi vengono utilizzati i seguenti eventi personalizzati:

* **[!DNL Event-view-start]**: Esegui all&#39;inizio della visualizzazione o dello stato che viene caricato.
* **[!DNL Event-view-end]**: Esegui quando si verifica una modifica di visualizzazione/stato e tutti i componenti SPA sulla pagina finiscono il caricamento. Questo è l’evento che in genere invia dati ad Adobe Analytics.
* **[!DNL Event-action-trigger]**: Esegui quando si verifica un evento sulla pagina, tranne il caricamento visualizzazione/stato. Esempi di questo includono un evento clic o una modifica del contenuto più piccola senza una modifica della visualizzazione.

Per ulteriori informazioni su come e quando si attivano questi eventi, consulta le pagine e i documenti citati in precedenza. Non è necessario utilizzare gli stessi nomi evento nell’implementazione. Il caso d’uso funzionale del metodo utilizzato è essenziale per comprendere come best practice consigliate per ciascuno di essi. Il video seguente illustra un esempio di pagina SPA e di codice di esempio in [!DNL Experience Platform Tags] che ascolta gli eventi personalizzati.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12)

## Esegui s.t() o s.tl() nel [!DNL Experience Platform Tags] {#running-s-t-or-s-tl-in-the-launch-rule}

Un concetto importante da comprendere [!DNL Analytics] quando si lavora con un SPA è la differenza tra `s.t()` e `s.tl()`. Il codice attiva uno o più di questi metodi in [!DNL Experience Platform Tags] per inviare dati in [!DNL Analytics].

* **s.t()** - La &quot;t&quot; sta per &quot;track&quot; e rappresenta una visualizzazione di pagina. Se la visualizzazione cambia abbastanza  *considerare* è una nuova &quot;pagina&quot;, usa questa chiamata. Imposta un valore univoco su [!DNL s.pageName] variabile e utilizzo `s.t()` per inviare i dati in [!DNL Analytics].

* **s.tl()** - &quot;tl&quot; sta per &quot;track link&quot;, e questo rappresenta un clic di collegamento o una piccola modifica del contenuto. Se la modifica della visualizzazione è minima, utilizza `s.tl()` per trasmettere un valore univoco sull&#39;interazione a [!DNL Analytics]. Questa variabile passata non è [!DNL s.pageName], poiché questa viene ignorata in Analytics quando `s.tl()` vengono ricevute le chiamate .

**SUGGERIMENTO:** Come linea guida generale, se lo schermo cambia di oltre il 50%, utilizza la `s.t()` chiamata alla visualizzazione della pagina. In caso contrario, utilizza `s.tl()`. Tuttavia, usa il tuo giudizio quando consideri le azioni che costituiscono una nuova &quot;pagina&quot; e come dovrebbero essere presentate nei rapporti di Adobe Analytics.

Il video seguente mostra dove e come attivare `s.t()` o `s.tl()` in Tag.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12)

## Cancella variabili {#clear-variables}

Invia i dati giusti a [!DNL Analytics] al momento giusto. In un ambiente SPA, un valore memorizzato in un [!DNL Analytics] persiste e restituisce in [!DNL Analytics], potenzialmente quando non lo desideri più. Esiste una funzione nel [!DNL Analytics] [!DNL Tags] per cancellare le variabili in modo che la chiamata successiva non invii erroneamente i dati in [!DNL Analytics].

Il diagramma precedente mostra le variabili eliminate *dopo* invii dati. In realtà, questo può accadere prima O dopo la chiamata, tuttavia, essere coerente nel [!DNL Experience Platform Tags] regole per un&#39;implementazione più pulita. Se cancelli le variabili *prima* esegui `s.t()`, imposta le nuove variabili immediatamente dopo la chiamata , quindi procedi all’invio dei nuovi dati in [!DNL Analytics].

**NOTA:** La cancellazione delle variabili non è sempre necessaria quando si esegue `s.tl()`. Questa chiamata richiede l&#39;utilizzo del [!DNL linkTrackVars] variabile da istruire [!DNL Analytics] le variabili da impostare. Questo accade automaticamente [!DNL Experience Platform Tags] attraverso la configurazione. Impedisce l’impostazione di variabili erranti a differenza del comportamento con `s.t()` effettua chiamate in un ambiente SPA. Per garantire un’implementazione più pulita e affidabile, è probabile che sia più facile utilizzare la funzione clear variables per entrambe le chiamate in un ambiente SPA.

Il video seguente mostra dove e come cancellare le variabili in [!DNL Tags].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12)

## Considerazioni aggiuntive {#additional-considerations}

### Finestre Codice personalizzato in [!DNL Experience Platform Tags] {#custom-code-windows-in-tags}

In [!DNL Tags] [!DNL Analytics] estensione, esistono due posizioni in cui può essere inserito il codice personalizzato: &quot;[!UICONTROL library management]&quot; e &quot;[!UICONTROL Configure tracker using custom code]&quot; sezioni.

![Finestre del codice personalizzato di Analytics dei tag](assets/launch_analyticscustomcodewindows.png)

Una di queste posizioni esegue il codice in essa contenuto una volta per il caricamento iniziale della pagina SPA. Se il codice deve essere eseguito su una visualizzazione o su una modifica dell’azione, implementalo nel **[!UICONTROL rule]** (ad esempio, il &quot;caricamento della pagina: event-view-end&quot; rule), per garantire che il codice venga eseguito ogni volta che il [!UICONTROL rule] corre. Quando si crea un&#39;azione in [!UICONTROL rule], set *Estensione = Core* e *Tipo di azione = Codice personalizzato*.

### SPA &quot;ibridi&quot; e siti tradizionali {#hybrid-spa-and-traditional-sites}

Alcuni siti sono composti da una combinazione di pagine tradizionali e SPA. In questo caso, utilizza una strategia che funzioni per entrambi i tipi di pagina. Durante la configurazione degli eventi personalizzati sul sito e l&#39;attivazione delle regole in [!DNL Experience Platform Tags], assicurati che i doppi hit non vengano inviati in [!DNL Analytics] in base ai cambiamenti di hash e così via. In questo caso, elimina una delle visualizzazioni di pagina per evitare la trasmissione di dati duplicati in Adobe Analytics.

Se decidi di separare la funzionalità in un’unica [!UICONTROL rules] per un maggiore controllo, ricorda di documentare che hai fatto questo. Se ne cambia uno [!UICONTROL rule], effettuare la stessa modifica all&#39;altro [!UICONTROL rule].

### Integrazione con [!DNL Target] utilizzo di A4T {#integration-with-target-using-a4t}

Durante l&#39;integrazione con [!DNL Target] utilizzando A4T, verifica che il [!DNL Target] e [!DNL Analytics] le richieste inviate sulla stessa visualizzazione o azione passano lo stesso valore del parametro SDID. In questo modo i dati verranno sincronizzati correttamente nel backend.

Per visualizzare questi risultati, utilizza uno strumento di debug o di monitoraggio dei pacchetti. Adobe fornisce un debugger Experience Platform a questo scopo. È un’estensione Chrome che può essere [scaricato qui](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob?hl=en). [!DNL Target] deve essere eseguito per primo sulla pagina. Questo può essere verificato anche nel debugger.

## Risorse aggiuntive {#additional-resources}

* [Discussione su applicazioni a pagina singola nei forum Adobe](https://experienceleaguecommunities.adobe.com:443/t5/adobe-experience-platform-launch/best-practices-for-single-page-apps/m-p/267940)
* [Architettura di riferimento per mostrare come implementare applicazioni a pagina singola in Experience Platform Launch](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)
