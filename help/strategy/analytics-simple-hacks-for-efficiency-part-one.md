---
title: Semplici hacks per una maggiore efficienza e self-service - parte 1
description: Scopri le principali sfide che i team di analytics devono affrontare oggi e i nostri consigli per superarle utilizzando strategie al di fuori dell’interfaccia utente di Adobe Analytics.
solution: Analytics
exl-id: 5d1077fd-d006-4a85-bf1c-54f6b2d31934
source-git-commit: dad200fdb5c5d15c00254d693fb47bbcec80afaf
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 0%

---

# Adobe Analytics: Funzionalità semplici per una maggiore efficienza e self-service

**Parte 1: Fuori dall’interfaccia utente**

Questo articolo descrive le principali sfide che i team di analytics devono affrontare oggi e i nostri consigli per superarle utilizzando strategie al di fuori dell’interfaccia di Adobe Analytics.

## Sfide chiave per i team di Analytics

Molti team di Analytics si trovano con una distribuzione del lavoro non equilibrata. Invece di un mix di analisi all&#39;80% e implementazione al 20%, numerose organizzazioni si trovano al contrario. Essi vedono la maggior parte dei loro sforzi spesi per l&#39;impostazione, il reporting e il supporto, invece di produrre analisi che guidano informazioni di alto valore.

I team di Analytics stanno trovando la loro produttività ed efficienza prosciugata per vari motivi. Tra queste, le implementazioni in continua evoluzione, che cercano di mantenere la fiducia organizzativa nei dati e riducono il fatturato degli analisti. La riduzione del fatturato evita il lungo processo di formazione dei nuovi membri del team su strumenti di implementazione personalizzati non familiari.

Altre sfide chiave affrontate dagli analisti:

* **Concorrenza:** Le aziende retail online e multicanale crescono più competitive.
* **Aspettative dei clienti:** Le esperienze dei clienti e le strategie di marketing diventano più complesse.
* **Valore dati:** Il valore di dati e informazioni accurati per favorire un vantaggio competitivo diventa sempre più importante.
* **Aspettative delle parti interessate:** Partner commerciali, parti interessate e dirigenti richiedono sempre più dati prima dell&#39;approvazione.
* **Gestione dei progetti:** Il team di analytics soddisfa le richieste per implementare la raccolta dati per un flusso infinito di nuove funzioni, producendo allo stesso tempo report accurati, aggiungendo nuovi analisti e scoprendo le nuove informazioni successive.

## Tasti per l&#39;efficienza: Fuori dall’interfaccia utente

1. Mantieni il tuo [Riferimento per la progettazione della soluzione](/help/implementation/implementation-basics/creating-and-maintaining-an-sdr.md) (DSP) aggiornato:

   * Il DSP è la principale fonte di verità per la definizione e l’uso previsto di tutte le variabili all’interno dell’implementazione di Analytics.
   * Il DSP è il riferimento principale con cui gli utenti devono avere familiarità per trarre valore dall’interfaccia utente di Adobe Analytics.
   * Mantenere l’aggiornamento e le versioni (è possibile utilizzare un formato data semplice) è importante.

1. Documentazione sulla raccolta dei dati e governance - specifiche tecniche:

   Le specifiche tecniche dispongono di un pubblico più limitato rispetto al DSP, ma sono importanti, se non di più, per un’implementazione completamente funzionale. Una buona specifica tecnica dovrebbe essere costituita da tutte le risorse di sviluppo, controllo qualità e gestione dei tag necessarie per implementare la soluzione. Assicurati di conservare tutti i documenti necessari per disporre di architetture di implementazione univoche.

   **Specifiche tecniche**

   _Caso d’uso:_ Istruzioni che descrivono come creare script per la raccolta di dati

   _Utenti principali:_ Sviluppatori

   _Altre note:_

   * Documento altamente tecnico creato appositamente per gli ambienti di distribuzione
   * Utile sia per l&#39;implementazione iniziale che per la successiva manutenzione/riferimento
   * Organizzato per tipo di soluzione (ad esempio, tracciamento campagna, metadati pagina e così via).
   * Il documento primario deve essere aggiornato e mantenuto in quanto vengono apportate modifiche al DSP
   * Archivio centrale
   * Numeri di versione sincronizzati per SDR e Tech Spec

1. Comunicare e documentare le finalità di progettazione della soluzione al momento del lancio:

   * Comunicare con l&#39;utente in mente
   * Quando avvii o aumenti la raccolta di dati, crea riepiloghi semplici da condividere con le parti interessate
   * Rafforzare l&#39;uso corretto della variabile fuori dal cancello
   * Invia un messaggio e-mail di annuncio di riepilogo alle principali parti interessate e analisti
   * Crea una libreria che può essere utilizzata per supportare le ore di ufficio, le sessioni di abilitazione del team o per l’onboarding specifico per il team

1. Documentazione sulla raccolta dei dati, governance e igiene dei dati - AHD:

   Il dashboard di Analytics Health (AHD) si tuffa profondamente in un _singolo_ suite di rapporti e fornisce una visualizzazione dei dati raccolti in ogni componente (eVar, prop ed evento). Questo può aiutare a capire se i dati hanno smesso di raccogliere in un componente in modo da poter intervenire per risolvere il problema. Puoi eseguire questo dashboard in qualsiasi momento in futuro per qualsiasi suite di rapporti.

   Dashboard di stato di Analytics (AHD):

   _Caso d’uso:_ Snapshot di ogni metrica e dimensione acquisito da una singola suite di rapporti

   _Utenti principali:_ PMI e/o sviluppo principali di Analytics

   _Altre note:_
   * Fornito tramite Excel utilizzando un’integrazione personalizzata dell’API di reporting di Adobe
   * Gli utenti devono avere accesso API ai servizi web di Analytics
   * Sono disponibili opzioni per la semiautomazione

1. Vincere con l&#39;espansione del mondo degli esperti in materia (PMI):

   * Creare PMI all&#39;interno delle varie squadre dell&#39;organizzazione
   * Costruire la loro presenza aiutando a socializzare rilasci e vittorie
   * Utilizzare gli orari regolari dell&#39;ufficio per aiutare i formatori e ridurre le domande ad hoc

Per saperne di più sulla strategia e la leadership del pensiero, consulta [Successo del cliente](https://experienceleague.corp.adobe.com/docs/customer-success/customer-success/overview.html) hub