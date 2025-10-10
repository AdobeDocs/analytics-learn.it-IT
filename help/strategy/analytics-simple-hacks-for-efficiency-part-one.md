---
title: Semplici trucchi per più efficienza e autonomia - Parte 1
description: Scopri le principali sfide che i team di Analytics devono affrontare e i nostri consigli per superarle mediante strategie al di fuori dell’interfaccia utente di Adobe Analytics.
feature: Analytics Basics
role: Admin, Leader
level: Intermediate
solution: Analytics
exl-id: 5d1077fd-d006-4a85-bf1c-54f6b2d31934
source-git-commit: d7fd77640928697f5857ccfcaf2c0f561aebeac3
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 94%

---

# Adobe Analytics: semplici trucchi per più efficienza e autonomia

**Parte 1: fuori dall’interfaccia utente**

Questo articolo descrive le principali sfide che i team di Analytics devono affrontare e i nostri consigli per superarle mediante strategie al di fuori dell’interfaccia di Adobe Analytics.

## Sfide chiave per i team di Analytics

Molti team di Analytics si trovano con una distribuzione del lavoro non equilibrata. Invece di un mix di 80% analisi e 20% implementazione, molte organizzazioni si trovano nella situazione opposta. La maggior parte del lavoro è dedicato all’impostazione, al reporting e al supporto, invece di produrre analisi che consentano di ottenere informazioni di alto valore.

I team di Analytics subiscono un calo di produttività ed efficienza per vari motivi. Tra questi: implementazioni in continua evoluzione; la necessità di assicurare fiducia nei dati a livello aziendale; e riduzione dell’avvicendamento degli analisti. Riducendo l’avvicendamento del personale si evita di dover fornire ai nuovi membri del gruppo la formazione necessaria su strumenti con cui non hanno dimestichezza e che richiedono un’implementazione personalizzata.

Altre sfide chiave affrontate dagli analisti:

* **Concorrenza:** le aziende retail online e multicanale diventano sempre più competitive.
* **Aspettative dei clienti:** le esperienze dei clienti e le strategie di marketing diventano più complesse.
* **Valore dei dati:** informazioni e dati accurati su cui basare un vantaggio competitivo assumono un ruolo sempre più importante.
* **Aspettative delle parti interessate:** partner commerciali, parti interessate e dirigenti richiedono sempre più dati prima dell’approvazione.
* **Gestione dei progetti:** il team di analisi è sommerso di richieste per l’implementazione della raccolta dati per un flusso infinito di nuove funzioni; e allo stesso tempo è necessario produrre rapporti accurati, aggiungere al team nuovi analisti e scoprire nuovi insight.

## Chiavi per l’efficienza: fuori dall’interfaccia utente

1. Mantieni il documento [Solution Design Reference](/help/implementation/implementation-basics/creating-and-maintaining-an-sdr.md) (SDR) aggiornato:

   * Il documento SDR è la principale fonte di verità per la definizione e l’uso previsto di tutte le variabili per la propria implementazione di Analytics.
   * Il documento SDR rappresenta la documentazione principale a cui gli utenti faranno riferimento per trarre valore dall’interfaccia utente di Adobe Analytics.
   * È importante mantenerlo aggiornato e gestirne le versioni (anche tramite un semplice formato di date).

1. Documentazione su raccolta dati e governance - Specifiche tecniche:

   Le specifiche tecniche sono destinate a un pubblico più limitato rispetto al documento SDR, ma sono altrettanto importanti, se non di più, per un’implementazione completamente funzionale. Le specifiche tecniche devono comprendere tutte le risorse di sviluppo, controllo qualità e gestione dei tag necessarie per implementare la soluzione. Assicurati di includere e mantenere aggiornati tutti i documenti necessari per tutte le singole architetture di implementazione.

   **Specifiche tecniche**

   _Use Case :_Istruzioni che descrivono come creare script per la raccolta dati

   Utenti _primari :_sviluppatori

   _Altre note :_

   * Documento altamente tecnico creato appositamente per gli ambienti di implementazione
   * Utile sia per l’implementazione iniziale che per la successiva manutenzione e come riferimento
   * Organizzato per tipo di soluzione (ad esempio, tracciamento delle campagne, metadati delle pagine, ecc.).
   * Il documento primario deve essere aggiornato e mantenuto man mano che vengono apportate modifiche all’SDR
   * Archivio centrale
   * Numeri di versione sincronizzati per SDR e specifiche tecniche

1. Comunica e documenta le finalità di progettazione della soluzione al momento del lancio:

   * Comunica tenendo conto delle esigenze dell’utente.
   * Quando avvii o ottimizzi la raccolta dati, crea semplici riepiloghi da condividere con le parti interessate.
   * Sottolinea l’importanza di un uso corretto delle variabili.
   * Invia un’e-mail di riepilogo per l’annuncio del lancio agli analisti e alle parti interessate principali.
   * Crea una libreria da utilizzare a supporto di sessioni di approfondimento e di abilitazione del team o per l’onboarding di specifici team.

1. Documentazione su raccolta dati, governance e igiene dei dati - AHD:

   Analytics Health Dashboard (AHD) esamina una _singola_ suite di rapporti e fornisce informazioni sui dati raccolti in ogni componente (eVar, prop ed evento). Può aiutare a capire se i dati non vengono più raccolti in un componente, in modo da poter intervenire per risolvere il problema. Puoi eseguire questa dashboard in qualsiasi momento in futuro per qualsiasi suite di rapporti.

   Analytics Health Dashboard (AHD):

   _Caso d&#39;uso :_istantanea di ogni metrica e dimensione acquisita da una singola suite di rapporti

   Utenti _primari :_sviluppatori e/o esperti di analisi con lead

   _Altre note :_
   * Fornito tramite Excel con integrazione personalizzata dell’API di reporting di Adobe
   * Gli utenti devono avere accesso tramite API ai servizi web di Analytics.
   * Sono disponibili opzioni per la semi-automazione.

1. Crea un maggior numero di esperti in materia:

   * Crea esperti in materia nei vari team dell’organizzazione.
   * Rafforzane la presenza aiutandoli a rendere noti rilasci e successi.
   * Organizza sessioni regolari di approfondimento per la formazione dei formatori e per ridurre il numero di richieste di assistenza.

Per saperne di più su strategia e leadership di pensiero, visita l’hub [Customer Success](https://experienceleague.adobe.com/docs/customer-success/customer-success/overview.html?lang=it).