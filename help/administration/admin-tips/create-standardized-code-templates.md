---
title: Creare modelli di codice standardizzati
description: 'Per un’implementazione di base (ovvero ciò che la tua azienda considera i KPI (Key Performance Indicator) necessari per tutti i siti Adobe Analytics), la tua organizzazione deve disporre di un unico metodo di implementazione, ove possibile. '
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10532.jpg
kt: 10532
source-git-commit: 160df6c23acb67f1b07f2fcd25f1eca96eb6dee7
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 2%

---


# Creare modelli di codice standardizzati

**COSA:** Per un’implementazione di base (ovvero ciò che la tua azienda considera i KPI (Key Performance Indicator) necessari per tutti i siti Adobe Analytics), la tua organizzazione deve disporre di un unico metodo di implementazione, ove possibile. Ad esempio, utilizza la stessa struttura di livello dati su più siti e sfrutta lo stesso codice personalizzato/regola di gestione tag per acquisire elementi come ricerche interne o informazioni sul profilo visitatore.

**PERCHÉ:** L’implementazione di una linea di base ripetibile e scalabile rende l’aggiunta di nuovi elementi o nuovi siti/app un’impresa semplice e a basso impegno, mantenendo al tempo stesso pulita e facile la risoluzione dei problemi della tua implementazione. L’utilizzo di un metodo uniforme semplifica inoltre la pubblicazione online e la comprensione dei contenuti utilizzati dai nuovi amministratori/sviluppatori.

**COME:** Adotta un modello a formato singolo per gli sviluppatori quando un nuovo sito o il miglioramento dei tag vengono online. In genere, un documento word funziona bene in cui è possibile delineare i seguenti elementi:

* Le variabili da implementare, il loro scopo e quando impostarle. Ad esempio:

| Variabile AA | Descrizione | Quando/Dove impostare | Come impostare |
|--- |--- |--- |--- |
| eVar8 | Parole chiave per la ricerca interna | All’arrivo della pagina dei risultati di ricerca interna | livello dati |
| evento8 | Numero di ricerche interne | All’arrivo della pagina dei risultati di ricerca interna | Regola di avvio |

* Dettagli su come impostare. In questo punto puoi specificare tutti gli oggetti livello dati necessari, la relativa sintassi, nonché tutte le regole TMS che devono essere configurate e i dettagli della configurazione della regola.
* I casi di test per garantire sono trattati nel controllo qualità e tutte le variabili che si prevede di visualizzare in un caso di test di successo. Descrivi cosa deve includere un’implementazione di successo quando lo sviluppatore sottopone a test questo miglioramento.

Idealmente, questo documento dovrà essere modificato solo per il sito successivo in cui vengono aggiornate le nozioni di base come nome della proprietà, convenzione di denominazione delle pagine e così via. Non è necessario reinventare la ruota ogni volta, e si può risparmiare più tempo.

## Autori

Questo documento è stato scritto congiuntamente da:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager presso NortonLifeLock Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Consulente senior all&#39;Adobe
