---
title: Creare modelli di codice standardizzati
description: Per un’implementazione che funga da “linea di base” (con i KPI considerati indispensabili per tutti i siti Adobe Analytics), ove possibile la tua organizzazione deve seguire un unico metodo di implementazione.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10532.jpg
kt: 10532
exl-id: be00c8c0-a4bc-4380-98da-d1e2a3d31ec5
source-git-commit: df00d4fb8cc5093903ed4628dfe12f152294123a
workflow-type: ht
source-wordcount: '363'
ht-degree: 100%

---

# Creare modelli di codice standardizzati

**COSA:** per un’implementazione che funga da “linea di base” (con i KPI considerati indispensabili per tutti i siti Adobe Analytics), ove possibile la tua organizzazione deve seguire un unico metodo di implementazione. Ad esempio, utilizza per tutti i siti la stessa struttura del livello dati su e sfrutta lo stesso codice personalizzato o le stesse regole di gestione dei tag per acquisire elementi quali ricerche interne o informazioni sui profili dei visitatori.

**PERCHÉ:** una volta implementata una linea di base ripetibile e scalabile, risulterà più semplice aggiungere nuovi elementi o nuovi siti/app; inoltre l’implementazione sarà più pulita e sarà più facile risolvere eventuali problemi. L’utilizzo di un metodo uniforme facilita anche il compito di nuovi amministratori o sviluppatori, che potranno capire meglio e più rapidamente su cosa devono lavorare.

**COME:** adotta un modello in un singolo formato per gli sviluppatori quando occorre pubblicare un nuovo sito o miglioramenti dei tag. In genere, un documento Word funziona bene per delineare i seguenti elementi:

* Le variabili da implementare, il loro scopo e quando impostarle. Ad esempio:

| Variabile AA | Descrizione | Quando/Dove impostarla | Come impostarla |
|--- |--- |--- |--- |
| eVar8 | Parole chiave per la ricerca interna | All’arrivo nella pagina dei risultati di ricerca interna | livello dati |
| event8 | Numero di ricerche interne | All’arrivo nella pagina dei risultati di ricerca interna | Regola di avvio |

* Dettagli per l’impostazione. Qui puoi specificare tutti gli oggetti livello dati necessari e la relativa sintassi, nonché eventuali regole TMS da configurare e i relativi dettagli di configurazione.
* I casi di test da trattare in fase di controllo qualità e tutte le variabili che si prevede di trovare in un caso di test di successo. Descrivi cosa deve essere incluso un’implementazione di successo quando lo sviluppatore esegue il test di questo miglioramento.

Questo documento dovrebbe essere modificato solo per il prossimo sito in cui vengano aggiornati elementi di base come nome della proprietà, convenzione di denominazione delle pagine e così via. Non è necessario rifare tutto da capo ogni volta, e si può risparmiare tempo.

## Autori

Questo documento è stato scritto da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock 
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant presso Adobe
