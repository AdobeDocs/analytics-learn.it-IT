---
title: Scarica la playlist di implementazione Adobe Analytics
description: Un documento sui requisiti aziendali (comunemente denominato BRD) è una documentazione molto importante su cui i principali soggetti interessati, utenti aziendali e utenti tecnologici vorranno collaborare. È un luogo in cui documentare tutti i KPI desiderati, i requisiti di reporting e qualsiasi punto dati che desideri visualizzare al termine dell’implementazione di AA.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10530.jpg
kt: 10530
source-git-commit: 160df6c23acb67f1b07f2fcd25f1eca96eb6dee7
workflow-type: tm+mt
source-wordcount: '1805'
ht-degree: 0%

---


# Scarica la playlist di implementazione Adobe Analytics

Prima di iniziare, [scarica il playbook](assets/aa-implementation-playbook.xlsx).

## Scheda Requisiti aziendali

**COSA:** Un documento sui requisiti aziendali (comunemente denominato BRD) è una documentazione molto importante su cui i principali soggetti interessati, utenti aziendali e utenti tecnologici vorranno collaborare. È un luogo in cui documentare tutti i KPI desiderati, i requisiti di reporting e qualsiasi punto dati che desideri visualizzare al termine dell’implementazione di Adobe Analytics (AA).

**PERCHÉ:** Questo funge da punto di partenza per la documentazione seguente (SDR, specifiche tecniche, ecc.) ed è una fonte comune di verità per uno stato finale concordato di AA. Questo documento organizza riflessioni tra i team all’interno dell’organizzazione per formare una direzione guida che consenta di progredire nella creazione o nel miglioramento dell’implementazione.

**COME:** Documentare i requisiti aziendali è comunemente fatto dagli utenti aziendali finali di AA, ma è importante ottenere feedback dagli utenti tecnologici in quanto ci possono essere problemi tecnici da notare e alcuni punti dati possono richiedere più sforzo di altri, quali fattori nella definizione delle priorità.

Chiedetevi, &quot;quali sono le cose che vogliamo monitorare sul nostro sito&quot;, &quot;quali punti di dati saranno importanti per me nel reporting dell&#39;utilizzo&quot;, e, soprattutto, &quot;come questi punti di dati daranno informazioni alle decisioni&quot;. È importante garantire che ciascuno dei requisiti aziendali si riferisca a un punto dati che può essere utilizzato per informare le decisioni aziendali. Ad esempio, può essere utile tenere traccia di ogni clic sul sito, ma alla fine di tutto il giorno, quali informazioni trai da quel rapporto?

Inizia compilando la colonna C nella schermata sottostante (Requisiti aziendali). Questo dovrebbe essere qualcosa come &quot;Quante ricerche interne sono completate sul nostro sito&quot; o &quot;Quale spot della campagna interna è più efficace in termini di impression&quot;. Dopo aver riempito questo livello di dettaglio, è possibile tornare indietro e compilare la colonna B (Categoria) e raggruppare i requisiti in categorie come &quot;Ricerca&quot; o &quot;Promozione Interna&quot; che dovrebbe corrispondere perfettamente con le sezioni specifiche tecniche.

Indica inoltre se si pensa che utilizzando un eVar, un evento, un prop o una combinazione si otterrà ciò che si sta cercando di tracciare.

Infine, la colonna Stato di implementazione fungerà da controllo di stato quando inizierai ad aggiungere elementi al tuo sito.

![Documento sui requisiti aziendali](assets/brd-template.png)

## Scheda Mappa variabile (assegnazione tag doc/SDR)

**COSA:** Un documento per l’assegnazione tag (comunemente denominato SDR) è un elemento critico della documentazione, utile sia per gli utenti tecnologici che per gli utenti aziendali di AA. Elenca tutte le variabili utilizzate dalle suite di rapporti insieme a tutti i dettagli rilevanti per le impostazioni delle variabili, il modo in cui la variabile viene implementata e lo scopo del rapporto. Come il tuo documento sulle proprietà, questo dovrebbe essere un documento Excel vivente e ben governato con una persona responsabile di mantenerlo aggiornato man mano che vengono introdotti miglioramenti di tagging o modifiche di implementazione.

**PERCHÉ:** Questo documento ha molti scopi, ma i più importanti sono i seguenti:

* Per tutti coloro che non sono esperti nella tua implementazione (nuovo noleggio, proprietario aziendale che cercano di comprendere meglio le informazioni disponibili, ecc.) questo documento offre una visione ottimale di tutte le variabili implementate e del loro scopo in modo che gli individui possano self-service in termini di apprendimento della configurazione AA.
* Per l’utente proprietario/tecnico del prodotto AA, questo documento fungerà da promemoria della configurazione di altre variabili e delle variabili disponibili per l’utilizzo quando si aggiunge una nuova dimensione.

**COME:** Inizia elencando tutte le variabili predefinite di Adobe (pagina, prodotto, geo, ecc.), nonché eVar, prop, eventi ed elenchi variabili in un documento Excel. Dovrebbe essere presente una scheda per sito/suite di rapporti.
Per ciascuna di queste dimensioni, aggiungo le colonne seguenti:
* **Nome:** Fornisci un nome semplice e breve che può essere compreso dalla maggior parte. Questo dovrebbe essere sufficientemente intuitivo da consentire a un nuovo utente di raccoglierlo e capire quale sia il suo scopo.
* **Descrizione:** Maggiori dettagli su ciò per cui viene utilizzata la variabile e su quali dati tiene traccia. Mantengo questo breve e semplice e lo faccio corrispondere alla descrizione utilizzata nell&#39;interfaccia. Idealmente, non voglio che i miei utenti abbiano bisogno di consultare il documento di assegnazione tag. Quindi, quando una nuova dimensione viene impostata sul backend amministratore, aggiungo la stessa descrizione. In questo modo, l’utente può fare clic sull’icona delle informazioni direttamente in Workspace per capire quale dimensione è - non è necessario estrarre un documento Excel!

![URL della pagina semplificato](assets/page-url-simplified.png)

* **Codice:** Il codice del backend che imposta il valore. Questo può essere il campo dal livello dati sulla pagina, oppure puoi chiamare che questo è fatto con una regola Launch, una regola di elaborazione, ecc.
* **Rapporti di classificazione:** Richiama tutti i rapporti di classificazione eseguiti con Importazione classificazioni o Generatore regole di classificazione
* **Ambito della soluzione:** Trovo utile elencare tutte le proprietà (almeno quelle che utilizzano più variabili standard) in colonne di piccole dimensioni e aggiungere un segno di spunta per ogni dimensione impostata su tale proprietà. In questo modo puoi filtrare facilmente una specifica proprietà e vedere rapidamente dove viene impostata una particolare dimensione.
* **Configurazione:** Impostazioni dell’interfaccia utente amministratore per ciascuna variabile (ad es. per eVar: scadenza, allocazione, merchandising, ecc.)

Schermata del campione SDR:
![DSP campione](assets/sample-sdr.png)

Si consiglia inoltre di utilizzare questo documento di assegnazione tag per tenere traccia di eventuali variabili gratuite e di eventuali variabili &quot;spazzatura&quot;. Quando una dimensione non è più utile, in genere deve essere eliminata solo dopo un po’ di tempo. Anche dopo questo, può verificarsi la memorizzazione in cache, o si può rendersi conto che la dimensione era impostata anche altrove. Pulire le dimensioni non è facile e spesso richiede pazienza. Ecco alcuni suggerimenti per mantenere la tua spazzatura nascosta sotto il letto in modo che i tuoi utenti non si confondano mentre ne tengono traccia.

* Tutte le dimensioni/eventi non utilizzati sono &quot;gratuiti&quot; o &quot;eliminati&quot;
   * Se negli ultimi 90 giorni la dimensione ha valori non consentiti, viene &#39;eliminata&#39;
   * Se la dimensione è libera e chiara per almeno gli ultimi 90 giorni, è &quot;gratuita&quot;
   * Contrassegna questi come tali in &#39;Nome&#39; nel documento di assegnazione tag, in modo da poterli filtrare facilmente. Tengo questi dati deselezionati nel documento di assegnazione tag (filtro dati Excel) in modo che gli utenti non li vedano
   * Contrassegna questi come nome eVar nell’interfaccia in modo che gli utenti non li trovino in una ricerca (ad es. &#39;(v6)&#39;) e rimuovi la descrizione nell&#39;interfaccia
* In questo modo, quando è necessaria una nuova dimensione, puoi facilmente filtrare &#39;gratis&#39; nella colonna &#39;Nome&#39; per trovare una dimensione pulita da utilizzare
* Per le dimensioni ed eventi &quot;essere eliminati&quot;, ti consigliamo di tenere traccia di questi eventi utilizzando Workspace:
   * Crea un progetto visibile agli amministratori solo con 3 tabelle: eVar, prop ed eventi. Utilizzo le &quot;istanze&quot; per le eVar specifiche e per le proprietà creo segmenti HIT con &quot;prop5 exists&quot;, ad esempio.
   * Imposta data su Ultimi 90 giorni
   * Utilizzare le righe precedenti nelle 3 tabelle, insieme alle occorrenze
   * Non appena qualcosa arriva a &#39;0&#39;, lo contrassegno come &#39;gratuito&#39; nel documento di assegnazione tag e lo rimuoverò dal progetto Workspace

In questo modo i tuoi dati sono sempre puliti, e hai una chiara idea della tua spazzatura.

![Panoramica delle variabili e degli eventi](assets/variables-and-events-overview.png)

## Scheda Proprietà

**COSA:** Un documento sulle proprietà dovrebbe elencare tutte le proprietà digitali: siti web, app mobili, altri strumenti (chat, feedback, ecc.), indipendentemente dal fatto che tali proprietà siano o meno taggate con Adobe Analytics. Questo dovrebbe fungere da documento centralizzato e vivente per gli utenti aziendali e tecnologici.

**PERCHÉ:** Questo ti darà una visione chiara del percorso dell’utente in tutte le tue proprietà digitali, e di cosa fa e non copre Adobe Analytics, in modo da poter iniziare ad assegnare priorità all’aggiunta di tag a qualsiasi proprietà in cui manca. Inserendo l’ecosistema digitale in questo modo, è possibile identificare potenziali opportunità nella strategia di assegnazione tag per ottenere una visione completa del percorso dell’utente. Ad esempio, è necessaria una suite di rapporti globale per il monitoraggio tra più domini/siti? È necessaria una consegna ID visitatore tra domini o un’esperienza ibrida dall’app all’app? È necessario aggiornare i filtri URL interni per il tracciamento tra domini diversi?

**COME:** Identifica un proprietario del documento per fornire governance e un&#39;unica fonte di responsabilità per la gestione degli aggiornamenti.
Elenca quanto segue nella scheda delle proprietà:
* **Nome proprietà:** Può essere un dominio, un sottodominio, un nome app, ecc. Anche all’interno dello stesso dominio, se alcune parti di esso sono gestite separatamente (come un team diverso, o una tecnologia diversa), queste devono essere separate.
* **Collegamento (URL)** a proprietà se disponibile
* **Proprietario e contatti:** Elencare il proprietario principale o i contatti per la proprietà
* **Metodo di tag:** Molti di noi dispongono di diversi metodi e implementazioni di codice (Launch, file JS, AEP, ecc.). Puoi suddividerlo ulteriormente se necessario (ad esempio tramite la versione del codice o il sistema di gestione dei tag), ma con questo scopo puoi tenere traccia di tutti i diversi metodi e versioni del codice, di dove è necessario aggiornare il codice e di come deve essere mantenuto. Se utilizzi Adobe Launch, elenca il nome della proprietà Launch.

Ricorda di includere tutte le proprietà digitali, anche se non dispongono di tag con Adobe Analytics. Questo ti aiuterà a comprendere il tuo panorama digitale e come gli utenti interagiscono con tutte le tue proprietà.

Si consiglia di mantenere questo documento il più semplice possibile e non annotarlo con troppe informazioni in modo che rimanga facile da interpretare da diverse parti dell&#39;organizzazione. I team di Analytics spesso capiscono meglio il panorama digitale rispetto a qualsiasi altro team, pertanto questo documento viene spesso utilizzato da altri team e dirigenti per fornire una panoramica completa.

>[!TIP]
>
>Crea una dimensione nome/proprietà del sito in Adobe Analytics. Avere una dimensione dedicata (in genere un eVar) in Adobe Analytics che identifica il nome del sito/dell’app consentirà la segmentazione, la risoluzione dei problemi, la creazione di suite di rapporti virtuali, ecc. I vantaggi sono infiniti, soprattutto quando si combinano più siti in una singola suite di rapporti (globale). La chiave consiste nell’assicurarsi che i team di sviluppo impostino sempre questo valore nella dimensione delle proprietà, inclusi tutti i caricamenti di pagina (s.t call/trackState) e tutti gli eventi personalizzati (s.tl call/trackAction). Le regole di elaborazione possono essere uno strumento utile per aiutarti a impostare correttamente e in modo coerente questi valori.

[Guarda questo video di Doug Moore](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html){target=&quot;_blank&quot;} per ulteriori informazioni sulla compilazione del playbook di implementazione.

## Autori

Questo documento è stato scritto congiuntamente da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Consulente senior all&#39;Adobe
