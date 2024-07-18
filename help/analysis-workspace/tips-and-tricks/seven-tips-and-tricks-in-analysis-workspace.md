---
title: 7 suggerimenti per creare progetti di Analytics personalizzati in modo più facile e veloce
description: Analysis Workspace è uno strumento potente all’interno di Adobe Analytics che può aiutarti a creare progetti di analisi di maggiore impatto. La sua vasta gamma di funzioni consente di eseguire qualsiasi tipo di analisi a forma libera. Inoltre, offre un’esperienza di utilizzo intuitiva che permette di sfruttare al meglio la sua potenza e scalabilità.
feature: Workspace Basics
topics: topics
activity: use
doc-type: feature video
team: Technical Marketing
kt: 3945
role: User, Developer, Data Engineer, Architect, Data Architect, Admin, Leader
level: Beginner
exl-id: af0e66cb-4e74-4ce0-9429-4a461fd54263
source-git-commit: 8fc641743bc9e07b838a22ca64ccc15344d52764
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 100%

---

# 7 suggerimenti per creare progetti di Analytics personalizzati in modo più facile e veloce

**Diventa un utente esperto di Analysis Workspace.**
Analysis Workspace è uno strumento potente all’interno di Adobe Analytics che può aiutarti a creare progetti di analisi di maggiore impatto. La sua vasta gamma di funzioni consente di eseguire qualsiasi tipo di analisi a forma libera. Inoltre, offre un’esperienza di utilizzo intuitiva che permette di sfruttare al meglio la sua potenza e scalabilità.

## Creare: evidenziare i dati giusti

### ***1: rilascia [!UICONTROL dimension], [!UICONTROL date range], [!UICONTROL segment] o [!UICONTROL metric] in una parte del progetto***

Rilascia un [!UICONTROL segment] o altro componente nella zona di rilascio [!UICONTROL segment] nella parte superiore di un pannello. Puoi segmentare rapidamente tale pannello per determinati punti di dati. Ad esempio, per segmentare il pannello in modo da mostrare solo gli hit in cui sono presenti degli ordini, rilascia la [!UICONTROL metric] “ordini” nella zona di rilascio [!UICONTROL segment]. Puoi anche segmentare per dati che non esistono all’interno di un componente (per visualizzare gli hit senza ordini, ad esempio) rilasciando nella zona la dimensione “non specificato” o “nessuno”.

>[!VIDEO](https://video.tv.adobe.com/v/24036/?quality=12&learn=on)

>[!TIP]
>
>**Prova:** scopri tutto quello che puoi fare con il menu di scelta rapida. Da questo menu puoi accedere a molti strumenti e funzionalità direttamente in Analysis Workspace. In caso di dubbio, fai clic con il pulsante destro del mouse: lo strumento o la funzionalità di cui hai bisogno potrebbe essere proprio lì, a portata di mano.

### ***2: crea metriche semplici senza uscire dal flusso di lavoro***

Con le [!UICONTROL Calculated Metrics] rapide, puoi creare nuove [!UICONTROL metrics] direttamente in Analysis Workspace, senza dover passare a [!UICONTROL Calculated Metric] Builder. Seleziona semplicemente le colonne delle [!UICONTROL metric] da calcolare, quindi dal menu di scelta rapida seleziona “[!UICONTROL Create Metric From Selection]”. A questo punto puoi aggiungere, sottrarre, dividere, moltiplicare e altro, senza uscire dal progetto e senza perdere il filo.

>[!VIDEO](https://video.tv.adobe.com/v/23126/?quality=12&learn=on)

>[!TIP]
>
>**Consiglio:** puoi selezionare fino a due colonne di [!UICONTROL metric] con la funzione Quick [!UICONTROL Calculated Metrics] (Metriche calcolate rapide). Utilizza [!UICONTROL Calculated Metric] Builder (Generatore di metriche calcolate) per creare [!UICONTROL metrics] che includono più di due [!UICONTROL metrics].

## Visualizzare: dare vita ai dati nei progetti

### ***3: copia e inserisci visualizzazioni e pannelli ovunque possano servire***

Copia facilmente visualizzazioni e pannelli esistenti per inserirli altrove, anche in un progetto diverso. Così puoi spostare facilmente i dati man mano che il progetto cresce, e condividere i risultati con nuovi utenti in modo che non debbano iniziare un’analisi da zero. Fai clic con il pulsante destro del mouse sul pannello o sulla visualizzazione da copiare, seleziona “[!UICONTROL Copy Visualization]” e fai clic con il pulsante destro del mouse su un pannello vuoto per inserirlo.

>[!VIDEO](https://video.tv.adobe.com/v/23230/?quality=12&learn=on)

>[!TIP]
>
>**Funzionalità ad alta richiesta:** i nostri clienti ci hanno chiesto di facilitare la copia e l’inserimento di visualizzazioni e pannelli. Ora possono passare meno tempo a ricreare gli insight, e più tempo a scoprirne di nuovi.

### ***4: passa da una visualizzazione con granularità temporale all’altra con un solo clic***

Cambia facilmente la vista del tempo nelle visualizzazioni con tendenze. Nelle precedenti iterazioni di Analysis Workspace, per cambiare il tempo era necessario rendere visibile una tabella di origine, trascinare una nuova [!UICONTROL dimension] e poi nascondere di nuovo la tabella. Ora è sufficiente selezionare la granularità temporale desiderata direttamente dal menu a discesa “[!UICONTROL Visualizations Settings]” (icona ingranaggio in alto a destra).

>[!VIDEO](https://video.tv.adobe.com/v/23548/?quality=12&learn=on)

## Condividere: consentire ad altri di usare e comprendere facilmente i risultati

### ***5: crea una [!DNL Virtual Report Suite] personalizzata per specifiche unità aziendali***

Adobe Analytics raccoglie grandi quantità di dati. La scelta dei componenti nelle [!DNL Virtual Report Suites] consente agli amministratori di creare un set di dati per ogni unità aziendale di un’organizzazione. Ciò significa che gli analisti che lavorano in Analysis Workspace possono trovare rapidamente i dati più importanti per le loro esigenze. Basta selezionare la casella “[!UICONTROL Enable Customization of Virtual Report Suite Components]” nel generatore di [!UICONTROL Virtual Report Suites] nella sezione [!UICONTROL “Components], e selezionare i [!UICONTROL components] che corrispondono a ciò che un team deve misurare.

>[!VIDEO](https://video.tv.adobe.com/v/23544/?quality=12&learn=on)

>[!TIP]
>
>**Consiglio:** puoi anche cambiare il nome dei componenti di una [!UICONTROL Virtual Report Suite], in base ai termini utilizzati da un particolare team. Fai clic sull’icona a forma di matita accanto al componente e digita un nuovo nome.

### ***6: collega pannelli e visualizzazioni all’interno di un progetto o in altri progetti***

Crea collegamenti che porteranno il tuo pubblico ovunque in Analysis Workspace. Fai clic con il pulsante destro del mouse sul pannello di destinazione, seleziona “[!UICONTROL Get Panel Link]” e copia. Evidenzia quindi il testo su cui vuoi impostare il collegamento, seleziona l’icona del collegamento nell’editor di testo di una casella o di una descrizione, e incolla. Per collegare un intero progetto, fai clic sulla scheda “[!UICONTROL Share]”, seleziona “[!UICONTROL Get Project Link]” e segui gli stessi passaggi di cui sopra.

>[!VIDEO](https://video.tv.adobe.com/v/23724/?quality=12&learn=on)

>[!TIP]
>
>**Consiglio:** i collegamenti possono migliorare l’esperienza dei lettori in tanti modi diversi. Puoi indirizzarli verso illustrazioni relative ai risultati e a consigli nei progetti. Oppure puoi consentire loro di passare direttamente dall’indice alle sezioni a cui sono interessati. Puoi anche inserire collegamenti verso progetti di altri utenti correlati alla tua analisi.

### ***7: salva i progetti come modelli personalizzati riutilizzabili***

Ora puoi facilmente trasformare qualsiasi progetto in un modello personalizzato. Seleziona semplicemente “[!UICONTROL Save As Template]” dal menu a discesa “[!UICONTROL Project]”, aggiungi i tag appropriati per rendere il modello facile da trovare e fai clic su “[!UICONTROL Save Project As Template]”. Ora il modello sarà disponibile per tutti gli utenti di Analysis Workspace, nella scheda “[!UICONTROL Custom Templates]”. Questo consente agli analisti di iniziare i loro progetti con dati significativi, invece di iniziare da zero.

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12&learn=on)

>[!TIP]
>
>**Funzionalità ad alta richiesta:** diversi clienti ci hanno chiesto di poter salvare i progetti come modelli personalizzati. Questa funzione è diventata una delle loro preferite.

[Fai clic qui per ulteriori suggerimenti e trucchi su Experience League](https://experienceleague.adobe.com/?search=tips&amp;lang=it#recommended/solutions/analytics)

| Informazioni sull’autore |            |
|------------|------------|
| ![Jen Lasser](assets/jlasser-headshot-s.jpg) | Jen Lasser è un manager del team di gestione dei prodotti Adobe Analytics. <br> In questo ruolo incontra i clienti per comprendere le loro esigenze aziendali, <br>e utilizza ciò che apprende per delineare la roadmap del prodotto Adobe Analytics <br>e assegnare il livello di priorità alle varie nuove funzioni del prodotto. Prima della sua attuale posizione, <br>Jen era Principal Consultant nel team di consulenza Adobe, <br>esperta di visualizzazione dati, Analysis Workspace e [!DNL Report Builder]. <br><br>Sulla base della sua esperienza sul campo, abbiamo selezionato i seguenti suggerimenti per <br>facilitare la creazione, la visualizzazione e la condivisione di progetti Analysis Workspace. |
