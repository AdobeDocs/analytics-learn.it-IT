---
title: Utilizzare l’analisi per coorte per comprendere il comportamento del cliente
description: Per migliorare la customer experience e le entrate, le aziende devono comprendere il comportamento dei clienti. L’analisi per coorte può aiutare a comprendere il coinvolgimento e la fidelizzazione, portando a azioni come il miglioramento della creazione dell’account e la creazione di campagne per mesi con volumi elevati.
feature: Cohort Analysis
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-16T00:00:00Z
jira: KT-13213
thumbnail: KT-13213.jpeg
source-git-commit: 5988e9d68f0c2200168da56373259bdf9f4f901b
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 14%

---


# Utilizzare l’analisi per coorte per comprendere il comportamento del cliente

Per migliorare la customer experience e le entrate, le aziende devono comprendere il comportamento dei clienti. L’analisi per coorte può aiutare a comprendere il coinvolgimento e la fidelizzazione, portando a azioni come il miglioramento della creazione dell’account e la creazione di campagne per mesi con volumi elevati.

L’analisi delle prestazioni digitali è fondamentale per comprendere come i clienti interagiscono con un’azienda e quali azioni possono essere intraprese per migliorare la loro esperienza. In questo post di blog scopriremo come utilizzare l’analisi per coorte per comprendere meglio il comportamento dei clienti.

## Parte 1: Confronto delle prestazioni digitali tra le prime e le visite di ritorno

### Impostazione dello stage

Un cliente sta cercando di capire le prestazioni digitali negli ultimi 2 anni e sta prendendo in considerazione lo sviluppo di un programma fedeltà per guidare le prestazioni digitali. Per iniziare, possiamo esaminare l’attuale combinazione di siti tra utenti nuovi e ripetuti per capire come si comportano oggi i due gruppi di visitatori.

Prestazioni digitali attuali

1. Nel 2022, il 62% degli ordini proveniva da visite di prima visita rispetto al 38% degli ordini di visite di ritorno (soggetti a cookie, più dispositivi).
1. Le prime visite vengono convertite a un tasso leggermente superiore rispetto alle visite di ritorno per entrambe, 11,6% rispetto all’11,4%.
1. Rispetto al 2021, i tassi di conversione sono scesi in entrambi i segmenti.

![Tabella delle visite](assets/visits-table.png)

## Parte 2: Analisi per coorte - Visite Commestibili Accordi Globali

Per comprendere la fedeltà dei canali digitali e l&#39;opportunità di guidare gli acquirenti ripetuti, la domanda successiva a cui rispondere è: Qual è il volume di visitatori che ritornano al sito ogni mese nel 2022?

### Introduzione all’analisi per coorte

L’analisi per coorte è uno strumento utile per comprendere in che modo le coorti interagiscono con un marchio nel tempo. Per iniziare, abbiamo deciso quali domande rispondere:

1. In un dato anno, qual è il periodo medio di conservazione per mese?
1. Quale volume di visitatori del sito torna ogni mese in un dato anno?
1. Qual è l&#39;impatto degli accessi sulla conservazione?
1. Ci sono prodotti specifici che hanno portato a una maggiore fidelizzazione?

Come impostare la tabella coorte

1. Imposta intervallo di date su Gen a Dic 2022
1. **Criteri di inclusione:** Visite
1. **Criteri di ritorno:** Visite
1. **Granularità:** Mese
1. **Impostazioni:** Rolling Calculation (Calcolo continuo) \*\*Consente di calcolare la fidelizzazione in base alla colonna precedente, non alla colonna inclusa. Questo significa che un utente è incluso in ciascuno dei mesi\*\*
1. **Segmenti:** puoi selezionare segmenti specifici per approfondire l’analisi
   1. Pagine di destinazione specifiche
   1. Tipo di dispositivo
   1. Canali marketing
   1. Ecc.

### Interpretazione dei risultati

**Nel 2022:**

1) I mesi con i tassi di ritenzione più elevati +1 mese includono gennaio, aprile e novembre
1) I mesi con il maggior volume includono febbraio e maggio
1) Ci sono circa 1.000 visitatori che ritornano al sito ogni mese

![Tabella di conservazione 2022](assets/2022-retention-table.png)

**Nel 2021:**

1) I mesi con i tassi di ritenzione più elevati +1 mese includono aprile, gennaio e marzo
1) I mesi con il maggior volume includono febbraio e maggio

![Tabella Retention 2021](assets/2021-retention-table.png)

**Azioni:**

Crea un segmento in base a circa 1.000 visitatori e scopri di più su di essi:

- Dove si trovano?
- Quali prodotti acquistano durante tutto l&#39;anno?
- Da quali negozi stanno comprando?

I mesi chiave evidenziano l&#39;opportunità di guidare la conservazione in base al volume:

- Ci sono tattiche specifiche che possono portare ad un ulteriore acidità durante febbraio e maggio per sfruttare il volume?

Ripeti l’analisi per gli ordini per comprendere gli acquirenti ripetuti

- I tassi di conservazione più elevati da +1 mese negli stessi mesi?
- I mesi più elevati di visite sono gli stessi per gli ordini?

## Parte 3: Aggiunta di due metriche ai criteri di inclusione

### Impatto del login

Poiché questo client cerca di comprendere il valore di un programma Fedeltà, il passaggio successivo nell’analisi include l’aggiunta nell’evento di successo Accesso come metrica Inclusione alla coorte.

Avvertimento: L’analisi per coorte non può essere utilizzata per metriche calcolate (come il tasso di conversione) o per metriche non intere (come Revenue). Solo le metriche utilizzabili nei segmenti possono essere utilizzate in Analisi per coorte e possono essere incrementate solo di >1 alla volta.

È più probabile che il sito mantenga gli utenti che accedono?

Quale sarebbe l&#39;impatto se potessimo fare in modo che più utenti accedano? È un&#39;esperienza più difficile?

### Impostazione della tabella coorte

1. **Imposta intervallo date:** da gennaio a dicembre 2022
1. **Criteri di inclusione:** Visite + Evento di successo di accesso
1. **Criteri di ritorno:** Visite
1. **Granularità:** Mese
1. **Impostazioni:** Rolling Calculation (Calcolo continuo) \*\*Consente di calcolare la fidelizzazione in base alla colonna precedente, non alla colonna inclusa. Questo significa che un utente è incluso in ciascuno dei mesi\*\*

### Interpretazione dei risultati

**Nel 2022:**

1) I mesi con i tassi di ritenzione più elevati +1 mese includono gennaio, aprile e novembre (stessi mesi della prima tabella coorte)
1) I mesi con il maggior volume includono febbraio, maggio e dicembre
1) Ci sono circa 2500 visitatori che ritornano ogni mese \*\*più del doppio\*\*

**Azioni:**

Esperienza utente del sito per consentire agli utenti di creare un account durante l&#39;estrazione

![Tabella coorte 4](assets/cohort-table-4.png)

## Parte 4: Coorte Dimension personalizzato

Custom Dimension Cohort (Coorte con dimensione personalizzata): consente di creare coorti in base alla dimensione selezionata, anziché in base al tempo (impostazione predefinita). Molti clienti vogliono poter analizzare le coorti in base a fattori diversi dal tempo. Con la nuova funzione per coorti con dimensione personalizzata hai la flessibilità di creare le coorti in base alle dimensioni che rispondono alle tue esigenze. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia, in base a valori diversi di tali dimensioni. Le selezioni del menu 

La definizione del segmento di coorte di Dimension personalizzato applica l’elemento dimensionale solo come parte del periodo di inclusione e non come parte della definizione di ritorno.

Dopo aver scelto l’opzione Custom Dimension Cohort (Coorte con dimensione personalizzata), puoi trascinare nella zona di rilascio la dimensione che ti interessa. Puoi quindi confrontare elementi con dimensione simile in uno stesso periodo di tempo. Ad esempio, puoi confrontare le prestazioni delle città una accanto all’altra

lato, prodotti, campagne, ecc. Verranno restituiti i primi 14 elementi dimensionali. Per visualizzare solo specifici elementi per la dimensione scelta, puoi anche usare un filtro, passando il cursore a destra della dimensione che hai trascinato. Una coorte con dimensione personalizzata non può essere usata con la funzione Tabella di latenza.

### Quali prodotti sono alla base della vischiosità del sito?

La tabella per coorti per Dimension personalizzati evidenzia i prodotti che generano tassi di fidelizzazione più elevati rispetto alla media.  Questa tabella consente di identificare i prodotti principali per la creazione di campagne di marketing interne ed esterne con prodotti di altissima qualità.

**A febbraio:** 3 prodotti con tassi di fidelizzazione più elevati

1) Prodotto 1
1) Prodotto 2
1) Prodotto 3

**In marzo:**

1) Prodotto 1
1) Prodotto 2
1) Prodotto 3: offre spesso prestazioni superiori con un tasso di fidelizzazione più elevato rispetto alla conservazione media.

![Tabella coorte 5](assets/cohort-table-5.png)

## Conclusione

L’analisi per coorte e la coorte per Dimension personalizzati sono strumenti potenti per comprendere il comportamento dei clienti e migliorare le prestazioni digitali. Analizzando i tassi di conservazione, i tassi di accesso e l&#39;impatto di prodotti specifici, le aziende possono prendere decisioni basate sui dati per migliorare l&#39;esperienza del cliente e favorire la crescita.

## Autore

Questo documento è stato scritto da:

![Jennifer Yacenda](assets/jennifer-yacenda.png)

**Jennifer Yacenda**, Director senior al Marriott

Adobe Analytics Champion