---
title: Scarica il playbook di implementazione di Adobe Analytics
description: Un documento sui requisiti aziendali (BRD, Business Requirements Doc) è una risorsa molto importante per la cui realizzazione sarà importante coinvolgere le principali parti interessate, utenti aziendali e utenti tecnici. Consente di documentare tutti i KPI desiderati, i requisiti di reporting e tutti i punti dati che dovranno essere disponibili al termine dell’implementazione di AA.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10530.jpg
kt: 10530
exl-id: aab53a12-3f11-49c9-aba4-dc926bcf776b
source-git-commit: df00d4fb8cc5093903ed4628dfe12f152294123a
workflow-type: ht
source-wordcount: '1805'
ht-degree: 100%

---

# Scarica il playbook di implementazione di Adobe Analytics

Prima di iniziare, [scarica il playbook](assets/aa-implementation-playbook.xlsx).

## Scheda Requisiti aziendali

**COSA:** un documento sui requisiti aziendali (BRD, Business Requirements Doc) è una risorsa molto importante per la cui realizzazione sarà importante coinvolgere le principali parti interessate, utenti aziendali e utenti tecnici. Consente di documentare tutti i KPI desiderati, i requisiti di reporting e tutti i punti dati che dovranno essere disponibili al termine dell’implementazione di Adobe Analytics (AA).

**PERCHÉ:** funge da punto di partenza per la documentazione successiva (SDR, specifiche tecniche, ecc.) ed è una fonte comune di verità per lo stato finale concordato di AA. Questo documento raccoglie i punti proposti dai vari team all’interno dell’organizzazione e definisce la direzione da seguire per sviluppare o ottimizzare l’implementazione.

**COME:** la documentazione dei requisiti aziendali è comunemente preparata dagli utenti aziendali finali di AA, ma è importante ottenere feedback anche dagli utenti tecnici, in quanto ci possono essere problemi tecnici da considerare e alcuni punti dati possono richiedere più lavoro di altri, e sarà necessario tenerne conto nella definizione delle priorità.

Cosa desideri monitorare sul sito? Quali punti dati saranno utili in termini di reporting? E, soprattutto, in che modo orienteranno il processo decisionale? È importante assicurarsi che ciascuno dei requisiti aziendali si riferisca a un punto dati che possa essere utilizzato per orientare le decisioni aziendali. Ad esempio, si può essere tentati di tenere traccia di ogni clic sul sito, ma alla fine... quali informazioni potrai trarre da tali dati?

Per iniziare, compila la colonna C nella schermata sottostante (Requisiti aziendali). Ad esempio: “Quante ricerche interne sono state completate sul nostro sito” o “Quale annuncio di una campagna interna è più efficace in termini di impression”. Dopo averlo compilato questo tipo di dettagli, compila la colonna B (Categoria) e raggruppa i requisiti in categorie, ad esempio “Ricerca” o “Promozione interna”, in base alle sezioni delle specifiche tecniche.

Indica inoltre se, utilizzando un eVar, un evento, un prop o una combinazione di questi, si otterrà ciò che si intende tracciare.

Infine, la colonna Stato di implementazione fungerà da verifica dello stato una volta che inizierai ad aggiungere elementi al sito.

![Documento sui requisiti aziendali (BRD)](assets/brd-template.png)

## Scheda Mappa variabili (documento sui tag/SDR)

**COSA:** un documento sui tag (SDR, Solution Design Reference) è un elemento fondamentale della documentazione, utile sia per gli utenti tecnici che per gli utenti aziendali di AA. Elenca tutte le variabili utilizzate dalle suite di rapporti e tutti i dettagli rilevanti per le impostazioni delle variabili, il modo in cui ogni variabile viene implementata e il suo scopo nei rapporti. Come il documento sulle proprietà, questo dovrebbe essere un documento Excel attivo e ben gestito, con una persona responsabile di mantenerlo aggiornato man mano che vengono introdotti miglioramenti ai tag o modifiche all’implementazione.

**PERCHÉ:** questo documento ha molti scopi, ma i più importanti sono i seguenti:

* Per ogni nuovo utente dell’implementazione (nuovo assunto, responsabile Business che desidera comprendere meglio i rapporti disponibili, ecc.) questo documento offre un quadro completo di tutte le variabili implementate e del loro scopo, in modo che gli utenti possano servirsene in autonomia, apprendendo la configurazione di AA.
* Per l’utente tecnico o proprietario del prodotto AA, questo documento fungerà da promemoria della configurazione di altre variabili e delle variabili disponibili che possono essere utilizzate quando si aggiunge una nuova dimensione.

**COME:** per iniziare, elenca in un documento Excel tutte le variabili predefinite di Adobe (page, product, geo, ecc.), nonché eVar, prop, eventi. Dovrebbe essere presente una scheda per ogni sito o suite di rapporti.
Per ciascuna di queste dimensioni, aggiungo le colonne seguenti:
* **Nome:** il nome deve essere breve e semplice, facilmente comprensibile dalla maggior parte degli utenti. Dovrebbe essere abbastanza intuitivo da consentire a un nuovo utente di sceglierlo e di capirne lo scopo.
* **Descrizione:** maggiori dettagli sullo scopo della variabile e sui dati di cui tiene traccia. Nel mio caso, uso descrizioni brevi e semplici, che corrispondono a quelle utilizzate nell’interfaccia. Gli utenti non dovrebbero mai avere bisogno di consultare il documento sui tag. Quindi, quando una nuova dimensione viene impostata sul backend di amministrazione, aggiungo qui la stessa descrizione. L’utente può fare clic sull’icona delle informazioni direttamente in Workspace per capire a cosa serve una dimensione, non è necessario consultare un documento Excel.

![URL della pagina semplificato](assets/page-url-simplified.png)

* **Codice:** il codice del backend che imposta il valore. Può essere il campo dal livello dati sulla pagina, oppure puoi richiamarlo con una regola di avvio, una regola di elaborazione, ecc.
* **Rapporti di classificazione:** richiama i rapporti di classificazione eseguiti mediante Classifications Importer (Importazione classificazioni) o Classification Rule Builder (Generatore regole di classificazione).
* **Ambito della soluzione:** è utile elencare tutte le proprietà (almeno quelle che utilizzano più variabili standard) in colonne di piccole dimensioni e aggiungere un segno di spunta per ogni dimensione impostata su tale proprietà. Così potrai filtrare facilmente una specifica proprietà e vedere al volo dove viene impostata una particolare dimensione.
* **Configurazione:** impostazioni dell’interfaccia di amministrazione per ciascuna variabile (ad esempio, per le eVar: scadenza, allocazione, merchandising, ecc.)

Schermata del documento SDR di esempio:
![Documento SDR di esempio](assets/sample-sdr.png)

Si consiglia inoltre di utilizzare questo documento sui tag per tenere traccia di eventuali variabili libere o non più valide. Quando una dimensione non è più utile, in genere è necessario un po’ di tempo per eliminarla. Anche dopo la sua eliminazione, può essere ancora presente in cache, oppure ti puoi rendere conto che la dimensione era stata impostata anche altrove. Pulire le dimensioni non è facile e spesso richiede pazienza. Ecco alcuni suggerimenti per nascondere ciò che non serve agli utenti, per non confonderli, pur tenendone traccia.

* Tutte le dimensioni e tutti gli eventi non utilizzati sono contrassegnati “liberi” o “in eliminazione”.
   * Se negli ultimi 90 giorni una dimensione presenta dei valori non validi, è “in eliminazione”.
   * Se la dimensione è libera e “pulita” da almeno 90 giorni, è “libera”.
   * Contrassegna questi stati nella sezione “Nome” nel documento sui tag, in modo da poterli filtrare facilmente. Nel documento sui tag, tengo questi dati deselezionati (tramite la funzione filtro dei dati in Excel) in modo che gli utenti non possano vederli.
   * Indicali come nome eVar nell’interfaccia, in modo che gli utenti non li possano trovare in una ricerca (ad es. “(v6)”) e rimuovine la descrizione nell’interfaccia.
* In questo modo, quando è necessaria una nuova dimensione, puoi facilmente filtrare i dati della colonna “Nome” per trovare una voce “libera” (pulita) da utilizzare.
* Per le dimensioni e gli eventi “in eliminazione”, ti consigliamo di tenerne traccia utilizzando Workspace:
   * Crea un progetto visibile agli amministratori che contenga solo 3 tabelle: eVar, prop ed eventi. Ad esempio, io utilizzo “istanze” per le eVar specifiche, mentre per i prop creo dei segmenti HIT con, ad esempio, “prop5 esiste”.
   * Imposta la data su Ultimi 90 giorni.
   * Usa quanto sopra come righe nelle 3 tabelle, insieme alle occorrenze.
   * Non appena qualcosa arriva a “0”, lo contrassegno come “libero” nel documento sui tag e lo rimuovo dal progetto Workspace

In questo modo i dati sono sempre puliti, e avrai una chiara idea di ciò che non è più utile.

![Panoramica delle variabili e degli eventi](assets/variables-and-events-overview.png)

## Scheda Proprietà

**COSA:** un documento sulle proprietà dovrebbe elencare tutte le tue proprietà digitali: siti web, app mobili, altri strumenti (chat, feedback, ecc.), che siano o meno taggate con Adobe Analytics. Questo dovrebbe fungere da documento centralizzato e attivo per gli utenti sia aziendali che tecnici.

**PERCHÉ:** ti darà una visione chiara del percorso dell’utente in tutte le tue proprietà digitali, e di quali siano coperte o meno da Adobe Analytics; così potrai definire l’ordine di priorità da seguire per aggiungere i tag alle proprietà a cui mancano. Delineando in questo modo il tuo ecosistema digitale, potrai individuare potenziali opportunità nella strategia di assegnazione dei tag per avere una visione completa del percorso dell’utente. Ad esempio: è necessaria una suite di rapporti globale per tenere traccia dei dati tra più domini o siti? È necessario trasmettere l’ID visitatore a un altro dominio o un’altra app per esperienze ibride? È necessario aggiornare i filtri URL interni per il tracciamento tra domini diversi?

**COME:** identifica un proprietario del documento a scopo di governance e un’unica fonte di responsabilità per la gestione degli aggiornamenti.
Elenca quanto segue nella scheda delle proprietà:
* **Nome proprietà:** può essere un dominio, un sottodominio, il nome di un’app, ecc. Anche all’interno dello stesso dominio, se alcune parti sono gestite separatamente (ad esempio, da un team diverso o con una tecnologia diversa), queste devono essere separate.
* **Collegamento (URL)** per la proprietà, se disponibile
* **Proprietario e contatti:** elenca il proprietario principale o i contatti per la proprietà.
* **Metodo di tag:** spesso usiamo diversi metodi e implementazioni di codice (Launch, file JS, AEP, ecc.). Se necessario, puoi suddividerlo ulteriormente (ad esempio in base alla versione del codice o al sistema di gestione dei tag), ma questo ha lo scopo di tenere traccia di tutti i diversi metodi e versioni del codice, dove è necessario aggiornare il codice e come deve essere mantenuto. Se utilizzi Adobe Launch, elenca il nome della proprietà Launch.

Ricorda di includere tutte le proprietà digitali, anche se non utilizzano i tag di Adobe Analytics. Questo ti aiuterà a comprendere il tuo panorama digitale e come gli utenti interagiscono con tutte le tue proprietà.

È consigliabile mantenere questo documento il più semplice possibile, senza appesantirlo con troppe informazioni, in modo che possa essere consultato facilmente da diversi team dell’organizzazione. In genere i team di Analytics comprendono meglio il panorama digitale rispetto ad altri team, e questo documento viene spesso utilizzato da altri team e dirigenti per ottenere una panoramica completa.

>[!TIP]
>
>Crea una dimensione per il nome del sito o la proprietà in Adobe Analytics. Se in Adobe Analytics è presente una dimensione dedicata (in genere un eVar) che identifica il nome del sito o dell’app, sarà possibile eseguire segmentazioni, risolvere problemi, creare di suite di rapporti virtuali, ecc. I vantaggi sono infiniti, soprattutto quando si combinano più siti in una singola suite di rapporti globale. La chiave consiste nell’assicurarsi che i team di sviluppo impostino sempre questo valore nella dimensione delle proprietà, inclusi tutti i caricamenti di pagina (s.t calls/trackState) e tutti gli eventi personalizzati (s.tl calls/trackAction). Le regole di elaborazione possono essere utili per impostare questi valori in modo corretto e coerente.

Per ulteriori informazioni sulla compilazione del playbook di implementazione, [guarda questo video di Doug Moore](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=it){target=&quot;_blank&quot;}.

## Autori

Questo documento è stato scritto da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock 
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant presso Adobe
