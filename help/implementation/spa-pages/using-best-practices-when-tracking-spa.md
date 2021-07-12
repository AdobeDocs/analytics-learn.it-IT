---
title: 'Utilizzo delle best practice per il tracciamento delle applicazioni a pagina singola (SPA) in Adobe Analytics '
description: In questo documento verranno descritte diverse best practice da seguire e di cui tenere conto quando utilizzi Adobe Analytics per monitorare le applicazioni a pagina singola (SPA). Questo documento si concentrerà sull'utilizzo di Experience Platform Launch, che è il metodo di implementazione consigliato.
feature: Nozioni di base sull’implementazione
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
workflow-type: tm+mt
source-wordcount: '1642'
ht-degree: 0%

---

# Utilizzo delle best practice per il tracciamento delle applicazioni a pagina singola (SPA) in Adobe Analytics {#using-best-practices-when-tracking-spa-in-adobe-analytics}

In questo documento verranno descritte diverse best practice da seguire e di cui tenere conto quando utilizzi Adobe Analytics per monitorare le applicazioni a pagina singola (SPA). Questo documento si concentrerà sull&#39;utilizzo dell&#39;Adobe [!DNL Experience Platform Launch], che è il metodo di implementazione consigliato.

NOTE INIZIALI:

* Gli elementi seguenti presupporranno l&#39;utilizzo di [!DNL Experience Platform Launch] per l&#39;implementazione sul sito. Le considerazioni esistono ancora se non utilizzi [!DNL Experience Platform Launch], ma dovrai adattarle al metodo di implementazione.
* Tutte le SPA sono diverse, quindi potrebbe essere necessario modificare alcuni dei seguenti elementi per soddisfare al meglio le tue esigenze, ma abbiamo voluto condividere alcune best practice con te; cose a cui devi pensare durante l’implementazione di Adobe Analytics sulle pagine SPA.

## Diagramma semplice del lavoro con SPA in [!DNL Experience Platform Launch] {#simple-diagram-of-working-with-spas-in-launch}

![spa per analytics in launch](assets/spa_for_analyticsinlaunch.png)

**NOTA:** come indicato, si tratta di un diagramma semplificato per la gestione delle pagine SPA in un’implementazione Adobe Analytics utilizzando  [!DNL Experience Platform Launch]. Nelle seguenti sezioni di questa pagina, discuteremo i passaggi e tutti i problemi che dovresti considerare attentamente o su cui devi agire.

## Impostazione del livello dati {#setting-the-data-layer}

Quando un nuovo contenuto viene caricato su una pagina SPA o quando un’azione viene eseguita su una pagina SPA, una delle prime operazioni da eseguire è aggiornare il livello dati. Questo deve accadere PRIMA che l&#39;evento personalizzato attivi e attivi regole in [!DNL Experience Platform Launch], in modo che [!DNL Experience Platform Launch] possa raccogliere i nuovi valori dal livello dati e inviarli in Adobe Analytics.

Di seguito è riportato un livello di dati di esempio, i cui elementi possono essere modificati in seguito a una modifica della visualizzazione o a un’azione sul SPA. Ad esempio, in caso di modifica a schermo intero/a maggioranza, è comune modificare un elemento &quot;[!DNL pageName]&quot; in modo che il nuovo possa essere acquisito in [!DNL Experience Platform Launch] e inviato in Adobe Analytics.

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

Quando un nuovo contenuto viene caricato sulla pagina o quando si verifica un&#39;azione sul sito, è necessario informare [!DNL Experience Platform Launch] in modo che possa eseguire una regola e inviare dati a [!DNL Analytics]. Ci sono un paio di modi diversi per farlo: [!UICONTROL Direct Call] [!UICONTROL rules] o Eventi personalizzati.

* [!UICONTROL Direct Call] [!UICONTROL Rules]: in  [!DNL Experience Platform Launch], puoi impostare un  [!UICONTROL direct call] [!UICONTROL rule] che viene eseguito quando viene chiamato direttamente dalla pagina. Se il caricamento della pagina o l&#39;azione sul sito è molto semplice o se è univoco e può eseguire un set specifico di istruzioni ogni volta (impostare [!DNL eVar4] su X e attivare [!DNL event2] ogni volta), puoi utilizzare un [!UICONTROL direct call] [!UICONTROL rule]. Consulta la documentazione [!DNL Experience Platform Launch] relativa alla creazione di [!UICONTROL direct call] [!UICONTROL rules] .
* Eventi personalizzati: Per ulteriori funzionalità e per la possibilità di allegare dinamicamente un payload con valori diversi, è necessario impostare eventi JavaScript personalizzati e ascoltarli in [!DNL Experience Platform Launch], dove è possibile utilizzare il payload per impostare le variabili e inviare i dati in Adobe Analytics. È più probabile che questa funzionalità sia necessaria, quindi questa opzione è considerata la best practice. Tuttavia, ogni funzione sul sito può determinare quale sarà il metodo più appropriato. In questo documento si procederà partendo dal presupposto che sarà necessario utilizzare questo metodo di eventi personalizzati.

**Esempi:** nel documento  [](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html) ThisHelp sono presenti collegamenti a siti di SPA di esempio che sono stati implementati  [!DNL Analytics] (e altre soluzioni Experience Cloud), nonché documenti che descrivono ciò che è stato implementato. In questi SPA esempi sono stati utilizzati i seguenti eventi personalizzati:

* [!DNL event-view-start]: Questo evento deve essere attivato all&#39;inizio della visualizzazione o dello stato che si sta caricando.
* [!DNL event-view-end]: Questo evento deve essere attivato anche quando si è verificata una modifica della visualizzazione o dello stato e il caricamento di tutti i componenti SPA sulla pagina è terminato. Questo è l’evento che in genere attiva una chiamata ad Adobe Analytics.
* [!DNL event-action-trigger]: Questo evento deve essere attivato quando si verifica un evento sulla pagina ad eccezione del caricamento visualizzazione/stato. Potrebbe trattarsi di un evento clic o di una modifica del contenuto più piccola senza una modifica della visualizzazione.

Per ulteriori informazioni su come/quando vengono attivate, consulta le pagine/documenti di cui sopra. Non è necessario utilizzare gli stessi nomi di evento, ma la funzionalità riportata di seguito è la best practice consigliata. Il video seguente mostra un sito di esempio e dove in [!DNL Experience Platform Launch] per ascoltare gli eventi personalizzati.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12)

## Esecuzione di s.t() o s.tl() in [!DNL Experience Platform Launch] [!UICONTROL Rule] {#running-s-t-or-s-tl-in-the-launch-rule}

Una delle cose più importanti da comprendere per [!DNL Analytics] quando si lavora con un SPA è la differenza tra `s.t()` e `s.tl()`. Verrà attivato uno di questi metodi in [!DNL Experience Platform Launch] per inviare dati a [!DNL Analytics], ma è necessario sapere quando inviarli.

* **s.t()**  - La &quot;t&quot; sta per &quot;track&quot; ed è una normale visualizzazione di pagina. Anche se l&#39;URL potrebbe non cambiare, la visualizzazione cambia abbastanza da *considerare* una nuova &quot;pagina&quot;? In tal caso, imposta la variabile s.[!DNL pageName] e utilizza `s.t()` per inviare la chiamata a [!DNL Analytics]

* **s.tl()**  - Il &quot;tl&quot; sta per &quot;tracciamento collegamento&quot; e viene normalmente utilizzato per tracciare clic o piccole modifiche di contenuto sulla pagina, invece di una modifica a schermo intero. Se la modifica sulla pagina è piccola, in modo da non considerarla una nuova &quot;pagina&quot; completa, utilizza `s.tl()` e non preoccuparti di impostare la variabile s.pageName, in quanto [!DNL Analytics] la ignorerà.

**SUGGERIMENTO:** alcune persone utilizzano una linea guida generale che indica che se la schermata cambia di oltre il 50%, deve essere considerata una visualizzazione di pagina e utilizzata  `s.t()`. Se la modifica allo schermo è inferiore al 50%, utilizza `s.tl()`. Tuttavia, dipende interamente da te e da cosa consideri una nuova &quot;pagina&quot; e come desideri monitorare il tuo sito in Adobe Analytics.

Il video seguente mostra dove/come attivare `s.t()` o `s.tl()` in Launch by Adobe.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12)

## Cancellazione delle variabili {#clearing-variables}

Quando monitori il tuo sito con Adobe Analytics, ovviamente desideri solo inviare i dati giusti in [!DNL Analytics] al momento giusto. In un ambiente SPA, un valore tracciato in una variabile [!DNL Analytics] può persistere e essere reinviato in [!DNL Analytics], potenzialmente quando non lo desideri più. Per questo motivo, esiste una funzione nell&#39;estensione [!DNL Analytics] [!DNL Launch] per cancellare le variabili, in modo da avere una nuova ardesia quando esegui la richiesta di immagine successiva e invii dati in [!DNL Analytics].

Nel diagramma precedente, lo abbiamo elencato alla fine del processo, cancellando le variabili *dopo* che invii l&#39;hit. In realtà può essere eseguito prima o dopo l’invio dell’hit, ma deve essere coerente nelle regole [!DNL Experience Platform Launch], in modo da cancellare sempre prima o dopo l’impostazione delle variabili e l’invio delle stesse. Ricorda che se vuoi cancellare le variabili *prima* esegui `s.t()`, assicurati di cancellare prima le variabili, quindi di impostare le nuove variabili e infine di inviare i nuovi dati in [!DNL Analytics].

**NOTA:** la cancellazione delle variabili non è sempre necessaria durante l’esecuzione  `s.tl()`, perché  `s.tl()` richiede l’utilizzo della  [!DNL linkTrackVars] variabile accanto a essa ogni volta per sapere  [!DNL Analytics] quali variabili saranno impostate (aggiunta automatica dietro le quinte in  [!DNL Experience Platform Launch]). Questo significa che le variabili erranti di solito non vengono incluse quando si utilizza `s.tl()`, ma è molto consigliato quando si utilizza `s.t()` in un ambiente SPA. Detto questo, vorrei raccomandare come best practice l&#39;utilizzo della funzione Clear Variables sia per `s.t()` che per `s.tl()` in un ambiente SPA, solo per garantire una raccolta di dati di qualità.

Il video seguente mostra dove/come cancellare le variabili in [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12)

## Considerazioni aggiuntive {#additional-considerations}

### Finestre del codice personalizzato in [!DNL Experience Platform Launch] {#custom-code-windows-in-launch}

Nell&#39;estensione [!DNL Launch] [!DNL Analytics] sono disponibili due posizioni in cui è possibile inserire codice personalizzato: La sezione [!UICONTROL library management] e la sezione &quot;[!UICONTROL Configure Tracker Using Custom Code]&quot; aggiuntiva.

![Finestra del codice personalizzato di Launch Analytics](assets/launch_analyticscustomcodewindows.png)

È importante sapere che una di queste posizioni eseguirà il codice solo una volta, quando il caricamento iniziale della pagina avviene sulla pagina SPA. Se hai bisogno che il codice venga eseguito su una modifica della visualizzazione o su un&#39;azione sul tuo sito, devi aggiungere un&#39;azione aggiuntiva alla **[!UICONTROL rule]** appropriata (ad esempio nel &quot;caricamento della pagina: event-view-end&quot; [!UICONTROL rule]), in modo che il codice venga eseguito ogni volta che [!UICONTROL rule] viene eseguito. Quando crei tale azione in [!UICONTROL rule], imposta *Estensione = Core* e *Tipo azione = Codice personalizzato*.

### Siti SPA/regolari &quot;ibridi&quot; {#hybrid-spa-regular-sites}

Alcuni siti sono una combinazione di pagine &quot;regolari&quot; e pagine SPA. In questo caso, dovrai utilizzare una strategia che funzioni per entrambi i tipi di pagina. Durante la configurazione degli eventi personalizzati sul sito e l’attivazione delle regole in [!DNL Experience Platform Launch], assicurati che non ci siano doppi hit che entrano in [!DNL Analytics] dalla pagina, in base a modifiche hash e così via. (in questo modo hai scelto di attivare la regola [!DNL Experience Platform Launch]). In questo caso, sarà necessario eliminare una delle visualizzazioni di pagina in modo che non fornisca dati errati in Adobe Analytics.

Se decidi di suddividere la funzionalità in [!UICONTROL rules] separate in modo da avere un maggiore controllo su di essa, ricorda/documenta di aver eseguito questa operazione, in modo che tutte le modifiche apportate a una [!UICONTROL rule] possano essere apportate anche all&#39;altra [!UICONTROL rule], proteggendo l&#39;integrità dei dati [!DNL Analytics].

### Integrazione con [!DNL Target] tramite A4T {#integration-with-target-via-a4t}

Solo un rapido callout. Se esegui l’integrazione con [!DNL Target] utilizzando A4T, assicurati che la richiesta [!DNL Target] e la richiesta [!DNL Analytics] sulla stessa modifica di visualizzazione abbiano lo stesso SDID. In questo modo i dati verranno sincronizzati correttamente sulle soluzioni.

Per visualizzare gli hit, utilizza un programma di debug o packet sniffer. Puoi anche utilizzare il Experience Cloud Debugger, un&#39;estensione Chrome che può essere scaricata [QUI](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). [!DNL Target] dovrebbe essere attivato per primo sulla pagina, in modo da poter controllare anche nella console JavaScript o nel debugger.

## Risorse aggiuntive {#additional-resources}

* [SPA discussione sui forum Adobi](https://forums.adobe.com/thread/2451022)
* [Siti dell’architettura di riferimento per mostrare come implementare SPA in Experience Platform Launch](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html)
