---
title: Differenze tra il generatore di segmenti e i segmenti rapidi in Analysis Workspace
description: I segmenti possono essere uno degli strumenti più potenti del tuo kit di analisi dei dati. Scopri le differenze tra l’utilizzo del generatore di segmenti e i segmenti rapidi in Analysis Workspace per migliorare l’efficienza.
feature: Segmentation
role: User
level: Beginner
doc-type: article
kt: KT-13118
exl-id: 144e71fd-8d42-4d20-b55e-3d81ad992a79
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 100%

---

# Differenze tra il generatore di segmenti e i segmenti rapidi in Analysis Workspace

I segmenti possono essere uno degli strumenti più potenti del tuo kit di analisi dei dati. Scopri le differenze tra l’utilizzo del generatore di segmenti e i segmenti rapidi in Analysis Workspace per migliorare l’efficienza.

>[!TIP]
>
> Fai clic sull’immagine nella parte inferiore della pagina per scaricare un utile promemoria su quando utilizzare ogni strumento in Analysis Workspace.

I segmenti possono essere uno degli strumenti più potenti del tuo kit di analisi dei dati. Quando desideri esaminare specifici gruppi di traffico, sezioni del sito o percorsi dei clienti, l’utilizzo dei segmenti può essere un ottimo modo per concentrare l’analisi su un particolare sottoinsieme di traffico per il sito. Provenendo da un ambiente di vendita al dettaglio, alcuni dei segmenti più utili che ho creato sono per diversi tipi di gruppi di clienti, ad esempio clienti nuovi o clienti esistenti, clienti con accesso a un account o ospiti e così via. Ma puoi anche crearli per diverse sezioni del sito, clienti che eseguono azioni specifiche o qualsiasi altra cosa ti venga in mente!

**Esistono due modi principali per generare i segmenti:**

* Utilizzo del generatore di segmenti nel menu dei componenti
* Utilizzo dei segmenti rapidi nella parte superiore di un pannello

Se generi il segmento utilizzando il generatore di segmenti, puoi salvarlo per riutilizzarlo in altri progetti. Questo è un ottimo modo per essere in grado di concentrarsi su specifici gruppi di clienti, ad esempio, le persone che visitano determinate sezioni del sito e poi fanno un acquisto. Se invece esegui un’analisi esplorativa e desideri testare diverse impostazioni dei segmenti, il generatore di segmenti rapidi può essere di grande aiuto. Diamo un’occhiata ad alcuni dei principali vantaggi di ogni metodo.

## Segmenti rapidi

Nella parte superiore di ciascun pannello, puoi fare clic sull’icona del segmento rapido (un funnel con il simbolo +) per aprire il generatore. In questo modo puoi generare un segmento a qualsiasi livello (hit, visita o visitatore) con un massimo di tre condizioni. Simile al generatore di segmenti principale, questo fornisce un’indicazione sul lato destro che segnala se il segmento sta restituendo dei dati e la percentuale della popolazione di traffico complessivo incluso nel segmento, anche se si tratta di una versione più semplificata rispetto alla visualizzazione completa del volume del segmento visualizzata nel generatore di segmenti. Quando si aggiunge più di una condizione, è possibile utilizzare gli operatori “and” e “or”. Purtroppo, non esiste un’opzione “then” per i segmenti rapidi, quindi in caso di necessità di segmenti sequenziali bisognerà utilizzare il generatore di segmenti completo. In un segmento rapido esiste anche un limite di un contenitore, poiché questo è progettato per essere utilizzato per segmenti di base che possono essere creati e modificati rapidamente. Quando un segmento rapido viene applicato o salvato in un pannello, non può più essere modificato all’interno di quest’ultimo.

Quando viene eseguita un’analisi esplorativa e si desidera testare diversi tipi di segmenti per vedere come reagiscono i diversi gruppi di clienti o come operano le diverse categorie, l’utilizzo di segmenti rapidi è molto più veloce dell’utilizzo del generatore di segmenti. Inoltre, questi segmenti sono disponibili solo nel progetto in cui sono stati creati, quindi se non forniscono i risultati desiderati, non è necessario preoccuparsi di eliminare il segmento salvato dall’elenco principale. Se dopo aver eseguito il test dei segmenti ci si accorge che questi potrebbero essere utili in altri progetti, è possibile sempre fare clic sul pulsante “apri generatore” per aprire il segmento nel generatore di segmenti completo e salvarlo come segmento regolare. Una volta eseguita tale operazione, tuttavia, non sarà più possibile modificarlo nel generatore di segmenti rapidi.

![Segmento rapido](assets/quick-segement.png)

## Generatore di segmenti

Per accedere al generatore di segmenti, fai clic sul simbolo + sopra l’elenco dei segmenti nel menu dei componenti a sinistra oppure fai clic sul menu a discesa dei componenti e seleziona “Crea segmento...” A differenza dei segmenti rapidi, questo menu contiene tutte le opzioni disponibili. Per aggiungere più condizioni, è possibile creare segmenti sequenziali utilizzando l’operatore “then”. I segmenti sequenziali consentono inoltre di utilizzare “logic group” come livello (invece di hit, visita o visitatore). Il generatore di segmenti consentirà anche di aggiungere una descrizione ai segmenti, che può fornire indicazioni su chi ha creato il segmento o su quale tipo di dati è stato creato per filtrare, o anche di aggiungere semplicemente dei “tag” al segmento per scopi organizzativi, opzioni entrambe impossibili nel generatore di segmenti rapidi.

L’utilizzo del generatore di segmenti è essenziale quando il segmento ha più di 3 condizioni, se è necessario l’utilizzo di contenitori o se si vogliono utilizzare i segmenti sequenziali. Il generatore di segmenti completo dispone di molte più opzioni per creare segmenti molto più complessi, che possono servire a suddividere diversi tipi di clienti, categorie, percorsi dei clienti e così via. Una volta creati e salvati, i segmenti vengono aggiunti all’elenco principale dei segmenti e possono quindi essere taggati, approvati, condivisi, utilizzati in più rapporti e pubblicati nell’Experience Cloud. La pubblicazione nell’Experience Cloud consente di utilizzare il segmento in altri prodotti Adobe, ad esempio in Adobe Target per il targeting della personalizzazione. I segmenti generati nel generatore di segmenti non possono essere modificati nel pannello dei segmenti rapidi, occorrerà aprire il generatore di segmenti per apportare eventuali modifiche. Fortunatamente, la visualizzazione in anteprima a destra fornisce un’analisi più dettagliata del traffico che il segmento porterebbe negli ultimi 90 giorni, il che significa che si può avere la certezza che il segmento inserisca ciò che si desidera prima di salvare.

![Generatore di segmenti](assets/segment-builder-quick.png)

## Casi di utilizzo

In diversi settori, gli utilizzi per la creazione di segmenti personalizzati possono variare. Lavorando per la divisione e-commerce di un grande rivenditore, spesso si eseguono analisi esplorative per determinare i percorsi di acquisto dei clienti. Quando vengono osservati picchi o cali di azioni come l’aggiunta di prodotti ai carrelli o l’invio di ordini, l’utilizzo dei segmenti rapidi può rivelarsi utile. Durante un’analisi è possibile creare rapidamente un segmento per un tipo specifico di cliente o per una particolare azione/collegamento su cui poter cliccare. Non è necessario aprire il generatore di segmenti e salvare ogni segmento, le condizioni possono essere aggiunte e rimosse rapidamente. Questo consente di risparmiare molto tempo quando si cerca di spiegare il motivo di un cambiamento sul sito.

Oppure ci sono volte in cui il generatore di segmenti diventa il proprio punto di riferimento. Non tutti i clienti sono uguali, e spesso si vogliono analizzare tipi specifici di clienti identificati in base alle azioni o ai percorsi intrapresi. Utilizzando il generatore di segmenti, è possibile aggiungere più condizioni per identificare i diversi tipi di clienti e salvare i segmenti in modo che possano essere condivisi e utilizzati da più analisti. È importante che questi tipi di segmenti siano coerenti tra i rapporti, quindi è opportuno averne uno costruito che possa essere utilizzato da tutti, piuttosto che lasciare che ogni persona crei la propria versione, in quanto i risultati potrebbero differire.

Nel complesso, sia i segmenti rapidi che il generatore di segmenti sono strumenti eccellenti da utilizzare nell’analisi. Ognuno di essi ha i propri scopi, vantaggi e svantaggi. Per una rapida guida di riferimento, consulta il nostro pratico foglio di trucchi e suggerimenti scaricabile qui sotto.

## Autore

Questo documento è stato scritto da:

![George Mandy](assets/mandy-george.jpg)

**George Mandy**, Digital Analyst III presso Best Buy Canada

Adobe Analytics Champion

## Scarica

[![Scarica i segmenti rapidi](assets/quick-segments-download-small.jpg)](assets/Adobe_Analytics_Segments_Vs_Segment_Builder_Reference_Guide.pdf)
