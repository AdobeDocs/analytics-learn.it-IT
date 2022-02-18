---
title: 'Best practice per il monitoraggio delle applicazioni a pagina singola (SPA) in Adobe Analytics '
description: In questo documento verranno descritte alcune best practice da seguire e di cui tenere conto quando utilizzi Adobe Analytics per monitorare le applicazioni a pagina singola (SPA). Questo documento si concentrerà sull’utilizzo di Experience Platform Launch, che è il metodo di implementazione consigliato.
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
source-git-commit: 32424f3f2b05952fe4df9ea91dcbe51684cee905
workflow-type: ht
source-wordcount: '1639'
ht-degree: 100%

---

# Best practice per il monitoraggio delle applicazioni a pagina singola (SPA) in Adobe Analytics {#using-best-practices-when-tracking-spa-in-adobe-analytics}

In questo documento verranno descritte alcune best practice da seguire e di cui tenere conto quando utilizzi Adobe Analytics per monitorare le applicazioni a pagina singola (SPA). Questo documento si concentrerà sull’utilizzo di Adobe [!DNL Experience Platform Launch], che è il metodo di implementazione consigliato.

NOTE INIZIALI:

* Gli elementi riportati di seguito presuppongono l’uso di [!DNL Experience Platform Launch] per l’implementazione sul sito. Le considerazioni sono valide anche se non utilizzi [!DNL Experience Platform Launch], ma dovrai adattarle al tuo metodo di implementazione.
* Tutte le applicazioni a pagina singola sono diverse, quindi potrebbe essere necessario modificare alcuni dei seguenti elementi per soddisfare al meglio le tue esigenze. Abbiamo comunque voluto raccogliere alcune best practice che riguardano aspetti da tenere presenti quando si implementa Adobe Analytics nelle pagine di applicazioni a pagina singola.

## Diagramma semplice dell’uso delle applicazioni a pagina singola in [!DNL Experience Platform Launch] {#simple-diagram-of-working-with-spas-in-launch}

![applicazioni a pagina singola per analytics in launch](assets/spa_for_analyticsinlaunch.png)

**NOTA:** come indicato, si tratta di un diagramma semplificato del modo in cui le pagine di applicazioni a pagina singola vengono gestite in un’implementazione di Adobe Analytics utilizzando [!DNL Experience Platform Launch]. Nelle seguenti sezioni di questa pagina, vengono trattati i passaggi ed eventuali problemi che dovresti considerare attentamente o su cui potresti dover intervenire.

## Impostazione del livello dati {#setting-the-data-layer}

Quando si caricano nuovi contenuti o si esegue un’azione sulla pagina di un’applicazione a pagina singola, una delle prime operazioni da eseguire è aggiornare il livello dati. Questo deve accadere PRIMA che l’evento personalizzato si avvii e attivi regole in [!DNL Experience Platform Launch], affinché [!DNL Experience Platform Launch] possa raccogliere i nuovi valori dal livello dati e inviarli in Adobe Analytics.

Di seguito è riportato un livello dati di esempio, i cui elementi possono essere modificati in seguito a una modifica della visualizzazione o a un’azione nell’applicazione a pagina singola. Ad esempio, per una modifica che coinvolge tutta la schermata o quasi, può essere opportuno modificare un elemento “[!DNL pageName]” in modo che il nuovo elemento possa essere acquisito in [!DNL Experience Platform Launch] e inviato ad Adobe Analytics.

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

## Impostazione di eventi personalizzati e ascolto in [!DNL Experience Platform Launch] {#setting-custom-events-and-listening-in-launch}

Quando un nuovo contenuto viene caricato sulla pagina o quando si verifica un’azione sul sito, è necessario informare [!DNL Experience Platform Launch] affinché possa eseguire una regola e inviare i dati a [!DNL Analytics]. Esistono due modi diversi per farlo: tramite [!UICONTROL rules] [!UICONTROL Direct Call] o Eventi personalizzati.

*  [!UICONTROL Rules] [!UICONTROL Direct Call]: in [!DNL Experience Platform Launch] puoi impostare una [!UICONTROL rule] [!UICONTROL direct call] che viene eseguita quando viene chiamata direttamente dalla pagina. Se il caricamento della pagina o l’azione sul sito è molto semplice o se è univoco e può eseguire ogni volta un set di istruzioni specifico (imposta [!DNL eVar4] su X e attiva [!DNL event2] ogni volta), puoi utilizzare una [!UICONTROL rule] [!UICONTROL direct call]. Vedi la documentazione di [!DNL Experience Platform Launch] relativa alla creazione di [!UICONTROL rules] [!UICONTROL direct call].
* Eventi personalizzati: per ulteriori funzionalità e per la possibilità di allegare dinamicamente un payload con valori diversi, è necessario impostare eventi JavaScript personalizzati e ascoltarli in [!DNL Experience Platform Launch], dove puoi utilizzare il payload per impostare le variabili e inviare i dati ad Adobe Analytics. È più probabile che questa funzionalità sia necessaria, quindi questa opzione è considerata la best practice. Tuttavia, il metodo più appropriato dipende dalle funzioni specifiche del tuo sito. Per questo documento, si partirà dal presupposto che sia necessario utilizzare questo metodo con eventi personalizzati.

**Esempi:** in [QUESTO](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html?lang=it) documento dell’Aiuto trovi i link a siti basati su applicazioni a pagina singola di esempio in cui è implementato [!DNL Analytics] (oltre ad altre soluzioni Experience Cloud), nonché i documenti che descrivono ciò che è stato implementato. In questi esempi di applicazioni a pagina singola sono stati utilizzati i seguenti eventi personalizzati:

* [!DNL event-view-start]: questo evento deve essere attivato all’inizio della visualizzazione o dello stato che si sta caricando.
* [!DNL event-view-end]: questo evento deve essere attivato anche quando si è verificata una modifica della visualizzazione o dello stato ed è stato completato il caricamento di tutti i componenti dell’applicazione a pagina singola. Questo è l’evento che in genere attiva una chiamata ad Adobe Analytics.
* [!DNL event-action-trigger]: questo evento deve essere attivato quando si verifica un evento sulla pagina, ad eccezione del caricamento di una visualizzazione o uno stato. Potrebbe trattarsi di un evento clic o di una modifica minore del contenuto, che non comporta una modifica della visualizzazione.

Per ulteriori informazioni su come/quando vengono attivati, consulta le pagine o i documenti menzionati sopra. Non è necessario utilizzare gli stessi nomi di evento, ma la funzionalità indicata qui è la best practice consigliata. Il video seguente mostra un sito di esempio e la posizione in [!DNL Experience Platform Launch] per l’ascolto degli eventi personalizzati.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12)

## Esecuzione di s.t() o s.tl() nella [!UICONTROL Rule] di [!DNL Experience Platform Launch] {#running-s-t-or-s-tl-in-the-launch-rule}

Una delle cose più importanti da capire per [!DNL Analytics] quando si lavora con un’applicazione a pagina singola è la differenza tra `s.t()` e `s.tl()`. Verrà attivato uno di questi metodi in [!DNL Experience Platform Launch] per inviare dati in [!DNL Analytics], ma è importante sapere quando inviarli.

* **s.t()** - La “t” sta per “track” ed è una normale visualizzazione pagina. Anche se l’URL non cambia, la visualizzazione è sufficientemente diversa da poter essere *considerata* come una nuova “pagina”? In tal caso, imposta la variabile s.[!DNL pageName] e utilizza `s.t()` per inviare la chiamata a [!DNL Analytics]

* **s.tl()** - “tl” sta per “track link” e viene normalmente utilizzato per monitorare i clic o le piccole modifiche al contenuto della pagina, anziché una modifica che interessa l’intera schermata. Se la modifica sulla pagina è piccola, tale da non essere considerata come una nuova “pagina” completa, utilizza `s.tl()` e non preoccuparti di impostare la variabile s.pageName poiché [!DNL Analytics] la ignorerà.

**SUGGERIMENTO:** una linea guida generale seguita da alcuni utenti prevede che, se la schermata cambia di oltre il 50%, deve essere trattata come una visualizzazione pagina e richiede quindi l’utilizzo di `s.t()`. Se la modifica della schermata è inferiore al 50%, si utilizza invece `s.tl()`. Tuttavia, dipende interamente da te, da cosa consideri una nuova “pagina” e come desideri eseguire il tracciamento nel tuo sito in Adobe Analytics.

Il video seguente mostra dove e come attivare `s.t()` o `s.tl()` in Experience Platform Launch.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12)

## Cancellazione delle variabili {#clearing-variables}

Quando esegui il tracciamento nel tuo sito con Adobe Analytics, vorrai ovviamente inviare ad [!DNL Analytics] solo i dati giusti al momento giusto. In un ambiente con applicazioni a pagina singola, un valore tracciato in una variabile di [!DNL Analytics] può persistere ed essere inviato nuovamente in [!DNL Analytics], anche se magari non serve più. Per questo motivo, nell’estensione [!DNL Analytics] di [!DNL Launch] esiste una funzione che consente di cancellare le variabili, in modo da ricominciare da zero quando si esegue la richiesta di immagine successiva e si inviano i dati ad [!DNL Analytics].

Nel diagramma precedente, è riportata alla fine del processo affinché le variabili vengono cancellate *dopo* che l’invio dell’hit. In realtà può essere eseguita prima o dopo l’invio dell’hit, purché sia coerente nelle regole di [!DNL Experience Platform Launch]: la cancellazione dovrà avvenire sempre prima o sempre dopo l’impostazione e l’invio delle variabili. Se vuoi cancellare le variabili *prima* di eseguire `s.t()`, assicurati di cancellare prima le variabili, quindi imposta le nuove variabili e infine invia i nuovi dati ad [!DNL Analytics].

**NOTA:** la cancellazione delle variabili non è sempre necessaria quando si esegue `s.tl()` perché `s.tl()` richiede anche l’utilizzo della variabile [!DNL linkTrackVars] ogni volta per indicare ad [!DNL Analytics] quali variabili verranno impostate (aggiunte automaticamente dietro le quinte in [!DNL Experience Platform Launch]). Pertanto, le variabili erranti di solito non vengono incluse quando si utilizza `s.tl()`, ma è molto consigliato che lo siano se si utilizza `s.t()` in un ambiente con applicazioni a pagina singola. Detto questo, è consigliabile adottare come best practice l’utilizzo della funzione di cancellazione delle variabili sia per `s.t()` che per `s.tl()` in un ambiente per applicazioni a pagina singola, per garantire una raccolta di dati di qualità.

Il video seguente mostra dove e come cancellare le variabili in [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12)

## Considerazioni aggiuntive {#additional-considerations}

### Finestre per codice personalizzato in [!DNL Experience Platform Launch] {#custom-code-windows-in-launch}

Nell’estensione [!DNL Analytics] di [!DNL Launch] puoi inserire codice personalizzato in due luoghi: nella sezione [!UICONTROL library management] e nella sezione aggiuntiva “[!UICONTROL Configure Tracker Using Custom Code]”.

![Finestre per codice personalizzato di Analytics per Launch](assets/launch_analyticscustomcodewindows.png)

È importante sapere che in entrambe queste posizioni il codice verrà eseguito solo una volta, quando il caricamento iniziale della pagina avviene sulla pagina dell’applicazione a pagina singola. Se il codice deve essere eseguito quando cambia la visualizzazione o quando si esegue una specifica azione sul sito, devi aggiungere un’ulteriore azione alla **[!UICONTROL rule]** appropriata (ad esempio, nella [!UICONTROL rule] “page load: event-view-end”), in modo che il codice venga eseguito ogni volta che viene eseguita tale [!UICONTROL rule]. Quando crei tale azione nella [!UICONTROL rule], imposta *Extension = Core* e *Action Type = Custom Code*.

### Siti ibridi regolari e con applicazione a pagina singola {#hybrid-spa-regular-sites}

Alcuni siti contengono una combinazione di pagine “regolari” e pagine da applicazioni a pagina singola. In tali situazioni, dovrai utilizzare una strategia che funzioni per entrambi i tipi di pagina. Quando configuri gli eventi personalizzati sul sito e attivi le regole in [!DNL Experience Platform Launch], fai attenzione a che non finiscano doppi hit in [!DNL Analytics] dalla pagina, in base a modifiche hash, ecc. (se è così che hai scelto di attivare la regola [!DNL Experience Platform Launch]). In questo caso, dovrai eliminare una delle visualizzazioni di pagina affinché non fornisca dati errati ad Adobe Analytics.

Se decidi di suddividere la funzionalità in [!UICONTROL rules] separate in modo da avere più controllo su di essa, assicurati di ricordare/documentare questa operazione: così le modifiche apportate a una [!UICONTROL rule] potranno essere apportate anche all’altra [!UICONTROL rule], per proteggere l’integrità dei dati di [!DNL Analytics].

### Integrazione con [!DNL Target] tramite A4T {#integration-with-target-via-a4t}

Solo un rapido callout. Se esegui l’integrazione con [!DNL Target] tramite A4T, assicurati che la richiesta di [!DNL Target] e quella di [!DNL Analytics] per lo stesso cambiamento di visualizzazione abbiano lo stesso SDID. In questo modo i dati verranno sincronizzati correttamente tra le due soluzioni.

Per visualizzare gli hit, utilizza un programma di debug o packet sniffing. Puoi anche utilizzare Experience Cloud Debugger, un’estensione per Chrome che puoi scaricare [QUI](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). [!DNL Target] deve essere attivato prima sulla pagina, e puoi verificare anche questo nella console JavaScript o nel debugger.

## Risorse aggiuntive {#additional-resources}

* [Discussione su applicazioni a pagina singola nei forum Adobe](https://forums.adobe.com/thread/2451022)
* [Architettura di riferimento per mostrare come implementare applicazioni a pagina singola in Experience Platform Launch](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html?lang=it)
