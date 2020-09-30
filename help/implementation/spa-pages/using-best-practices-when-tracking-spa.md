---
title: 'Utilizzo delle procedure ottimali per il tracciamento delle applicazioni a pagina singola (SPA) in  Adobe Analytics '
description: In questo documento verranno descritte le best practice da seguire e di cui sei a conoscenza quando utilizzi  Adobe Analytics per monitorare le applicazioni Single Page (SPA). Questo documento si concentrerà sull'utilizzo di Experience Platform Launch, che è il metodo di implementazione consigliato.
feature: implementation basics
topics: spa
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1389
translation-type: tm+mt
source-git-commit: 548ac75589383dfd4da4ae02412de91a0a3b28d6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Utilizzo delle procedure ottimali per il tracciamento delle applicazioni a pagina singola (SPA) in  Adobe Analytics {#using-best-practices-when-tracking-spa-in-adobe-analytics}

In questo documento verranno descritte le best practice da seguire e di cui sei a conoscenza quando utilizzi  Adobe Analytics per monitorare le applicazioni Single Page (SPA). Questo documento si concentrerà sull&#39;utilizzo  Adobe [!DNL Experience Platform Launch], che è il metodo di implementazione consigliato.

NOTE INIZIALI:

* Gli elementi seguenti presupporranno che si stia utilizzando [!DNL Experience Platform Launch] per implementare sul sito. Se non utilizzi [!DNL Experience Platform Launch]le considerazioni, devi adattarle al metodo di implementazione.
* Tutti gli SPA sono diversi, quindi potrebbe essere necessario modificare alcuni dei seguenti elementi per soddisfare al meglio le vostre esigenze, ma abbiamo voluto condividere con voi alcune best practice; cose a cui devi pensare quando stai implementando  Adobe Analytics sulle pagine SPA.

## Diagramma semplice dell&#39;utilizzo degli SPA in [!DNL Experience Platform Launch] {#simple-diagram-of-working-with-spas-in-launch}

![spa per l&#39;analisi all&#39;avvio](assets/spa_for_analyticsinlaunch.png)

**NOTA:** Come già detto, questo è un diagramma semplificato del modo in cui le pagine SPA vengono gestite in un&#39;implementazione Adobe Analytics  utilizzando [!DNL Experience Platform Launch]. Nelle seguenti sezioni di questa pagina, discuteremo i passaggi e tutti i problemi che dovresti considerare attentamente o su cui dovresti intervenire.

## Impostazione del livello dati {#setting-the-data-layer}

Quando un nuovo contenuto viene caricato su una pagina SPA, o quando un’azione viene eseguita su una pagina SPA, una delle prime operazioni da eseguire è aggiornare il livello dati. Questo deve avvenire PRIMA che l&#39;evento personalizzato attivi e attivi regole in [!DNL Experience Platform Launch], in modo che [!DNL Experience Platform Launch] possa acquisire i nuovi valori dal livello dati e spingerli in  Adobe Analytics.

Di seguito è riportato un livello di dati di esempio, i cui elementi potrebbero essere modificati in seguito a modifiche della visualizzazione o azioni dell&#39;SPA. Ad esempio, con una modifica a schermo intero/a maggioranza, sarebbe comune modificare un elemento &quot;[!DNL pageName]&quot;, in modo che il nuovo elemento possa essere acquisito [!DNL Experience Platform Launch] e inviato  Adobe Analytics.

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

Quando un nuovo contenuto viene caricato sulla pagina o quando si verifica un&#39;azione sul sito, è necessario informare l&#39;utente [!DNL Experience Platform Launch] affinché possa eseguire una regola e inviare dati a [!DNL Analytics]. Esistono due modi diversi per farlo: [!UICONTROL Direct Call] [!UICONTROL rules] o Eventi personalizzati.

* [!UICONTROL Direct Call] [!UICONTROL Rules]: in [!DNL Experience Platform Launch], è possibile impostare un [!UICONTROL direct call] [!UICONTROL rule] che viene eseguito quando viene chiamato direttamente dalla pagina. Se il caricamento della pagina o l&#39;azione sul sito è molto semplice, o se è univoco e può eseguire un set di istruzioni specifico ogni volta (impostato [!DNL eVar4] su X e attivato [!DNL event2] ogni volta), è possibile utilizzare un [!UICONTROL direct call][!UICONTROL rule]. Consultate [!DNL Experience Platform Launch] la documentazione relativa alla creazione [!UICONTROL direct call] . [!UICONTROL rules]
* Eventi personalizzati: Per ulteriori funzionalità e per la possibilità di allegare dinamicamente un payload con valori diversi, è necessario impostare eventi JavaScript personalizzati e ascoltarli in [!DNL Experience Platform Launch], dove è possibile utilizzare il payload per impostare le variabili e inviare i dati a  Adobe Analytics. È più probabile che vi serva questa funzionalità, quindi questa opzione è considerata la best practice. Tuttavia, ogni funzione sul sito può determinare quale sarà il metodo più appropriato. In questo documento si procederà partendo dal presupposto che sarà necessario utilizzare questo metodo di eventi personalizzato.

**Esempi:** In [QUESTO](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html) documento di aiuto, sono presenti collegamenti a siti SPA di esempio che hanno implementato [!DNL Analytics] (e altre soluzioni  Experience Cloud), nonché documenti che descrivono ciò che è stato implementato. In questi esempi SPA, sono stati utilizzati i seguenti eventi personalizzati:

* [!DNL event-view-start]: Questo evento deve essere attivato all’inizio della visualizzazione o dello stato che si sta caricando.
* [!DNL event-view-end]: Questo evento deve essere attivato anche quando si è verificata una modifica di visualizzazione/stato e il caricamento di tutti i componenti SPA sulla pagina è terminato. Si tratta dell&#39;evento che in genere attiva una chiamata in  Adobe Analytics.
* [!DNL event-action-trigger]: Questo evento deve essere attivato quando si verifica un evento sulla pagina tranne il caricamento di visualizzazione/stato. Potrebbe trattarsi di un evento clic o di una modifica di contenuto minore senza una modifica della visualizzazione.

Per ulteriori informazioni su come/quando vengono avviate, vedere i documenti/pagine di riferimento riportati sopra. Non è necessario utilizzare gli stessi nomi evento, ma è consigliabile seguire le procedure ottimali per la funzionalità indicata di seguito. Nel video seguente viene mostrato un sito di esempio e dove [!DNL Experience Platform Launch] ascoltare gli eventi personalizzati.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12)

## Esecuzione di s.t() o s.tl() nella variabile [!DNL Experience Platform Launch] [!UICONTROL Rule] {#running-s-t-or-s-tl-in-the-launch-rule}

Una delle cose più importanti per [!DNL Analytics] lavorare con uno SPA è la differenza tra `s.t()` e `s.tl()`. Uno di questi metodi verrà attivato [!DNL Experience Platform Launch] per inviare dati a [!DNL Analytics], ma è necessario sapere quando inviarli a ciascuno.

* **s.t()** - &quot;t&quot; significa &quot;track&quot; ed è una visualizzazione di pagina normale. Anche se l’URL non può essere modificato, la visualizzazione cambia abbastanza da *considerarlo* una nuova &quot;pagina&quot;? In tal caso, impostare s.[!DNL pageName] e utilizzate `s.t()` per inviare la chiamata a [!DNL Analytics]

* **s.tl()** - &quot;tl&quot; sta per &quot;track link&quot; (tracciamento collegamento) e viene normalmente utilizzato per monitorare i clic o le piccole modifiche di contenuto sulla pagina, invece di una modifica a schermo intero. Se la modifica sulla pagina è piccola, in modo da non considerarla una nuova &quot;pagina&quot; completa, utilizzate `s.tl()` e non preoccupatevi di impostare la variabile s.pageName, come [!DNL Analytics] verrà ignorata.

**SUGGERIMENTO:** Alcune persone utilizzano una linea guida generale che, se la schermata cambia più del 50%, dovrebbe essere considerata una visualizzazione di pagina e utilizzata `s.t()`. Se è inferiore al 50%, modificare lo schermo, utilizzare `s.tl()`. Tuttavia, dipende totalmente da voi e ciò che considerate una nuova &quot;pagina&quot; e come vorreste monitorare il vostro sito in  Adobe Analytics.

Il seguente video mostra dove/come attivare `s.t()` o `s.tl()` in Launch by Adobe.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12)

## Cancellazione delle variabili {#clearing-variables}

Quando monitori il tuo sito con  Adobe Analytics, naturalmente vuoi solo inviare i dati giusti in [!DNL Analytics] al momento giusto. In un ambiente SPA, un valore tracciato in una [!DNL Analytics] variabile può persistere ed essere inviato nuovamente [!DNL Analytics], potenzialmente quando non lo desideriamo più. Per questo motivo, nell’ [!DNL Analytics] estensione è presente una funzione per cancellare le variabili, in modo da ottenere una nuova ardesia quando si esegue la richiesta immagine successiva e si inviano dati in [!DNL Launch] [!DNL Analytics].

Nel diagramma qui sopra, è elencata alla fine del processo, cancellando le variabili *dopo* l’invio dell’hit. In realtà, può essere eseguito prima o dopo l’invio dell’hit, ma deve essere coerente nelle [!DNL Experience Platform Launch] regole, in modo da cancellare sempre le variabili prima o dopo l’impostazione e inviarle. Ricordare che se si desidera cancellare le variabili *prima* dell&#39;esecuzione `s.t()`, assicurarsi di cancellare prima le variabili, quindi impostare le nuove variabili e infine inviare i nuovi dati in [!DNL Analytics].

**NOTA:** La cancellazione delle variabili non è sempre necessaria quando viene eseguita `s.tl()`, perché `s.tl()` richiede l&#39;utilizzo della [!DNL linkTrackVars] variabile accanto a essa ogni volta per indicare [!DNL Analytics] quali variabili verranno impostate (aggiunta automaticamente dietro le quinte di [!DNL Experience Platform Launch]). Ciò significa che le variabili erranti di solito non vengono incluse quando si utilizzano `s.tl()`, ma è molto consigliato quando si utilizzano `s.t()` in un ambiente SPA. Detto questo, vorrei raccomandare come procedura ottimale di utilizzare la funzione Clear Variables sia per `s.t()` che `s.tl()` in un ambiente SPA, solo per garantire la raccolta di dati di qualità.

Il seguente video mostra dove/come cancellare le variabili in [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12)

## Considerazioni aggiuntive {#additional-considerations}

### Finestra del codice personalizzato in [!DNL Experience Platform Launch] {#custom-code-windows-in-launch}

Nell&#39; [!DNL Launch] [!DNL Analytics] estensione sono disponibili due posizioni in cui è possibile inserire il codice personalizzato: La [!UICONTROL library management] sezione e la sezione &quot;[!UICONTROL Configure Tracker Using Custom Code]&quot; supplementare.

![Avvia le finestre dei codici personalizzati di Analytics](assets/launch_analyticscustomcodewindows.png)

È importante sapere che una di queste posizioni eseguirà il codice solo una volta, quando il caricamento iniziale della pagina avviene sulla pagina SPA. Se è necessario che il codice venga eseguito su una modifica di visualizzazione o su un’azione del sito, è necessario aggiungere un’azione aggiuntiva al codice appropriato **[!UICONTROL rule]** (ad esempio, nel &quot;caricamento della pagina: event-view-end&quot; [!UICONTROL rule]), in modo che il codice venga eseguito ogni volta che viene [!UICONTROL rule] eseguito. Quando create tale azione in [!UICONTROL rule], impostate *Estensione = Core* e Tipo *azione = Codice* personalizzato.

### Siti &quot;ibridi&quot; SPA/Siti regolari {#hybrid-spa-regular-sites}

Alcuni siti sono una combinazione di pagine &quot;regolari&quot; e pagine SPA. In questo caso, dovrete utilizzare una strategia che funzioni per entrambi i tipi di pagina. Durante la configurazione degli eventi personalizzati sul sito e l&#39;attivazione delle regole in [!DNL Experience Platform Launch], prestate attenzione a non introdurre doppi hit [!DNL Analytics] dalla pagina, in base a modifiche hash e così via. (se è così che avete scelto di attivare la [!DNL Experience Platform Launch] regola). In questo caso, è necessario sopprimere una delle visualizzazioni di pagina in modo che non fornisca dati errati in  Adobe Analytics.

Se decidi di suddividere la funzionalità in un&#39;altra [!UICONTROL rules] in modo da avere maggiore controllo su di essa, ricordati di aver fatto questo, in modo che [!UICONTROL rule] possano essere apportate modifiche a una delle due [!UICONTROL rule] anche, proteggendo l&#39;integrità [!DNL Analytics] dei dati.

### Integrazione con [!DNL Target] via A4T {#integration-with-target-via-a4t}

Solo un breve richiamo qui. Se esegui l’integrazione con [!DNL Target] A4T, accertati che la [!DNL Target] richiesta e la [!DNL Analytics] richiesta nella stessa modifica di visualizzazione abbiano lo stesso SDID. In questo modo i dati verranno sincronizzati correttamente sulle soluzioni.

Per visualizzare gli hit, usa un programma debugger o packet sniffer. Potete anche utilizzare l&#39;Experience Cloud Debugger, un&#39;estensione Chrome che può essere scaricata [QUI](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). [!DNL Target] deve essere attivato per primo sulla pagina, in modo da poter verificare tale comportamento anche nella console JavaScript o nel debugger.

## Risorse aggiuntive {#additional-resources}

* [Discussione SPA sui forum dei Adobi](https://forums.adobe.com/thread/2451022)
* [Siti di architettura di riferimento per mostrare come implementare SPA nel Experience Platform Launch](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html)