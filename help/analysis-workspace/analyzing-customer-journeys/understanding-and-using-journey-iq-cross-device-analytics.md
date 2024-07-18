---
title: 'Informazioni e utilizzo di Journey IQ: Cross-Device Analytics'
description: Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più dispositivi. Cross-Device Analytics si integra con il servizio di identità Adobe Experience Platform per identificare in che modo i dispositivi si associano alle persone. Queste informazioni vengono sfruttate per creare una visione del comportamento degli utenti su tutti i dispositivi. Questo si traduce nella possibilità di eseguire analisi sulle persone, non sui dispositivi.
feature: CDA
topics: null
activity: use
doc-type: article
team: Technical Marketing
kt: 4138
role: User
level: Intermediate
exl-id: 3748d5d7-d250-4057-8131-afdc66c80200
source-git-commit: 01e6e84f748e359aeb42c9be3afa52088f41018b
workflow-type: tm+mt
source-wordcount: '1408'
ht-degree: 100%

---

# Informazioni e utilizzo di [!DNL Journey IQ]: Cross-Device Analytics

Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più dispositivi. Cross-Device Analytics si integra con [!DNL Adobe Experience Platform Identity Service] per identificare il modo in cui i dispositivi si associano alle persone. Queste informazioni vengono sfruttate per creare una visione del comportamento degli utenti su tutti i dispositivi. Questo si traduce nella possibilità di eseguire analisi sulle persone, non sui dispositivi.

## Panoramica di Cross-Device Analytics

### Io non sono i miei dispositivi

Quando gli utenti interagiscono con il tuo marchio lo fanno in molti modi e su più “superfici” o “dispositivi”. Possono utilizzare un browser web su un PC o su un dispositivo mobile, oppure un’app mobile. Nell’analisi digitale tradizionale, sviluppata sulla raccolta di dati basata sui cookie, ciascuna di queste superfici è rappresentata come un “visitatore” univoco. Ciò significa che ogni utente umano è rappresentato da molti visitatori univoci.

Ecco un esempio. Supponiamo che Isabelle interagisca con il tuo marchio nel modo seguente:

*Isabelle riconosciuta come tre visitatori*
![Percorso tradizionale di Analytics](assets/cda-isabelle-journey-traditional-analytics.png)

Nell’analisi tradizionale, il percorso di Isabelle viene suddiviso in tre parti. Viene riconosciuta come tre visitatori univoci, ciascuno dei quali ha utilizzato un dispositivo diverso per eseguire attività isolate. Ma serve una visione unificata e cross-device delle interazioni di Isabelle. [!DNL Journey IQ: Cross-Device Analytics] fornisce proprio questo tipo di visualizzazione.

*Isabelle riconosciuta come una singola persona*
![Percorso di Cross-Device Analytics](assets/cda-isabelle-journey-cross-device-analytics.png)

### Visualizzazione cross-device per una migliore analisi

Avere una visione del comportamento di Isabelle incentrata sulla persona e cross-device può fare una differenza significativa nelle analisi. Ad esempio, l’approccio tradizionale basato sul visitatore non offre un quadro completo dell’efficacia dei diversi canali di marketing. Vediamo ancora una volta il percorso di Isabelle, concentrandoci sui canali a cui vengono attribuiti la visualizzazione e l’acquisto del prodotto. Per semplicità, useremo l’attribuzione [!UICONTROL last-touch], ma lo stesso problema si verifica per qualsiasi modello di attribuzione se si divide il comportamento di Isabelle in base a visitatori separati. Con la visione tradizionale basata sul visitatore si ottengono risultati molto diversi, anche fuorvianti:

*Analisi tradizionale e Cross-Device Analytics*
![attribuzione del canale](assets/channel-attribution.png)

Con la visualizzazione cross-device, al canale e-mail vengono attribuiti sia la visualizzazione del prodotto che l’acquisto, e questo rappresenta più accuratamente l’effettiva esperienza di Isabelle.

Leggi le sezioni seguenti e scopri:

* Come funziona [!DNL Cross-Device Analytics]
* Prerequisiti per [!DNL Cross-Device Analytics]
* Interpretazione dei dati cross-device
* Analisi dei dati cross-device in Analysis Workspace

## Come funziona [!DNL Cross-Device Analytics]

[!DNL Journey IQ: Cross-Device Analytics (CDA)] si integra con [!DNL Adobe Experience Platform Identity Service], utilizzando [!DNL Device Graph] per identificare la correlazione tra dispositivi e persone. Queste informazioni vengono sfruttate per creare una visione del comportamento degli utenti su tutti i dispositivi. CDA include funzionalità e strumenti unici per aiutarti a comprendere l’utilizzo di più dispositivi e l’esperienza del cliente che interagisce con il tuo marchio usando diversi dispositivi. Si trova un livello sotto Analysis Workspace e fornisce informazioni approfondite sull’analisi del pubblico basata su persone e sull’attribuzione, la segmentazione e l’analisi del percorso con diversi dispositivi utilizzando potenti strumenti come [!UICONTROL Fallout], [!DNL Flow], [!DNL Cohort], [!DNL Segment IQ] e [!DNL Attribution IQ].

### [!DNL Cross-Device Virtual Report Suite]

CDA viene presentato attraverso uno speciale tipo di [[!UICONTROL Virtual Report Suite]](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) cross-device. Questo consente di continuare a utilizzare la suite di rapporti originale basata su dispositivi mentre si inizia a introdurre l’analisi cross-device nell’organizzazione. Configurare una suite di rapporti virtuale per CDA è facile.

Nel primo passaggio della creazione di una suite di rapporti virtuale, scegli la [!UICONTROL report suite] che è stata configurata da Adobe come abilitata per CDA:

*Scegliere una[!UICONTROL report suite]* di base (sorgente) abilitata per CDA
![[!UICONTROL Virtual Report Suite] Passaggio uno](assets/cda-vrs-step-one.png)

Quindi, attiva [!UICONTROL Report Time Processing] e abilita [!UICONTROL cross-device stitching]:

*Abilitare [!UICONTROL report-time processing] e[!UICONTROL cross-device stitching]*
![[!UICONTROL Virtual Report Suite] Passaggio due](assets/cda-vrs-step-two.png)

Completa la configurazione della suite di rapporti virtuale e salvala. La suite di rapporti virtuale di CDA viene visualizzata in Analysis Workspace con un’icona speciale, come illustrato di seguito:

*Selezionare la suite di rapporti virtuale di CDA in Analysis Workspace*
![[!UICONTROL Virtual Report Suite] Passaggio tre](assets/cda-vrs-step-three.png)

>[!TIP]
>
>Sulla [!UICONTROL report suite] di base abilitata per CDA puoi creare tutte le [!UICONTROL virtual report suites] per CDA che ti servono.

### Aggiornare la cronologia

A volte ci vuole un po’ di tempo perché gli utenti accedano e vengano identificati da [!DNL Device Graph] con la relativa mappatura dei loro dispositivi. CDA utilizza un intervallo di look-back di 30 giorni che consente di riconoscere come persone quei visitatori che non erano stati identificati in precedenza, fino a 30 giorni nel passato.

A cosa può servire? Torniamo al percorso utente di Isabelle dalla discussione precedente:

![[!DNL Cross-Device Analytics] Percorso](assets/cda-isabelle-journey-cross-device-analytics.png)

È possibile che Isabelle abbia effettuato l’accesso solo al momento di effettuare l’acquisto e che [!DNL Device Graph] ne abbia mappato i dispositivi solo qualche attimo dopo l’acquisto. Il look-back di 30 giorni di CDA permette di aggiornare il comportamento passato di Isabelle a livello di persona, fornendo la visione cross-device del suo percorso di cui hai bisogno.

>[!NOTE]
>
>Poiché la cronologia può essere aggiornata, i dati possono cambiare nel tempo in una [!UICONTROL virtual report suite] abilitata per CDA. Tieni presente questo aspetto durante la comunicazione di insights da un’analisi basata su CDA.

## Prerequisiti per [!UICONTROL Cross-Device Analytics]

CDA è incluso in [[!DNL Analytics Ultimate]](https://helpx.adobe.com/it/legal/product-descriptions/adobe-analytics.html). A partire da settembre 2019, i clienti [!DNL Analytics Ultimate] che soddisfano i prerequisiti elencati di seguito possono utilizzare CDA. I prerequisiti per CDA sono i seguenti:

* La tua azienda deve utilizzare [!DNL Adobe Experience Platform Identity Service Device Graph].
* Devi implementare tutto ciò che è richiesto da [!DNL Device Graph], compreso [Experience Cloud ID (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) e la sincronizzazione degli ID con il grafo.
* Attualmente non è possibile utilizzare due organizzazioni IMS con un solo [!DNL Device Graph], quindi occorre standardizzare su una singola organizzazione IMS.
* [!DNL Device Graph], così come alcuni componenti di CDA, sono ospitati in [!DNL Microsoft Azure]. Pertanto, i dati di [!DNL Analytics] vengono copiati avanti e indietro tra il centro di elaborazione dati di Adobe e la presenza di Adobe in [!DNL Microsoft Azure]. Alcuni dati di [!DNL Analytics] saranno memorizzati in [!DNL Azure]. La tua azienda deve accettare questo accordo.
* CDA richiede una [!UICONTROL report suite] “cross-device”. Questo significa che la [!UICONTROL report suite] utilizzata per CDA deve includere dati provenienti da più tipi di dispositivi o “superfici” diversi, ad esempio web da desktop, web da dispositivi mobili e app mobili. A settembre 2019, il volume massimo di chiamate server per questa [!UICONTROL report suite] è di 100 milioni di chiamate al server al giorno. I limiti di volume delle chiamate al server aumenteranno nei prossimi mesi.

## Interpretazione dei dati cross-device

### Persone, non visitatori

All’interno della [!UICONTROL Virtual Report Suite] di CDA, vedrai alcune modifiche. Ad esempio, [!UICONTROL Unique Visitors] è sostituito da due nuove metriche: [!UICONTROL People] e [!UICONTROL Unique Devices]. Queste consentono di ottenere informazioni approfondite molto migliori sulle dimensioni del pubblico.

*Persone e dispositivi univoci*
![CDA [!UICONTROL People Metric]](assets/cda-people-metric.png)

In [[!UICONTROL Segment Builder]](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it), il contenitore di segmenti [!UICONTROL Visitor] è stato sostituito da un contenitore di segmenti [!UICONTROL Person]. Utilizzando una suite di rapporti virtuale per CDA, puoi creare segmenti cross-device quali:

* Utenti che utilizzano più dispositivi
* Persone che iniziano il percorso su un dispositivo mobile e poi acquistano da un dispositivo desktop
* Visite in cui le persone utilizzano più dispositivi per eseguire un’attività

*Segmenti a livello di persona*
![[!DNL Segment Builder] [!UICONTROL Person] Contenitore](assets/cda-segment-builder-person-container.png)

### Persistenza della dimensione

All’interno di una VRS CDA, dimensioni come [!DNL eVars] ora persistono automaticamente tra i dispositivi. Ad esempio, una [!DNL eVar] configurata come:

* Allocazione: più recente (ultimo)
* Scadenza dopo: acquisto

persisterà automaticamente da un dispositivo all’altro fino all’attivazione dell’evento di acquisto.

## Analisi dei dati cross-device in Analysis Workspace

### Analisi del pubblico basata su persona

Hai mai avuto la curiosità di sapere quante persone interagiscono con il tuo marchio? Ti piacerebbe capire quanti e che tipo di dispositivi utilizzano? Come si sovrappone il loro utilizzo? Utilizzando una VRS CDA, puoi creare [Diagrammi di Venn](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html?lang=it) cross-device e [istogrammi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/histogram.html?lang=it) su dispositivi per persona.

*Analisi del pubblico basata su persona*
![Venn e istogramma](assets/cda-venn-and-histogram.png)

### [!DNL Flow] cross-device

Con CDA e Analysis Workspace, puoi visualizzare il modo in cui le persone si spostano da un dispositivo all’altro nel tempo in [[!DNL Flow visualization]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow.html?lang=it). Puoi constatare a che punto del percorso abbandonano e dove continuano.

*[!DNL Flow] con CDA*
![[!DNL Flow Visualization]](assets/cda-flow-viz.png)

### [!DNL Fallout] cross-device

È probabile che tu debba utilizzare diversi [[!DNL Fallout visualizations]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=it) per analizzare il modo in cui gli utenti percorrono una determinata serie di passaggi prima di raggiungere il successo. Sapevi che la tua visione di questi [!DNL Fallout visualizations] è limitata quando utilizzi analisi tradizionali basate su dispositivo? Per esaminare con successo il “fallimento”, il passaggio successivo deve verificarsi nello stesso browser o app del passaggio precedente. Nelle analisi basate su dispositivi, non puoi vedere le persone che hanno completato con successo il passaggio successivo su un altro dispositivo.

Nessun problema, ci pensa CDA. CDA crea la visualizzazione cross-device che rende [!DNL Fallout visualizations] molto più utile. Dopo tutto, ciò che conta veramente è se da qualche parte la persona alla fine è riuscita suo intento.

*[!DNL Fallout] con CDA*
![[!DNL Fallout Visualization]](assets/cda-fallout-viz.png)

### [!DNL Cross-Device Attribution IQ]

Poiché CDA crea un livello di dati cross-device sotto Analysis Workspace, tutte le analisi saranno caratterizzate da una prospettiva cross-device. Abbiamo un esempio efficace con [[!DNL Attribution IQ]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution/attribution.html?lang=it). [!DNL Attribution IQ] in Analysis Workspace consente di confrontare più modelli di attribuzione uno accanto all’altro. Utilizzando questa funzionalità con CDA, ora puoi confrontare i modi in cui i diversi dispositivi contribuiscono al successo.

Ad esempio, supponi di voler capire quanto spesso un telefono cellulare è il primo dispositivo utilizzato in un’interazione che alla fine porta al successo. Ciò rappresenta il “tasso di acquisizione” del telefono cellulare. CDA con [!DNL Attribution IQ] consente di eseguire questa analisi:

*[!DNL Attribution IQ] con CDA*
![[!DNL Attribution IQ]](assets/cda-attribution-iq.png)

Per ulteriori informazioni, consulta la [[!DNL Cross-Device Analytics] documentazione di supporto](https://experienceleague.adobe.com/docs/analytics/components/cda/cda-home.html?lang=it).
