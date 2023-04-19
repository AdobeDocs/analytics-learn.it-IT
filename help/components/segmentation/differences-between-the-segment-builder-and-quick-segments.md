---
title: Differenze tra il generatore di segmenti e i segmenti rapidi in Analysis Workspace
description: I segmenti possono essere uno degli strumenti più potenti del tuo kit di analisi dei dati. Scopri le differenze tra l’utilizzo del generatore di segmenti e i segmenti rapidi in Analysis Workspace per migliorare l’efficienza.
feature: Segmentation
role: User
level: Beginner
doc-type: article
kt: KT-13118
source-git-commit: 9484b2e981d78be59b6ea16eeae2cf6f212c81ab
workflow-type: tm+mt
source-wordcount: '1264'
ht-degree: 1%

---


# Differenze tra il generatore di segmenti e i segmenti rapidi in Analysis Workspace

I segmenti possono essere uno degli strumenti più potenti del tuo kit di analisi dei dati. Scopri le differenze tra l’utilizzo del generatore di segmenti e i segmenti rapidi in Analysis Workspace per migliorare l’efficienza.

>[!TIP]
>
> Fai clic sull’immagine nella parte inferiore della pagina per scaricare un utile promemoria su quando utilizzare ogni strumento in Analysis Workspace.

I segmenti possono essere uno degli strumenti più potenti del tuo kit di analisi dei dati. Quando desideri esaminare specifici gruppi di traffico, sezioni del sito o percorsi di clienti, l’utilizzo dei segmenti può essere un ottimo modo per concentrare l’analisi su un particolare sottoinsieme di traffico per il sito. Proveniente da un ambiente di vendita al dettaglio, alcuni dei segmenti più utili che ho creato sono per diversi tipi di gruppi di clienti, ad esempio clienti nuovi rispetto a clienti esistenti, clienti con accesso a un account vs ospiti e così via. Ma puoi anche renderli per diverse sezioni del sito, clienti che eseguono azioni specifiche o qualsiasi altra cosa pensi!

**Esistono due modi principali per creare i segmenti:**

* Utilizzo del generatore di segmenti nel menu dei componenti
* Utilizzo dei segmenti rapidi nella parte superiore di un pannello

Se crei il segmento utilizzando il generatore di segmenti, puoi salvarlo per riutilizzarlo in altri progetti. Questo è un ottimo modo per essere in grado di concentrarsi su specifici gruppi di clienti, ad esempio, le persone che visitano determinate sezioni del sito e poi fanno un acquisto. Se invece esegui un’analisi esplorativa e desideri testare diverse impostazioni dei segmenti, il generatore di segmenti rapidi può essere di grande aiuto. Diamo un&#39;occhiata ad alcuni dei principali vantaggi di ogni metodo.

## Segmenti rapidi

Nella parte superiore di ciascun pannello, puoi fare clic sull’icona del segmento rapido (un funnel con il simbolo +) per aprire il generatore. In questo modo puoi creare un segmento a qualsiasi livello (hit, visita o visitatore) con fino a tre condizioni. Simile al generatore di segmenti principale, questo fornisce un’indicazione sul lato destro che indica se il segmento sta restituendo dati e % del traffico complessivo incluso nel segmento, anche se si tratta di una versione più semplificata rispetto alla visualizzazione del volume del segmento completa visualizzata nel generatore di segmenti. Quando aggiungi più di una condizione, puoi utilizzare gli operatori &quot;e&quot; e &quot;o&quot;. Sfortunatamente, non esiste un’opzione &quot;then&quot; per i segmenti rapidi, quindi se hai bisogno di segmenti sequenziali dovrai utilizzare il generatore di segmenti completo. Esiste anche un limite di un contenitore in un segmento rapido. È progettato per essere utilizzato per segmenti di base che possono essere creati e modificati rapidamente. Quando un segmento rapido viene applicato o salvato a un pannello, non può più essere modificato all’interno del pannello.

Quando esegui un’analisi esplorativa e desideri testare diversi tipi di segmenti per vedere come reagiscono diversi gruppi di clienti o come operano diverse categorie: l’utilizzo di segmenti rapidi è molto più veloce dell’utilizzo del generatore di segmenti. Inoltre, questi segmenti sono disponibili solo nel progetto in cui sono stati creati, quindi se non forniscono i risultati desiderati, non è necessario preoccuparsi di eliminare il segmento salvato dall’elenco principale. Se dopo aver eseguito il test dei segmenti ti accorgi che sarà utile in altri progetti, puoi sempre fare clic sul pulsante &quot;open builder&quot; per aprire il segmento nel generatore di segmenti completo per salvarlo come segmento normale. Una volta fatto questo, tuttavia, non sarà più possibile modificarlo nel generatore di segmenti rapidi.

![Segmento rapido](assets/quick-segement.png)

## Generatore di segmenti

Per accedere al generatore di segmenti, fai clic sul simbolo + sopra l’elenco dei segmenti nel menu a discesa dei componenti a sinistra oppure fai clic sul menu a discesa dei componenti e seleziona &quot;Crea segmento..&quot; A differenza dei segmenti rapidi, questa opzione offre tutte le opzioni disponibili. Per aggiungere più condizioni, puoi creare segmenti sequenziali utilizzando l’operatore &quot;then&quot;. I segmenti sequenziali ti consentono inoltre di utilizzare un &quot;gruppo logico&quot; come livello (invece di hit, visite o visitatori). Il generatore di segmenti ti consentirà anche di aggiungere una descrizione ai segmenti, che può aggiungere contesto riguardo a chi ha creato il segmento o quale tipo di dati è stato creato per filtrare, o anche semplicemente aggiungere &quot;tag&quot; al segmento a scopo organizzativo, entrambi non possibili all’interno del generatore di segmenti rapidi.

L’utilizzo del generatore di segmenti è essenziale quando il segmento avrà più di 3 condizioni, se devi utilizzare dei contenitori o se desideri segmenti sequenziali. Il generatore di segmenti completo dispone di molte più opzioni per creare segmenti più complessi, che possono aiutarti a suddividere diversi tipi di clienti, categorie, percorsi cliente e così via. Una volta creati e salvati, i segmenti vengono aggiunti all’elenco principale dei segmenti e possono quindi essere taggati, approvati, condivisi, utilizzati in più rapporti e pubblicati nell’Experience Cloud. La pubblicazione nell’Experience Cloud ti consente di utilizzare il segmento in altri prodotti Adobe, ad esempio in Adobe Target per il targeting di personalizzazione. I segmenti generati nel generatore di segmenti non possono essere modificati nel pannello segmenti rapidi, dovrai aprire il generatore di segmenti per apportare eventuali modifiche. Fortunatamente, la visualizzazione di anteprima a destra fornisce un’analisi più dettagliata del traffico che il segmento inserirà negli ultimi 90 giorni, il che significa che è più facile essere sicuri che il segmento stia inserendo ciò che si desidera prima di salvare.

![Generatore di segmenti](assets/segment-builder-quick.png)

## Casi di utilizzo

In settori diversi, gli utilizzi per la creazione di segmenti personalizzati possono variare. Lavorando per la divisione e-commerce di un grande rivenditore, spesso eseguiamo analisi esplorative per determinare quali percorsi i clienti stanno prendendo per acquistare. Quando vediamo picchi o gocce in azioni come l’aggiunta di prodotti ai carrelli o l’invio di ordini, l’utilizzo dei segmenti rapidi può rivelarsi utile. Durante un’analisi posso creare rapidamente un segmento per un tipo specifico di cliente o per una particolare azione/collegamento su cui fanno clic. Non è necessario aprire il generatore di segmenti e salvare ogni segmento, posso aggiungere le condizioni rapidamente e rimuoverle altrettanto rapidamente. Questo consente di risparmiare molto tempo quando si cerca di spiegare perché vediamo un cambiamento sul nostro sito.

In alternativa, ci sono volte in cui il generatore di segmenti è stato il mio go-to. Non tutti i clienti sono uguali, e spesso vogliamo osservare specifici tipi di clienti identificati da azioni o percorsi seguiti. Utilizzando il generatore di segmenti, possiamo aggiungere più condizioni per identificare i diversi tipi di clienti e salvare i segmenti in modo che possano essere condivisi e utilizzati da più analisti. È importante che questi tipi di segmenti siano coerenti tra i vari rapporti, quindi averne uno costruito che possa essere utilizzato da tutti è migliore di ogni persona che crea la propria versione, in quanto i risultati possono variare.

Nel complesso, sia i segmenti rapidi che il generatore di segmenti sono strumenti eccellenti da utilizzare nell’analisi. Ognuno di essi ha i propri scopi, benefici e svantaggi. Per una guida rapida di riferimento, controlla il nostro pratico foglio di suggerimenti e trucchi scaricabili qui sotto.

## Autore

Questo documento è stato scritto da:

![George Mandy](assets/mandy-george.jpg)

**George Mandy**, Digital Analytics III a Best Buy Canada

Adobe Analytics Champion

##  Download (Scarica)

[![Download dei segmenti rapidi](assets/quick-segments-download-small.jpg)](assets/Adobe_Analytics_Segments_Vs_Segment_Builder_Reference_Guide.pdf)
