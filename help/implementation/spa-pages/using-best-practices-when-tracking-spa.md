---
title: Best practice di implementazione per le applicazioni a pagina singola (SPA)
description: Scopri alcune best practice per l’implementazione di Adobe Analytics nelle applicazioni a pagina singola (SPA). Ciò include l’utilizzo dei Tag per Experience Platform, il metodo di implementazione consigliato.
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
source-git-commit: 8fc641743bc9e07b838a22ca64ccc15344d52764
workflow-type: ht
source-wordcount: '1288'
ht-degree: 100%

---

# Best practice di implementazione per le applicazioni a pagina singola (SPA) {#implementation-best-practices-for-single-page-appliations}

Scopri alcune best practice per l’implementazione di [!DNL Adobe Analytics] su applicazioni a pagina singola (SPA). Ciò include l&#39;utilizzo di [!DNL Experience Platform Tags], il metodo di implementazione consigliato.

NOTE INIZIALI:

* Il seguente contenuto fa riferimento all&#39;utilizzo di [!DNL Experience Platform Tags] per implementare Adobe Analytics sul tuo sito. Queste considerazioni si applicano se non si utilizza [!DNL Experience Platform Tags], pertanto devi adattarle al tuo metodo di implementazione.
* Nelle applicazioni a pagina singola ci sono alcune differenze, quindi è necessario adattare il tuo approccio di conseguenza per soddisfare al meglio le tue esigenze.

## Diagramma semplice dell’uso delle applicazioni a pagina singola in [!DNL Experience Platform Tags] {#simple-diagram-of-working-with-spas-in-tags}

![applicazioni a pagina singola per analytics nei tag](assets/spa_for_analyticsinlaunch.png)

**NOTA:** si tratta di un diagramma semplificato del modo in cui le pagine di applicazioni a pagina singola vengono gestite in un’implementazione di Adobe Analytics utilizzando [!DNL Experience Platform Tags]. Le sezioni seguenti identificano i passaggi e i problemi da considerare.

## Impostare il livello dati {#set-the-data-layer}

Quando viene caricato un nuovo contenuto o quando si verifica un&#39;azione sulla pagina di un’applicazione a pagina singola, *prima aggiorna il livello dati*. Ciò deve accadere **prima** che un evento personalizzato che attiva una regola venga eseguito in [!DNL Experience Platform Tags]. In questo modo i valori corretti dal livello dati vengono inviati ai Tag e poi ad Adobe Analytics.

Di seguito è riportato un esempio di livello di dati. Uno qualsiasi di questi elementi può variare in base alla visualizzazione iniziale o alla successiva modifica della visualizzazione, in base a un&#39;azione eseguita sulla tua pagina dell’applicazione a pagina singola. Ad esempio, in caso di modifica totale o parziale della la visualizzazione, viene comunemente richiesto di trasmettere un valore univoco “[!DNL pageName]” per differenziare le visualizzazioni nel reporting di Adobe Analytics.

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

## Impostare eventi personalizzati e ascoltarli su [!DNL Experience Platform Tags] {#setting-custom-events-and-listening-in-tags}

Quando viene caricato un nuovo contenuto o si verifica un’azione nella pagina di un’applicazione a pagina singola, è necessario informare i Tag di Experience Platform per eseguire una regola che invia i dati a [!DNL Analytics]. Esistono due approcci per farlo: tramite [!UICONTROL Direct Call rules] o Eventi personalizzati.

* [!UICONTROL Direct Call rules]: imposta una [!UICONTROL direct call rule] che viene eseguita quando viene chiamata direttamente dalla pagina. Se il caricamento o l’azione della pagina è semplice o univoco e può eseguire ogni volta un set di istruzioni (ad esempio, imposta [!DNL eVar4] su X e attiva [!DNL event2] ogni volta), allora questo approccio è adatto. Fai riferimento alla documentazione di [!DNL Experience Platform Tags] per maggiori dettagli sulla creazione di [!UICONTROL direct call rules].
* Eventi personalizzati: se devi allegare dinamicamente un payload con valori univoci per gli eventi che si verificano sulle pagine di applicazioni a pagina singola, utilizza eventi JavaScript personalizzati e ascoltali su [!DNL Experience Platform Tags]. Utilizzare il payload per impostare gli elementi dati e le variabili Analytics nei Tag. Questo metodo è considerato la best practice, in quanto questa necessità è generalmente prevalente per le applicazioni a pagina singola. Gli esempi seguenti utilizzano il metodo con eventi personalizzati.

**Esempi:** [in questo](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it) documento della Guida trovi i link ai siti basati su applicazioni a pagina singola di esempio in cui è implementato [!DNL Analytics] e altre soluzioni di Experience Cloud. In questi esempi vengono utilizzati i seguenti eventi personalizzati:

* **[!DNL Event-view-start]**: eseguito all&#39;inizio della visualizzazione o dello stato che viene caricato.
* **[!DNL Event-view-end]**: eseguito quando si è verificata una modifica della visualizzazione o dello stato ed è stato completato il caricamento di tutti i componenti dell’applicazione a pagina singola. Questo è l’evento che in genere invia i dati ad Adobe Analytics.
* **[!DNL Event-action-trigger]**: eseguito quando si verifica un evento sulla pagina, ad eccezione del caricamento di una visualizzazione o di uno stato. Potrebbe trattarsi di un evento clic o di una modifica minore del contenuto, che non comporta una modifica della visualizzazione.

Per ulteriori informazioni su come e quando si attivano questi eventi, consulta le pagine e i documenti menzionati in precedenza. Non è necessario utilizzare gli stessi nomi di evento nell’implementazione. È essenziale comprendere il caso d’uso funzionale del metodo utilizzato come best practice consigliata per ciascuno di essi. Il seguente video mostra un esempio di pagina di un’applicazione a pagina singola e un codice di esempio in [!DNL Experience Platform Tags] per l’ascolto degli eventi personalizzati.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12&learn=on)

## Esecuzione di s.t() o s.tl() in [!DNL Experience Platform Tags] {#running-s-t-or-s-tl-in-the-launch-rule}

Un concetto importante da capire per [!DNL Analytics] quando si lavora con un’applicazione a pagina singola è la differenza tra `s.t()` e `s.tl()`. Il tuo codice attiva uno o più di questi metodi su [!DNL Experience Platform Tags] per inviare dati in [!DNL Analytics].

* **s.t()**: la “t” sta per “tracciamento” e rappresenta una visualizzazione pagina. Se la visualizzazione cambia abbastanza da *considerarla* una nuova “pagina”, utilizza questa chiamata. Imposta un valore univoco sulla variabile [!DNL s.pageName] e utilizza `s.t()` per inviare i dati in [!DNL Analytics].

* **s.tl()**: “tl“ sta per “collegamento traccia” e rappresenta un clic di collegamento o una piccola modifica del contenuto. Se la modifica della visualizzazione è minima, utilizza `s.tl()` per trasmettere un valore univoco sull’interazione a [!DNL Analytics]. Questa variabile passata non è [!DNL s.pageName], poiché viene ignorata in Analytics quando vengono ricevute le chiamate `s.tl()`.

**SUGGERIMENTO:** come linea guida generale, se la schermata cambia di oltre il 50%, è necessario utilizzare la chiamata alla visualizzazione della pagina di `s.t()`. In caso contrario, utilizza `s.tl()`. Tuttavia, effettua una valutazione quando consideri le azioni che costituiscono una nuova “pagina” e come dovrebbero essere presentate nei rapporti di Adobe Analytics.

Il video seguente mostra dove e come attivare `s.t()` o `s.tl()` nei Tag.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12&learn=on)

## Cancella variabili {#clear-variables}

Invia i dati corretti a [!DNL Analytics] al momento giusto. In un ambiente di applicazioni a pagina singola, un valore archiviato in una variabile di [!DNL Analytics] persiste e viene inviato nuovamente in [!DNL Analytics], anche se magari non serve più. Nell’estensione [!DNL Tags] di [!DNL Analytics] esiste una funzione per cancellare le variabili in modo che la chiamata successiva non invii erroneamente i dati in [!DNL Analytics].

Il diagramma precedente mostra le variabili eliminate *dopo* l’invio dei dati. In realtà, questo può accadere prima O dopo la chiamata, tuttavia, cerca di essere coerente nelle regole [!DNL Experience Platform Tags] per un’implementazione più pulita. Se cancelli le variabili *prima* di eseguire `s.t()`, imposta le nuove variabili immediatamente dopo la chiamata, quindi procedi all’invio dei nuovi dati in [!DNL Analytics].

**NOTA:** la cancellazione delle variabili non è sempre necessaria quando si esegue `s.tl()`. Questa chiamata richiede l’utilizzo della variabile [!DNL linkTrackVars] per istruire [!DNL Analytics] su quali variabili impostare. Questo in [!DNL Experience Platform Tags] avviene automaticamente attraverso la configurazione. Impedisce l’impostazione di variabili erranti a differenza del comportamento con le chiamate `s.t()` in un ambiente di applicazioni a pagina singola. Per garantire un’implementazione più pulita e affidabile, è probabile che in un ambiente di applicazioni a pagina singola sia più facile utilizzare la funzione per cancellare le variabili in entrambe le chiamate.

Il video seguente mostra dove e come cancellare le variabili in [!DNL Tags].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12&learn=on)

## Considerazioni aggiuntive {#additional-considerations}

### Finestre per codice personalizzato in [!DNL Experience Platform Tags] {#custom-code-windows-in-tags}

Nell’estensione [!DNL Analytics] di [!DNL Tags], puoi inserire codice personalizzato in due luoghi: nella sezione “[!UICONTROL library management]” e nella sezione “[!UICONTROL Configure tracker using custom code]”.

![Finestre per codice personalizzato di Analytics per Tag](assets/launch_analyticscustomcodewindows.png)

Una di queste posizioni esegue il codice che contiene una sola volta per il caricamento iniziale della pagina di applicazioni a pagina singola. Se il codice deve essere eseguito su una visualizzazione o su una modifica dell’azione, implementalo nella giusta **[!UICONTROL rule]** (ad esempio, la regola “caricamento della pagina: event-view-end”), per garantire che il codice venga eseguito ogni volta che si esegue la [!UICONTROL rule]. Quando crei tale azione nella [!UICONTROL rule], imposta *Extension = Core* e *Action Type = Custom Code*.

### Siti ibridi regolari e con applicazione a pagina singola {#hybrid-spa-and-traditional-sites}

Alcuni siti sono composti da una combinazione di pagine regolari e pagine da applicazioni a pagina singola. In questa istanza, è necessario utilizzare una strategia che funzioni per entrambi i tipi di pagina. Quando configuri gli eventi personalizzati sul sito e attivi le regole in [!DNL Experience Platform Tags], assicurati che i doppi hit non vengano inviati in [!DNL Analytics] in base a modifiche di hash e così via. In questo caso, è necessario eliminare una delle visualizzazioni di pagina affinché non trametta dati duplicati ad Adobe Analytics.

Se decidi di separare la funzionalità in un’unica [!UICONTROL rules] per un maggiore controllo, ricorda di documentarne l&#39;esecuzione. Se modifichi una [!UICONTROL rule], effettua la stessa modifica nell’altra [!UICONTROL rule].

### Integrazione con [!DNL Target] utilizzando A4T {#integration-with-target-using-a4t}

Durante l’integrazione con [!DNL Target] utilizzando A4T, verifica che le richieste [!DNL Target] e [!DNL Analytics] inviate sulla stessa visualizzazione o azione trasmettano lo stesso valore del parametro SDID. In questo modo i dati verranno sincronizzati correttamente nel backend.

Per visualizzare gli hit, utilizza uno strumento di debug o di monitoraggio dei pacchetti. A questo scopo, Adobe fornisce Experience Platform Debugger. Si tratta di un’estensione di Chrome che può essere [scaricata qui](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob?hl=it). [!DNL Target] deve essere eseguito per primo sulla pagina. Questo può essere verificato anche nel debugger.

## Risorse aggiuntive {#additional-resources}

* [Discussione su applicazioni a pagina singola nei forum Adobe](https://experienceleaguecommunities.adobe.com:443/t5/adobe-experience-platform-launch/best-practices-for-single-page-apps/m-p/267940)
* [Architettura di riferimento per mostrare come implementare applicazioni a pagina singola in Experience Platform Launch](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html?lang=it)
